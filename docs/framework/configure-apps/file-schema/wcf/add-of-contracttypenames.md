---
title: '&lt;add&gt; de &lt;contractTypeNames&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03aff6be-5dfb-4a64-ada3-e36227cd43c7
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 191e3e221ae42e5c046f8df324989aae7ab0dc1c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltcontracttypenamesgt"></a><span data-ttu-id="3c31f-102">&lt;add&gt; de &lt;contractTypeNames&gt;</span><span class="sxs-lookup"><span data-stu-id="3c31f-102">&lt;add&gt; of &lt;contractTypeNames&gt;</span></span>
<span data-ttu-id="3c31f-103">Un elemento de configuración que especifica el nombre del contrato de los servicios que se están buscando y los criterios que suelen usarse al buscar un servicio.</span><span class="sxs-lookup"><span data-stu-id="3c31f-103">A configuration element that specifies the contract name of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="3c31f-104">Si se especifica más de un nombre del contrato, solo responderán los extremos del servicio que coincidan con TODOS los contratos.</span><span class="sxs-lookup"><span data-stu-id="3c31f-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="3c31f-105">Observe que en [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] un extremo sólo puede admitir un contrato.</span><span class="sxs-lookup"><span data-stu-id="3c31f-105">Note that in [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], an endpoint can only support one contract.</span></span>  
  
 <span data-ttu-id="3c31f-106">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="3c31f-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="3c31f-107">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="3c31f-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c31f-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3c31f-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
    <standardEndpoints>       <dynamicEndpoint>           <standardEndpoint>             <discoveryClientSettings discoveryEndpoint="String" >               <findCriteria duration="TimeSpan"                  maxResults="Integer"                   scopeMatchBy="Uri" >                  <contractTypeNames>                     <add name="String" namespace="String" />                  <contractTypeNames>                  <extensions />                  <scopes>                    <add scope="URI"/>                  </scopes>               </findCriteria>             </discoveryClientSettings>          <standardEndpoint>       </dynamicEndpoint>            </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3c31f-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3c31f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3c31f-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3c31f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3c31f-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="3c31f-111">Attributes</span></span>  
  
|<span data-ttu-id="3c31f-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="3c31f-112">Attribute</span></span>|<span data-ttu-id="3c31f-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="3c31f-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3c31f-114">name</span><span class="sxs-lookup"><span data-stu-id="3c31f-114">name</span></span>|<span data-ttu-id="3c31f-115">Cadena que especifica el nombre del tipo de contrato.</span><span class="sxs-lookup"><span data-stu-id="3c31f-115">A string that specifies the name of the contract type.</span></span>|  
|<span data-ttu-id="3c31f-116">namespace</span><span class="sxs-lookup"><span data-stu-id="3c31f-116">namespace</span></span>|<span data-ttu-id="3c31f-117">Cadena que especifica el espacio de nombres del tipo de contrato.</span><span class="sxs-lookup"><span data-stu-id="3c31f-117">A string that specifies the namespace of the contract type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3c31f-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3c31f-118">Child Elements</span></span>  
 <span data-ttu-id="3c31f-119">Ninguna</span><span class="sxs-lookup"><span data-stu-id="3c31f-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3c31f-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3c31f-120">Parent Elements</span></span>  
  
|<span data-ttu-id="3c31f-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="3c31f-121">Element</span></span>|<span data-ttu-id="3c31f-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="3c31f-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3c31f-123">\<contractTypeNames ></span><span class="sxs-lookup"><span data-stu-id="3c31f-123">\<contractTypeNames></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|<span data-ttu-id="3c31f-124">Colección de nombres de tipos de contrato.</span><span class="sxs-lookup"><span data-stu-id="3c31f-124">A collection of contract type names.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3c31f-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c31f-125">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.FindCriteria>  
 <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>  
 <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement>
