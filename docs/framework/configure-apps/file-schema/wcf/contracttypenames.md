---
title: <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 5ec5efc6-87f8-4160-9be0-dcd2e01df3df
ms.openlocfilehash: 12f9d4eca02ae3b306646826667c4eafef51a95c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919371"
---
# <a name="contracttypenames"></a><span data-ttu-id="51012-101">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="51012-101">\<contractTypeNames></span></span>
<span data-ttu-id="51012-102">Una sección de configuración que especifica una lista de nombres de tipos de contrato, que son los nombres del contrato de los servicios que se están buscando, y los criterios que suelen usarse al buscar un servicio.</span><span class="sxs-lookup"><span data-stu-id="51012-102">A configuration section that specifies a list of contract type names, which are the contract names of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="51012-103">Si se especifica más de un nombre del contrato, solo responderán los extremos del servicio que coincidan con TODOS los contratos.</span><span class="sxs-lookup"><span data-stu-id="51012-103">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="51012-104">Tenga en cuenta que en Windows Communication Foundation (WCF), un punto de conexión solo puede admitir un contrato.</span><span class="sxs-lookup"><span data-stu-id="51012-104">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
 <span data-ttu-id="51012-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="51012-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="51012-106">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="51012-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51012-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="51012-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="51012-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="51012-108">Attributes and Elements</span></span>  
 <span data-ttu-id="51012-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="51012-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="51012-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="51012-110">Attributes</span></span>  
 <span data-ttu-id="51012-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="51012-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="51012-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="51012-112">Child Elements</span></span>  
  
|<span data-ttu-id="51012-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="51012-113">Element</span></span>|<span data-ttu-id="51012-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="51012-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="51012-115">\<add></span><span class="sxs-lookup"><span data-stu-id="51012-115">\<add></span></span>](contracttypenames.md)|<span data-ttu-id="51012-116">Un nombre de tipo de contrato es una propiedad que hace referencia al conjunto de criterios que suele usarse al buscar un servicio.</span><span class="sxs-lookup"><span data-stu-id="51012-116">A contract type name is a property that refers to the set of criteria typically used when searching for a service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="51012-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="51012-117">Parent Elements</span></span>  
  
|<span data-ttu-id="51012-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="51012-118">Element</span></span>|<span data-ttu-id="51012-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="51012-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="51012-120">\<findCriteria></span><span class="sxs-lookup"><span data-stu-id="51012-120">\<findCriteria></span></span>](findcriteria.md)|<span data-ttu-id="51012-121">Elemento de configuración que proporciona un conjunto de criterios utilizado por una aplicación cliente para buscar un servicio de detección.</span><span class="sxs-lookup"><span data-stu-id="51012-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="51012-122">Los criterios se pueden agrupar en criterios de búsqueda (especificando qué servicios está buscando) y criterios de finalización de búsqueda (cuánto tiempo debe durar la búsqueda).</span><span class="sxs-lookup"><span data-stu-id="51012-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="51012-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="51012-123">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElementCollection>
