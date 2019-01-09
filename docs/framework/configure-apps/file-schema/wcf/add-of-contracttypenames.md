---
title: '&lt;add&gt; de &lt;contractTypeNames&gt;'
ms.date: 03/30/2017
ms.assetid: 03aff6be-5dfb-4a64-ada3-e36227cd43c7
ms.openlocfilehash: 79972eaea6918b3fe923c963b6a219fd8f972516
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145619"
---
# <a name="ltaddgt-of-ltcontracttypenamesgt"></a><span data-ttu-id="9607b-102">&lt;add&gt; de &lt;contractTypeNames&gt;</span><span class="sxs-lookup"><span data-stu-id="9607b-102">&lt;add&gt; of &lt;contractTypeNames&gt;</span></span>
<span data-ttu-id="9607b-103">Un elemento de configuración que especifica el nombre del contrato de los servicios que se están buscando y los criterios que suelen usarse al buscar un servicio.</span><span class="sxs-lookup"><span data-stu-id="9607b-103">A configuration element that specifies the contract name of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="9607b-104">Si se especifica más de un nombre del contrato, solo responderán los puntos de conexión del servicio que coincidan con TODOS los contratos.</span><span class="sxs-lookup"><span data-stu-id="9607b-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="9607b-105">Tenga en cuenta que en Windows Communication Foundation (WCF), un punto de conexión solo puede admitir un contrato.</span><span class="sxs-lookup"><span data-stu-id="9607b-105">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
 <span data-ttu-id="9607b-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9607b-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="9607b-107">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="9607b-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9607b-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9607b-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9607b-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9607b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9607b-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9607b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9607b-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="9607b-111">Attributes</span></span>  
  
|<span data-ttu-id="9607b-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="9607b-112">Attribute</span></span>|<span data-ttu-id="9607b-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="9607b-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9607b-114">name</span><span class="sxs-lookup"><span data-stu-id="9607b-114">name</span></span>|<span data-ttu-id="9607b-115">Cadena que especifica el nombre del tipo de contrato.</span><span class="sxs-lookup"><span data-stu-id="9607b-115">A string that specifies the name of the contract type.</span></span>|  
|<span data-ttu-id="9607b-116">namespace</span><span class="sxs-lookup"><span data-stu-id="9607b-116">namespace</span></span>|<span data-ttu-id="9607b-117">Cadena que especifica el espacio de nombres del tipo de contrato.</span><span class="sxs-lookup"><span data-stu-id="9607b-117">A string that specifies the namespace of the contract type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9607b-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9607b-118">Child Elements</span></span>  
 <span data-ttu-id="9607b-119">Ninguna</span><span class="sxs-lookup"><span data-stu-id="9607b-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9607b-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9607b-120">Parent Elements</span></span>  
  
|<span data-ttu-id="9607b-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="9607b-121">Element</span></span>|<span data-ttu-id="9607b-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="9607b-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9607b-123">\<contractTypeNames ></span><span class="sxs-lookup"><span data-stu-id="9607b-123">\<contractTypeNames></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|<span data-ttu-id="9607b-124">Colección de nombres de tipos de contrato.</span><span class="sxs-lookup"><span data-stu-id="9607b-124">A collection of contract type names.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9607b-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="9607b-125">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.FindCriteria>  
 <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>  
 <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement>
