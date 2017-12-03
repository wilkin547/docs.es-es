---
title: '&lt;endpointDiscovery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6cca48cec486cfdbb9bca2eba48847c25c35abe9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltendpointdiscoverygt"></a><span data-ttu-id="13bd3-102">&lt;endpointDiscovery&gt;</span><span class="sxs-lookup"><span data-stu-id="13bd3-102">&lt;endpointDiscovery&gt;</span></span>
<span data-ttu-id="13bd3-103">Especifica las distintas configuraciones de detección para un punto de conexión, como su detectabilidad, ámbitos y cualquier extensión personalizada a sus metadatos.</span><span class="sxs-lookup"><span data-stu-id="13bd3-103">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>  
  
<span data-ttu-id="13bd3-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="13bd3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="13bd3-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="13bd3-105">\<behaviors></span></span>  
<span data-ttu-id="13bd3-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="13bd3-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="13bd3-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="13bd3-107">\<behavior></span></span>  
<span data-ttu-id="13bd3-108">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="13bd3-108">\<endpointDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13bd3-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="13bd3-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="13bd3-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="13bd3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="13bd3-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="13bd3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="13bd3-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="13bd3-112">Attributes</span></span>  
  
|<span data-ttu-id="13bd3-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="13bd3-113">Attribute</span></span>|<span data-ttu-id="13bd3-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="13bd3-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="13bd3-115">enabled</span><span class="sxs-lookup"><span data-stu-id="13bd3-115">enabled</span></span>|<span data-ttu-id="13bd3-116">Valor booleano que especifica si la detectabilidad está habilitada en este extremo.</span><span class="sxs-lookup"><span data-stu-id="13bd3-116">A Boolean value that that specifies whether discoverability is enabled on this endpoint.</span></span> <span data-ttu-id="13bd3-117">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="13bd3-117">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="13bd3-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="13bd3-118">Child Elements</span></span>  
  
|<span data-ttu-id="13bd3-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="13bd3-119">Element</span></span>|<span data-ttu-id="13bd3-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="13bd3-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="13bd3-121">\<ámbitos ></span><span class="sxs-lookup"><span data-stu-id="13bd3-121">\<scopes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|<span data-ttu-id="13bd3-122">Colección de URI de ámbito para el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="13bd3-122">A collection of scope URIs for the endpoint.</span></span> <span data-ttu-id="13bd3-123">Se puede asociar más de un URI de ámbito a un único punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="13bd3-123">More than one scope Uris can be associated with a single endpoint.</span></span>|  
|<span data-ttu-id="13bd3-124">[\<las extensiones >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) [de \<endpointDiscovery >]</span><span class="sxs-lookup"><span data-stu-id="13bd3-124">[\<extensions>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) [of \<endpointDiscovery>]</span></span>|<span data-ttu-id="13bd3-125">Colección de elementos XML que le permite especificar metadatos personalizados que se van a publicar para un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="13bd3-125">A collection of XML elements that allows you to specify custom metadata to be published for an endpoint.</span></span>|  
|<span data-ttu-id="13bd3-126">\<tipos ></span><span class="sxs-lookup"><span data-stu-id="13bd3-126">\<types></span></span>|<span data-ttu-id="13bd3-127">Una colección de interfaces para buscar.</span><span class="sxs-lookup"><span data-stu-id="13bd3-127">A collection of interfaces to search for.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="13bd3-128">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="13bd3-128">Parent Elements</span></span>  
  
|<span data-ttu-id="13bd3-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="13bd3-129">Element</span></span>|<span data-ttu-id="13bd3-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="13bd3-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="13bd3-131">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="13bd3-131">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="13bd3-132">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="13bd3-132">Specifies a behavior element.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="13bd3-133">Comentarios</span><span class="sxs-lookup"><span data-stu-id="13bd3-133">Remarks</span></span>  
 <span data-ttu-id="13bd3-134">Cuando se agrega a la configuración de comportamiento del extremo y con el atributo `enabled` establecido en `true`, este elemento de configuración habilita su detectabilidad.</span><span class="sxs-lookup"><span data-stu-id="13bd3-134">When added to the endpoint’s behavior configuration and with the `enabled` attribute set to `true`, this configuration element enables its discoverability.</span></span> <span data-ttu-id="13bd3-135">Además, puede usar el [ \<ámbitos >](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)elemento secundario para especificar el URI que pueden usarse para filtrar los puntos de conexión de servicio durante la consulta, del ámbito personalizado así como el [ \<extensiones >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) elemento secundario al especificar metadatos personalizados que deben publicarse junto con los metadatos detectables estándar (EPR, ContractTypeName, BindingName, ámbito y ListenURI).</span><span class="sxs-lookup"><span data-stu-id="13bd3-135">In addition, you can use the [\<scopes>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)child element to specifying custom scope Uris that can be used to filter service endpoints during query, as well as the [\<extensions>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) child element to specify custom metadata that should be published along with the standard discoverable metadata (EPR, ContractTypeName, BindingName, Scope and ListenURI).</span></span>  
  
 <span data-ttu-id="13bd3-136">Este elemento de configuración es dependiente de la [ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) elemento que proporciona el control de nivel de servicio de detectabilidad.</span><span class="sxs-lookup"><span data-stu-id="13bd3-136">This configuration element is dependent on the [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) element that provides the service level control of discoverability.</span></span> <span data-ttu-id="13bd3-137">Esto significa que la configuración de este elemento se omite si [ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) no está presente en la configuración.</span><span class="sxs-lookup"><span data-stu-id="13bd3-137">This means that this element’s settings are ignored if [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) is not present in the configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13bd3-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="13bd3-138">Example</span></span>  
 <span data-ttu-id="13bd3-139">El siguiente ejemplo de configuración especifica los ámbitos del filtrado y metadatos de la extensión que se van a publicar para un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="13bd3-139">The following configuration example specifies filtering scopes and extension metadata to be published for an endpoint.</span></span>  
  
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
          <add scope="http://contoso/test1"/>  
          <add scope="http://contoso/test2"/>  
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
  
## <a name="see-also"></a><span data-ttu-id="13bd3-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="13bd3-140">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
