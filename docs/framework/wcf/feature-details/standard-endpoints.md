---
title: Extremos estándar
ms.date: 03/30/2017
ms.assetid: 3fcb4225-addc-44f2-935d-30e4943a8812
ms.openlocfilehash: 880601664d7602e279c5d022fa37c44914a58772
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184401"
---
# <a name="standard-endpoints"></a>Extremos estándar
Los puntos de conexión se definen mediante la especificación de una dirección, un enlace y un contrato. Otros parámetros que se pueden establecer en un extremo incluyen la configuración del comportamiento, los encabezados y los URI de escucha.  Para ciertos tipos de puntos de conexión, estos valores no cambian. Por ejemplo, los extremos de intercambio de metadatos siempre utilizan el contrato <xref:System.ServiceModel.Description.IMetadataExchange>. Otros extremos, como <xref:System.ServiceModel.Description.WebHttpEndpoint>, siempre requieren un comportamiento de extremo especificado. La utilidad de un punto de conexión se puede mejorar teniendo puntos de conexión con valores predeterminado para las propiedades de punto de conexión utilizadas normalmente. Los extremos estándar permiten a un desarrollador definir un extremo que tenga los valores predeterminados o en el que una o más propiedades del extremo no cambien.  Estos puntos de conexión le permiten utilizar un punto de conexión de este tipo sin tener que especificar información de tipo estático. Los puntos de conexión estándar se pueden usar para puntos de conexión de la aplicación y de la infraestructura.  
  
## <a name="infrastructure-endpoints"></a>Extremos de infraestructura  
 Un servicio puede exponer extremos con algunas de las propiedades no implementadas de forma explícita por el autor del servicio. Por ejemplo, el punto de conexión del intercambio de metadatos expone el contrato <xref:System.ServiceModel.Description.IMetadataExchange> pero, como autor del servicio, no implementa esa interfaz, pues la implementa WCF. Estos extremos de infraestructura tienen valores predeterminados para una o más propiedades de extremo, algunos de los cuales pueden ser inalterables. La propiedad <xref:System.ServiceModel.Description.ServiceEndpoint.Contract%2A> del extremo del intercambio de metadatos debe ser <xref:System.ServiceModel.Description.IMetadataExchange>, mientras que el desarrollador puede proporcionar otras propiedades, como el enlace. Los puntos de conexión de la infraestructura se identifican estableciendo la propiedad <xref:System.ServiceModel.Description.ServiceEndpoint.IsSystemEndpoint%2A> en `true`.  
  
## <a name="application-endpoints"></a>Extremos de la aplicación  
 Los desarrolladores de la aplicación pueden definir sus propios puntos de conexión estándar que especifican los valores predeterminados para la dirección, el enlace o el contrato. Defina un extremo estándar derivando una clase de <xref:System.ServiceModel.Description.ServiceEndpoint> y estableciendo las propiedades de extremo adecuadas. Puede proporcionar valores predeterminados a propiedades que se pueden cambiar. Otras propiedades tendrán valores estáticos que no podrán cambiar. En el siguiente ejemplo, se muestra cómo implementar un punto de conexión estándar.  
  
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
  
 Para usar un punto de conexión personalizado definido por <xref:System.ServiceModel.Configuration.StandardEndpointElement>el usuario en <xref:System.ServiceModel.Configuration.StandardEndpointCollectionElement%602>un archivo de configuración, debe derivar una clase de , derivar una clase de y registrar el nuevo punto de conexión estándar en la sección de extensiones en app.config o machine.config.  Proporciona <xref:System.ServiceModel.Configuration.StandardEndpointElement> compatibilidad de configuración para el punto de conexión estándar, como se muestra en el ejemplo siguiente.  
  
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
  
 Proporciona <xref:System.ServiceModel.Configuration.StandardEndpointCollectionElement%602> el tipo de respaldo para la `standardEndpoints` colección que aparece bajo la sección <> de la configuración para el punto de conexión estándar.  En el siguiente ejemplo, se muestra cómo implementar esta clase.  
  
