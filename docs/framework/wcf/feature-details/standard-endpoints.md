---
title: Extremos estándar
ms.date: 03/30/2017
ms.assetid: 3fcb4225-addc-44f2-935d-30e4943a8812
ms.openlocfilehash: a2f8d45990c5bc845aeee87ee82a2d043d6d1292
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96246451"
---
# <a name="standard-endpoints"></a><span data-ttu-id="5d2dd-102">Extremos estándar</span><span class="sxs-lookup"><span data-stu-id="5d2dd-102">Standard Endpoints</span></span>

<span data-ttu-id="5d2dd-103">Los puntos de conexión se definen mediante la especificación de una dirección, un enlace y un contrato.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-103">Endpoints are defined by specifying an address, a binding, and a contract.</span></span> <span data-ttu-id="5d2dd-104">Otros parámetros que se pueden establecer en un extremo incluyen la configuración del comportamiento, los encabezados y los URI de escucha.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-104">Other parameters that may be set on an endpoint include behavior configuration, headers, and listen URIs.</span></span>  <span data-ttu-id="5d2dd-105">Para ciertos tipos de puntos de conexión, estos valores no cambian.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-105">For certain types of endpoints these values do not change.</span></span> <span data-ttu-id="5d2dd-106">Por ejemplo, los extremos de intercambio de metadatos siempre utilizan el contrato <xref:System.ServiceModel.Description.IMetadataExchange>.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-106">For example, metadata exchange endpoints always use the <xref:System.ServiceModel.Description.IMetadataExchange> contract.</span></span> <span data-ttu-id="5d2dd-107">Otros extremos, como <xref:System.ServiceModel.Description.WebHttpEndpoint>, siempre requieren un comportamiento de extremo especificado.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-107">Other endpoints, such as <xref:System.ServiceModel.Description.WebHttpEndpoint> always require a specified endpoint behavior.</span></span> <span data-ttu-id="5d2dd-108">La utilidad de un punto de conexión se puede mejorar teniendo puntos de conexión con valores predeterminado para las propiedades de punto de conexión utilizadas normalmente.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-108">The usability of an endpoint can be improved by having endpoints with default values for commonly used endpoint properties.</span></span> <span data-ttu-id="5d2dd-109">Los extremos estándar permiten a un desarrollador definir un extremo que tenga los valores predeterminados o en el que una o más propiedades del extremo no cambien.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-109">Standard endpoints enable a developer to define an endpoint that has default values or where one or more endpoint’s properties does not change.</span></span>  <span data-ttu-id="5d2dd-110">Estos puntos de conexión le permiten utilizar un punto de conexión de este tipo sin tener que especificar información de tipo estático.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-110">These endpoints allow you to use such an endpoint without having to specify information of a static nature.</span></span> <span data-ttu-id="5d2dd-111">Los puntos de conexión estándar se pueden usar para puntos de conexión de la aplicación y de la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-111">Standard endpoints can be used for infrastructure and application endpoints.</span></span>  
  
## <a name="infrastructure-endpoints"></a><span data-ttu-id="5d2dd-112">Extremos de infraestructura</span><span class="sxs-lookup"><span data-stu-id="5d2dd-112">Infrastructure Endpoints</span></span>  

 <span data-ttu-id="5d2dd-113">Un servicio puede exponer extremos con algunas de las propiedades no implementadas de forma explícita por el autor del servicio.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-113">A service may expose endpoints with some of the properties not explicitly implemented by the service author.</span></span> <span data-ttu-id="5d2dd-114">Por ejemplo, el punto de conexión del intercambio de metadatos expone el contrato <xref:System.ServiceModel.Description.IMetadataExchange> pero, como autor del servicio, no implementa esa interfaz, pues la implementa WCF.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-114">For example, the metadata exchange endpoint exposes the <xref:System.ServiceModel.Description.IMetadataExchange> contract but as a service author you do not implement that interface, it is implemented by WCF.</span></span> <span data-ttu-id="5d2dd-115">Estos extremos de infraestructura tienen valores predeterminados para una o más propiedades de extremo, algunos de los cuales pueden ser inalterables.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-115">Such infrastructure endpoints have default values for one or more endpoint properties, some of which may be unalterable.</span></span> <span data-ttu-id="5d2dd-116">La propiedad <xref:System.ServiceModel.Description.ServiceEndpoint.Contract%2A> del extremo del intercambio de metadatos debe ser <xref:System.ServiceModel.Description.IMetadataExchange>, mientras que el desarrollador puede proporcionar otras propiedades, como el enlace.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-116">The <xref:System.ServiceModel.Description.ServiceEndpoint.Contract%2A> property of the metadata exchange endpoint must be <xref:System.ServiceModel.Description.IMetadataExchange>, while other properties like binding can be supplied by the developer.</span></span> <span data-ttu-id="5d2dd-117">Los puntos de conexión de la infraestructura se identifican estableciendo la propiedad <xref:System.ServiceModel.Description.ServiceEndpoint.IsSystemEndpoint%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-117">Infrastructure endpoints are identified by setting the <xref:System.ServiceModel.Description.ServiceEndpoint.IsSystemEndpoint%2A> property to `true`.</span></span>  
  
