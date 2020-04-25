---
title: Host de servicio personalizado
ms.date: 03/30/2017
ms.assetid: fe16ff50-7156-4499-9c32-13d8a79dc100
ms.openlocfilehash: 6470249c557d571dfee165d57ce518d475340093
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/24/2020
ms.locfileid: "82140939"
---
# <a name="custom-service-host"></a>Host de servicio personalizado
Este ejemplo muestra cómo utilizar un derivado personalizado de la clase <xref:System.ServiceModel.ServiceHost> para modificar el comportamiento de tiempo de ejecución de un servicio. Este enfoque proporciona una alternativa reutilizable para configurar un gran número de servicios de una manera común. El ejemplo también muestra cómo utilizar la clase <xref:System.ServiceModel.Activation.ServiceHostFactory> para utilizar un ServiceHost personalizado en el entorno de host de Internet Information Services (IIS) o el Servicio de activación de procesos de Windows (WAS).  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Hosting\CustomServiceHost`  
  
## <a name="about-the-scenario"></a>Sobre el escenario
 Para evitar la revelación involuntaria de metadatos de servicio potencialmente confidenciales, la configuración predeterminada de los servicios Windows Communication Foundation (WCF) deshabilita la publicación de metadatos. Este comportamiento es seguro de forma predeterminada, pero también quiere decir que no puede usar una herramienta de importación de metadatos (como Svcutil.exe) Para compilar el código de cliente necesario para llamar al servicio a menos que el comportamiento de publicación de metadatos del servicio se habilite de manera explícita en la configuración.  
  
 Habilitar los metadatos que publican para un número grande de servicios implica agregar los mismos elementos de configuración a cada servicio individual, lo cual produce una gran cantidad de información de configuración que es esencialmente la misma. Como una alternativa a configurar individualmente cada servicio, es posible escribir el código imperativo que habilita metadatos que se publican una vez y a continuación reutilizar ese código entre varios servicios diferentes. Esto se logra creando una nueva clase que derive de <xref:System.ServiceModel.ServiceHost> e invalide el método `ApplyConfiguration`() para agregar imperiosamente los metadatos que publican el comportamiento.  
  
> [!IMPORTANT]
> Para mostrar más claridad, este ejemplo muestra cómo crear un punto de conexión de publicación de metadatos no se seguros. Tales extremos pueden estar disponibles para los consumidores anónimos no autenticados y se debe tener cuidado antes de implementar tales extremos para garantizar que la revelación pública de un metadato del servicio sea la adecuada.  
  
## <a name="implementing-a-custom-servicehost"></a>Implementar un ServiceHost personalizado
 La clase <xref:System.ServiceModel.ServiceHost> expone varios métodos virtuales útiles que los herederos pueden invalidar para modificar el comportamiento del tiempo de ejecución de un servicio. Por ejemplo, el método `ApplyConfiguration`() lee información de la configuración de servicio del almacén de configuración y modifica la <xref:System.ServiceModel.Description.ServiceDescription> del host según corresponda. La implementación predeterminada lee la configuración del archivo de configuración de la aplicación. Las implementaciones personalizadas pueden invalidar `ApplyConfiguration`() para seguir modificando la <xref:System.ServiceModel.Description.ServiceDescription> mediante el código imperativo o incluso reemplazar completamente el almacén de la configuración predeterminada. Por ejemplo, leer la configuración del extremo de un servicio de una base de datos en lugar del archivo de configuración de la aplicación.  
  
 En este ejemplo, deseamos compilar un ServiceHost personalizado que agregue ServiceMetadataBehavior, (que habilita la publicación de los metadatos) aun cuando este comportamiento no se agregue explícitamente en el archivo de configuración del servicio. Para lograr esto, creamos una nueva clase que hereda de <xref:System.ServiceModel.ServiceHost> e invalida `ApplyConfiguration`().  
  
```csharp
class SelfDescribingServiceHost : ServiceHost  
{  
    public SelfDescribingServiceHost(Type serviceType, params Uri[] baseAddresses)  
        : base(serviceType, baseAddresses) { }  
  
