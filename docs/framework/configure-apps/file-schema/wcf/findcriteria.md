---
title: <findCriteria>
ms.date: 03/30/2017
ms.assetid: 5454cd19-6bf5-4ba8-94d1-f58d10dc1917
ms.openlocfilehash: 44e068ee205bc5e04382164e7ab00716b2c07dcf
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855165"
---
# \<findCriteria>
<span data-ttu-id="5207b-101">Elemento de configuración que proporciona un conjunto de criterios utilizado por una aplicación cliente para buscar un servicio de detección.</span><span class="sxs-lookup"><span data-stu-id="5207b-101">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="5207b-102">Los criterios pueden agruparse en criterios de búsqueda (que especifican qué servicios está buscando) y en criterios de finalización de búsqueda (cuánto tiempo debería durar la búsqueda).</span><span class="sxs-lookup"><span data-stu-id="5207b-102">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<discoveryClientSettings>**](discoveryclientsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<findCriteria>**  
  
## <a name="syntax"></a><span data-ttu-id="5207b-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5207b-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5207b-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5207b-104">Attributes and Elements</span></span>  
 <span data-ttu-id="5207b-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5207b-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5207b-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="5207b-106">Attributes</span></span>  
  
|<span data-ttu-id="5207b-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="5207b-107">Attribute</span></span>|<span data-ttu-id="5207b-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="5207b-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5207b-109">duration</span><span class="sxs-lookup"><span data-stu-id="5207b-109">duration</span></span>|<span data-ttu-id="5207b-110">Un valor Timespan que especifica el tiempo máximo para esperar respuestas de los servicios en la red.</span><span class="sxs-lookup"><span data-stu-id="5207b-110">A Timespan value that specifies the maximum time to wait for replies from services on the network.</span></span> <span data-ttu-id="5207b-111">La duración predeterminada es de 20 segundos.</span><span class="sxs-lookup"><span data-stu-id="5207b-111">The default duration is 20 seconds.</span></span>|  
|<span data-ttu-id="5207b-112">maxResults</span><span class="sxs-lookup"><span data-stu-id="5207b-112">maxResults</span></span>|<span data-ttu-id="5207b-113">Entero que especifica el número máximo de respuestas que se deben esperar, de los servicios en una red o de Internet.</span><span class="sxs-lookup"><span data-stu-id="5207b-113">An integer that specifies the maximum number of replies to wait for, from services on a network or the Internet.</span></span> <span data-ttu-id="5207b-114">Si se recibe el máximo de respuestas antes de que haya transcurrido el valor especificado en el atributo `duration`, finalizará la operación de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="5207b-114">If maximum replies are received before the value specified in the `duration` attribute has elapsed, the find operation ends.</span></span>|  
|<span data-ttu-id="5207b-115">scopeMatchBy</span><span class="sxs-lookup"><span data-stu-id="5207b-115">scopeMatchBy</span></span>|<span data-ttu-id="5207b-116">URI que especifica el algoritmo de coincidencia que se va a utilizar al establecer las coincidencias de los ámbitos del mensaje de sondeo con los del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="5207b-116">A URI that specify the matching algorithm to use while matching the scopes in the Probe message with that of the endpoint.</span></span><br /><br /> <span data-ttu-id="5207b-117">Hay cinco reglas de coincidencia de ámbito admitidas.</span><span class="sxs-lookup"><span data-stu-id="5207b-117">There are five supported scope-matching rules.</span></span> <span data-ttu-id="5207b-118">Si no especifica ninguna regla de coincidencia de ámbito, se usa `ScopeMatchByPrefix`.</span><span class="sxs-lookup"><span data-stu-id="5207b-118">If you do not specify a scope-matching rule, `ScopeMatchByPrefix` is used.</span></span> <span data-ttu-id="5207b-119">Para obtener más información sobre este tema vea <xref:System.ServiceModel.Discovery.FindCriteria>.</span><span class="sxs-lookup"><span data-stu-id="5207b-119">For more information on this, see <xref:System.ServiceModel.Discovery.FindCriteria>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5207b-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5207b-120">Child Elements</span></span>  
  
|<span data-ttu-id="5207b-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="5207b-121">Element</span></span>|<span data-ttu-id="5207b-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="5207b-122">Description</span></span>|  
|-------------|-----------------|  
|[\<contractTypeNames>](contracttypenames.md)|<span data-ttu-id="5207b-123">Colección de elementos de configuración que contienen los nombres de los tipos de contrato de servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5207b-123">A collection of configuration elements that contain the names of workflow service contract types.</span></span>|  
|<span data-ttu-id="5207b-124">\<extensions> de \<findCriteria></span><span class="sxs-lookup"><span data-stu-id="5207b-124">\<extensions> of \<findCriteria></span></span>|<span data-ttu-id="5207b-125">Colección de objetos de elementos XML que proporcionan las extensiones.</span><span class="sxs-lookup"><span data-stu-id="5207b-125">A collection of XML element objects that provide extensions.</span></span>|  
|[\<scopes>](scopes.md)|<span data-ttu-id="5207b-126">Colección de objetos que contienen URI absolutos que se usan durante una operación de búsqueda para localizar un servicio o servicios concretos.</span><span class="sxs-lookup"><span data-stu-id="5207b-126">A collection of objects that contain absolute URIs that are used during a find operation to locate a specific service or services.</span></span><br /><br /> <span data-ttu-id="5207b-127">Si se encuentra el servicio concreto, se ha establecido una coincidencia correcta entre el URI del servicio y el URI del ámbito, en ocasiones con la ayuda de las reglas de ámbito que se ocupan de las complicaciones relativas a las coincidencias.</span><span class="sxs-lookup"><span data-stu-id="5207b-127">If the specific service is found, a successful match has been made between the service URI and the Scope URI, sometimes with the help of scope rules that handle complications of matching.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5207b-128">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5207b-128">Parent Elements</span></span>  
  
|<span data-ttu-id="5207b-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="5207b-129">Element</span></span>|<span data-ttu-id="5207b-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="5207b-130">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="5207b-131">Contiene la configuración que necesita una aplicación para participar en el proceso de detección del servicio como un cliente.</span><span class="sxs-lookup"><span data-stu-id="5207b-131">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5207b-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5207b-132">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
