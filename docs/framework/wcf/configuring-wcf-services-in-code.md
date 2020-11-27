---
title: Configurar servicios WCF en el código
description: Obtenga información sobre cómo configurar servicios WCF mediante el uso de código en lugar de archivos de configuración para servicios hospedados en Web y autohospedados.
ms.date: 03/30/2017
ms.assetid: 193c725d-134f-4d31-a8f8-4e575233bff6
ms.openlocfilehash: 0ba59856d94168c7f18319c09c9b00f26ecdff5c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253315"
---
# <a name="configuring-wcf-services-in-code"></a><span data-ttu-id="7294c-103">Configurar servicios WCF en el código</span><span class="sxs-lookup"><span data-stu-id="7294c-103">Configuring WCF Services in Code</span></span>

<span data-ttu-id="7294c-104">Windows Communication Foundation (WCF) permite a los desarrolladores configurar servicios mediante el código o los archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="7294c-104">Windows Communication Foundation (WCF) allows developers to configure services using configuration files or code.</span></span>  <span data-ttu-id="7294c-105">Los archivos de configuración son útiles cuando un servicio se debe configurar después de implementarse.</span><span class="sxs-lookup"><span data-stu-id="7294c-105">Configuration files are useful when a service needs to be configured after being deployed.</span></span> <span data-ttu-id="7294c-106">Cuando se usan archivos de configuración, un profesional de TI solo debe actualizar el archivo de configuración; no es necesario que realice ninguna recompilación.</span><span class="sxs-lookup"><span data-stu-id="7294c-106">When using configuration files, an IT professional only needs to update the configuration file, no recompilation is required.</span></span> <span data-ttu-id="7294c-107">Los archivos de configuración, sin embargo, pueden ser complejos y difíciles de mantener.</span><span class="sxs-lookup"><span data-stu-id="7294c-107">Configuration files, however, can be complex and difficult to maintain.</span></span> <span data-ttu-id="7294c-108">No se admite la depuración de archivos de configuración y se hace referencia a los elementos de configuración por nombre, con lo que la creación de archivos de configuración resulta propensa a errores y difícil.</span><span class="sxs-lookup"><span data-stu-id="7294c-108">There is no support for debugging configuration files and configuration elements are referenced by names which makes authoring configuration files error-prone and difficult.</span></span> <span data-ttu-id="7294c-109">WCF también permite configurar servicios en el código.</span><span class="sxs-lookup"><span data-stu-id="7294c-109">WCF also allows you to configure services in code.</span></span> <span data-ttu-id="7294c-110">En versiones anteriores de WCF (4,0 y anteriores), la configuración de servicios en código era muy fácil en escenarios autohospedados, la <xref:System.ServiceModel.ServiceHost> clase permitía configurar los extremos y comportamientos antes de llamar a ServiceHost. Open.</span><span class="sxs-lookup"><span data-stu-id="7294c-110">In earlier versions of WCF (4.0 and earlier) configuring services in code was easy in self-hosted scenarios, the <xref:System.ServiceModel.ServiceHost> class allowed you to configure endpoints and behaviors prior to calling ServiceHost.Open.</span></span> <span data-ttu-id="7294c-111">En escenarios hospedados en web, sin embargo, no tiene acceso directo a la clase <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="7294c-111">In web hosted scenarios, however, you don’t have direct access to the <xref:System.ServiceModel.ServiceHost> class.</span></span> <span data-ttu-id="7294c-112">Para configurar un servicio hospedado en web era necesario crear un `System.ServiceModel.ServiceHostFactory` que creó el <xref:System.ServiceModel.Activation.ServiceHostFactory> y realizar cualquier configuración necesaria.</span><span class="sxs-lookup"><span data-stu-id="7294c-112">To configure a web hosted service you were required to create a `System.ServiceModel.ServiceHostFactory` that created the <xref:System.ServiceModel.Activation.ServiceHostFactory> and performed any needed configuration.</span></span> <span data-ttu-id="7294c-113">A partir de .NET Framework 4,5, WCF proporciona una manera más fácil de configurar servicios hospedados en Web y autohospedados en el código.</span><span class="sxs-lookup"><span data-stu-id="7294c-113">Starting with .NET Framework 4.5, WCF provides an easier way to configure both self-hosted and web hosted services in code.</span></span>

