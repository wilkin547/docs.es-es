---
title: <findCriteria>
ms.date: 03/30/2017
ms.assetid: 5454cd19-6bf5-4ba8-94d1-f58d10dc1917
ms.openlocfilehash: 44e068ee205bc5e04382164e7ab00716b2c07dcf
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855165"
---
# <a name="findcriteria"></a><span data-ttu-id="2a709-101">\<findCriteria></span><span class="sxs-lookup"><span data-stu-id="2a709-101">\<findCriteria></span></span>
<span data-ttu-id="2a709-102">Elemento de configuración que proporciona un conjunto de criterios utilizado por una aplicación cliente para buscar un servicio de detección.</span><span class="sxs-lookup"><span data-stu-id="2a709-102">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="2a709-103">Los criterios se pueden agrupar en criterios de búsqueda (especificando qué servicios está buscando) y criterios de finalización de búsqueda (cuánto tiempo debe durar la búsqueda).</span><span class="sxs-lookup"><span data-stu-id="2a709-103">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>  
  
<span data-ttu-id="2a709-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2a709-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2a709-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2a709-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2a709-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> standardEndpoints**](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="2a709-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="2a709-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> dynamicEndpoint**](dynamicendpoint.md)</span><span class="sxs-lookup"><span data-stu-id="2a709-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)</span></span>\
<span data-ttu-id="2a709-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> standardEndpoint**</span><span class="sxs-lookup"><span data-stu-id="2a709-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**</span></span>\
<span data-ttu-id="2a709-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> discoveryClientSettings**](discoveryclientsettings.md)</span><span class="sxs-lookup"><span data-stu-id="2a709-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<discoveryClientSettings>**](discoveryclientsettings.md)</span></span>\
<span data-ttu-id="2a709-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> findCriteria**</span><span class="sxs-lookup"><span data-stu-id="2a709-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<findCriteria>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a709-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2a709-111">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
        <discoveryClientSettings discoveryEndpoint="String">
          <findCriteria duration="TimeSpan"
                        maxResults="Integer"
                        scopeMatchBy="Uri">
            <contractTypeNames>
              <add name="String"
                   namespace="String" />
            </contractTypeNames>
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2a709-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2a709-112">Attributes and Elements</span></span>  
 <span data-ttu-id="2a709-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2a709-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2a709-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="2a709-114">Attributes</span></span>  
  
|<span data-ttu-id="2a709-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="2a709-115">Attribute</span></span>|<span data-ttu-id="2a709-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2a709-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2a709-117">duration</span><span class="sxs-lookup"><span data-stu-id="2a709-117">duration</span></span>|<span data-ttu-id="2a709-118">Un valor Timespan que especifica el tiempo máximo para esperar respuestas de los servicios en la red.</span><span class="sxs-lookup"><span data-stu-id="2a709-118">A Timespan value that specifies the maximum time to wait for replies from services on the network.</span></span> <span data-ttu-id="2a709-119">La duración predeterminada es de 20 segundos.</span><span class="sxs-lookup"><span data-stu-id="2a709-119">The default duration is 20 seconds.</span></span>|  
|<span data-ttu-id="2a709-120">maxResults</span><span class="sxs-lookup"><span data-stu-id="2a709-120">maxResults</span></span>|<span data-ttu-id="2a709-121">Entero que especifica el número máximo de respuestas que se deben esperar, de los servicios en una red o de Internet.</span><span class="sxs-lookup"><span data-stu-id="2a709-121">An integer that specifies the maximum number of replies to wait for, from services on a network or the Internet.</span></span> <span data-ttu-id="2a709-122">Si se recibe el máximo de respuestas antes de que haya transcurrido el valor especificado en el atributo `duration`, finalizará la operación de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="2a709-122">If maximum replies are received before the value specified in the `duration` attribute has elapsed, the find operation ends.</span></span>|  
|<span data-ttu-id="2a709-123">scopeMatchBy</span><span class="sxs-lookup"><span data-stu-id="2a709-123">scopeMatchBy</span></span>|<span data-ttu-id="2a709-124">URI que especifica el algoritmo de coincidencia que se va a utilizar al establecer las coincidencias de los ámbitos del mensaje de sondeo con los del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="2a709-124">A URI that specify the matching algorithm to use while matching the scopes in the Probe message with that of the endpoint.</span></span><br /><br /> <span data-ttu-id="2a709-125">Hay cinco reglas de coincidencia de ámbito admitidas.</span><span class="sxs-lookup"><span data-stu-id="2a709-125">There are five supported scope-matching rules.</span></span> <span data-ttu-id="2a709-126">Si no especifica ninguna regla de coincidencia de ámbito, se usa `ScopeMatchByPrefix`.</span><span class="sxs-lookup"><span data-stu-id="2a709-126">If you do not specify a scope-matching rule, `ScopeMatchByPrefix` is used.</span></span> <span data-ttu-id="2a709-127">Para obtener más información sobre este tema vea <xref:System.ServiceModel.Discovery.FindCriteria>.</span><span class="sxs-lookup"><span data-stu-id="2a709-127">For more information on this, see <xref:System.ServiceModel.Discovery.FindCriteria>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2a709-128">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2a709-128">Child Elements</span></span>  
  
|<span data-ttu-id="2a709-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="2a709-129">Element</span></span>|<span data-ttu-id="2a709-130">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2a709-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2a709-131">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="2a709-131">\<contractTypeNames></span></span>](contracttypenames.md)|<span data-ttu-id="2a709-132">Colección de elementos de configuración que contienen los nombres de los tipos de contrato de servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2a709-132">A collection of configuration elements that contain the names of workflow service contract types.</span></span>|  
|<span data-ttu-id="2a709-133">\<> de extensiones \<de findCriteria ></span><span class="sxs-lookup"><span data-stu-id="2a709-133">\<extensions> of \<findCriteria></span></span>|<span data-ttu-id="2a709-134">Colección de objetos de elementos XML que proporcionan las extensiones.</span><span class="sxs-lookup"><span data-stu-id="2a709-134">A collection of XML element objects that provide extensions.</span></span>|  
|[<span data-ttu-id="2a709-135">\<scopes></span><span class="sxs-lookup"><span data-stu-id="2a709-135">\<scopes></span></span>](scopes.md)|<span data-ttu-id="2a709-136">Colección de objetos que contienen URI absolutos que se usan durante una operación de búsqueda para localizar un servicio o servicios concretos.</span><span class="sxs-lookup"><span data-stu-id="2a709-136">A collection of objects that contain absolute URIs that are used during a find operation to locate a specific service or services.</span></span><br /><br /> <span data-ttu-id="2a709-137">Si se encuentra el servicio concreto, se ha establecido una coincidencia correcta entre el URI del servicio y el URI del ámbito, en ocasiones con la ayuda de las reglas de ámbito que se ocupan de las complicaciones relativas a las coincidencias.</span><span class="sxs-lookup"><span data-stu-id="2a709-137">If the specific service is found, a successful match has been made between the service URI and the Scope URI, sometimes with the help of scope rules that handle complications of matching.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2a709-138">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2a709-138">Parent Elements</span></span>  
  
|<span data-ttu-id="2a709-139">Elemento</span><span class="sxs-lookup"><span data-stu-id="2a709-139">Element</span></span>|<span data-ttu-id="2a709-140">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2a709-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2a709-141">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="2a709-141">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="2a709-142">Contiene la configuración que necesita una aplicación para participar en el proceso de detección del servicio como un cliente.</span><span class="sxs-lookup"><span data-stu-id="2a709-142">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2a709-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a709-143">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
