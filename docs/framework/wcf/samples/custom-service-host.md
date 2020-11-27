---
title: Host de servicio personalizado
ms.date: 03/30/2017
ms.assetid: fe16ff50-7156-4499-9c32-13d8a79dc100
ms.openlocfilehash: 56846f4021b2a0be1801decedb02c4c637847d07
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275598"
---
# <a name="custom-service-host"></a><span data-ttu-id="47108-102">Host de servicio personalizado</span><span class="sxs-lookup"><span data-stu-id="47108-102">Custom Service Host</span></span>

<span data-ttu-id="47108-103">Este ejemplo muestra cómo utilizar un derivado personalizado de la clase <xref:System.ServiceModel.ServiceHost> para modificar el comportamiento de tiempo de ejecución de un servicio.</span><span class="sxs-lookup"><span data-stu-id="47108-103">This sample demonstrates how to use a custom derivative of the <xref:System.ServiceModel.ServiceHost> class to alter the run-time behavior of a service.</span></span> <span data-ttu-id="47108-104">Este enfoque proporciona una alternativa reutilizable para configurar un gran número de servicios de una manera común.</span><span class="sxs-lookup"><span data-stu-id="47108-104">This approach provides a reusable alternative to configuring a large number of services in a common way.</span></span> <span data-ttu-id="47108-105">El ejemplo también muestra cómo utilizar la clase <xref:System.ServiceModel.Activation.ServiceHostFactory> para utilizar un ServiceHost personalizado en el entorno de host de Internet Information Services (IIS) o el Servicio de activación de procesos de Windows (WAS).</span><span class="sxs-lookup"><span data-stu-id="47108-105">The sample also demonstrates how to use the <xref:System.ServiceModel.Activation.ServiceHostFactory> class to use a custom ServiceHost in the Internet Information Services (IIS) or Windows Process Activation Service (WAS) hosting environment.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="47108-106">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="47108-106">The samples may already be installed on your machine.</span></span> <span data-ttu-id="47108-107">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="47108-107">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="47108-108">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="47108-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="47108-109">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="47108-109">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Hosting\CustomServiceHost`  
  
## <a name="about-the-scenario"></a><span data-ttu-id="47108-110">Sobre el escenario</span><span class="sxs-lookup"><span data-stu-id="47108-110">About the scenario</span></span>

 <span data-ttu-id="47108-111">Para evitar la revelación involuntaria de metadatos de servicio potencialmente confidenciales, la configuración predeterminada de los servicios Windows Communication Foundation (WCF) deshabilita la publicación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="47108-111">To prevent unintentional disclosure of potentially sensitive service metadata, the default configuration for Windows Communication Foundation (WCF) services disables metadata publishing.</span></span> <span data-ttu-id="47108-112">Este comportamiento es seguro de forma predeterminada, pero también significa que no se puede usar una herramienta de importación de metadatos (como Svcutil.exe) para generar el código de cliente necesario para llamar al servicio a menos que el comportamiento de publicación de metadatos del servicio esté habilitado explícitamente en la configuración.</span><span class="sxs-lookup"><span data-stu-id="47108-112">This behavior is secure by default, but also means that you cannot use a metadata import tool (such as Svcutil.exe) to generate the client code required to call the service unless the service's metadata publishing behavior is explicitly enabled in configuration.</span></span>  
  
 <span data-ttu-id="47108-113">Habilitar los metadatos que publican para un número grande de servicios implica agregar los mismos elementos de configuración a cada servicio individual, lo cual produce una gran cantidad de información de configuración que es esencialmente la misma.</span><span class="sxs-lookup"><span data-stu-id="47108-113">Enabling metadata publishing for a large number of services involves adding the same configuration elements to each individual service, which results in a large amount of configuration information that is essentially the same.</span></span> <span data-ttu-id="47108-114">Como una alternativa a configurar individualmente cada servicio, es posible escribir el código imperativo que habilita metadatos que se publican una vez y a continuación reutilizar ese código entre varios servicios diferentes.</span><span class="sxs-lookup"><span data-stu-id="47108-114">As an alternative to configuring each service individually, it is possible to write the imperative code that enables metadata publishing once and then reuse that code across several different services.</span></span> <span data-ttu-id="47108-115">Esto se logra creando una nueva clase que derive de <xref:System.ServiceModel.ServiceHost> e invalide el método `ApplyConfiguration`() para agregar imperiosamente los metadatos que publican el comportamiento.</span><span class="sxs-lookup"><span data-stu-id="47108-115">This is accomplished by creating a new class that derives from <xref:System.ServiceModel.ServiceHost> and overrides the `ApplyConfiguration`() method to imperatively add the metadata publishing behavior.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="47108-116">Para mostrar más claridad, este ejemplo muestra cómo crear un punto de conexión de publicación de metadatos no se seguros.</span><span class="sxs-lookup"><span data-stu-id="47108-116">For clarity, this sample demonstrates how to create an unsecured metadata publishing endpoint.</span></span> <span data-ttu-id="47108-117">Estos puntos de conexión pueden estar disponibles para los consumidores anónimos no autenticados y se debe tener cuidado antes de implementar tales extremos para garantizar que el cierre público de los metadatos de un servicio es adecuado.</span><span class="sxs-lookup"><span data-stu-id="47108-117">Such endpoints are potentially available to anonymous unauthenticated consumers and care must be taken before deploying such endpoints to ensure that publicly disclosing a service's metadata is appropriate.</span></span>  
  