## <a name="the-configure-method"></a><span data-ttu-id="7294c-114">El método Configure</span><span class="sxs-lookup"><span data-stu-id="7294c-114">The Configure method</span></span>

 <span data-ttu-id="7294c-115">Defina simplemente un método estático público denominado `Configure` con la signatura siguiente en la clase de implementación del servicio:</span><span class="sxs-lookup"><span data-stu-id="7294c-115">Simply define a public static method called `Configure` with the following signature in your service implementation class:</span></span>

```csharp
public static void Configure(ServiceConfiguration config)
```

 <span data-ttu-id="7294c-116">El método Configure toma una instancia de <xref:System.ServiceModel.ServiceConfiguration> que permite al desarrollador agregar puntos de conexión y comportamientos.</span><span class="sxs-lookup"><span data-stu-id="7294c-116">The Configure method takes a <xref:System.ServiceModel.ServiceConfiguration> instance that enables the developer to add endpoints and behaviors.</span></span> <span data-ttu-id="7294c-117">WCF llama a este método antes de que se abra el host de servicio.</span><span class="sxs-lookup"><span data-stu-id="7294c-117">This method is called by WCF before the service host is opened.</span></span> <span data-ttu-id="7294c-118">Cuando se definen, los valores de configuración de servicio especificados en un archivo app.config o web.config se omitirán.</span><span class="sxs-lookup"><span data-stu-id="7294c-118">When defined, any service configuration settings specified in an app.config or web.config file will be ignored.</span></span>

 <span data-ttu-id="7294c-119">El fragmento de código siguiente muestra cómo definir el método `Configure` y agregar un extremo de servicio, un comportamiento de extremo y comportamientos del servicio:</span><span class="sxs-lookup"><span data-stu-id="7294c-119">The following code snippet illustrates how to define the `Configure` method and add a service endpoint, an endpoint behavior and service behaviors:</span></span>

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
            return $"You entered: {value}";
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

 <span data-ttu-id="7294c-120">Para habilitar un protocolo como https para un servicio, puede agregar explícitamente un extremo que use el protocolo o puede agregar automáticamente extremos llamando a ServiceConfiguration.EnableProtocol (Binding) que agregue un extremo para cada dirección base compatible con el protocolo y cada contrato de servicio definido.</span><span class="sxs-lookup"><span data-stu-id="7294c-120">To enable a protocol such as https for a service, you can either explicitly add an endpoint that uses the protocol or you can automatically add endpoints by calling ServiceConfiguration.EnableProtocol(Binding) which adds an endpoint for each base address compatible with the protocol and each service contract defined.</span></span> <span data-ttu-id="7294c-121">El código siguiente ilustra cómo usar el método ServiceConfiguration.EnableProtocol:</span><span class="sxs-lookup"><span data-stu-id="7294c-121">The following code illustrates how to use the ServiceConfiguration.EnableProtocol method:</span></span>

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
       config.EnableProtocol(new BasicHttpsBinding());
       config.EnableProtocol(new NetTcpBinding());
       config.EnableProtocol(new NetNamedPipeBinding());
       // add an extra BasicHttpBinding endpoint at http:///basic
       config.AddServiceEndpoint(typeof(IService1), new BasicHttpBinding(),"basic");
    }
}
```

 <span data-ttu-id="7294c-122">La configuración de la `protocolMappings` sección <> solo se utiliza si no se agregan puntos de conexión de aplicación al <xref:System.ServiceModel.ServiceConfiguration> mediante programación. Opcionalmente, puede cargar la configuración del servicio desde el archivo de configuración de la aplicación predeterminado llamando a <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> y, a continuación, cambiar la configuración.</span><span class="sxs-lookup"><span data-stu-id="7294c-122">The settings in the <`protocolMappings`> section are only used if no application endpoints are added to the <xref:System.ServiceModel.ServiceConfiguration> programmatically.You can optionally load the service configuration from the default application configuration file by calling <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> and then change the settings.</span></span> <span data-ttu-id="7294c-123">La clase <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration> también permite cargar la configuración desde una configuración centralizada.</span><span class="sxs-lookup"><span data-stu-id="7294c-123">The <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration> class also allows you to load configuration from a centralized configuration.</span></span> <span data-ttu-id="7294c-124">El código siguiente muestra cómo implementar esto:</span><span class="sxs-lookup"><span data-stu-id="7294c-124">The following code illustrates how to implement this:</span></span>

```csharp
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
> <span data-ttu-id="7294c-125">Tenga en cuenta que <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> omite `host` la configuración de> de <dentro de la `service` etiqueta de> de <de <> `system.serviceModel` .</span><span class="sxs-lookup"><span data-stu-id="7294c-125">Note that <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> ignores <`host`> settings within the <`service`> tag of <`system.serviceModel`>.</span></span> <span data-ttu-id="7294c-126">Conceptualmente, <`host`> es acerca de la configuración del host, no de la configuración del servicio, y se carga antes de que se ejecute el método de configuración.</span><span class="sxs-lookup"><span data-stu-id="7294c-126">Conceptually, <`host`> is about host configuration, not service configuration, and it gets loaded before the Configure method executes.</span></span>

