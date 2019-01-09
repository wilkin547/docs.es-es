---
title: '&lt;clientVia&gt;'
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: 48e56b79f47e84122ddd4d7f55d50044510bfa66
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149064"
---
# <a name="ltclientviagt"></a><span data-ttu-id="336a8-102">&lt;clientVia&gt;</span><span class="sxs-lookup"><span data-stu-id="336a8-102">&lt;clientVia&gt;</span></span>
<span data-ttu-id="336a8-103">Especifica URI para el que se debe crear el canal de transporte.</span><span class="sxs-lookup"><span data-stu-id="336a8-103">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="336a8-104">Para obtener más información, consulta <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="336a8-104">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="336a8-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="336a8-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="336a8-106">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="336a8-106">\<behaviors></span></span>  
<span data-ttu-id="336a8-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="336a8-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="336a8-108">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="336a8-108">\<behavior></span></span>  
<span data-ttu-id="336a8-109">\<clientVia ></span><span class="sxs-lookup"><span data-stu-id="336a8-109">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="336a8-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="336a8-110">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="336a8-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="336a8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="336a8-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="336a8-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="336a8-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="336a8-113">Attributes</span></span>  
  
|<span data-ttu-id="336a8-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="336a8-114">Attribute</span></span>|<span data-ttu-id="336a8-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="336a8-115">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="336a8-116">Una cadena que especifica un URI que indica la ruta que un mensaje debe tomar.</span><span class="sxs-lookup"><span data-stu-id="336a8-116">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="336a8-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="336a8-117">Child Elements</span></span>  
 <span data-ttu-id="336a8-118">Ninguna</span><span class="sxs-lookup"><span data-stu-id="336a8-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="336a8-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="336a8-119">Parent Elements</span></span>  
  
|<span data-ttu-id="336a8-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="336a8-120">Element</span></span>|<span data-ttu-id="336a8-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="336a8-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="336a8-122">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="336a8-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="336a8-123">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="336a8-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="336a8-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="336a8-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientViaElement>  
 <xref:System.ServiceModel.Description.ClientViaBehavior>
