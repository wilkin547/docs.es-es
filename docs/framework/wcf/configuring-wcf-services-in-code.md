---
title: Configurar servicios WCF en el código
ms.date: 03/30/2017
ms.assetid: 193c725d-134f-4d31-a8f8-4e575233bff6
ms.openlocfilehash: 714236bcdb562840323698622cdf3d0c6c89b6ca
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="configuring-wcf-services-in-code"></a><span data-ttu-id="1e8a5-102">Configurar servicios WCF en el código</span><span class="sxs-lookup"><span data-stu-id="1e8a5-102">Configuring WCF Services in Code</span></span>
<span data-ttu-id="1e8a5-103">Windows Communication Foundation (WCF) permite a los desarrolladores configurar servicios mediante archivos de configuración o código.</span><span class="sxs-lookup"><span data-stu-id="1e8a5-103">Windows Communication Foundation (WCF) allows developers to configure services using configuration files or code.</span></span>  <span data-ttu-id="1e8a5-104">Los archivos de configuración son útiles cuando un servicio se debe configurar después de implementarse.</span><span class="sxs-lookup"><span data-stu-id="1e8a5-104">Configuration files are useful when a service needs to be configured after being deployed.</span></span> <span data-ttu-id="1e8a5-105">Cuando se usan archivos de configuración, un profesional de TI solo debe actualizar el archivo de configuración; no es necesario que realice ninguna recompilación.</span><span class="sxs-lookup"><span data-stu-id="1e8a5-105">When using configuration files, an IT professional only needs to update the configuration file, no recompilation is required.</span></span> <span data-ttu-id="1e8a5-106">Los archivos de configuración, sin embargo, pueden ser complejos y difíciles de mantener.</span><span class="sxs-lookup"><span data-stu-id="1e8a5-106">Configuration files, however, can be complex and difficult to maintain.</span></span> <span data-ttu-id="1e8a5-107">No se admite la depuración de archivos de configuración y se hace referencia a los elementos de configuración por nombre, con lo que la creación de archivos de configuración resulta propensa a errores y difícil.</span><span class="sxs-lookup"><span data-stu-id="1e8a5-107">There is no support for debugging configuration files and configuration elements are referenced by names which makes authoring configuration files error-prone and difficult.</span></span> <span data-ttu-id="1e8a5-108">WCF también permite configurar servicios en el código.</span><span class="sxs-lookup"><span data-stu-id="1e8a5-108">WCF also allows you to configure services in code.</span></span> <span data-ttu-id="1e8a5-109">En versiones anteriores de servicios de configuración de WCF (4.0 y anteriores) en código era sencilla en escenarios autohospedados; la <xref:System.ServiceModel.ServiceHost> clase permitía configurar extremos y comportamientos antes de llamar a ServiceHost.Open.</span><span class="sxs-lookup"><span data-stu-id="1e8a5-109">In earlier versions of WCF (4.0 and earlier) configuring services in code was easy in self-hosted scenarios, the <xref:System.ServiceModel.ServiceHost> class allowed you to configure endpoints and behaviors prior to calling ServiceHost.Open.</span></span> <span data-ttu-id="1e8a5-110">En escenarios hospedados en web, sin embargo, no tiene acceso directo a la clase <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="1e8a5-110">In web hosted scenarios, however, you don’t have direct access to the <xref:System.ServiceModel.ServiceHost> class.</span></span> <span data-ttu-id="1e8a5-111">Para configurar un servicio hospedado en web era necesario crear un `System.ServiceModel.ServiceHostFactory` que creó el <xref:System.ServiceModel.Activation.ServiceHostFactory> y realizar cualquier configuración necesaria.</span><span class="sxs-lookup"><span data-stu-id="1e8a5-111">To configure a web hosted service you were required to create a `System.ServiceModel.ServiceHostFactory` that created the <xref:System.ServiceModel.Activation.ServiceHostFactory> and performed any needed configuration.</span></span> <span data-ttu-id="1e8a5-112">A partir de .NET 4.5, WCF proporciona una manera más fácil de configurar ambos hospeda a sí mismo y servicios en el código hospedado en web.</span><span class="sxs-lookup"><span data-stu-id="1e8a5-112">Starting with .NET 4.5, WCF provides an easier way to configure both self-hosted and web hosted services in code.</span></span>  
  
## <a name="the-configure-method"></a><span data-ttu-id="1e8a5-113">El método Configure</span><span class="sxs-lookup"><span data-stu-id="1e8a5-113">The Configure method</span></span>  
 <span data-ttu-id="1e8a5-114">Defina simplemente un método estático público denominado `Configure` con la signatura siguiente en la clase de implementación del servicio:</span><span class="sxs-lookup"><span data-stu-id="1e8a5-114">Simply define a public static method called `Configure` with the following signature in your service implementation class:</span></span>  
  
