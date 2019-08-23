---
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: b12a882d942555a24c145b243d2cea764ba106b1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919506"
---
# <a name="clientvia"></a><span data-ttu-id="9fbf2-101">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="9fbf2-101">\<clientVia></span></span>
<span data-ttu-id="9fbf2-102">Especifica URI para el que se debe crear el canal de transporte.</span><span class="sxs-lookup"><span data-stu-id="9fbf2-102">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="9fbf2-103">Para obtener más información, consulta <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="9fbf2-103">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="9fbf2-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9fbf2-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9fbf2-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="9fbf2-105">\<behaviors></span></span>  
<span data-ttu-id="9fbf2-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="9fbf2-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="9fbf2-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="9fbf2-107">\<behavior></span></span>  
<span data-ttu-id="9fbf2-108">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="9fbf2-108">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fbf2-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9fbf2-109">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9fbf2-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9fbf2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9fbf2-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9fbf2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9fbf2-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="9fbf2-112">Attributes</span></span>  
  
|<span data-ttu-id="9fbf2-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="9fbf2-113">Attribute</span></span>|<span data-ttu-id="9fbf2-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="9fbf2-114">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="9fbf2-115">Una cadena que especifica un URI que indica la ruta que un mensaje debe tomar.</span><span class="sxs-lookup"><span data-stu-id="9fbf2-115">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9fbf2-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9fbf2-116">Child Elements</span></span>  
 <span data-ttu-id="9fbf2-117">None</span><span class="sxs-lookup"><span data-stu-id="9fbf2-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9fbf2-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9fbf2-118">Parent Elements</span></span>  
  
|<span data-ttu-id="9fbf2-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="9fbf2-119">Element</span></span>|<span data-ttu-id="9fbf2-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="9fbf2-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9fbf2-121">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="9fbf2-121">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="9fbf2-122">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="9fbf2-122">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9fbf2-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="9fbf2-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