## <a name="application-endpoints"></a><span data-ttu-id="5d2dd-118">Extremos de la aplicación</span><span class="sxs-lookup"><span data-stu-id="5d2dd-118">Application Endpoints</span></span>  

 <span data-ttu-id="5d2dd-119">Los desarrolladores de la aplicación pueden definir sus propios puntos de conexión estándar que especifican los valores predeterminados para la dirección, el enlace o el contrato.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-119">Application developers can define their own standard endpoints which specify default values for the address, binding, or contract.</span></span> <span data-ttu-id="5d2dd-120">Defina un extremo estándar derivando una clase de <xref:System.ServiceModel.Description.ServiceEndpoint> y estableciendo las propiedades de extremo adecuadas.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-120">You define a standard endpoint by deriving a class from <xref:System.ServiceModel.Description.ServiceEndpoint> and setting the appropriate endpoint properties.</span></span> <span data-ttu-id="5d2dd-121">Puede proporcionar valores predeterminados a propiedades que se pueden cambiar.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-121">You can provide default values for properties that can be changed.</span></span> <span data-ttu-id="5d2dd-122">Otras propiedades tendrán valores estáticos que no podrán cambiar.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-122">Some other properties will have static values that cannot change.</span></span> <span data-ttu-id="5d2dd-123">En el siguiente ejemplo, se muestra cómo implementar un punto de conexión estándar.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-123">The following example shows how to implement a standard endpoint.</span></span>  
  
```csharp
public class CustomEndpoint : ServiceEndpoint
{
    public CustomEndpoint()
        : this(string.Empty)
    { }  

    public CustomEndpoint(string address)
        : this(address, ContractDescription.GetContract(typeof(ICalculator)))
    { }  

    // Create the custom endpoint with a fixed binding
    public CustomEndpoint(string address, ContractDescription contract)
        : base(contract)
    {
        this.Binding = new BasicHttpBinding();
        this.IsSystemEndpoint = false;
    }

    // Definition of the additional property of this endpoint
    public bool Property { get; set; }
}
```
  
 <span data-ttu-id="5d2dd-124">Para usar un punto de conexión personalizado definido por el usuario en un archivo de configuración, debe derivar una clase de <xref:System.ServiceModel.Configuration.StandardEndpointElement> , derivar una clase de <xref:System.ServiceModel.Configuration.StandardEndpointCollectionElement%602> y registrar el nuevo extremo estándar en la sección de extensiones en app.config o machine.config.  <xref:System.ServiceModel.Configuration.StandardEndpointElement> Proporciona compatibilidad con la configuración del punto de conexión estándar, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-124">To use a user-defined custom endpoint in a configuration file you must derive a class from <xref:System.ServiceModel.Configuration.StandardEndpointElement>, derive a class from <xref:System.ServiceModel.Configuration.StandardEndpointCollectionElement%602>, and register the new standard endpoint in the extensions section in app.config or machine.config.  The <xref:System.ServiceModel.Configuration.StandardEndpointElement> provides configuration support for the standard endpoint, as shown in the following example.</span></span>  
  