```csharp  
public static void Configure(ServiceConfiguration config)  
```  
  
 <span data-ttu-id="1e8a5-115">El método Configure toma una instancia de <xref:System.ServiceModel.ServiceConfiguration> que permite al desarrollador agregar extremos y comportamientos.</span><span class="sxs-lookup"><span data-stu-id="1e8a5-115">The Configure method takes a <xref:System.ServiceModel.ServiceConfiguration> instance that enables the developer to add endpoints and behaviors.</span></span> <span data-ttu-id="1e8a5-116">WCF llama a este método antes de abrir el host del servicio.</span><span class="sxs-lookup"><span data-stu-id="1e8a5-116">This method is called by WCF before the service host is opened.</span></span> <span data-ttu-id="1e8a5-117">Cuando se definen, los valores de configuración de servicio especificados en un archivo app.config o web.config se omitirán.</span><span class="sxs-lookup"><span data-stu-id="1e8a5-117">When defined, any service configuration settings specified in an app.config or web.config file will be ignored.</span></span>  
  
 <span data-ttu-id="1e8a5-118">El fragmento de código siguiente muestra cómo definir el método `Configure` y agregar un extremo de servicio, un comportamiento de extremo y comportamientos del servicio:</span><span class="sxs-lookup"><span data-stu-id="1e8a5-118">The following code snippet illustrates how to define the `Configure` method and add a service endpoint, an endpoint behavior and service behaviors:</span></span>  
  
```csharp  
public class Service1 : IService1  
    {  
        public static void Configure(ServiceConfiguration config)  
        {  
            ServiceEndpoint se = new ServiceEndpoint(new ContractDescription("IService1"), new BasicHttpBinding(), new EndpointAddress("basic"));  
            se.Behaviors.Add(new MyEndpointBehavior());  
            config.AddServiceEndpoint(se);  
  
            config.Description.Behaviors.Add(new ServiceMetadataBehavior { HttpGetEnabled = true });  
            config.Description.Behaviors.Add(new ServiceDebugBehavior { IncludeExceptionDetailInFaults = true });  
        }  
  
        public string GetData(int value)  
        {  
            return string.Format("You entered: {0}", value);  
        }  
  
        public CompositeType GetDataUsingDataContract(CompositeType composite)  
        {  
            if (composite == null)  
            {  
                throw new ArgumentNullException("composite");  
            }  
            if (composite.BoolValue)  
            {  
                composite.StringValue += "Suffix";  
            }  
            return composite;  
        }  
    }  
```  
  
 <span data-ttu-id="1e8a5-119">Para habilitar un protocolo como https para un servicio, puede agregar explícitamente un punto de conexión que use el protocolo o puede agregar automáticamente puntos de conexión llamando a ServiceConfiguration.EnableProtocol (enlace) que agregue un punto de conexión para cada dirección base compatible con el protocolo y cada contrato de servicio definido.</span><span class="sxs-lookup"><span data-stu-id="1e8a5-119">To enable a protocol such as https for a service, you can either explicitly add an endpoint that uses the protocol or you can automatically add endpoints by calling ServiceConfiguration.EnableProtocol(Binding) which adds an endpoint for each base address compatible with the protocol and each service contract defined.</span></span> <span data-ttu-id="1e8a5-120">El código siguiente ilustra cómo usar el método ServiceConfiguration.EnableProtocol:</span><span class="sxs-lookup"><span data-stu-id="1e8a5-120">The following code illustrates how to use the ServiceConfiguration.EnableProtocol method:</span></span>  
  
```csharp  
public class Service1 : IService1   
{   
    public string GetData(int value);   
    public static void Configure(ServiceConfiguration config)   
    {   
        // Enable "Add Service Reference" support   
       config.Description.Behaviors.Add( new ServiceMetadataBehavior { HttpGetEnabled = true });   
       // set up support for http, https, net.tcp, net.pipe   
       config.EnableProtocol(new BasicHttpBinding());   
       config.EnableProtocol(new BasicHttpBinding());   
       config.EnableProtocol(new NetTcpBinding());   
       config.EnableProtocol(new NetNamedPipeBinding());   
       // add an extra BasicHttpBinding endpoint at http:///basic   
       config.AddServiceEndpoint(typeof(IService1), new BasicHttpBinding(),"basic");   
    }   
}   
```  
  
 <span data-ttu-id="1e8a5-121">La configuración en el <`protocolMappings`> sección sólo se utilizarán si no hay extremos de la aplicación se agregan a la <xref:System.ServiceModel.ServiceConfiguration> mediante programación. Si lo desea, puede cargar la configuración del servicio desde el archivo de configuración de aplicación predeterminado mediante una llamada a <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> y, a continuación, cambiar la configuración.</span><span class="sxs-lookup"><span data-stu-id="1e8a5-121">The settings in the <`protocolMappings`> section are only used if no application endpoints are added to the <xref:System.ServiceModel.ServiceConfiguration> programmatically.You can optionally load the service configuration from the default application configuration file by calling <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> and then change the settings.</span></span> <span data-ttu-id="1e8a5-122">La clase <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration> también permite cargar la configuración desde una configuración centralizada.</span><span class="sxs-lookup"><span data-stu-id="1e8a5-122">The <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration> class also allows you to load configuration from a centralized configuration.</span></span> <span data-ttu-id="1e8a5-123">El código siguiente muestra cómo implementar esto:</span><span class="sxs-lookup"><span data-stu-id="1e8a5-123">The following code illustrates how to implement this:</span></span>  
  
