---
title: '&lt;contractTypeNames&gt;'
ms.date: 03/30/2017
ms.assetid: 5ec5efc6-87f8-4160-9be0-dcd2e01df3df
ms.openlocfilehash: 99547967b65e5d7663ec11be98247e2018aaa34c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltcontracttypenamesgt"></a><span data-ttu-id="d4925-102">&lt;contractTypeNames&gt;</span><span class="sxs-lookup"><span data-stu-id="d4925-102">&lt;contractTypeNames&gt;</span></span>
<span data-ttu-id="d4925-103">Una sección de configuración que especifica una lista de nombres de tipos de contrato, que son los nombres del contrato de los servicios que se están buscando, y los criterios que suelen usarse al buscar un servicio.</span><span class="sxs-lookup"><span data-stu-id="d4925-103">A configuration section that specifies a list of contract type names, which are the contract names of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="d4925-104">Si se especifica más de un nombre del contrato, solo responderán los puntos de conexión del servicio que coincidan con TODOS los contratos.</span><span class="sxs-lookup"><span data-stu-id="d4925-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="d4925-105">Tenga en cuenta que en Windows Communication Foundation (WCF), un punto de conexión sólo puede admitir un contrato.</span><span class="sxs-lookup"><span data-stu-id="d4925-105">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
 <span data-ttu-id="d4925-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d4925-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="d4925-107">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="d4925-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4925-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d4925-108">Syntax</span></span>  
  
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
              <add name="String" namespace="String" />
            <contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI"/>
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d4925-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d4925-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d4925-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d4925-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d4925-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="d4925-111">Attributes</span></span>  
 <span data-ttu-id="d4925-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d4925-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d4925-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d4925-113">Child Elements</span></span>  
  
|<span data-ttu-id="d4925-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="d4925-114">Element</span></span>|<span data-ttu-id="d4925-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="d4925-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d4925-116">\<add></span><span class="sxs-lookup"><span data-stu-id="d4925-116">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|<span data-ttu-id="d4925-117">Un nombre de tipo de contrato es una propiedad que hace referencia al conjunto de criterios que suele usarse al buscar un servicio.</span><span class="sxs-lookup"><span data-stu-id="d4925-117">A contract type name is a property that refers to the set of criteria typically used when searching for a service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d4925-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d4925-118">Parent Elements</span></span>  
  
|<span data-ttu-id="d4925-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="d4925-119">Element</span></span>|<span data-ttu-id="d4925-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="d4925-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d4925-121">\<findCriteria ></span><span class="sxs-lookup"><span data-stu-id="d4925-121">\<findCriteria></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/findcriteria.md)|<span data-ttu-id="d4925-122">Elemento de configuración que proporciona un conjunto de criterios utilizado por una aplicación cliente para buscar un servicio de detección.</span><span class="sxs-lookup"><span data-stu-id="d4925-122">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="d4925-123">Criterios pueden agruparse en criterios de búsqueda (que especifican qué servicios está buscando) y encuentra criterios de finalización (cuánto tiempo debe durar la búsqueda).</span><span class="sxs-lookup"><span data-stu-id="d4925-123">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d4925-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4925-124">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.FindCriteria>  
 <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>  
 <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElementCollection>