```csharp
public class CustomEndpointElement : StandardEndpointElement
{
    // Definition of the additional property for the standard endpoint element
    public bool Property
    {
        get { return (bool)base["property"]; }
        set { base["property"] = value; }
    }

    // The additional property needs to be added to the properties of the standard endpoint element
    protected override ConfigurationPropertyCollection Properties
    {
        get
        {
            ConfigurationPropertyCollection properties = base.Properties;
            properties.Add(new ConfigurationProperty("property", typeof(bool), false, ConfigurationPropertyOptions.None));
            return properties;
        }
    }

    // Return the type of this standard endpoint
    protected override Type EndpointType
    {
        get { return typeof(CustomEndpoint); }
    }

    // Create the custom service endpoint
    protected override ServiceEndpoint CreateServiceEndpoint(ContractDescription contract)
    {
        return new CustomEndpoint();
    }

    // Read the value given to the property in config and save it
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ServiceEndpointElement serviceEndpointElement)
    {
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;
        customEndpoint.Property = this.Property;
    }

    // Read the value given to the property in config and save it
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ChannelEndpointElement channelEndpointElement)
    {
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;
        customEndpoint.Property = this.Property;
    }

    // No validation in this sample
    protected override void OnInitializeAndValidate(ServiceEndpointElement serviceEndpointElement)
    {
    }

    // No validation in this sample
    protected override void OnInitializeAndValidate(ChannelEndpointElement channelEndpointElement)
    {
    }
}
```  
  
 <span data-ttu-id="5d2dd-125"><xref:System.ServiceModel.Configuration.StandardEndpointCollectionElement%602>Proporciona el tipo de respaldo para la colección que aparece en la `standardEndpoints` sección <> de la configuración del punto de conexión estándar.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-125">The <xref:System.ServiceModel.Configuration.StandardEndpointCollectionElement%602> provides the backing type for the collection that appears under the <`standardEndpoints`> section in the configuration for the standard endpoint.</span></span>  <span data-ttu-id="5d2dd-126">En el siguiente ejemplo, se muestra cómo implementar esta clase.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-126">The following example shows how to implement this class.</span></span>  
  
```csharp
public class CustomEndpointCollectionElement : StandardEndpointCollectionElement<CustomEndpoint, CustomEndpointElement>
{
    // ...
}
```

<span data-ttu-id="5d2dd-127">En el siguiente ejemplo, se muestra cómo registrar un punto de conexión estándar en la sección de extensiones.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-127">The following example shows how to register a standard endpoint in the extensions section.</span></span>

```xml  
<extensions>  
      <standardEndpointExtensions>  
        <add  
          name="customStandardEndpoint"  
          type="CustomEndpointCollectionElement, Example.dll,  
                Version=1.0.0.0, Culture=neutral, PublicKeyToken=ffffffffffffffff"/>  
      </standardEndpointExtensions>
</extensions>  
```  
  
## <a name="configuring-a-standard-endpoint"></a><span data-ttu-id="5d2dd-128">Configurar un punto de conexión estándar</span><span class="sxs-lookup"><span data-stu-id="5d2dd-128">Configuring a Standard Endpoint</span></span>  

 <span data-ttu-id="5d2dd-129">Los puntos de conexión estándar se pueden agregar en código o en configuración.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-129">Standard endpoints can be added in code or in configuration.</span></span>  <span data-ttu-id="5d2dd-130">Para agregar un punto de conexión estándar en código, basta con crear instancias del tipo de punto de conexión estándar adecuado y agregarlo al host del servicio, tal y como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5d2dd-130">To add a standard endpoint in code simply instantiate the appropriate standard endpoint type and add it to the service host as shown in the following example:</span></span>  
  
