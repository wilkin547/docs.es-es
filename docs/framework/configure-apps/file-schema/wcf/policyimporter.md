---
title: <policyImporter>
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 273bd0d5e68a661c639b82264b440b83d8127427
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933790"
---
# <a name="policyimporter"></a><span data-ttu-id="27e5c-101">\<policyImporter></span><span class="sxs-lookup"><span data-stu-id="27e5c-101">\<policyImporter></span></span>
<span data-ttu-id="27e5c-102">Especifica un importador de directivas que controla la importación de aserciones de directivas personalizadas de los enlaces.</span><span class="sxs-lookup"><span data-stu-id="27e5c-102">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
 <span data-ttu-id="27e5c-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="27e5c-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="27e5c-104">\<client></span><span class="sxs-lookup"><span data-stu-id="27e5c-104">\<client></span></span>  
<span data-ttu-id="27e5c-105">\<metadata></span><span class="sxs-lookup"><span data-stu-id="27e5c-105">\<metadata></span></span>  
<span data-ttu-id="27e5c-106">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="27e5c-106">\<policyImporters></span></span>  
<span data-ttu-id="27e5c-107">\<policyImporter></span><span class="sxs-lookup"><span data-stu-id="27e5c-107">\<policyImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27e5c-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="27e5c-108">Syntax</span></span>  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="27e5c-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="27e5c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="27e5c-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="27e5c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="27e5c-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="27e5c-111">Attributes</span></span>  
  
|<span data-ttu-id="27e5c-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="27e5c-112">Attribute</span></span>|<span data-ttu-id="27e5c-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="27e5c-113">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="27e5c-114">El tipo de este elemento.</span><span class="sxs-lookup"><span data-stu-id="27e5c-114">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="27e5c-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="27e5c-115">Child Elements</span></span>  
 <span data-ttu-id="27e5c-116">None</span><span class="sxs-lookup"><span data-stu-id="27e5c-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="27e5c-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="27e5c-117">Parent Elements</span></span>  
  
|<span data-ttu-id="27e5c-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="27e5c-118">Element</span></span>|<span data-ttu-id="27e5c-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="27e5c-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="27e5c-120">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="27e5c-120">\<policyImporters></span></span>](policyimporters.md)|<span data-ttu-id="27e5c-121">Especifica todos los importadores de directivas que controlan la importación de aserciones de directivas personalizadas de los enlaces.</span><span class="sxs-lookup"><span data-stu-id="27e5c-121">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27e5c-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="27e5c-122">Remarks</span></span>  
 <span data-ttu-id="27e5c-123">Un importador de directiva se usa para buscar en las aserciones de directivas personalizadas sobre características de enlace, así como para adjuntar un elemento de enlace personalizado que implementa las características que la aserción requiere.</span><span class="sxs-lookup"><span data-stu-id="27e5c-123">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27e5c-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="27e5c-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.PolicyImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Description.MetadataImporter>
- [<span data-ttu-id="27e5c-125">Configuración del cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="27e5c-125">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="27e5c-126">Clientes</span><span class="sxs-lookup"><span data-stu-id="27e5c-126">Clients</span></span>](../../../wcf/feature-details/clients.md)
