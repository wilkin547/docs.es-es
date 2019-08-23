---
title: <enableWebScript>
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: 123f58ee3d77bf605db21fa0d9537b3196d56468
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919112"
---
# <a name="enablewebscript"></a><span data-ttu-id="a9135-101">\<enableWebScript></span><span class="sxs-lookup"><span data-stu-id="a9135-101">\<enableWebScript></span></span>
<span data-ttu-id="a9135-102">Este elemento habilita el comportamiento del extremo que permite utilizar el servicio de las páginas web de AJAX de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a9135-102">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
 <span data-ttu-id="a9135-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a9135-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="a9135-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="a9135-104">\<behaviors></span></span>  
<span data-ttu-id="a9135-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="a9135-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="a9135-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="a9135-106">\<behavior></span></span>  
<span data-ttu-id="a9135-107">\<enableWebScript></span><span class="sxs-lookup"><span data-stu-id="a9135-107">\<enableWebScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9135-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9135-108">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a9135-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a9135-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a9135-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a9135-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a9135-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="a9135-111">Attributes</span></span>  
 <span data-ttu-id="a9135-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a9135-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a9135-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a9135-113">Child Elements</span></span>  
 <span data-ttu-id="a9135-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a9135-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a9135-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a9135-115">Parent Elements</span></span>  
  
|<span data-ttu-id="a9135-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="a9135-116">Element</span></span>|<span data-ttu-id="a9135-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a9135-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a9135-118">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="a9135-118">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="a9135-119">Especifica el conjunto de comportamientos del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="a9135-119">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9135-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a9135-120">Remarks</span></span>  
 <span data-ttu-id="a9135-121">Este comportamiento solo se debe usar junto con la [ \<>](webhttpbinding.md) de enlace de webHttpBinding o el elemento de enlace de [ \<> de webMessageEncoding](webmessageencoding.md) .</span><span class="sxs-lookup"><span data-stu-id="a9135-121">This behavior should only be used in conjunction with either the [\<webHttpBinding>](webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="a9135-122">Para obtener más información sobre este comportamiento, vea <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span><span class="sxs-lookup"><span data-stu-id="a9135-122">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9135-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9135-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [<span data-ttu-id="a9135-124">Integración de AJAX y compatibilidad de JSON</span><span class="sxs-lookup"><span data-stu-id="a9135-124">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="a9135-125">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="a9135-125">\<webHttp></span></span>](webhttp.md)
