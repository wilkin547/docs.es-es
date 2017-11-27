---
title: '&lt;clientVia&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7cdc85c23202154728610ab4721bf830004928c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltclientviagt"></a><span data-ttu-id="cad99-102">&lt;clientVia&gt;</span><span class="sxs-lookup"><span data-stu-id="cad99-102">&lt;clientVia&gt;</span></span>
<span data-ttu-id="cad99-103">Especifica URI para el que se debe crear el canal de transporte.</span><span class="sxs-lookup"><span data-stu-id="cad99-103">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="cad99-104">Para obtener más información, consulta <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="cad99-104">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="cad99-105">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="cad99-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="cad99-106">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="cad99-106">\<behaviors></span></span>  
<span data-ttu-id="cad99-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="cad99-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="cad99-108">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="cad99-108">\<behavior></span></span>  
<span data-ttu-id="cad99-109">\<clientVia ></span><span class="sxs-lookup"><span data-stu-id="cad99-109">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cad99-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cad99-110">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cad99-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="cad99-111">Attributes and Elements</span></span>  
 <span data-ttu-id="cad99-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="cad99-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cad99-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="cad99-113">Attributes</span></span>  
  
|<span data-ttu-id="cad99-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="cad99-114">Attribute</span></span>|<span data-ttu-id="cad99-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="cad99-115">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="cad99-116">Una cadena que especifica un URI que indica la ruta que un mensaje debe tomar.</span><span class="sxs-lookup"><span data-stu-id="cad99-116">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cad99-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="cad99-117">Child Elements</span></span>  
 <span data-ttu-id="cad99-118">Ninguna</span><span class="sxs-lookup"><span data-stu-id="cad99-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cad99-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="cad99-119">Parent Elements</span></span>  
  
|<span data-ttu-id="cad99-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="cad99-120">Element</span></span>|<span data-ttu-id="cad99-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="cad99-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cad99-122">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="cad99-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="cad99-123">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="cad99-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cad99-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="cad99-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientViaElement>  
 <xref:System.ServiceModel.Description.ClientViaBehavior>
