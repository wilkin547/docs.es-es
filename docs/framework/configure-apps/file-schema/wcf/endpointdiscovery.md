---
description: 'Más información acerca de: <endpointDiscovery>'
title: <endpointDiscovery>
ms.date: 03/30/2017
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
ms.openlocfilehash: 01913de37ae426484d5bb1ff6a815a64302024fb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782135"
---
# \<endpointDiscovery>

<span data-ttu-id="18e53-102">Especifica las distintas configuraciones de detección para un punto de conexión, como su detectabilidad, ámbitos y cualquier extensión personalizada a sus metadatos.</span><span class="sxs-lookup"><span data-stu-id="18e53-102">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpointDiscovery>**  
  
## <a name="syntax"></a><span data-ttu-id="18e53-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="18e53-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="18e53-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="18e53-104">Attributes and Elements</span></span>  

 <span data-ttu-id="18e53-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="18e53-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="18e53-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="18e53-106">Attributes</span></span>  
  
|<span data-ttu-id="18e53-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="18e53-107">Attribute</span></span>|<span data-ttu-id="18e53-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="18e53-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="18e53-109">enabled</span><span class="sxs-lookup"><span data-stu-id="18e53-109">enabled</span></span>|<span data-ttu-id="18e53-110">Valor booleano que especifica si la detectabilidad está habilitada en este extremo.</span><span class="sxs-lookup"><span data-stu-id="18e53-110">A Boolean value that specifies whether discoverability is enabled on this endpoint.</span></span> <span data-ttu-id="18e53-111">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="18e53-111">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="18e53-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="18e53-112">Child Elements</span></span>  
  
|<span data-ttu-id="18e53-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="18e53-113">Element</span></span>|<span data-ttu-id="18e53-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="18e53-114">Description</span></span>|  
|-------------|-----------------|  
|[\<scopes>](scopes.md)|<span data-ttu-id="18e53-115">Colección de URI de ámbito para el extremo.</span><span class="sxs-lookup"><span data-stu-id="18e53-115">A collection of scope URIs for the endpoint.</span></span> <span data-ttu-id="18e53-116">Se puede asociar más de un URI de ámbito a un único punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="18e53-116">More than one scope Uris can be associated with a single endpoint.</span></span>|  
|<span data-ttu-id="18e53-117">[\<extensions>](extensions.md) [de \<endpointDiscovery> ]</span><span class="sxs-lookup"><span data-stu-id="18e53-117">[\<extensions>](extensions.md) [of \<endpointDiscovery>]</span></span>|<span data-ttu-id="18e53-118">Colección de elementos XML que le permite especificar metadatos personalizados que se van a publicar para un extremo.</span><span class="sxs-lookup"><span data-stu-id="18e53-118">A collection of XML elements that allows you to specify custom metadata to be published for an endpoint.</span></span>|  
|\<types>|<span data-ttu-id="18e53-119">Una colección de interfaces para buscar.</span><span class="sxs-lookup"><span data-stu-id="18e53-119">A collection of interfaces to search for.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="18e53-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="18e53-120">Parent Elements</span></span>  
  
|<span data-ttu-id="18e53-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="18e53-121">Element</span></span>|<span data-ttu-id="18e53-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="18e53-122">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="18e53-123">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="18e53-123">Specifies a behavior element.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="18e53-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="18e53-124">Remarks</span></span>  

 <span data-ttu-id="18e53-125">Cuando se agrega a la configuración de comportamiento del punto de conexión y con el atributo `enabled` establecido en `true`, este elemento de configuración habilita su detectabilidad.</span><span class="sxs-lookup"><span data-stu-id="18e53-125">When added to the endpoint’s behavior configuration and with the `enabled` attribute set to `true`, this configuration element enables its discoverability.</span></span> <span data-ttu-id="18e53-126">Además, puede usar el [\<scopes>](scopes.md) elemento secundario para especificar los URI de ámbito personalizado que se pueden usar para filtrar los extremos de servicio durante la consulta, así como el [\<extensions>](extensions.md) elemento secundario para especificar los metadatos personalizados que se deben publicar junto con los metadatos detectables estándar (EPR, ContractTypeName, BindingName, Scope y ListenURI).</span><span class="sxs-lookup"><span data-stu-id="18e53-126">In addition, you can use the [\<scopes>](scopes.md)child element to specifying custom scope Uris that can be used to filter service endpoints during query, as well as the [\<extensions>](extensions.md) child element to specify custom metadata that should be published along with the standard discoverable metadata (EPR, ContractTypeName, BindingName, Scope and ListenURI).</span></span>  
  
 <span data-ttu-id="18e53-127">Este elemento de configuración depende del [\<serviceDiscovery>](servicediscovery.md) elemento que proporciona el control de nivel de servicio de detectabilidad.</span><span class="sxs-lookup"><span data-stu-id="18e53-127">This configuration element is dependent on the [\<serviceDiscovery>](servicediscovery.md) element that provides the service level control of discoverability.</span></span> <span data-ttu-id="18e53-128">Esto significa que la configuración de este elemento se omite si [\<serviceDiscovery>](servicediscovery.md) no está presente en la configuración.</span><span class="sxs-lookup"><span data-stu-id="18e53-128">This means that this element’s settings are ignored if [\<serviceDiscovery>](servicediscovery.md) is not present in the configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18e53-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="18e53-129">Example</span></span>  

 <span data-ttu-id="18e53-130">El siguiente ejemplo de configuración especifica los ámbitos del filtrado y metadatos de la extensión que se van a publicar para un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="18e53-130">The following configuration example specifies filtering scopes and extension metadata to be published for an endpoint.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="18e53-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="18e53-131">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
