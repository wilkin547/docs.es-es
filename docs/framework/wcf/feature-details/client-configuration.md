---
title: "Configuración del cliente"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5da5bd3b-65d9-43b7-91b9-cc9e989b1350
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 35dc7ad932ea114e2751fa86ceb757dc795795f5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="client-configuration"></a><span data-ttu-id="54e5c-102">Configuración del cliente</span><span class="sxs-lookup"><span data-stu-id="54e5c-102">Client Configuration</span></span>
<span data-ttu-id="54e5c-103">Puede utilizar la configuración de cliente de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] para especificar la dirección, enlace, comportamiento y contrato, las propiedades "ABC" del extremo del cliente, que los clientes utilizan para conectarse a los extremos del servicio.</span><span class="sxs-lookup"><span data-stu-id="54e5c-103">You can use the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client configuration to specify the address, binding, behavior, and contract, the "ABC" properties of the client endpoint, which clients use to connect to service endpoints.</span></span> <span data-ttu-id="54e5c-104">El [ \<cliente >](../../../../docs/framework/configure-apps/file-schema/wcf/client.md) elemento tiene un [ \<extremo >](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017) elemento cuyos atributos se utilizan para configurar los ABC del extremo.</span><span class="sxs-lookup"><span data-stu-id="54e5c-104">The [\<client>](../../../../docs/framework/configure-apps/file-schema/wcf/client.md) element has an [\<endpoint>](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017) element whose attributes are used to configure the endpoint ABCs.</span></span> <span data-ttu-id="54e5c-105">Estos atributos se discuten en la sección “Configuración de puntos de conexión” de este tema.</span><span class="sxs-lookup"><span data-stu-id="54e5c-105">These attributes are discussed in the "Configuring Endpoints" section of this topic.</span></span>  
  
 <span data-ttu-id="54e5c-106">El [ \<extremo >](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017) elemento también contiene un [ \<metadatos >](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) elemento que se utiliza para especificar la configuración para la importación y exportación de metadatos, un [ \<encabezados >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) elemento que contiene una colección de encabezados de dirección personalizados y un [ \<identidad >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) elemento que habilita la autenticación de un extremo por otros puntos de conexión intercambiar mensajes con él.</span><span class="sxs-lookup"><span data-stu-id="54e5c-106">The [\<endpoint>](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017) element also contains a [\<metadata>](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) element that is used to specify settings for importing and exporting metadata , a [\<headers>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) element that contains a collection of custom address headers, and an [\<identity>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) element that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span> <span data-ttu-id="54e5c-107">El [ \<encabezados >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) y [ \<identidad >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) elementos forman parte de la <xref:System.ServiceModel.EndpointAddress> y se describen en la [direcciones](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md) tema.</span><span class="sxs-lookup"><span data-stu-id="54e5c-107">The [\<headers>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) and [\<identity>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) elements are part of the <xref:System.ServiceModel.EndpointAddress> and are discussed in the [Addresses](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md) topic.</span></span> <span data-ttu-id="54e5c-108">En la subsección Configuración de metadatos de este tema se proporcionan vínculos a temas que explican el uso de extensiones de metadatos.</span><span class="sxs-lookup"><span data-stu-id="54e5c-108">Links to topics that explain the use of metadata extensions are provided in the Configuring Metadata sub-section of this topic.</span></span>  
  