## <a name="implementing-a-custom-servicehost"></a><span data-ttu-id="47108-118">Implementar un ServiceHost personalizado</span><span class="sxs-lookup"><span data-stu-id="47108-118">Implementing a custom ServiceHost</span></span>

 <span data-ttu-id="47108-119">La clase <xref:System.ServiceModel.ServiceHost> expone varios métodos virtuales útiles que los herederos pueden invalidar para modificar el comportamiento del tiempo de ejecución de un servicio.</span><span class="sxs-lookup"><span data-stu-id="47108-119">The <xref:System.ServiceModel.ServiceHost> class exposes several useful virtual methods that inheritors can override to alter the run-time behavior of a service.</span></span> <span data-ttu-id="47108-120">Por ejemplo, el método `ApplyConfiguration`() lee información de la configuración de servicio del almacén de configuración y modifica la <xref:System.ServiceModel.Description.ServiceDescription> del host según corresponda.</span><span class="sxs-lookup"><span data-stu-id="47108-120">For example, the `ApplyConfiguration`() method reads service configuration information from the configuration store and alters the host's <xref:System.ServiceModel.Description.ServiceDescription> accordingly.</span></span> <span data-ttu-id="47108-121">La implementación predeterminada lee la configuración del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="47108-121">The default implementation reads configuration from the application's configuration file.</span></span> <span data-ttu-id="47108-122">Las implementaciones personalizadas pueden invalidar `ApplyConfiguration`() para seguir modificando la <xref:System.ServiceModel.Description.ServiceDescription> mediante el código imperativo o incluso reemplazar completamente el almacén de la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="47108-122">Custom implementations can override `ApplyConfiguration`() to further alter the <xref:System.ServiceModel.Description.ServiceDescription> using imperative code or even replace the default configuration store entirely.</span></span> <span data-ttu-id="47108-123">Por ejemplo, para leer la configuración del punto de conexión de un servicio desde una base de datos en lugar del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="47108-123">For example, to read a service's endpoint configuration from a database instead of the application's configuration file.</span></span>  
  
 <span data-ttu-id="47108-124">En este ejemplo, queremos crear un ServiceHost personalizado que agregue ServiceMetadataBehavior (que habilita la publicación de metadatos) aunque este comportamiento no se agregue explícitamente en el archivo de configuración del servicio.</span><span class="sxs-lookup"><span data-stu-id="47108-124">In this sample, we want to build a custom ServiceHost that adds the ServiceMetadataBehavior (which enables metadata publishing) even if this behavior is not explicitly added in the service's configuration file.</span></span> <span data-ttu-id="47108-125">Para ello, cree una nueva clase que herede de <xref:System.ServiceModel.ServiceHost> e invalide `ApplyConfiguration` ().</span><span class="sxs-lookup"><span data-stu-id="47108-125">To accomplish this, create a new class that inherits from <xref:System.ServiceModel.ServiceHost> and overrides `ApplyConfiguration`().</span></span>  
  
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
  
 <span data-ttu-id="47108-126">Dado que no deseamos omitir ninguna configuración que se haya proporcionado en el archivo de configuración de la aplicación, lo primero que nuestra invalidación de `ApplyConfiguration` () hace es llamar a la implementación base.</span><span class="sxs-lookup"><span data-stu-id="47108-126">Because we do not want to ignore any configuration that has been provided in the application's configuration file, the first thing our override of `ApplyConfiguration`() does is call the base implementation.</span></span> <span data-ttu-id="47108-127">Cuando este método se completa, podemos agregar imperiosamente <xref:System.ServiceModel.Description.ServiceMetadataBehavior> a la descripción utilizando el código imperativo siguiente.</span><span class="sxs-lookup"><span data-stu-id="47108-127">Once this method completes, we can imperatively add the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> to the description using the following imperative code.</span></span>  
  
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
  
 <span data-ttu-id="47108-128">La última cosa que nuestro () invalidador`ApplyConfiguration`debe hacer, es agregar el punto de conexión de metadatos predeterminado.</span><span class="sxs-lookup"><span data-stu-id="47108-128">The last thing our `ApplyConfiguration`() override must do is add the default metadata endpoint.</span></span> <span data-ttu-id="47108-129">Por Convención, se crea un punto de conexión de metadatos para cada URI en la colección BaseAddresses del host de servicio.</span><span class="sxs-lookup"><span data-stu-id="47108-129">By convention, one metadata endpoint is created for each URI in the service host's BaseAddresses collection.</span></span>  
  
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
  
