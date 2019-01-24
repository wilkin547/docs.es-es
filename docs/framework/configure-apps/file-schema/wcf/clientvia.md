---
title: '&lt;clientVia&gt;'
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: 6491411d8cfe5c7a5a944f3b1cd728c9f0a4b852
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54641218"
---
# <a name="ltclientviagt"></a><span data-ttu-id="60602-102">&lt;clientVia&gt;</span><span class="sxs-lookup"><span data-stu-id="60602-102">&lt;clientVia&gt;</span></span>
<span data-ttu-id="60602-103">Especifica URI para el que se debe crear el canal de transporte.</span><span class="sxs-lookup"><span data-stu-id="60602-103">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="60602-104">Para obtener más información, consulta <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="60602-104">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="60602-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="60602-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="60602-106">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="60602-106">\<behaviors></span></span>  
<span data-ttu-id="60602-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="60602-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="60602-108">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="60602-108">\<behavior></span></span>  
<span data-ttu-id="60602-109">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="60602-109">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60602-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="60602-110">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="60602-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="60602-111">Attributes and Elements</span></span>  
 <span data-ttu-id="60602-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="60602-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="60602-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="60602-113">Attributes</span></span>  
  
|<span data-ttu-id="60602-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="60602-114">Attribute</span></span>|<span data-ttu-id="60602-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="60602-115">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="60602-116">Una cadena que especifica un URI que indica la ruta que un mensaje debe tomar.</span><span class="sxs-lookup"><span data-stu-id="60602-116">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="60602-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="60602-117">Child Elements</span></span>  
 <span data-ttu-id="60602-118">Ninguna</span><span class="sxs-lookup"><span data-stu-id="60602-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="60602-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="60602-119">Parent Elements</span></span>  
  
|<span data-ttu-id="60602-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="60602-120">Element</span></span>|<span data-ttu-id="60602-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="60602-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="60602-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="60602-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="60602-123">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="60602-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="60602-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="60602-124">See also</span></span>
- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
