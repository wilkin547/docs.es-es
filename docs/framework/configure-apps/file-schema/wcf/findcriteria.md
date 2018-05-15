---
title: '&lt;findCriteria&gt;'
ms.date: 03/30/2017
ms.assetid: 5454cd19-6bf5-4ba8-94d1-f58d10dc1917
ms.openlocfilehash: fc9cd3b87d0f47ae0f16b5c5bfcaa4a1167bae9f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltfindcriteriagt"></a><span data-ttu-id="e74a0-102">&lt;findCriteria&gt;</span><span class="sxs-lookup"><span data-stu-id="e74a0-102">&lt;findCriteria&gt;</span></span>
<span data-ttu-id="e74a0-103">Elemento de configuración que proporciona un conjunto de criterios utilizado por una aplicación cliente para buscar un servicio de detección.</span><span class="sxs-lookup"><span data-stu-id="e74a0-103">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="e74a0-104">Criterios pueden agruparse en criterios de búsqueda (que especifican qué servicios está buscando) y encuentra criterios de finalización (cuánto tiempo debe durar la búsqueda).</span><span class="sxs-lookup"><span data-stu-id="e74a0-104">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>  
  
 <span data-ttu-id="e74a0-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e74a0-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="e74a0-106">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="e74a0-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e74a0-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e74a0-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
        <discoveryClientSettings discoveryEndpoint="String">
          <findCriteria duration="TimeSpan" maxResults="Integer" scopeMatchBy="Uri">
            <contractTypeNames>
              <add name="String" namespace="String" />
            <contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI" />
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      </standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e74a0-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e74a0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e74a0-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e74a0-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e74a0-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="e74a0-110">Attributes</span></span>  
  
|<span data-ttu-id="e74a0-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="e74a0-111">Attribute</span></span>|<span data-ttu-id="e74a0-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="e74a0-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e74a0-113">duration</span><span class="sxs-lookup"><span data-stu-id="e74a0-113">duration</span></span>|<span data-ttu-id="e74a0-114">Un valor Timespan que especifica el tiempo máximo para esperar respuestas de los servicios en la red.</span><span class="sxs-lookup"><span data-stu-id="e74a0-114">A Timespan value that specifies the maximum time to wait for replies from services on the network.</span></span> <span data-ttu-id="e74a0-115">La duración predeterminada es de 20 segundos.</span><span class="sxs-lookup"><span data-stu-id="e74a0-115">The default duration is 20 seconds..</span></span>|  
|<span data-ttu-id="e74a0-116">maxResults</span><span class="sxs-lookup"><span data-stu-id="e74a0-116">maxResults</span></span>|<span data-ttu-id="e74a0-117">Entero que especifica el número máximo de respuestas que se deben esperar, de los servicios en una red o de Internet.</span><span class="sxs-lookup"><span data-stu-id="e74a0-117">An integer that specifies the maximum number of replies to wait for, from services on a network or the Internet.</span></span> <span data-ttu-id="e74a0-118">Si se recibe el máximo de respuestas antes de que haya transcurrido el valor especificado en el atributo `duration`, finalizará la operación de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e74a0-118">If maximum replies are received before the value specified in the `duration` attribute has elapsed, the find operation ends.</span></span>|  
|<span data-ttu-id="e74a0-119">scopeMatchBy</span><span class="sxs-lookup"><span data-stu-id="e74a0-119">scopeMatchBy</span></span>|<span data-ttu-id="e74a0-120">URI que especifica el algoritmo de coincidencia que se va a utilizar al establecer las coincidencias de los ámbitos del mensaje de sondeo con los del extremo.</span><span class="sxs-lookup"><span data-stu-id="e74a0-120">A URI that specify the matching algorithm to use while matching the scopes in the Probe message with that of the endpoint.</span></span><br /><br /> <span data-ttu-id="e74a0-121">Hay cinco reglas de coincidencia de ámbito admitidas.</span><span class="sxs-lookup"><span data-stu-id="e74a0-121">There are five supported scope-matching rules.</span></span> <span data-ttu-id="e74a0-122">Si no especifica ninguna regla de coincidencia de ámbito, se usa `ScopeMatchByPrefix`.</span><span class="sxs-lookup"><span data-stu-id="e74a0-122">If you do not specify a scope-matching rule, `ScopeMatchByPrefix` is used.</span></span> <span data-ttu-id="e74a0-123">Para obtener más información sobre este tema vea <xref:System.ServiceModel.Discovery.FindCriteria>.</span><span class="sxs-lookup"><span data-stu-id="e74a0-123">For more information on this, see <xref:System.ServiceModel.Discovery.FindCriteria>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e74a0-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e74a0-124">Child Elements</span></span>  
  
|<span data-ttu-id="e74a0-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="e74a0-125">Element</span></span>|<span data-ttu-id="e74a0-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="e74a0-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e74a0-127">\<contractTypeNames ></span><span class="sxs-lookup"><span data-stu-id="e74a0-127">\<contractTypeNames></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|<span data-ttu-id="e74a0-128">Colección de elementos de configuración que contiene los nombres de tipos de contrato de servicios de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e74a0-128">A collection of configuration elements that contain the names of workflow service contract types..</span></span>|  
|<span data-ttu-id="e74a0-129">\<las extensiones > de \<findCriteria ></span><span class="sxs-lookup"><span data-stu-id="e74a0-129">\<extensions> of \<findCriteria></span></span>|<span data-ttu-id="e74a0-130">Colección de objetos de elementos XML que proporcionan las extensiones.</span><span class="sxs-lookup"><span data-stu-id="e74a0-130">A collection of XML element objects that provide extensions.</span></span>|  
|[<span data-ttu-id="e74a0-131">\<ámbitos ></span><span class="sxs-lookup"><span data-stu-id="e74a0-131">\<scopes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|<span data-ttu-id="e74a0-132">Colección de objetos que contienen URI absolutos que se usan durante una operación de búsqueda para localizar un servicio o servicios concretos.</span><span class="sxs-lookup"><span data-stu-id="e74a0-132">A collection of objects that contain absolute URIs that are used during a find operation to locate a specific service or services.</span></span><br /><br /> <span data-ttu-id="e74a0-133">Si se encuentra el servicio concreto, se ha establecido una coincidencia correcta entre el URI del servicio y el URI del ámbito, en ocasiones con la ayuda de las reglas de ámbito que se ocupan de las complicaciones relativas a las coincidencias.</span><span class="sxs-lookup"><span data-stu-id="e74a0-133">If the specific service is found, a successful match has been made between the service URI and the Scope URI, sometimes with the help of scope rules that handle complications of matching.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e74a0-134">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e74a0-134">Parent Elements</span></span>  
  
|<span data-ttu-id="e74a0-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="e74a0-135">Element</span></span>|<span data-ttu-id="e74a0-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="e74a0-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e74a0-137">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="e74a0-137">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="e74a0-138">Contiene la configuración que necesita una aplicación para participar en el proceso de detección del servicio como un cliente.</span><span class="sxs-lookup"><span data-stu-id="e74a0-138">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e74a0-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="e74a0-139">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.FindCriteria>  
 <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
