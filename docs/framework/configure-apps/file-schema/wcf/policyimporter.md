---
title: '&lt;policyImporter&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 99bb7c6be02bad85792dfce9de1f6ef8ba1dcd17
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltpolicyimportergt"></a><span data-ttu-id="a0efc-102">&lt;policyImporter&gt;</span><span class="sxs-lookup"><span data-stu-id="a0efc-102">&lt;policyImporter&gt;</span></span>
<span data-ttu-id="a0efc-103">Especifica un importador de directivas que controla la importación de aserciones de directivas personalizadas de los enlaces.</span><span class="sxs-lookup"><span data-stu-id="a0efc-103">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
 <span data-ttu-id="a0efc-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a0efc-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a0efc-105">\<cliente ></span><span class="sxs-lookup"><span data-stu-id="a0efc-105">\<client></span></span>  
<span data-ttu-id="a0efc-106">\<metadatos ></span><span class="sxs-lookup"><span data-stu-id="a0efc-106">\<metadata></span></span>  
<span data-ttu-id="a0efc-107">\<policyImporters ></span><span class="sxs-lookup"><span data-stu-id="a0efc-107">\<policyImporters></span></span>  
<span data-ttu-id="a0efc-108">\<policyImporter ></span><span class="sxs-lookup"><span data-stu-id="a0efc-108">\<policyImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0efc-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a0efc-109">Syntax</span></span>  
  
```xml  
<metadata>  
   <policyImporters>  
      <policyImporter type="string" />  
   </policyImporters>  
</metadata>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a0efc-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a0efc-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a0efc-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a0efc-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a0efc-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="a0efc-112">Attributes</span></span>  
  
|<span data-ttu-id="a0efc-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="a0efc-113">Attribute</span></span>|<span data-ttu-id="a0efc-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="a0efc-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="a0efc-115">El tipo de este elemento.</span><span class="sxs-lookup"><span data-stu-id="a0efc-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a0efc-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a0efc-116">Child Elements</span></span>  
 <span data-ttu-id="a0efc-117">Ninguna</span><span class="sxs-lookup"><span data-stu-id="a0efc-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a0efc-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a0efc-118">Parent Elements</span></span>  
  
|<span data-ttu-id="a0efc-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="a0efc-119">Element</span></span>|<span data-ttu-id="a0efc-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="a0efc-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a0efc-121">\<policyImporters ></span><span class="sxs-lookup"><span data-stu-id="a0efc-121">\<policyImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|<span data-ttu-id="a0efc-122">Especifica todos los importadores de directivas que controlan la importación de aserciones de directivas personalizadas de los enlaces.</span><span class="sxs-lookup"><span data-stu-id="a0efc-122">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0efc-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a0efc-123">Remarks</span></span>  
 <span data-ttu-id="a0efc-124">Un importador de directiva se usa para buscar en las aserciones de directivas personalizadas sobre características de enlace, así como para adjuntar un elemento de enlace personalizado que implementa las características que la aserción requiere.</span><span class="sxs-lookup"><span data-stu-id="a0efc-124">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0efc-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0efc-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>  
 <xref:System.ServiceModel.Configuration.PolicyImporterElement>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 <xref:System.ServiceModel.Description.MetadataImporter>  
 [<span data-ttu-id="a0efc-126">Configuración de cliente WCF</span><span class="sxs-lookup"><span data-stu-id="a0efc-126">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [<span data-ttu-id="a0efc-127">Clientes</span><span class="sxs-lookup"><span data-stu-id="a0efc-127">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
