---
title: <clientVia>
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: a1c2ee68fb039e24e1462148cb52daf1bb57f8ed
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398107"
---
# <a name="clientvia"></a><span data-ttu-id="e2de7-101">\<clientVia></span><span class="sxs-lookup"><span data-stu-id="e2de7-101">\<clientVia></span></span>
<span data-ttu-id="e2de7-102">Especifica URI para el que se debe crear el canal de transporte.</span><span class="sxs-lookup"><span data-stu-id="e2de7-102">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="e2de7-103">Para obtener más información, consulta <xref:System.ServiceModel.Description.ClientViaBehavior>.</span><span class="sxs-lookup"><span data-stu-id="e2de7-103">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
<span data-ttu-id="e2de7-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e2de7-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e2de7-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e2de7-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e2de7-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e2de7-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="e2de7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e2de7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="e2de7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e2de7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="e2de7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> clientVia**</span><span class="sxs-lookup"><span data-stu-id="e2de7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientVia>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2de7-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e2de7-110">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e2de7-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e2de7-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e2de7-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e2de7-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e2de7-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="e2de7-113">Attributes</span></span>  
  
|<span data-ttu-id="e2de7-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="e2de7-114">Attribute</span></span>|<span data-ttu-id="e2de7-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e2de7-115">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="e2de7-116">Una cadena que especifica un URI que indica la ruta que un mensaje debe tomar.</span><span class="sxs-lookup"><span data-stu-id="e2de7-116">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e2de7-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e2de7-117">Child Elements</span></span>  
 <span data-ttu-id="e2de7-118">None</span><span class="sxs-lookup"><span data-stu-id="e2de7-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e2de7-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e2de7-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e2de7-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="e2de7-120">Element</span></span>|<span data-ttu-id="e2de7-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e2de7-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e2de7-122">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="e2de7-122">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="e2de7-123">Especifica el comportamiento de un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="e2de7-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e2de7-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2de7-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientViaElement>
- <xref:System.ServiceModel.Description.ClientViaBehavior>
