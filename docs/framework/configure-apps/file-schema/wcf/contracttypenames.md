---
title: <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 5ec5efc6-87f8-4160-9be0-dcd2e01df3df
ms.openlocfilehash: d8f2b600b700a19cf587a6c8c4cc3f0e851edbd9
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55261288"
---
# <a name="contracttypenames"></a><span data-ttu-id="c763e-101">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="c763e-101">\<contractTypeNames></span></span>
<span data-ttu-id="c763e-102">Una sección de configuración que especifica una lista de nombres de tipos de contrato, que son los nombres del contrato de los servicios que se están buscando, y los criterios que suelen usarse al buscar un servicio.</span><span class="sxs-lookup"><span data-stu-id="c763e-102">A configuration section that specifies a list of contract type names, which are the contract names of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="c763e-103">Si se especifica más de un nombre del contrato, solo responderán los puntos de conexión del servicio que coincidan con TODOS los contratos.</span><span class="sxs-lookup"><span data-stu-id="c763e-103">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="c763e-104">Tenga en cuenta que en Windows Communication Foundation (WCF), un punto de conexión solo puede admitir un contrato.</span><span class="sxs-lookup"><span data-stu-id="c763e-104">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
 <span data-ttu-id="c763e-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c763e-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="c763e-106">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="c763e-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c763e-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c763e-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c763e-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c763e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c763e-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c763e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c763e-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="c763e-110">Attributes</span></span>  
 <span data-ttu-id="c763e-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c763e-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c763e-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c763e-112">Child Elements</span></span>  
  
|<span data-ttu-id="c763e-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="c763e-113">Element</span></span>|<span data-ttu-id="c763e-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="c763e-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c763e-115">\<add></span><span class="sxs-lookup"><span data-stu-id="c763e-115">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|<span data-ttu-id="c763e-116">Un nombre de tipo de contrato es una propiedad que hace referencia al conjunto de criterios que suele usarse al buscar un servicio.</span><span class="sxs-lookup"><span data-stu-id="c763e-116">A contract type name is a property that refers to the set of criteria typically used when searching for a service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c763e-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c763e-117">Parent Elements</span></span>  
  
|<span data-ttu-id="c763e-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="c763e-118">Element</span></span>|<span data-ttu-id="c763e-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="c763e-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c763e-120">\<findCriteria></span><span class="sxs-lookup"><span data-stu-id="c763e-120">\<findCriteria></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/findcriteria.md)|<span data-ttu-id="c763e-121">Elemento de configuración que proporciona un conjunto de criterios utilizado por una aplicación cliente para buscar un servicio de detección.</span><span class="sxs-lookup"><span data-stu-id="c763e-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="c763e-122">Los criterios pueden agruparse en criterios de búsqueda (que especifican qué servicios está buscando) y encuentra criterios de finalización (cuánto tiempo debe durar la búsqueda).</span><span class="sxs-lookup"><span data-stu-id="c763e-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c763e-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="c763e-123">See also</span></span>
- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElementCollection>
