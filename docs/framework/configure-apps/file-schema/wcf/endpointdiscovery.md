---
title: <endpointDiscovery>
ms.date: 03/30/2017
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
ms.openlocfilehash: effceee30abdaa1725b8c8718df22632961871e8
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266421"
---
# <a name="endpointdiscovery"></a><span data-ttu-id="5ebe4-101">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="5ebe4-101">\<endpointDiscovery></span></span>
<span data-ttu-id="5ebe4-102">Especifica las distintas configuraciones de detección para un punto de conexión, como su detectabilidad, ámbitos y cualquier extensión personalizada a sus metadatos.</span><span class="sxs-lookup"><span data-stu-id="5ebe4-102">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>  
  
<span data-ttu-id="5ebe4-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5ebe4-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="5ebe4-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="5ebe4-104">\<behaviors></span></span>  
<span data-ttu-id="5ebe4-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="5ebe4-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="5ebe4-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="5ebe4-106">\<behavior></span></span>  
<span data-ttu-id="5ebe4-107">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="5ebe4-107">\<endpointDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ebe4-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5ebe4-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5ebe4-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5ebe4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="5ebe4-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5ebe4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5ebe4-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="5ebe4-111">Attributes</span></span>  
  
|<span data-ttu-id="5ebe4-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="5ebe4-112">Attribute</span></span>|<span data-ttu-id="5ebe4-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="5ebe4-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5ebe4-114">enabled</span><span class="sxs-lookup"><span data-stu-id="5ebe4-114">enabled</span></span>|<span data-ttu-id="5ebe4-115">Un valor booleano que especifica si la detectabilidad está habilitada en este punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="5ebe4-115">A Boolean value that specifies whether discoverability is enabled on this endpoint.</span></span> <span data-ttu-id="5ebe4-116">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="5ebe4-116">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5ebe4-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5ebe4-117">Child Elements</span></span>  
  
|<span data-ttu-id="5ebe4-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="5ebe4-118">Element</span></span>|<span data-ttu-id="5ebe4-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="5ebe4-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5ebe4-120">\<scopes></span><span class="sxs-lookup"><span data-stu-id="5ebe4-120">\<scopes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|<span data-ttu-id="5ebe4-121">Colección de URI de ámbito para el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="5ebe4-121">A collection of scope URIs for the endpoint.</span></span> <span data-ttu-id="5ebe4-122">Se puede asociar más de un URI de ámbito a un único punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="5ebe4-122">More than one scope Uris can be associated with a single endpoint.</span></span>|  
|<span data-ttu-id="5ebe4-123">[\<Extensiones >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) [de \<endpointDiscovery >]</span><span class="sxs-lookup"><span data-stu-id="5ebe4-123">[\<extensions>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) [of \<endpointDiscovery>]</span></span>|<span data-ttu-id="5ebe4-124">Colección de elementos XML que le permite especificar metadatos personalizados que se van a publicar para un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="5ebe4-124">A collection of XML elements that allows you to specify custom metadata to be published for an endpoint.</span></span>|  
|<span data-ttu-id="5ebe4-125">\<types></span><span class="sxs-lookup"><span data-stu-id="5ebe4-125">\<types></span></span>|<span data-ttu-id="5ebe4-126">Una colección de interfaces para buscar.</span><span class="sxs-lookup"><span data-stu-id="5ebe4-126">A collection of interfaces to search for.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5ebe4-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5ebe4-127">Parent Elements</span></span>  
  
|<span data-ttu-id="5ebe4-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="5ebe4-128">Element</span></span>|<span data-ttu-id="5ebe4-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="5ebe4-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5ebe4-130">\<behavior></span><span class="sxs-lookup"><span data-stu-id="5ebe4-130">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="5ebe4-131">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="5ebe4-131">Specifies a behavior element.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="5ebe4-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5ebe4-132">Remarks</span></span>  
 <span data-ttu-id="5ebe4-133">Cuando se agrega a la configuración de comportamiento del punto de conexión y con el atributo `enabled` establecido en `true`, este elemento de configuración habilita su detectabilidad.</span><span class="sxs-lookup"><span data-stu-id="5ebe4-133">When added to the endpoint’s behavior configuration and with the `enabled` attribute set to `true`, this configuration element enables its discoverability.</span></span> <span data-ttu-id="5ebe4-134">Además, puede usar el [ \<ámbitos >](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)elemento secundario que se va a especificar los identificadores URI que se pueden usar para filtrar los puntos de conexión de servicio durante la consulta, de ámbito personalizada, así como la [ \<extensiones >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) elemento secundario que se va a especificar metadatos personalizados que se deberían publicar junto con los metadatos detectables estándar (EPR, ContractTypeName, BindingName, ámbito y ListenURI).</span><span class="sxs-lookup"><span data-stu-id="5ebe4-134">In addition, you can use the [\<scopes>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)child element to specifying custom scope Uris that can be used to filter service endpoints during query, as well as the [\<extensions>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) child element to specify custom metadata that should be published along with the standard discoverable metadata (EPR, ContractTypeName, BindingName, Scope and ListenURI).</span></span>  
  
 <span data-ttu-id="5ebe4-135">Este elemento de configuración es dependiente de la [ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) elemento que proporciona el control de nivel de servicio de detectabilidad.</span><span class="sxs-lookup"><span data-stu-id="5ebe4-135">This configuration element is dependent on the [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) element that provides the service level control of discoverability.</span></span> <span data-ttu-id="5ebe4-136">Esto significa que la configuración de este elemento se omite si [ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) no está presente en la configuración.</span><span class="sxs-lookup"><span data-stu-id="5ebe4-136">This means that this element’s settings are ignored if [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) is not present in the configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ebe4-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5ebe4-137">Example</span></span>  
 <span data-ttu-id="5ebe4-138">El siguiente ejemplo de configuración especifica los ámbitos del filtrado y metadatos de la extensión que se van a publicar para un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="5ebe4-138">The following configuration example specifies filtering scopes and extension metadata to be published for an endpoint.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5ebe4-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ebe4-139">See also</span></span>
- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