## <a name="using-a-custom-servicehost-in-self-host"></a><span data-ttu-id="47108-130">Utilizar un ServiceHost personalizado en el mismo host</span><span class="sxs-lookup"><span data-stu-id="47108-130">Using a custom ServiceHost in self-host</span></span>  

 <span data-ttu-id="47108-131">Ahora que hemos completado nuestra implementación de ServiceHost personalizada, podemos utilizarla para agregar metadatos que publican el comportamiento de cualquier servicio, hospedando ese servicio dentro de una instancia de nuestro`SelfDescribingServiceHost`.</span><span class="sxs-lookup"><span data-stu-id="47108-131">Now that we have completed our custom ServiceHost implementation, we can use it to add metadata publishing behavior to any service by hosting that service inside of an instance of our `SelfDescribingServiceHost`.</span></span> <span data-ttu-id="47108-132">El código siguiente muestra cómo utilizarlo en el escenario del mismo host.</span><span class="sxs-lookup"><span data-stu-id="47108-132">The following code shows how to use it in the self-host scenario.</span></span>  
  
```csharp
SelfDescribingServiceHost host =
         new SelfDescribingServiceHost( typeof( Calculator ) );  
host.Open();  
```  
  
 <span data-ttu-id="47108-133">Nuestro host personalizado todavía lee la configuración del punto de conexión del servicio del archivo de configuración de la aplicación, como si hubiéramos utilizado la <xref:System.ServiceModel.ServiceHost> clase predeterminada para hospedar el servicio.</span><span class="sxs-lookup"><span data-stu-id="47108-133">Our custom host still reads the service's endpoint configuration from the application's configuration file, as if we had used the default <xref:System.ServiceModel.ServiceHost> class to host the service.</span></span> <span data-ttu-id="47108-134">Sin embargo, porque agregamos la lógica para habilitar metadatos que publican dentro de nuestro host personalizado, ya no debemos habilitar explícitamente los metadatos que publican el comportamiento en configuración.</span><span class="sxs-lookup"><span data-stu-id="47108-134">However, because we added the logic to enable metadata publishing inside of our custom host, we no longer must explicitly enable the metadata publishing behavior in configuration.</span></span> <span data-ttu-id="47108-135">Este enfoque tiene una ventaja distinta al estar creando una aplicación que contiene varios servicios y desea habilitar metadatos que publican en cada uno de ellos sin escribir los mismos elementos de configuración una y otra vez.</span><span class="sxs-lookup"><span data-stu-id="47108-135">This approach has a distinct advantage when you are building an application that contains several services and you want to enable metadata publishing on each of them without writing the same configuration elements over and over.</span></span>  
  
