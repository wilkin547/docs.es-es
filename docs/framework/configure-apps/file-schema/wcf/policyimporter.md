---
title: <policyImporter>
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 4ef5890d52c3f2af42322f023b9a2a23cb583035
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855065"
---
# \<policyImporter>
<span data-ttu-id="9c928-101">Especifica un importador de directivas que controla la importación de aserciones de directivas personalizadas de los enlaces.</span><span class="sxs-lookup"><span data-stu-id="9c928-101">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<metadata>**](metadata.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<policyImporters>**](policyimporters.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<policyImporter>**  
  
## <a name="syntax"></a><span data-ttu-id="9c928-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9c928-102">Syntax</span></span>  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9c928-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9c928-103">Attributes and Elements</span></span>  
 <span data-ttu-id="9c928-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9c928-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9c928-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="9c928-105">Attributes</span></span>  
  
|<span data-ttu-id="9c928-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="9c928-106">Attribute</span></span>|<span data-ttu-id="9c928-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9c928-107">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="9c928-108">El tipo de este elemento.</span><span class="sxs-lookup"><span data-stu-id="9c928-108">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9c928-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9c928-109">Child Elements</span></span>  
 <span data-ttu-id="9c928-110">None</span><span class="sxs-lookup"><span data-stu-id="9c928-110">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9c928-111">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9c928-111">Parent Elements</span></span>  
  
|<span data-ttu-id="9c928-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="9c928-112">Element</span></span>|<span data-ttu-id="9c928-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="9c928-113">Description</span></span>|  
|-------------|-----------------|  
|[\<policyImporters>](policyimporters.md)|<span data-ttu-id="9c928-114">Especifica todos los importadores de directivas que controlan la importación de aserciones de directivas personalizadas de los enlaces.</span><span class="sxs-lookup"><span data-stu-id="9c928-114">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c928-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9c928-115">Remarks</span></span>  
 <span data-ttu-id="9c928-116">Un importador de directiva se usa para buscar en las aserciones de directivas personalizadas sobre características de enlace, así como para adjuntar un elemento de enlace personalizado que implementa las características que la aserción requiere.</span><span class="sxs-lookup"><span data-stu-id="9c928-116">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c928-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9c928-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.PolicyImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Description.MetadataImporter>
- [<span data-ttu-id="9c928-118">Configuración de cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="9c928-118">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="9c928-119">Clientes</span><span class="sxs-lookup"><span data-stu-id="9c928-119">Clients</span></span>](../../../wcf/feature-details/clients.md)