## <a name="see-also"></a><span data-ttu-id="7294c-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="7294c-127">See also</span></span>

- [<span data-ttu-id="7294c-128">Configuración de servicios mediante archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="7294c-128">Configuring Services Using Configuration Files</span></span>](configuring-services-using-configuration-files.md)
- [<span data-ttu-id="7294c-129">Configuración de los comportamientos del cliente</span><span class="sxs-lookup"><span data-stu-id="7294c-129">Configuring Client Behaviors</span></span>](configuring-client-behaviors.md)
- [<span data-ttu-id="7294c-130">Configuración simplificada</span><span class="sxs-lookup"><span data-stu-id="7294c-130">Simplified Configuration</span></span>](simplified-configuration.md)
- [<span data-ttu-id="7294c-131">Configuración</span><span class="sxs-lookup"><span data-stu-id="7294c-131">Configuration</span></span>](./samples/configuration-sample.md)
- [<span data-ttu-id="7294c-132">Activación basada en la configuración en IIS y WAS</span><span class="sxs-lookup"><span data-stu-id="7294c-132">Configuration-Based Activation in IIS and WAS</span></span>](./feature-details/configuration-based-activation-in-iis-and-was.md)
- [<span data-ttu-id="7294c-133">Compatibilidad con metadatos y configuración</span><span class="sxs-lookup"><span data-stu-id="7294c-133">Configuration and Metadata Support</span></span>](./extending/configuration-and-metadata-support.md)
- [<span data-ttu-id="7294c-134">Configuración</span><span class="sxs-lookup"><span data-stu-id="7294c-134">Configuration</span></span>](./diagnostics/exceptions-reference/configuration.md)
- [<span data-ttu-id="7294c-135">Procedimiento para especificar un enlace de servicio en la configuración</span><span class="sxs-lookup"><span data-stu-id="7294c-135">How to: Specify a Service Binding in Configuration</span></span>](how-to-specify-a-service-binding-in-configuration.md)
- [<span data-ttu-id="7294c-136">Procedimiento para crear un punto de conexión de servicio en la configuración</span><span class="sxs-lookup"><span data-stu-id="7294c-136">How to: Create a Service Endpoint in Configuration</span></span>](./feature-details/how-to-create-a-service-endpoint-in-configuration.md)
- [<span data-ttu-id="7294c-137">Procedimiento para publicar metadatos para un servicio mediante un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="7294c-137">How to: Publish Metadata for a Service Using a Configuration File</span></span>](./feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="7294c-138">Procedimiento para especificar un enlace de cliente en la configuración</span><span class="sxs-lookup"><span data-stu-id="7294c-138">How to: Specify a Client Binding in Configuration</span></span>](how-to-specify-a-client-binding-in-configuration.md)
