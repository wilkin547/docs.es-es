---
title: Configuración del cliente
ms.date: 03/30/2017
ms.assetid: 5da5bd3b-65d9-43b7-91b9-cc9e989b1350
ms.openlocfilehash: 2d17438095e65ccf922061c03e406bab35b07c5d
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593664"
---
# <a name="client-configuration"></a><span data-ttu-id="116b1-102">Configuración del cliente</span><span class="sxs-lookup"><span data-stu-id="116b1-102">Client Configuration</span></span>
<span data-ttu-id="116b1-103">Puede usar la configuración de cliente de Windows Communication Foundation (WCF) para especificar la dirección, el enlace, el comportamiento y el contrato, las propiedades "ABC" del punto de conexión del cliente, que los clientes utilizan para conectarse a los puntos de conexión de servicio.</span><span class="sxs-lookup"><span data-stu-id="116b1-103">You can use the Windows Communication Foundation (WCF) client configuration to specify the address, binding, behavior, and contract, the "ABC" properties of the client endpoint, which clients use to connect to service endpoints.</span></span> <span data-ttu-id="116b1-104">El [\<client>](../../configure-apps/file-schema/wcf/client.md) elemento tiene un [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) elemento cuyos atributos se usan para configurar los ABC del extremo.</span><span class="sxs-lookup"><span data-stu-id="116b1-104">The [\<client>](../../configure-apps/file-schema/wcf/client.md) element has an [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) element whose attributes are used to configure the endpoint ABCs.</span></span> <span data-ttu-id="116b1-105">Estos atributos se describen en la sección [configuración de puntos de conexión](#configuring-endpoints) .</span><span class="sxs-lookup"><span data-stu-id="116b1-105">These attributes are discussed in the [Configuring Endpoints](#configuring-endpoints) section.</span></span>  
  
 <span data-ttu-id="116b1-106">El [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) elemento también contiene un [\<metadata>](../../configure-apps/file-schema/wcf/metadata.md) elemento que se usa para especificar la configuración para importar y exportar metadatos, un [\<headers>](../../configure-apps/file-schema/wcf/headers.md) elemento que contiene una colección de encabezados de dirección personalizados y un [\<identity>](../../configure-apps/file-schema/wcf/identity.md) elemento que habilita la autenticación de un extremo por otros extremos que intercambian mensajes con él.</span><span class="sxs-lookup"><span data-stu-id="116b1-106">The [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) element also contains a [\<metadata>](../../configure-apps/file-schema/wcf/metadata.md) element that is used to specify settings for importing and exporting metadata, a [\<headers>](../../configure-apps/file-schema/wcf/headers.md) element that contains a collection of custom address headers, and an [\<identity>](../../configure-apps/file-schema/wcf/identity.md) element that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span> <span data-ttu-id="116b1-107">Los [\<headers>](../../configure-apps/file-schema/wcf/headers.md) [\<identity>](../../configure-apps/file-schema/wcf/identity.md) elementos y forman parte del <xref:System.ServiceModel.EndpointAddress> y se describen en el artículo [direcciones](endpoint-addresses.md) .</span><span class="sxs-lookup"><span data-stu-id="116b1-107">The [\<headers>](../../configure-apps/file-schema/wcf/headers.md) and [\<identity>](../../configure-apps/file-schema/wcf/identity.md) elements are part of the <xref:System.ServiceModel.EndpointAddress> and are discussed in the [Addresses](endpoint-addresses.md) article.</span></span> <span data-ttu-id="116b1-108">Los vínculos a temas que explican el uso de las extensiones de metadatos se proporcionan en la sección [configuración de metadatos](#configuring-metadata) .</span><span class="sxs-lookup"><span data-stu-id="116b1-108">Links to topics that explain the use of metadata extensions are provided in the [Configuring Metadata](#configuring-metadata) section.</span></span>  
  
## <a name="configuring-endpoints"></a><span data-ttu-id="116b1-109">Configuración de puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="116b1-109">Configuring Endpoints</span></span>  
 <span data-ttu-id="116b1-110">La configuración del cliente está diseñada para permitir que el cliente especifique uno o más puntos de conexión, cada uno con su propio nombre, dirección y contrato, donde cada uno hace referencia a los [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) elementos y de la configuración del cliente que se va a usar para configurar ese extremo.</span><span class="sxs-lookup"><span data-stu-id="116b1-110">The client configuration is designed to allow the client to specify one or more endpoints, each with its own name, address, and contract, with each referencing the [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) and [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) elements in the client configuration to be used to configure that endpoint.</span></span> <span data-ttu-id="116b1-111">El archivo de configuración del cliente se debe denominar "app. config" porque es el nombre que espera el tiempo de ejecución de WCF.</span><span class="sxs-lookup"><span data-stu-id="116b1-111">The client configuration file should be named "App.config" because this is the name that the WCF runtime expects.</span></span> <span data-ttu-id="116b1-112">El siguiente ejemplo muestra un archivo de configuración de cliente.</span><span class="sxs-lookup"><span data-stu-id="116b1-112">The following example shows a client configuration file.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
        <client>  
          <endpoint  
            name="endpoint1"  
            address="http://localhost/ServiceModelSamples/service.svc"  
            binding="wsHttpBinding"  
            bindingConfiguration="WSHttpBinding_IHello"  
            behaviorConfiguration="IHello_Behavior"  
            contract="IHello" >  
  
            <metadata>  
              <wsdlImporters>  
                <extension  
                  type="Microsoft.ServiceModel.Samples.WsdlDocumentationImporter, WsdlDocumentation"/>  
              </wsdlImporters>  
            </metadata>  
  
            <identity>  
              <servicePrincipalName value="host/localhost" />  
            </identity>  
          </endpoint>  
            <!-- Add another endpoint by adding another <endpoint> element. -->
          <endpoint  
            name="endpoint2">  
           //Configure another endpoint here.  
          </endpoint>  
        </client>  
  
//The bindings section references by the bindingConfiguration endpoint attribute.  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_IHello"
                 bypassProxyOnLocal="false"
                 hostNameComparisonMode="StrongWildcard">  
          <readerQuotas maxDepth="32"/>  
          <reliableSession ordered="true"
                           enabled="false" />  
          <security mode="Message">  
           //Security settings go here.  
          </security>  
        </binding>  
        <binding name="Another Binding"  
          <!-- Configure this binding here. -->  
        </binding>  
          </wsHttpBinding>  
     </bindings>  
  
//The behavior section references by the behaviorConfiguration endpoint attribute.  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name=" IHello_Behavior ">  
                    <clientVia />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
  
    </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="116b1-113">El atributo opcional `name` identifica de manera única a un punto de conexión de un contrato determinado.</span><span class="sxs-lookup"><span data-stu-id="116b1-113">The optional `name` attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="116b1-114">Es utilizado por <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> o <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> para especificar qué extremo de la configuración del cliente se destina y se debe cargar cuando se crea un canal para el servicio.</span><span class="sxs-lookup"><span data-stu-id="116b1-114">It is used by the <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> or by the <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> to specify which endpoint in the client configuration is being targeted and must be loaded when a channel is created to service.</span></span> <span data-ttu-id="116b1-115">Hay disponible un nombre de configuración de punto de conexión de comodín " \* " que indica al <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> método que debe cargar cualquier configuración de extremo en el archivo, siempre que haya precisamente uno disponible y, de lo contrario, produzca una excepción.</span><span class="sxs-lookup"><span data-stu-id="116b1-115">A wildcard endpoint configuration name "\*" is available and indicates to the <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> method that it should load any endpoint configuration in the file, provided there is precisely one available, and otherwise throws an exception.</span></span> <span data-ttu-id="116b1-116">Si se omite este atributo, el punto de conexión correspondiente se usa como el punto de conexión predeterminado asociado al tipo de contrato especificado.</span><span class="sxs-lookup"><span data-stu-id="116b1-116">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified contract type.</span></span> <span data-ttu-id="116b1-117">El valor predeterminado para el atributo `name` es una cadena vacía que se iguala como cualquier otro nombre.</span><span class="sxs-lookup"><span data-stu-id="116b1-117">The default value for the `name` attribute is an empty string which is matched like any other name.</span></span>  
  
 <span data-ttu-id="116b1-118">Cada punto de conexión debe tener una dirección asociada a él para ubicar e identificar el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="116b1-118">Every endpoint must have an address associated with it to locate and identify the endpoint.</span></span> <span data-ttu-id="116b1-119">El atributo `address` se puede utilizar para especificar la dirección URL que proporciona la ubicación del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="116b1-119">The `address` attribute can be used to specify the URL that provides the location of the endpoint.</span></span> <span data-ttu-id="116b1-120">Pero la dirección de un extremo de servicio también se puede especificar en código mediante la creación de un Identificador uniforme de recursos (URI) y se agrega al <xref:System.ServiceModel.ServiceHost> utilizando uno de los métodos <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.</span><span class="sxs-lookup"><span data-stu-id="116b1-120">But the address for a service endpoint can also be specified in code by creating a Uniform Resource Identifier (URI) and is added to the <xref:System.ServiceModel.ServiceHost> using one of the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> methods.</span></span> <span data-ttu-id="116b1-121">Para obtener más información, vea [Addresses](endpoint-addresses.md).</span><span class="sxs-lookup"><span data-stu-id="116b1-121">For more information, see [Addresses](endpoint-addresses.md).</span></span> <span data-ttu-id="116b1-122">Como indica la introducción, los [\<headers>](../../configure-apps/file-schema/wcf/headers.md) [\<identity>](../../configure-apps/file-schema/wcf/identity.md) elementos y forman parte de <xref:System.ServiceModel.EndpointAddress> y también se tratan en el tema [direcciones](endpoint-addresses.md) .</span><span class="sxs-lookup"><span data-stu-id="116b1-122">As the introduction indicates, the [\<headers>](../../configure-apps/file-schema/wcf/headers.md) and [\<identity>](../../configure-apps/file-schema/wcf/identity.md) elements are part of the <xref:System.ServiceModel.EndpointAddress> and are also discussed in the [Addresses](endpoint-addresses.md) topic.</span></span>  
  
 <span data-ttu-id="116b1-123">El atributo `binding` indica el tipo de enlace que el punto de conexión espera utilizar al conectarse a un servicio.</span><span class="sxs-lookup"><span data-stu-id="116b1-123">The `binding` attribute indicates the type of binding the endpoint expects to use when connecting to a service.</span></span> <span data-ttu-id="116b1-124">El tipo debe tener una sección de configuración registrada si se le va a hacer referencia.</span><span class="sxs-lookup"><span data-stu-id="116b1-124">The type must have a registered configuration section if it is to be referenced.</span></span> <span data-ttu-id="116b1-125">En el ejemplo anterior, esta es la [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) sección, que indica que el extremo usa un <xref:System.ServiceModel.WSHttpBinding> .</span><span class="sxs-lookup"><span data-stu-id="116b1-125">In the previous example, this is the [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) section, which indicates that the endpoint uses a <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="116b1-126">Pero puede que haya más de un enlace de un tipo determinado que el punto de conexión puede utilizar.</span><span class="sxs-lookup"><span data-stu-id="116b1-126">But there may be more than one binding of a given type that the endpoint can use.</span></span> <span data-ttu-id="116b1-127">Cada uno de ellos tiene su propio [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento dentro del elemento de tipo (enlace).</span><span class="sxs-lookup"><span data-stu-id="116b1-127">Each of these has its own [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element within the (binding) type element.</span></span> <span data-ttu-id="116b1-128">El atributo `bindingconfiguration` se utiliza para distinguir entre enlaces del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="116b1-128">The `bindingconfiguration` attribute is used to distinguish between bindings of the same type.</span></span> <span data-ttu-id="116b1-129">Su valor coincide con el `name` atributo del [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="116b1-129">Its value is matched with the `name` attribute of the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element.</span></span> <span data-ttu-id="116b1-130">Para obtener más información sobre cómo configurar un enlace de cliente mediante la configuración, consulte [Cómo: especificar un enlace de cliente en la configuración](../how-to-specify-a-client-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="116b1-130">For more information about how to configure a client binding using configuration, see [How to: Specify a Client Binding in Configuration](../how-to-specify-a-client-binding-in-configuration.md).</span></span>  
  
 <span data-ttu-id="116b1-131">El `behaviorConfiguration` atributo se usa para especificar cuál [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) de los [\<endpointBehaviors>](../../configure-apps/file-schema/wcf/endpointbehaviors.md) extremos debe usar.</span><span class="sxs-lookup"><span data-stu-id="116b1-131">The `behaviorConfiguration` attribute is used to specify which [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) of the [\<endpointBehaviors>](../../configure-apps/file-schema/wcf/endpointbehaviors.md) the endpoint should use.</span></span> <span data-ttu-id="116b1-132">Su valor coincide con el `name` atributo del [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="116b1-132">Its value is matched with the `name` attribute of the [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element.</span></span> <span data-ttu-id="116b1-133">Para obtener un ejemplo del uso de la configuración para especificar comportamientos de cliente, consulte [configuración de comportamientos de cliente](../configuring-client-behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="116b1-133">For an example of using configuration to specify client behaviors, see [Configuring Client Behaviors](../configuring-client-behaviors.md).</span></span>  
  
 <span data-ttu-id="116b1-134">El atributo `contract` especifica qué contrato expone este punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="116b1-134">The `contract` attribute specifies which contract the endpoint is exposing.</span></span> <span data-ttu-id="116b1-135">Este valor se asigna al <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> del <xref:System.ServiceModel.ServiceContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="116b1-135">This value maps to the <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> of the <xref:System.ServiceModel.ServiceContractAttribute>.</span></span> <span data-ttu-id="116b1-136">El valor predeterminado es el nombre de tipo completo de la clase que implementa el servicio.</span><span class="sxs-lookup"><span data-stu-id="116b1-136">The default value is the full type name of the class that implements the service.</span></span>  
  
### <a name="configuring-metadata"></a><span data-ttu-id="116b1-137">Configuración de metadatos</span><span class="sxs-lookup"><span data-stu-id="116b1-137">Configuring Metadata</span></span>  
 <span data-ttu-id="116b1-138">El [\<metadata>](../../configure-apps/file-schema/wcf/metadata.md) elemento se usa para especificar la configuración que se usa para registrar las extensiones de importación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="116b1-138">The [\<metadata>](../../configure-apps/file-schema/wcf/metadata.md) element is used to specify settings used to register metadata import extensions.</span></span> <span data-ttu-id="116b1-139">Para obtener más información sobre cómo extender el sistema de metadatos, vea [extender el sistema de metadatos](../extending/extending-the-metadata-system.md).</span><span class="sxs-lookup"><span data-stu-id="116b1-139">For more information about extending the metadata system, see [Extending the Metadata System](../extending/extending-the-metadata-system.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="116b1-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="116b1-140">See also</span></span>

- [<span data-ttu-id="116b1-141">Puntos de conexión: direcciones, enlaces y contratos</span><span class="sxs-lookup"><span data-stu-id="116b1-141">Endpoints: Addresses, Bindings, and Contracts</span></span>](endpoints-addresses-bindings-and-contracts.md)
- [<span data-ttu-id="116b1-142">Configuración de los comportamientos del cliente</span><span class="sxs-lookup"><span data-stu-id="116b1-142">Configuring Client Behaviors</span></span>](../configuring-client-behaviors.md)
