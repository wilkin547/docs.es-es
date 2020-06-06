---
title: <endpointDiscovery>
ms.date: 03/30/2017
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
ms.openlocfilehash: 98b1655f42b7b43604ed4ab9d66870ec204a9590
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398018"
---
# \<endpointDiscovery>
<span data-ttu-id="83e13-101">Especifica las distintas configuraciones de detección para un punto de conexión, como su detectabilidad, ámbitos y cualquier extensión personalizada a sus metadatos.</span><span class="sxs-lookup"><span data-stu-id="83e13-101">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpointDiscovery>**  
  
## <a name="syntax"></a><span data-ttu-id="83e13-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="83e13-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enabled="Boolean">
        <scopes>
          <add scope="URI"/>
        </scopes>
        <extensions />
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="83e13-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="83e13-103">Attributes and Elements</span></span>  
 <span data-ttu-id="83e13-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="83e13-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="83e13-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="83e13-105">Attributes</span></span>  
  
|<span data-ttu-id="83e13-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="83e13-106">Attribute</span></span>|<span data-ttu-id="83e13-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="83e13-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="83e13-108">enabled</span><span class="sxs-lookup"><span data-stu-id="83e13-108">enabled</span></span>|<span data-ttu-id="83e13-109">Valor booleano que especifica si la detectabilidad está habilitada en este extremo.</span><span class="sxs-lookup"><span data-stu-id="83e13-109">A Boolean value that specifies whether discoverability is enabled on this endpoint.</span></span> <span data-ttu-id="83e13-110">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="83e13-110">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="83e13-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="83e13-111">Child Elements</span></span>  
  
|<span data-ttu-id="83e13-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="83e13-112">Element</span></span>|<span data-ttu-id="83e13-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="83e13-113">Description</span></span>|  
|-------------|-----------------|  
|[\<scopes>](scopes.md)|<span data-ttu-id="83e13-114">Colección de URI de ámbito para el extremo.</span><span class="sxs-lookup"><span data-stu-id="83e13-114">A collection of scope URIs for the endpoint.</span></span> <span data-ttu-id="83e13-115">Se puede asociar más de un URI de ámbito a un único punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="83e13-115">More than one scope Uris can be associated with a single endpoint.</span></span>|  
|<span data-ttu-id="83e13-116">[\<extensions>](extensions.md)[de \<endpointDiscovery> ]</span><span class="sxs-lookup"><span data-stu-id="83e13-116">[\<extensions>](extensions.md) [of \<endpointDiscovery>]</span></span>|<span data-ttu-id="83e13-117">Colección de elementos XML que le permite especificar metadatos personalizados que se van a publicar para un extremo.</span><span class="sxs-lookup"><span data-stu-id="83e13-117">A collection of XML elements that allows you to specify custom metadata to be published for an endpoint.</span></span>|  
|\<types>|<span data-ttu-id="83e13-118">Una colección de interfaces para buscar.</span><span class="sxs-lookup"><span data-stu-id="83e13-118">A collection of interfaces to search for.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="83e13-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="83e13-119">Parent Elements</span></span>  
  
|<span data-ttu-id="83e13-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="83e13-120">Element</span></span>|<span data-ttu-id="83e13-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="83e13-121">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="83e13-122">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="83e13-122">Specifies a behavior element.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="83e13-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="83e13-123">Remarks</span></span>  
 <span data-ttu-id="83e13-124">Cuando se agrega a la configuración de comportamiento del punto de conexión y con el atributo `enabled` establecido en `true`, este elemento de configuración habilita su detectabilidad.</span><span class="sxs-lookup"><span data-stu-id="83e13-124">When added to the endpoint’s behavior configuration and with the `enabled` attribute set to `true`, this configuration element enables its discoverability.</span></span> <span data-ttu-id="83e13-125">Además, puede usar el [\<scopes>](scopes.md) elemento secundario para especificar los URI de ámbito personalizado que se pueden usar para filtrar los extremos de servicio durante la consulta, así como el [\<extensions>](extensions.md) elemento secundario para especificar los metadatos personalizados que se deben publicar junto con los metadatos detectables estándar (EPR, ContractTypeName, BindingName, Scope y ListenURI).</span><span class="sxs-lookup"><span data-stu-id="83e13-125">In addition, you can use the [\<scopes>](scopes.md)child element to specifying custom scope Uris that can be used to filter service endpoints during query, as well as the [\<extensions>](extensions.md) child element to specify custom metadata that should be published along with the standard discoverable metadata (EPR, ContractTypeName, BindingName, Scope and ListenURI).</span></span>  
  
 <span data-ttu-id="83e13-126">Este elemento de configuración depende del [\<serviceDiscovery>](servicediscovery.md) elemento que proporciona el control de nivel de servicio de detectabilidad.</span><span class="sxs-lookup"><span data-stu-id="83e13-126">This configuration element is dependent on the [\<serviceDiscovery>](servicediscovery.md) element that provides the service level control of discoverability.</span></span> <span data-ttu-id="83e13-127">Esto significa que la configuración de este elemento se omite si [\<serviceDiscovery>](servicediscovery.md) no está presente en la configuración.</span><span class="sxs-lookup"><span data-stu-id="83e13-127">This means that this element’s settings are ignored if [\<serviceDiscovery>](servicediscovery.md) is not present in the configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83e13-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="83e13-128">Example</span></span>  
 <span data-ttu-id="83e13-129">El siguiente ejemplo de configuración especifica los ámbitos del filtrado y metadatos de la extensión que se van a publicar para un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="83e13-129">The following configuration example specifies filtering scopes and extension metadata to be published for an endpoint.</span></span>  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <endpoint binding="basicHttpBinding"
              address="calculator"
              contract="ICalculatorService"
              behaviorConfiguration="calculatorEndpointBehavior" />
  </service>
</services>
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <serviceDiscovery />
    </behavior>
  </serviceBehaviors>
  <endpointBehaviors>
    <behavior name="calculatorEndpointBehavior">
      <endpointDiscovery enabled="true">
        <scopes>
          <add scope="http://contoso/test1" />
          <add scope="http://contoso/test2" />
        </scopes>
        <extensions>
          <e:Publisher xmlns:e="http://example.org">
            <e:Name>The Example Organization</e:Name>
            <e:Address>One Example Way, ExampleTown, EX 12345</e:Address>
            <e:Contact>support@example.org</e:Contact>
          </e:Publisher>
          <AnotherCustomMetadata>Custom Metadata</AnotherCustomMetadata>
        </extensions>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="83e13-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="83e13-130">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
