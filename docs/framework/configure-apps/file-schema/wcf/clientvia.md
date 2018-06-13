---
title: '&lt;clientVia&gt;'
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: 6218bb3f205f2825eb3f10fabf834cfd0396ac87
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32754137"
---
# <a name="ltclientviagt"></a><span data-ttu-id="8c306-102">&lt;clientVia&gt;</span><span class="sxs-lookup"><span data-stu-id="8c306-102">&lt;clientVia&gt;</span></span>
<span data-ttu-id="8c306-103">Especifica URI para el que se debe crear el canal de transporte.</span><span class="sxs-lookup"><span data-stu-id="8c306-103">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="8c306-104">Para obtener más información, consulta <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="8c306-104">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="8c306-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8c306-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="8c306-106">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="8c306-106">\<behaviors></span></span>  
<span data-ttu-id="8c306-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="8c306-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="8c306-108">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="8c306-108">\<behavior></span></span>  
<span data-ttu-id="8c306-109">\<clientVia ></span><span class="sxs-lookup"><span data-stu-id="8c306-109">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c306-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8c306-110">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c306-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8c306-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8c306-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8c306-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c306-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="8c306-113">Attributes</span></span>  
  
|<span data-ttu-id="8c306-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="8c306-114">Attribute</span></span>|<span data-ttu-id="8c306-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="8c306-115">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="8c306-116">Una cadena que especifica un URI que indica la ruta que un mensaje debe tomar.</span><span class="sxs-lookup"><span data-stu-id="8c306-116">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8c306-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8c306-117">Child Elements</span></span>  
 <span data-ttu-id="8c306-118">Ninguna</span><span class="sxs-lookup"><span data-stu-id="8c306-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8c306-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8c306-119">Parent Elements</span></span>  
  
|<span data-ttu-id="8c306-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="8c306-120">Element</span></span>|<span data-ttu-id="8c306-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="8c306-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c306-122">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="8c306-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="8c306-123">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="8c306-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8c306-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c306-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientViaElement>  
 <xref:System.ServiceModel.Description.ClientViaBehavior>