## <a name="using-a-custom-servicehost-in-iis-or-was"></a><span data-ttu-id="47108-136">Utilizar un ServiceHost personalizado en IIS o WAS</span><span class="sxs-lookup"><span data-stu-id="47108-136">Using a custom ServiceHost in IIS or WAS</span></span>  

 <span data-ttu-id="47108-137">Utilizar un host del servicio personalizado en escenarios de autohospedaje es sencillo, porque es su código de aplicación el que es finalmente responsable de crear y abrir la instancia del host de servicio.</span><span class="sxs-lookup"><span data-stu-id="47108-137">Using a custom service host in self-host scenarios is straightforward, because it is your application code that is ultimately responsible for creating and opening the service host instance.</span></span> <span data-ttu-id="47108-138">En el entorno de hospedaje de IIS o WAS, sin embargo, la infraestructura de WCF está creando dinámicamente una instancia del host del servicio en respuesta a los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="47108-138">In the IIS or WAS hosting environment, however, the WCF infrastructure is dynamically instantiating your service's host in response to incoming messages.</span></span> <span data-ttu-id="47108-139">Los hosts de servicio personalizados también se pueden utilizar en este entorno host, pero requieren código adicional en el formulario de ServiceHostFactory.</span><span class="sxs-lookup"><span data-stu-id="47108-139">Custom service hosts can also be used in this hosting environment, but they require some additional code in the form of a ServiceHostFactory.</span></span> <span data-ttu-id="47108-140">El código siguiente muestra un derivado de <xref:System.ServiceModel.Activation.ServiceHostFactory> que devuelve instancias de nuestro `SelfDescribingServiceHost`personalizado.</span><span class="sxs-lookup"><span data-stu-id="47108-140">The following code shows a derivative of <xref:System.ServiceModel.Activation.ServiceHostFactory> that returns instances of our custom `SelfDescribingServiceHost`.</span></span>  
  
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
  
 <span data-ttu-id="47108-141">Como puede ver, la implementación de un ServiceHostFactory personalizado es sencilla.</span><span class="sxs-lookup"><span data-stu-id="47108-141">As you can see, implementing a custom ServiceHostFactory is straightforward.</span></span> <span data-ttu-id="47108-142">Toda la lógica personalizada reside dentro de la implementación de ServiceHost; el generador devuelve una instancia de la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="47108-142">All of the custom logic resides inside of the ServiceHost implementation; the factory returns an instance of the derived class.</span></span>  
  
 <span data-ttu-id="47108-143">Para usar un generador personalizado con una implementación de servicio, debemos agregar algunos metadatos adicionales al archivo. SVC del servicio.</span><span class="sxs-lookup"><span data-stu-id="47108-143">To use a custom factory with a service implementation, we must add some additional metadata to the service's .svc file.</span></span>  
  
