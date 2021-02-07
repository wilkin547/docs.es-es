---
description: 'Más información acerca de: <policyImporter>'
title: <policyImporter>
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 2103c424aef081b72fa822ed207537195b8fdea9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683520"
---
# \<policyImporter>

<span data-ttu-id="20b6d-102">Especifica un importador de directivas que controla la importación de aserciones de directivas personalizadas de los enlaces.</span><span class="sxs-lookup"><span data-stu-id="20b6d-102">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<metadata>**](metadata.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<policyImporters>**](policyimporters.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<policyImporter>**  
  
## <a name="syntax"></a><span data-ttu-id="20b6d-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="20b6d-103">Syntax</span></span>  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="20b6d-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="20b6d-104">Attributes and Elements</span></span>  

 <span data-ttu-id="20b6d-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="20b6d-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="20b6d-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="20b6d-106">Attributes</span></span>  
  
|<span data-ttu-id="20b6d-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="20b6d-107">Attribute</span></span>|<span data-ttu-id="20b6d-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="20b6d-108">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="20b6d-109">El tipo de este elemento.</span><span class="sxs-lookup"><span data-stu-id="20b6d-109">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="20b6d-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="20b6d-110">Child Elements</span></span>  

 <span data-ttu-id="20b6d-111">None</span><span class="sxs-lookup"><span data-stu-id="20b6d-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="20b6d-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="20b6d-112">Parent Elements</span></span>  
  
|<span data-ttu-id="20b6d-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="20b6d-113">Element</span></span>|<span data-ttu-id="20b6d-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="20b6d-114">Description</span></span>|  
|-------------|-----------------|  
|[\<policyImporters>](policyimporters.md)|<span data-ttu-id="20b6d-115">Especifica todos los importadores de directivas que controlan la importación de aserciones de directivas personalizadas de los enlaces.</span><span class="sxs-lookup"><span data-stu-id="20b6d-115">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20b6d-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="20b6d-116">Remarks</span></span>  

 <span data-ttu-id="20b6d-117">Un importador de directiva se usa para buscar en las aserciones de directivas personalizadas sobre características de enlace, así como para adjuntar un elemento de enlace personalizado que implementa las características que la aserción requiere.</span><span class="sxs-lookup"><span data-stu-id="20b6d-117">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20b6d-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="20b6d-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.PolicyImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Description.MetadataImporter>
- [<span data-ttu-id="20b6d-119">Configuración de cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="20b6d-119">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="20b6d-120">Clientes</span><span class="sxs-lookup"><span data-stu-id="20b6d-120">Clients</span></span>](../../../wcf/feature-details/clients.md)
