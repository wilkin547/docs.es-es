---
title: <endpointDiscovery>
ms.date: 03/30/2017
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
ms.openlocfilehash: 98b1655f42b7b43604ed4ab9d66870ec204a9590
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398018"
---
# <a name="endpointdiscovery"></a><span data-ttu-id="79650-101">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="79650-101">\<endpointDiscovery></span></span>
<span data-ttu-id="79650-102">Especifica las distintas configuraciones de detección para un punto de conexión, como su detectabilidad, ámbitos y cualquier extensión personalizada a sus metadatos.</span><span class="sxs-lookup"><span data-stu-id="79650-102">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>  
  
<span data-ttu-id="79650-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="79650-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="79650-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="79650-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="79650-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="79650-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="79650-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="79650-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="79650-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="79650-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="79650-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> endpointDiscovery**</span><span class="sxs-lookup"><span data-stu-id="79650-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpointDiscovery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79650-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="79650-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="79650-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="79650-110">Attributes and Elements</span></span>  
 <span data-ttu-id="79650-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="79650-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="79650-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="79650-112">Attributes</span></span>  
  
|<span data-ttu-id="79650-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="79650-113">Attribute</span></span>|<span data-ttu-id="79650-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="79650-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="79650-115">enabled</span><span class="sxs-lookup"><span data-stu-id="79650-115">enabled</span></span>|<span data-ttu-id="79650-116">Valor booleano que especifica si la detectabilidad está habilitada en este extremo.</span><span class="sxs-lookup"><span data-stu-id="79650-116">A Boolean value that specifies whether discoverability is enabled on this endpoint.</span></span> <span data-ttu-id="79650-117">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="79650-117">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="79650-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="79650-118">Child Elements</span></span>  
  
|<span data-ttu-id="79650-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="79650-119">Element</span></span>|<span data-ttu-id="79650-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="79650-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="79650-121">\<scopes></span><span class="sxs-lookup"><span data-stu-id="79650-121">\<scopes></span></span>](scopes.md)|<span data-ttu-id="79650-122">Colección de URI de ámbito para el extremo.</span><span class="sxs-lookup"><span data-stu-id="79650-122">A collection of scope URIs for the endpoint.</span></span> <span data-ttu-id="79650-123">Se puede asociar más de un URI de ámbito a un único punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="79650-123">More than one scope Uris can be associated with a single endpoint.</span></span>|  
|<span data-ttu-id="79650-124">Extensiones > [de \<endpointDiscovery >] [ \<](extensions.md)</span><span class="sxs-lookup"><span data-stu-id="79650-124">[\<extensions>](extensions.md) [of \<endpointDiscovery>]</span></span>|<span data-ttu-id="79650-125">Colección de elementos XML que le permite especificar metadatos personalizados que se van a publicar para un extremo.</span><span class="sxs-lookup"><span data-stu-id="79650-125">A collection of XML elements that allows you to specify custom metadata to be published for an endpoint.</span></span>|  
|<span data-ttu-id="79650-126">\<tipos ></span><span class="sxs-lookup"><span data-stu-id="79650-126">\<types></span></span>|<span data-ttu-id="79650-127">Una colección de interfaces para buscar.</span><span class="sxs-lookup"><span data-stu-id="79650-127">A collection of interfaces to search for.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="79650-128">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="79650-128">Parent Elements</span></span>  
  
|<span data-ttu-id="79650-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="79650-129">Element</span></span>|<span data-ttu-id="79650-130">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="79650-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="79650-131">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="79650-131">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="79650-132">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="79650-132">Specifies a behavior element.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="79650-133">Comentarios</span><span class="sxs-lookup"><span data-stu-id="79650-133">Remarks</span></span>  
 <span data-ttu-id="79650-134">Cuando se agrega a la configuración de comportamiento del punto de conexión y con el atributo `enabled` establecido en `true`, este elemento de configuración habilita su detectabilidad.</span><span class="sxs-lookup"><span data-stu-id="79650-134">When added to the endpoint’s behavior configuration and with the `enabled` attribute set to `true`, this configuration element enables its discoverability.</span></span> <span data-ttu-id="79650-135">Además, puede utilizar los [ \<ámbitos >](scopes.md)elemento secundario para especificar los URI de ámbito personalizado que se pueden usar para filtrar los extremos de servicio durante la consulta, así como las [ \<extensiones >](extensions.md) elemento secundario para especificar el personalizado. metadatos que se deben publicar junto con los metadatos detectables estándar (EPR, ContractTypeName, BindingName, Scope y ListenURI).</span><span class="sxs-lookup"><span data-stu-id="79650-135">In addition, you can use the [\<scopes>](scopes.md)child element to specifying custom scope Uris that can be used to filter service endpoints during query, as well as the [\<extensions>](extensions.md) child element to specify custom metadata that should be published along with the standard discoverable metadata (EPR, ContractTypeName, BindingName, Scope and ListenURI).</span></span>  
  
 <span data-ttu-id="79650-136">Este elemento de configuración depende [ \<del elemento > serviceDiscovery](servicediscovery.md) que proporciona el control de nivel de servicio de detectabilidad.</span><span class="sxs-lookup"><span data-stu-id="79650-136">This configuration element is dependent on the [\<serviceDiscovery>](servicediscovery.md) element that provides the service level control of discoverability.</span></span> <span data-ttu-id="79650-137">Esto significa que la configuración de este elemento se omite si [ \<serviceDiscovery >](servicediscovery.md) no está presente en la configuración.</span><span class="sxs-lookup"><span data-stu-id="79650-137">This means that this element’s settings are ignored if [\<serviceDiscovery>](servicediscovery.md) is not present in the configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79650-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="79650-138">Example</span></span>  
 <span data-ttu-id="79650-139">El siguiente ejemplo de configuración especifica los ámbitos del filtrado y metadatos de la extensión que se van a publicar para un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="79650-139">The following configuration example specifies filtering scopes and extension metadata to be published for an endpoint.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="79650-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="79650-140">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