    //Overriding ApplyConfiguration() allows us to
    //alter the ServiceDescription prior to opening  
    //the service host.
    protected override void ApplyConfiguration()  
    {  
        //First, we call base.ApplyConfiguration()  
        //to read any configuration that was provided for  
        //the service we're hosting. After this call,  
        //this.Description describes the service  
        //as it was configured.  
        base.ApplyConfiguration();
  
        //(rest of implementation elided for clarity)  
    }  
}  
```  
  
 Porque no deseamos omitir cualquier configuración proporcionada en el archivo de configuración de la aplicación, la primera cosa que nuestra reemplazo de `ApplyConfiguration`() hace, es llamar a la implementación base. Cuando este método se completa, podemos agregar imperiosamente <xref:System.ServiceModel.Description.ServiceMetadataBehavior> a la descripción utilizando el código imperativo siguiente.  
  
```csharp
ServiceMetadataBehavior mexBehavior = this.Description.Behaviors.Find<ServiceMetadataBehavior>();  
if (mexBehavior == null)  
{  
    mexBehavior = new ServiceMetadataBehavior();  
    this.Description.Behaviors.Add(mexBehavior);  
}  
else  
{  
    //Metadata behavior has already been configured,
    //so we do not have any work to do.  
    return;  
}  
```  
  
 La última cosa que nuestro () invalidador`ApplyConfiguration`debe hacer, es agregar el punto de conexión de metadatos predeterminado. Por convención, se crea un extremo de metadatos para cada URI en la colección BaseAddresses del host del servicio.  
  
```csharp
//Add a metadata endpoint at each base address  
//using the "/mex" addressing convention  
foreach (Uri baseAddress in this.BaseAddresses)  
{  
    if (baseAddress.Scheme == Uri.UriSchemeHttp)  
    {  
        mexBehavior.HttpGetEnabled = true;  
        this.AddServiceEndpoint(ServiceMetadataBehavior.MexContractName,  
                                MetadataExchangeBindings.CreateMexHttpBinding(),  
                                "mex");  
    }  
    else if (baseAddress.Scheme == Uri.UriSchemeHttps)  
    {  
        mexBehavior.HttpsGetEnabled = true;  
        this.AddServiceEndpoint(ServiceMetadataBehavior.MexContractName,  
                                MetadataExchangeBindings.CreateMexHttpsBinding(),  
                                "mex");  
    }  
    else if (baseAddress.Scheme == Uri.UriSchemeNetPipe)  
    {  
        this.AddServiceEndpoint(ServiceMetadataBehavior.MexContractName,  
                                MetadataExchangeBindings.CreateMexNamedPipeBinding(),  
                                "mex");  
    }  
    else if (baseAddress.Scheme == Uri.UriSchemeNetTcp)  
    {  
        this.AddServiceEndpoint(ServiceMetadataBehavior.MexContractName,  
                                MetadataExchangeBindings.CreateMexTcpBinding(),  
                                "mex");  
    }  
}  
```  
  
## <a name="using-a-custom-servicehost-in-self-host"></a>Utilizar un ServiceHost personalizado en el mismo host  
 Ahora que hemos completado nuestra implementación de ServiceHost personalizada, podemos utilizarla para agregar metadatos que publican el comportamiento de cualquier servicio, hospedando ese servicio dentro de una instancia de nuestro`SelfDescribingServiceHost`. El código siguiente muestra cómo utilizarlo en el escenario del mismo host.  
  
```csharp
SelfDescribingServiceHost host =
         new SelfDescribingServiceHost( typeof( Calculator ) );  