```csharp
public class CustomEndpointCollectionElement : StandardEndpointCollectionElement<CustomEndpoint, CustomEndpointElement>
{
    // ...
}
```

En el siguiente ejemplo, se muestra cómo registrar un punto de conexión estándar en la sección de extensiones.

```xml  
<extensions>  
      <standardEndpointExtensions>  
        <add  
          name="customStandardEndpoint"  
          type="CustomEndpointCollectionElement, Example.dll,  
                Version=1.0.0.0, Culture=neutral, PublicKeyToken=ffffffffffffffff"/>  
```  
  
## <a name="configuring-a-standard-endpoint"></a>Configurar un punto de conexión estándar  
 Los puntos de conexión estándar se pueden agregar en código o en configuración.  Para agregar un punto de conexión estándar en código, basta con crear instancias del tipo de punto de conexión estándar adecuado y agregarlo al host del servicio, tal y como se muestra en el siguiente ejemplo:  
  
```csharp  
serviceHost.AddServiceEndpoint(new CustomEndpoint());  
```  
  
 Para agregar un punto de conexión `endpoint` estándar en `service` la configuración, agregue un elemento `standardEndpoints`> <al elemento> <y cualquier configuración necesaria en el elemento> de <. En el siguiente ejemplo, se muestra cómo agregar <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>, uno de los puntos de conexión estándar que se distribuye con [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].  
  
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
  
 El tipo de punto de conexión estándar se `endpoint` especifica mediante el atributo kind del elemento <>. El punto de conexión `standardEndpoints` se configura dentro del elemento> <. En el ejemplo anterior, se agrega y se configura un punto de conexión de <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>. El `udpDiscoveryEndpoint` elemento <> `standardEndpoint` contiene un <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint.MulticastAddress%2A>> <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>de <que establece la propiedad del archivo .  
  
## <a name="standard-endpoints-shipped-with-the-net-framework"></a>puntos de conexión estándar distribuidos con .NET Framework  
 En la siguiente tabla, se muestra una lista de los puntos de conexión estándar distribuidos con [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].  
  
 `Mex Endpoint`  
 Un punto de conexión estándar que se usa para exponer metadatos del servicio.  
  
 <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>  
 Un extremo estándar que usan los servicios para enviar mensajes del anuncio.  
  
 <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>  
 Un punto de conexión estándar que usan los servicios para enviar mensajes de la detección.  
  
 <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>  
 Un punto de conexión estándar que se pre-configura para las operaciones de detección en un enlace de multidifusión de UDP.  
  
 <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>  
 Un punto de conexión estándar que usan los servicios para enviar mensajes de anuncio en un enlace de UDP.  
  
 <xref:System.ServiceModel.Discovery.DynamicEndpoint>  
 Un punto de conexión estándar que utiliza detección del WS-Discovery para encontrar la dirección del punto de conexión en el tiempo de ejecución de forma dinámica.  
  
 <xref:System.ServiceModel.Description.ServiceMetadataEndpoint>  
 Un punto de conexión estándar para el intercambio de metadatos.  
  
 <xref:System.ServiceModel.Description.WebHttpEndpoint>  
 Un punto de conexión estándar con un enlace <xref:System.ServiceModel.WebHttpBinding> que agrega automáticamente el comportamiento <xref:System.ServiceModel.Description.WebHttpBehavior>.  
  
 <xref:System.ServiceModel.Description.WebScriptEndpoint>  
 Un punto de conexión estándar con un enlace <xref:System.ServiceModel.WebHttpBinding> que agrega automáticamente el comportamiento <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.  
  
 <xref:System.ServiceModel.Description.WebServiceEndpoint>  
 Un extremo estándar con un enlace <xref:System.ServiceModel.WebHttpBinding>.  
  
 <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>  
 Extremo estándar que le permite llamar a las operaciones de control en instancias de flujo de trabajo.  
  
 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>  
 Un punto de conexión estándar que admite la creación de flujo de trabajo y la reanudación del marcador.