## <a name="configuring-endpoints"></a><span data-ttu-id="54e5c-109">Configuración de puntos de conexión</span><span class="sxs-lookup"><span data-stu-id="54e5c-109">Configuring Endpoints</span></span>  
 <span data-ttu-id="54e5c-110">La configuración del cliente está diseñada para permitir que el cliente especificar uno o más extremos, cada uno con su propio nombre, dirección y contrato, con cada referencia a la [ \<enlaces >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) y [ \< comportamientos >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elementos en la configuración del cliente que se usará para configurar dicho extremo.</span><span class="sxs-lookup"><span data-stu-id="54e5c-110">The client configuration is designed to allow the client to specify one or more endpoints, each with its own name, address, and contract, with each referencing the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) and [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elements in the client configuration to be used to configure that endpoint.</span></span> <span data-ttu-id="54e5c-111">El archivo de configuración del cliente debería llamarse "App.config", porque se trata del nombre que el tiempo de ejecución de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] espera.</span><span class="sxs-lookup"><span data-stu-id="54e5c-111">The client configuration file should be named "App.config" because this is the name that the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] runtime expects.</span></span> <span data-ttu-id="54e5c-112">El siguiente ejemplo muestra un archivo de configuración de cliente.</span><span class="sxs-lookup"><span data-stu-id="54e5c-112">The following example shows a client configuration file.</span></span>  
  
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
// Add another endpoint by adding another <endpoint> element.  
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
        //Configure this binding here.  
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
  
 <span data-ttu-id="54e5c-113">El atributo opcional `name` identifica de manera única a un extremo de un contrato determinado.</span><span class="sxs-lookup"><span data-stu-id="54e5c-113">The optional `name` attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="54e5c-114">Es utilizado por <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> o <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> para especificar qué extremo de la configuración del cliente se destina y se debe cargar cuando se crea un canal para el servicio.</span><span class="sxs-lookup"><span data-stu-id="54e5c-114">It is used by the <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> or by the <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> to specify which endpoint in the client configuration is being targeted and must be loaded when a channel is created to service.</span></span> <span data-ttu-id="54e5c-115">Hay disponible un nombre de configuración de extremo de comodín "*" e indica al método <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> que debería cargar cualquier configuración de extremo del archivo, suponiendo que haya precisamente uno disponible o, si no fuese así, produjese una excepción.</span><span class="sxs-lookup"><span data-stu-id="54e5c-115">A wildcard endpoint configuration name "*" is available and indicates to the <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> method that it should load any endpoint configuration in the file, provided there is precisely one available, and otherwise throws an exception.</span></span> <span data-ttu-id="54e5c-116">Si se omite este atributo, el extremo correspondiente se usa como el extremo predeterminado asociado al tipo de contrato especificado.</span><span class="sxs-lookup"><span data-stu-id="54e5c-116">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified contract type.</span></span> <span data-ttu-id="54e5c-117">El valor predeterminado para el atributo `name` es una cadena vacía que se iguala como cualquier otro nombre.</span><span class="sxs-lookup"><span data-stu-id="54e5c-117">The default value for the `name` attribute is an empty string which is matched like any other name.</span></span>  
  
 <span data-ttu-id="54e5c-118">Cada extremo debe tener una dirección asociada a él para ubicar e identificar el extremo.</span><span class="sxs-lookup"><span data-stu-id="54e5c-118">Every endpoint must have an address associated with it to locate and identify the endpoint.</span></span> <span data-ttu-id="54e5c-119">El atributo `address` se puede utilizar para especificar la dirección URL que proporciona la ubicación del extremo.</span><span class="sxs-lookup"><span data-stu-id="54e5c-119">The `address` attribute can be used to specify the URL that provides the location of the endpoint.</span></span> <span data-ttu-id="54e5c-120">Pero la dirección de un extremo de servicio también se puede especificar en código mediante la creación de un Identificador uniforme de recursos (URI) y se agrega al <xref:System.ServiceModel.ServiceHost> utilizando uno de los métodos <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.</span><span class="sxs-lookup"><span data-stu-id="54e5c-120">But the address for a service endpoint can also be specified in code by creating a Uniform Resource Identifier (URI) and is added to the <xref:System.ServiceModel.ServiceHost> using one of the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> methods.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="54e5c-121">[Direcciones](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md).</span><span class="sxs-lookup"><span data-stu-id="54e5c-121"> [Addresses](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md).</span></span> <span data-ttu-id="54e5c-122">Tal y como se indica en la introducción, el [ \<encabezados >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) y [ \<identidad >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) elementos forman parte de la <xref:System.ServiceModel.EndpointAddress> y también se describen en la [ Direcciones](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md) tema.</span><span class="sxs-lookup"><span data-stu-id="54e5c-122">As the introduction indicates, the [\<headers>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) and [\<identity>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) elements are part of the <xref:System.ServiceModel.EndpointAddress> and are also discussed in the [Addresses](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md) topic.</span></span>  
  
 <span data-ttu-id="54e5c-123">El atributo `binding` indica el tipo de enlace que el extremo espera utilizar al conectarse a un servicio.</span><span class="sxs-lookup"><span data-stu-id="54e5c-123">The `binding` attribute indicates the type of binding the endpoint expects to use when connecting to a service.</span></span> <span data-ttu-id="54e5c-124">El tipo debe tener una sección de configuración registrada si se le va a hacer referencia.</span><span class="sxs-lookup"><span data-stu-id="54e5c-124">The type must have a registered configuration section if it is to be referenced.</span></span> <span data-ttu-id="54e5c-125">En el ejemplo anterior, se trata de la [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) sección, que indica que el punto de conexión usa un <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="54e5c-125">In the previous example, this is the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) section, which indicates that the endpoint uses a <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="54e5c-126">Pero puede que haya más de un enlace de un tipo determinado que el punto de conexión puede utilizar.</span><span class="sxs-lookup"><span data-stu-id="54e5c-126">But there may be more than one binding of a given type that the endpoint can use.</span></span> <span data-ttu-id="54e5c-127">Cada uno de ellos tiene su propio [ \<enlace >](../../../../docs/framework/misc/binding.md) dentro del elemento de tipo (enlace).</span><span class="sxs-lookup"><span data-stu-id="54e5c-127">Each of these has its own [\<binding>](../../../../docs/framework/misc/binding.md) element within the (binding) type element.</span></span> <span data-ttu-id="54e5c-128">El atributo `bindingconfiguration` se utiliza para distinguir entre enlaces del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="54e5c-128">The `bindingconfiguration` attribute is used to distinguish between bindings of the same type.</span></span> <span data-ttu-id="54e5c-129">Su valor coincide con el `name` atributo de la [ \<enlace >](../../../../docs/framework/misc/binding.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="54e5c-129">Its value is matched with the `name` attribute of the [\<binding>](../../../../docs/framework/misc/binding.md) element.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="54e5c-130">Cómo configurar un cliente de enlace con la configuración, consulte [Cómo: especificar un enlace de cliente en configuración](../../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="54e5c-130"> how to configure a client binding using configuration, see [How to: Specify a Client Binding in Configuration](../../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md).</span></span>  
  
 <span data-ttu-id="54e5c-131">El `behaviorConfiguration` atributo se usa para especificar qué [ \<comportamiento >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) de la [ \<endpointBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) debe utilizar el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="54e5c-131">The `behaviorConfiguration` attribute is used to specify which [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) of the [\<endpointBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) the endpoint should use.</span></span> <span data-ttu-id="54e5c-132">Su valor coincide con el `name` atributo de la [ \<comportamiento >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="54e5c-132">Its value is matched with the `name` attribute of the [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element.</span></span> <span data-ttu-id="54e5c-133">Para obtener un ejemplo de usar la configuración para especificar los comportamientos del cliente, consulte [configurar comportamientos del cliente](../../../../docs/framework/wcf/configuring-client-behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="54e5c-133">For an example of using configuration to specify client behaviors, see [Configuring Client Behaviors](../../../../docs/framework/wcf/configuring-client-behaviors.md).</span></span>  
  
 <span data-ttu-id="54e5c-134">El atributo `contract` especifica qué contrato expone este extremo.</span><span class="sxs-lookup"><span data-stu-id="54e5c-134">The `contract` attribute specifies which contract the endpoint is exposing.</span></span> <span data-ttu-id="54e5c-135">Este valor se asigna al <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> del <xref:System.ServiceModel.ServiceContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="54e5c-135">This value maps to the <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> of the <xref:System.ServiceModel.ServiceContractAttribute>.</span></span> <span data-ttu-id="54e5c-136">El valor predeterminado es el nombre de tipo completo de la clase que implementa el servicio.</span><span class="sxs-lookup"><span data-stu-id="54e5c-136">The default value is the full type name of the class that implements the service.</span></span>  
  
### <a name="configuring-metadata"></a><span data-ttu-id="54e5c-137">Configuración de metadatos</span><span class="sxs-lookup"><span data-stu-id="54e5c-137">Configuring Metadata</span></span>  
 <span data-ttu-id="54e5c-138">El [ \<metadatos >](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) elemento se utiliza para especificar la configuración que se usa para registrar metadatos de las extensiones de importación.</span><span class="sxs-lookup"><span data-stu-id="54e5c-138">The [\<metadata>](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) element is used to specify settings used to register metadata import extensions.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="54e5c-139">extender el sistema de metadatos, vea[extender el sistema de metadatos](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md).</span><span class="sxs-lookup"><span data-stu-id="54e5c-139"> extending the metadata system, see[Extending the Metadata System](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54e5c-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="54e5c-140">See Also</span></span>  
 [<span data-ttu-id="54e5c-141">Los puntos de conexión: Direcciones, enlaces y contratos</span><span class="sxs-lookup"><span data-stu-id="54e5c-141">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)  
 [<span data-ttu-id="54e5c-142">Configuración de los comportamientos del cliente</span><span class="sxs-lookup"><span data-stu-id="54e5c-142">Configuring Client Behaviors</span></span>](../../../../docs/framework/wcf/configuring-client-behaviors.md)
