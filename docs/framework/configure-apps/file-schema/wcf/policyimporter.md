---
title: <policyImporter>
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 81f38d2a163163ca7255ca546bbddbbb58fa3a1b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59094182"
---
# <a name="policyimporter"></a><span data-ttu-id="756ed-101">\<policyImporter></span><span class="sxs-lookup"><span data-stu-id="756ed-101">\<policyImporter></span></span>
<span data-ttu-id="756ed-102">Especifica un importador de directivas que controla la importación de aserciones de directivas personalizadas de los enlaces.</span><span class="sxs-lookup"><span data-stu-id="756ed-102">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
 <span data-ttu-id="756ed-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="756ed-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="756ed-104">\<client></span><span class="sxs-lookup"><span data-stu-id="756ed-104">\<client></span></span>  
<span data-ttu-id="756ed-105">\<metadata></span><span class="sxs-lookup"><span data-stu-id="756ed-105">\<metadata></span></span>  
<span data-ttu-id="756ed-106">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="756ed-106">\<policyImporters></span></span>  
<span data-ttu-id="756ed-107">\<policyImporter></span><span class="sxs-lookup"><span data-stu-id="756ed-107">\<policyImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="756ed-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="756ed-108">Syntax</span></span>  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="756ed-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="756ed-109">Attributes and Elements</span></span>  
 <span data-ttu-id="756ed-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="756ed-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="756ed-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="756ed-111">Attributes</span></span>  
  
|<span data-ttu-id="756ed-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="756ed-112">Attribute</span></span>|<span data-ttu-id="756ed-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="756ed-113">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="756ed-114">El tipo de este elemento.</span><span class="sxs-lookup"><span data-stu-id="756ed-114">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="756ed-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="756ed-115">Child Elements</span></span>  
 <span data-ttu-id="756ed-116">Ninguna</span><span class="sxs-lookup"><span data-stu-id="756ed-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="756ed-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="756ed-117">Parent Elements</span></span>  
  
|<span data-ttu-id="756ed-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="756ed-118">Element</span></span>|<span data-ttu-id="756ed-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="756ed-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="756ed-120">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="756ed-120">\<policyImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|<span data-ttu-id="756ed-121">Especifica todos los importadores de directivas que controlan la importación de aserciones de directivas personalizadas de los enlaces.</span><span class="sxs-lookup"><span data-stu-id="756ed-121">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="756ed-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="756ed-122">Remarks</span></span>  
 <span data-ttu-id="756ed-123">Un importador de directiva se usa para buscar en las aserciones de directivas personalizadas sobre características de enlace, así como para adjuntar un elemento de enlace personalizado que implementa las características que la aserción requiere.</span><span class="sxs-lookup"><span data-stu-id="756ed-123">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="756ed-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="756ed-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.PolicyImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Description.MetadataImporter>
- [<span data-ttu-id="756ed-125">Configuración del cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="756ed-125">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="756ed-126">Clientes</span><span class="sxs-lookup"><span data-stu-id="756ed-126">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