```aspx-csharp
<% @ServiceHost Service="Microsoft.ServiceModel.Samples.CalculatorService"
               Factory="Microsoft.ServiceModel.Samples.SelfDescribingServiceHostFactory"
               language=c# Debug="true" %>
```
  
 <span data-ttu-id="47108-144">Aquí hemos agregado un atributo adicional `Factory` a la `@ServiceHost` Directiva y hemos pasado el nombre de tipo de CLR de nuestro generador personalizado como el valor del atributo.</span><span class="sxs-lookup"><span data-stu-id="47108-144">Here we have added an additional `Factory` attribute to the `@ServiceHost` directive, and passed the CLR type name of our custom factory as the attribute's value.</span></span> <span data-ttu-id="47108-145">Cuando IIS o WAS recibe un mensaje para este servicio, la infraestructura de hospedaje de WCF crea primero una instancia de ServiceHostFactory y, a continuación, crea instancias del propio host del servicio mediante una llamada a `ServiceHostFactory.CreateServiceHost()` .</span><span class="sxs-lookup"><span data-stu-id="47108-145">When IIS or WAS receives a message for this service, the WCF hosting infrastructure first creates an instance of the ServiceHostFactory and then instantiates the service host itself by calling `ServiceHostFactory.CreateServiceHost()`.</span></span>  
  
## <a name="running-the-sample"></a><span data-ttu-id="47108-146">Ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="47108-146">Running the sample</span></span>  

 <span data-ttu-id="47108-147">Aunque en este ejemplo se proporciona una implementación de servicio y cliente totalmente funcional, el punto del ejemplo es mostrar cómo modificar el comportamiento de tiempo de ejecución de un servicio por medio de un host personalizado. Realice los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="47108-147">Although this sample does provide a fully functional client and service implementation, the point of the sample is to illustrate how to alter a service's run-time behavior by means of a custom host., do the following steps:</span></span>  
  
### <a name="observe-the-effect-of-the-custom-host"></a><span data-ttu-id="47108-148">Observar el efecto del host personalizado</span><span class="sxs-lookup"><span data-stu-id="47108-148">Observe the effect of the custom host</span></span>
  
1. <span data-ttu-id="47108-149">Abra el archivo de Web.config del servicio y observe que no hay ninguna configuración que habilite explícitamente los metadatos para el servicio.</span><span class="sxs-lookup"><span data-stu-id="47108-149">Open the service's Web.config file and observe that there is no configuration explicitly enabling metadata for the service.</span></span>  
  
2. <span data-ttu-id="47108-150">Abra el archivo. SVC del servicio y observe que su @ServiceHost Directiva contiene un atributo de generador que especifica el nombre de un ServiceHostFactory personalizado.</span><span class="sxs-lookup"><span data-stu-id="47108-150">Open the service's .svc file and observe that its @ServiceHost directive contains a Factory attribute that specifies the name of a custom ServiceHostFactory.</span></span>  
  
### <a name="set-up-build-and-run-the-sample"></a><span data-ttu-id="47108-151">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="47108-151">Set up, build, and run the sample</span></span>
  
1. <span data-ttu-id="47108-152">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="47108-152">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="47108-153">Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="47108-153">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="47108-154">Una vez compilada la solución, ejecute Setup.bat para configurar la aplicación ServiceModelSamples en IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="47108-154">After the solution has been built, run Setup.bat to set up the ServiceModelSamples Application in IIS 7.0.</span></span> <span data-ttu-id="47108-155">El directorio ServiceModelSamples debería aparecer ahora como una aplicación de IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="47108-155">The ServiceModelSamples directory should now appear as an IIS 7.0 Application.</span></span>

4. <span data-ttu-id="47108-156">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="47108-156">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

5. <span data-ttu-id="47108-157">Para quitar la aplicación IIS 7,0, ejecute *Cleanup.bat*.</span><span class="sxs-lookup"><span data-stu-id="47108-157">To remove the IIS 7.0 application, run *Cleanup.bat*.</span></span>

## <a name="see-also"></a><span data-ttu-id="47108-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="47108-158">See also</span></span>

- [<span data-ttu-id="47108-159">Procedimiento para hospedar un servicio WCF en IIS</span><span class="sxs-lookup"><span data-stu-id="47108-159">How to: Host a WCF Service in IIS</span></span>](../feature-details/how-to-host-a-wcf-service-in-iis.md)