host.Open();  
```  
  
 Nuestro host personalizado todavía lee la configuración del extremo del servicio del archivo de configuración de la aplicación, así como si hubiéramos utilizado la clase <xref:System.ServiceModel.ServiceHost> predeterminada para hospedar el servicio. Sin embargo, porque agregamos la lógica para habilitar metadatos que publican dentro de nuestro host personalizado, ya no debemos habilitar explícitamente los metadatos que publican el comportamiento en configuración. Este enfoque tiene una ventaja distinta al estar creando una aplicación que contiene varios servicios y desea habilitar metadatos que publican en cada uno de ellos sin escribir los mismos elementos de configuración una y otra vez.  
  
## <a name="using-a-custom-servicehost-in-iis-or-was"></a>Utilizar un ServiceHost personalizado en IIS o WAS  
 Utilizar un host del servicio personalizado en escenarios de autohospedaje es sencillo, porque es su código de aplicación el que es finalmente responsable de crear y abrir la instancia del host de servicio. En el entorno de hospedaje de IIS o WAS, sin embargo, la infraestructura de WCF está creando dinámicamente una instancia del host del servicio en respuesta a los mensajes entrantes. Los hosts de servicio personalizados también se pueden utilizar en este entorno host, pero requieren código adicional en el formulario de ServiceHostFactory. El código siguiente muestra un derivado de <xref:System.ServiceModel.Activation.ServiceHostFactory> que devuelve instancias de nuestro `SelfDescribingServiceHost`personalizado.  
  
```csharp
public class SelfDescribingServiceHostFactory : ServiceHostFactory  
{  
    protected override ServiceHost CreateServiceHost(Type serviceType,
     Uri[] baseAddresses)  
    {  
        //All the custom factory does is return a new instance  
        //of our custom host class. The bulk of the custom logic should  
        //live in the custom host (as opposed to the factory)
        //for maximum  
        //reuse value outside of the IIS/WAS hosting environment.  
        return new SelfDescribingServiceHost(serviceType,
                                             baseAddresses);  
    }  
}  
```  
  
 Como se puede ver, implementar un ServiceHostFactory personalizado es muy sencillo. Toda la lógica personalizada reside dentro de la implementación de ServiceHost; el generador devuelve una instancia de la clase derivada.  
  
 Para utilizar un generador personalizado con una implementación del servicio, debemos agregar algunos metadatos adicionales al archivo .svc del servicio.  
  
```xml
<% @ServiceHost Service="Microsoft.ServiceModel.Samples.CalculatorService"
               Factory="Microsoft.ServiceModel.Samples.SelfDescribingServiceHostFactory"
               language=c# Debug="true" %>
```
  
 Aquí hemos agregado un atributo `Factory` adicional a la directiva `@ServiceHost` y pasamos el nombre de tipo de CLR de nuestro generador personalizado como el valor del atributo. Cuando IIS o WAS recibe un mensaje para este servicio, la infraestructura de hospedaje de WCF crea primero una instancia de ServiceHostFactory y, a continuación, crea instancias del propio `ServiceHostFactory.CreateServiceHost()`host del servicio mediante una llamada a.  
  
## <a name="running-the-sample"></a>Ejecución del ejemplo  
 Aunque este ejemplo proporciona un cliente totalmente funcional y una implementación del servicio completa, el ejemplo pretende mostrar cómo modificar el comportamiento del tiempo de ejecución de un servicio por medio de un host personalizado. Siga los siguientes pasos:  
  
### <a name="observe-the-effect-of-the-custom-host"></a>Observar el efecto del host personalizado
  
1. Abra el archivo Web. config del servicio y observe que no hay ninguna configuración que habilite explícitamente los metadatos para el servicio.  
  
2. Abra el archivo. SVC del servicio y observe que su @ServiceHost Directiva contiene un atributo de generador que especifica el nombre de un ServiceHostFactory personalizado.  
  
### <a name="set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo
  
1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).

2. Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).

3. Una vez compilada la solución, ejecute setup. bat para configurar la aplicación ServiceModelSamples en IIS 7,0. El directorio ServiceModelSamples debería aparecer ahora como una aplicación de IIS 7,0.

4. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).

5. Para quitar la aplicación IIS 7,0, ejecute *Cleanup. bat*.

## <a name="see-also"></a>Vea también

- [Procedimiento para hospedar un servicio WCF en IIS](../feature-details/how-to-host-a-wcf-service-in-iis.md)