```csharp  
serviceHost.AddServiceEndpoint(new CustomEndpoint());  
```  
  
 <span data-ttu-id="5d2dd-131">Para agregar un punto de conexión estándar en la configuración, agregue un `endpoint` elemento <> al `service` elemento <> y los valores de configuración necesarios en el `standardEndpoints` elemento <>.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-131">To add a standard endpoint in configuration, add an <`endpoint`> element to the <`service`> element and any needed configuration settings in the <`standardEndpoints`> element.</span></span> <span data-ttu-id="5d2dd-132">En el siguiente ejemplo, se muestra cómo agregar <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>, uno de los puntos de conexión estándar que se distribuye con [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d2dd-132">The following example shows how to add a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>, one of the standard endpoints that ships with [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span>  
  
```xml  
<services>  
  <service>  
    <endpoint isSystemEndpoint="true" kind="udpDiscoveryEndpoint" />  
  </service>  
</services>  
<standardEndpoints>
  <udpDiscoveryEndpoint>  
     <standardEndpoint multicastAddress="soap.udp://239.255.255.250:3702" />
  </udpDiscoveryEndpoint>
</standardEndpoints>
```  
  
 <span data-ttu-id="5d2dd-133">El tipo de extremo estándar se especifica mediante el atributo Kind en el `endpoint` elemento <>.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-133">The type of standard endpoint is specified using the kind attribute in the <`endpoint`> element.</span></span> <span data-ttu-id="5d2dd-134">El punto de conexión se configura dentro del `standardEndpoints` elemento <>.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-134">The endpoint is configured within the <`standardEndpoints`> element.</span></span> <span data-ttu-id="5d2dd-135">En el ejemplo anterior, se agrega y se configura un punto de conexión de <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-135">In the example above, a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> endpoint is added and configured.</span></span> <span data-ttu-id="5d2dd-136">El `udpDiscoveryEndpoint` elemento> de <contiene un <`standardEndpoint`> que establece la <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint.MulticastAddress%2A> propiedad de <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> .</span><span class="sxs-lookup"><span data-stu-id="5d2dd-136">The <`udpDiscoveryEndpoint`> element contains a <`standardEndpoint`> that sets the <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint.MulticastAddress%2A> property of the <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>.</span></span>  
  
## <a name="standard-endpoints-shipped-with-the-net-framework"></a><span data-ttu-id="5d2dd-137">puntos de conexión estándar distribuidos con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5d2dd-137">Standard Endpoints Shipped with the .NET Framework</span></span>  

 <span data-ttu-id="5d2dd-138">En la siguiente tabla, se muestra una lista de los puntos de conexión estándar distribuidos con [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d2dd-138">The following table lists the standard endpoints shipped with [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 `Mex Endpoint`  
 <span data-ttu-id="5d2dd-139">Un punto de conexión estándar que se usa para exponer metadatos del servicio.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-139">A standard endpoint that is used to expose service metadata.</span></span>  
  
 <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>  
 <span data-ttu-id="5d2dd-140">Un extremo estándar que usan los servicios para enviar mensajes del anuncio.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-140">A standard endpoint that is used by services to send announcement messages.</span></span>  
  
 <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>  
 <span data-ttu-id="5d2dd-141">Un punto de conexión estándar que usan los servicios para enviar mensajes de la detección.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-141">A standard endpoint that is used by services to send discovery messages.</span></span>  
  
 <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>  
 <span data-ttu-id="5d2dd-142">Un punto de conexión estándar que se pre-configura para las operaciones de detección en un enlace de multidifusión de UDP.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-142">A standard endpoint that is pre-configured for discovery operations over a UDP multicast binding.</span></span>  
  
 <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>  
 <span data-ttu-id="5d2dd-143">Un punto de conexión estándar que usan los servicios para enviar mensajes de anuncio en un enlace de UDP.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-143">A standard endpoint that is used by services to send announcement messages over a UDP binding.</span></span>  
  
 <xref:System.ServiceModel.Discovery.DynamicEndpoint>  
 <span data-ttu-id="5d2dd-144">Un punto de conexión estándar que utiliza detección del WS-Discovery para encontrar la dirección del punto de conexión en el tiempo de ejecución de forma dinámica.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-144">A standard endpoint that uses WS-Discovery to find the endpoint address dynamically at runtime.</span></span>  
  
 <xref:System.ServiceModel.Description.ServiceMetadataEndpoint>  
 <span data-ttu-id="5d2dd-145">Un punto de conexión estándar para el intercambio de metadatos.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-145">A standard endpoint for metadata exchange.</span></span>  
  
 <xref:System.ServiceModel.Description.WebHttpEndpoint>  
 <span data-ttu-id="5d2dd-146">Un punto de conexión estándar con un enlace <xref:System.ServiceModel.WebHttpBinding> que agrega automáticamente el comportamiento <xref:System.ServiceModel.Description.WebHttpBehavior>.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-146">A standard endpoint with a <xref:System.ServiceModel.WebHttpBinding> binding that automatically adds the <xref:System.ServiceModel.Description.WebHttpBehavior> behavior</span></span>  
  
 <xref:System.ServiceModel.Description.WebScriptEndpoint>  
 <span data-ttu-id="5d2dd-147">Un punto de conexión estándar con un enlace <xref:System.ServiceModel.WebHttpBinding> que agrega automáticamente el comportamiento <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-147">A standard endpoint with a <xref:System.ServiceModel.WebHttpBinding> binding that automatically adds the <xref:System.ServiceModel.Description.WebScriptEnablingBehavior> behavior.</span></span>  
  
 <xref:System.ServiceModel.Description.WebServiceEndpoint>  
 <span data-ttu-id="5d2dd-148">Un extremo estándar con un enlace <xref:System.ServiceModel.WebHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-148">A standard endpoint with a <xref:System.ServiceModel.WebHttpBinding> binding.</span></span>  
  
 <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>  
 <span data-ttu-id="5d2dd-149">Extremo estándar que le permite llamar a las operaciones de control en instancias de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-149">A standard endpoint that enables you to call control operations on workflow instances.</span></span>  
  
 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>  
 <span data-ttu-id="5d2dd-150">Un punto de conexión estándar que admite la creación de flujo de trabajo y la reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="5d2dd-150">A standard endpoint that supports workflow creation and bookmark resumption.</span></span>