```  
public class Service1 : IService1   
{   
    public void DoWork();   
    public static void Configure(ServiceConfiguration config)   
    {   
          config.LoadFromConfiguration(ConfigurationManager.OpenMappedExeConfiguration(new ExeConfigurationFileMap { ExeConfigFilename = @"c:\sharedConfig\MyConfig.config" }, ConfigurationUserLevel.None));   
    }   
}  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="1e8a5-124">Tenga en cuenta que <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> omite <`host`> configuración de la <`service`> etiqueta de <`system.serviceModel`>.</span><span class="sxs-lookup"><span data-stu-id="1e8a5-124">Note that <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> ignores <`host`> settings within the <`service`> tag of <`system.serviceModel`>.</span></span> <span data-ttu-id="1e8a5-125">Conceptualmente, <`host`> trata sobre la configuración del host, no configuración del servicio y se cargan antes de que se ejecuta el método de configurar.</span><span class="sxs-lookup"><span data-stu-id="1e8a5-125">Conceptually, <`host`> is about host configuration, not service configuration, and it gets loaded before the Configure method executes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e8a5-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e8a5-126">See Also</span></span>  
 [<span data-ttu-id="1e8a5-127">Configuración de servicios mediante archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="1e8a5-127">Configuring Services Using Configuration Files</span></span>](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)  
 [<span data-ttu-id="1e8a5-128">Configuración de los comportamientos del cliente</span><span class="sxs-lookup"><span data-stu-id="1e8a5-128">Configuring Client Behaviors</span></span>](../../../docs/framework/wcf/configuring-client-behaviors.md)  
 [<span data-ttu-id="1e8a5-129">Configuración simplificada</span><span class="sxs-lookup"><span data-stu-id="1e8a5-129">Simplified Configuration</span></span>](../../../docs/framework/wcf/simplified-configuration.md)  
 [<span data-ttu-id="1e8a5-130">Activación basada en la configuración</span><span class="sxs-lookup"><span data-stu-id="1e8a5-130">Configuration-Based Activation</span></span>](../../../docs/framework/wcf/samples/configuration-based-activation.md)  
 [<span data-ttu-id="1e8a5-131">Configuración</span><span class="sxs-lookup"><span data-stu-id="1e8a5-131">Configuration</span></span>](../../../docs/framework/wcf/samples/configuration-sample.md)  
 [<span data-ttu-id="1e8a5-132">Activación basada en la configuración en IIS y WAS</span><span class="sxs-lookup"><span data-stu-id="1e8a5-132">Configuration-Based Activation in IIS and WAS</span></span>](../../../docs/framework/wcf/feature-details/configuration-based-activation-in-iis-and-was.md)  
 [<span data-ttu-id="1e8a5-133">Compatibilidad con metadatos y configuración</span><span class="sxs-lookup"><span data-stu-id="1e8a5-133">Configuration and Metadata Support</span></span>](../../../docs/framework/wcf/extending/configuration-and-metadata-support.md)  
 [<span data-ttu-id="1e8a5-134">Configuración</span><span class="sxs-lookup"><span data-stu-id="1e8a5-134">Configuration</span></span>](../../../docs/framework/wcf/diagnostics/exceptions-reference/configuration.md)  
 [<span data-ttu-id="1e8a5-135">Cómo especificar un enlace de servicio en la configuración</span><span class="sxs-lookup"><span data-stu-id="1e8a5-135">How to: Specify a Service Binding in Configuration</span></span>](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)  
 [<span data-ttu-id="1e8a5-136">Creación de un punto de conexión de servicio en configuración</span><span class="sxs-lookup"><span data-stu-id="1e8a5-136">How to: Create a Service Endpoint in Configuration</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 [<span data-ttu-id="1e8a5-137">Publicación de metadatos para un servicio mediante un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="1e8a5-137">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [<span data-ttu-id="1e8a5-138">Cómo especificar un enlace de cliente en la configuración</span><span class="sxs-lookup"><span data-stu-id="1e8a5-138">How to: Specify a Client Binding in Configuration</span></span>](../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md)
