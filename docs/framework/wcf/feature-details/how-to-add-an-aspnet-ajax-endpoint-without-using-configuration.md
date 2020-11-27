---
title: Procedimiento para agregar un punto de conexión AJAX de ASP.NET sin usar la configuración
ms.date: 03/30/2017
ms.assetid: b05c1742-8d0a-4673-9d71-725b18a3008e
ms.openlocfilehash: e33f1fed7dd7bf45966815949ac544250f4d1de8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96257631"
---
# <a name="how-to-add-an-aspnet-ajax-endpoint-without-using-configuration"></a>Procedimiento para agregar un punto de conexión AJAX de ASP.NET sin usar la configuración

Windows Communication Foundation (WCF) le permite crear un servicio que exponga un punto de conexión habilitado para AJAX de ASP.NET al que se pueda llamar desde JavaScript en un sitio web del cliente. Para crear este tipo de extremo, puede usar un archivo de configuración, como con todos los otros extremos de WCF, o utilizar un método que no requiera ningún elemento de configuración. En este tema se muestra el segundo enfoque.  
  
 Para crear servicios con puntos de conexión de AJAX de ASP.NET sin configuración, Internet Information Services (IIS) debe hospedar los servicios. Para activar un punto de conexión de ASP.NET AJAX mediante este enfoque, especifique <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> como parámetro de generador en la Directiva de [ \@ ServiceHost](../../configure-apps/file-schema/wcf-directive/servicehost.md) en el archivo. SVC. Este generador personalizado es el componente que configura automáticamente un punto de conexión de AJAX de ASP.NET para que se le pueda llamar desde JavaScript en un sitio web del cliente.  
  
 Para obtener un ejemplo práctico, vea el [servicio Ajax sin configuración](../samples/ajax-service-without-configuration.md).  
  
 Para obtener una descripción de cómo configurar un punto de conexión de ASP.NET AJAX mediante los elementos de configuración, consulte [Cómo: usar la configuración para agregar un punto de conexión de ASP.NET AJAX](how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md).  
  
### <a name="to-create-a-basic-wcf-service"></a>Para crear un servicio WCF básico  
  
1. Defina un contrato de servicio WCF básico con una interfaz marcada con el <xref:System.ServiceModel.ServiceContractAttribute> atributo. Marque cada operación con el <xref:System.ServiceModel.OperationContractAttribute>. Asegúrese de establecer la propiedad <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.  
  
    ```csharp  
    [ServiceContract(Namespace = "MyService")]]  
    public interface ICalculator  
    {  
        [OperationContract]  
        // This operation returns the sum of d1 and d2.  
        double Add(double n1, double n2);  
  
        //Other operations omitted…  
  
    }  
    ```  
  
2. Implemente el contrato de servicios `ICalculator` con un `CalculatorService`.  
  
    ```csharp  
    public class CalculatorService : ICalculator  
    {  
        public double Add(double n1, double n2)  
        {  
            return n1 + n2;  
        }  
  
    //Other operations omitted…  
    ```  
  
3. Defina un espacio de nombres para las implementaciones de `ICalculator` e `CalculatorService` ajustándolas en un bloque de espacios de nombres.  
  
    ```csharp  
    Namespace Microsoft.Ajax.Samples  
    {  
        //Include the code for ICalculator and Caculator here.  
    }  
    ```  
  
### <a name="to-host-the-service-in-internet-information-services-without-configuration"></a>Hospedaje del servicio en Internet Information Services sin configuración  
  
1. Cree un nuevo archivo denominado servicio con una extensión .svc en la aplicación. Edite este archivo agregando la información de directiva de [ \@ ServiceHost](../../configure-apps/file-schema/wcf-directive/servicehost.md) adecuada para el servicio. Especifique que <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> se va a usar en la Directiva de [ \@ ServiceHost](../../configure-apps/file-schema/wcf-directive/servicehost.md) para configurar automáticamente un punto de conexión de ASP.NET AJAX.  
  
    ```text
    <%@ServiceHost
        language=c#
        Debug="true"
        Service="Microsoft.Ajax.Samples.CalculatorService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
2. Compile el servicio y llámelo desde el cliente. Internet Information Services (IIS) activa el servicio cuando se llama. Para obtener más información sobre el hospedaje en IIS, consulte [How to: host a WCF Service in IIS](how-to-host-a-wcf-service-in-iis.md).  
  
### <a name="to-call-the-service"></a>Realización de llamadas al servicio  
  
1. El punto de conexión se configura en una dirección vacía relativa al archivo. SVC, por lo que el servicio ahora está disponible y se puede invocar enviando solicitudes a Service. SVC/ \<operation> -por ejemplo, Service. SVC/Add para la `Add` operación. Puede utilizarlo introduciendo la URL de servicio en la colección Scripts del control del administrador de scripts de AJAX de ASP.NET. Para obtener un ejemplo, vea el [servicio Ajax sin configuración](../samples/ajax-service-without-configuration.md).  
  
## <a name="example"></a>Ejemplo  
  
 El punto de conexión configurado automáticamente se crea en una dirección vacía relativa a la URL base. También se puede agregar y utilizar un archivo de configuración con este enfoque. Si el archivo de configuración contiene las definiciones de punto de conexión, estos puntos de conexión se agregan al punto de conexión configurado automáticamente.  
  
 Por ejemplo, service.svc usa <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> y el directorio del servicio contiene un archivo Web.config que define un punto de conexión para el mismo servicio mediante el elemento <xref:System.ServiceModel.BasicHttpBinding> de la dirección relativa de "soap". En este caso, el servicio contiene dos puntos de conexión: uno en service.svc (que responde a las solicitudes de AJAX de ASP.NET) y otro en service.svc/soap (que responde a las solicitudes SOAP).  
  
 Si el archivo de configuración define un punto de conexión en una dirección relativa vacía y se utiliza <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, se produce una excepción y el servicio no puede iniciarse.  
  
 No puede utilizar la configuración para modificar los valores en el punto de conexión configurado automáticamente. Si se debe modificar algún valor (como una cuota del lector), no debe utilizar el enfoque sin configuración quitando el <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> del archivo .svc y creando una entrada de configuración para el extremo.  
  
 Si su servicio requiere el modo de compatibilidad de ASP.NET; por ejemplo, si utiliza la clase <xref:System.Web.HttpContext> o los mecanismos de autorización de ASP.NET, se sigue requiriendo un archivo de configuración para activar este modo. El elemento de configuración requerido es el [\<serviceHostingEnvironment>](../../configure-apps/file-schema/wcf/servicehostingenvironment.md) elemento, que se debe agregar como se indica a continuación.  
  
 `<system.serviceModel>`  
  
 `<serviceHostingEnvironment aspNetCompatibilityEnabled="true" /> </system.serviceModel>`  
  
 Para obtener más información, vea el tema [servicios WCF y ASP.net](wcf-services-and-aspnet.md) .  
  
 La clase <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> es una clase derivada de <xref:System.ServiceModel.Activation.ServiceHostFactory>. Para obtener una explicación detallada del mecanismo de fábrica de host de servicio, consulte el tema [Extending Hosting Using ServiceHostFactory](../extending/extending-hosting-using-servicehostfactory.md) .  
  
## <a name="see-also"></a>Vea también

- [Creación de servicios WCF para AJAX de ASP.NET](creating-wcf-services-for-aspnet-ajax.md)
- [Procedimiento para migrar servicios web de ASP.NET con AJAX habilitado a WCF](how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
