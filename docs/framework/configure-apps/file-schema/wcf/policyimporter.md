---
title: <policyImporter>
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 4ef5890d52c3f2af42322f023b9a2a23cb583035
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855065"
---
# <a name="policyimporter"></a><span data-ttu-id="68ba3-101">\<policyImporter></span><span class="sxs-lookup"><span data-stu-id="68ba3-101">\<policyImporter></span></span>
<span data-ttu-id="68ba3-102">Especifica un importador de directivas que controla la importación de aserciones de directivas personalizadas de los enlaces.</span><span class="sxs-lookup"><span data-stu-id="68ba3-102">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
<span data-ttu-id="68ba3-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="68ba3-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="68ba3-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="68ba3-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="68ba3-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de cliente**](client.md)</span><span class="sxs-lookup"><span data-stu-id="68ba3-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="68ba3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<metadatos >** ](metadata.md)</span><span class="sxs-lookup"><span data-stu-id="68ba3-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<metadata>**](metadata.md)</span></span>\
<span data-ttu-id="68ba3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> policyImporters**](policyimporters.md)</span><span class="sxs-lookup"><span data-stu-id="68ba3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<policyImporters>**](policyimporters.md)</span></span>  
<span data-ttu-id="68ba3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> policyImporter**</span><span class="sxs-lookup"><span data-stu-id="68ba3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<policyImporter>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68ba3-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="68ba3-109">Syntax</span></span>  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="68ba3-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="68ba3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="68ba3-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="68ba3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="68ba3-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="68ba3-112">Attributes</span></span>  
  
|<span data-ttu-id="68ba3-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="68ba3-113">Attribute</span></span>|<span data-ttu-id="68ba3-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="68ba3-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="68ba3-115">El tipo de este elemento.</span><span class="sxs-lookup"><span data-stu-id="68ba3-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="68ba3-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="68ba3-116">Child Elements</span></span>  
 <span data-ttu-id="68ba3-117">None</span><span class="sxs-lookup"><span data-stu-id="68ba3-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="68ba3-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="68ba3-118">Parent Elements</span></span>  
  
|<span data-ttu-id="68ba3-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="68ba3-119">Element</span></span>|<span data-ttu-id="68ba3-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="68ba3-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="68ba3-121">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="68ba3-121">\<policyImporters></span></span>](policyimporters.md)|<span data-ttu-id="68ba3-122">Especifica todos los importadores de directivas que controlan la importación de aserciones de directivas personalizadas de los enlaces.</span><span class="sxs-lookup"><span data-stu-id="68ba3-122">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68ba3-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="68ba3-123">Remarks</span></span>  
 <span data-ttu-id="68ba3-124">Un importador de directiva se usa para buscar en las aserciones de directivas personalizadas sobre características de enlace, así como para adjuntar un elemento de enlace personalizado que implementa las características que la aserción requiere.</span><span class="sxs-lookup"><span data-stu-id="68ba3-124">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68ba3-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="68ba3-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.PolicyImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Description.MetadataImporter>
- [<span data-ttu-id="68ba3-126">Configuración del cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="68ba3-126">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="68ba3-127">Clientes</span><span class="sxs-lookup"><span data-stu-id="68ba3-127">Clients</span></span>](../../../wcf/feature-details/clients.md)
