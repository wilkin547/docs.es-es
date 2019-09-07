---
title: <enableWebScript>
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: 20c0057c80b668df97379d0168bb7c005d9927ce
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400388"
---
# <a name="enablewebscript"></a><span data-ttu-id="5290e-101">\<enableWebScript></span><span class="sxs-lookup"><span data-stu-id="5290e-101">\<enableWebScript></span></span>
<span data-ttu-id="5290e-102">Este elemento habilita el comportamiento del extremo que permite utilizar el servicio de las páginas web de AJAX de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="5290e-102">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
<span data-ttu-id="5290e-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5290e-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5290e-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="5290e-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="5290e-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="5290e-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="5290e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="5290e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="5290e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="5290e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="5290e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> enableWebScript**</span><span class="sxs-lookup"><span data-stu-id="5290e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<enableWebScript>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5290e-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5290e-109">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5290e-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5290e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5290e-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5290e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5290e-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="5290e-112">Attributes</span></span>  
 <span data-ttu-id="5290e-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5290e-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5290e-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5290e-114">Child Elements</span></span>  
 <span data-ttu-id="5290e-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5290e-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5290e-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5290e-116">Parent Elements</span></span>  
  
|<span data-ttu-id="5290e-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="5290e-117">Element</span></span>|<span data-ttu-id="5290e-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5290e-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5290e-119">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="5290e-119">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="5290e-120">Especifica el conjunto de comportamientos del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="5290e-120">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5290e-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5290e-121">Remarks</span></span>  
 <span data-ttu-id="5290e-122">Este comportamiento solo se debe usar junto con la [ \<>](webhttpbinding.md) de enlace de webHttpBinding o el elemento de enlace de [ \<> de webMessageEncoding](webmessageencoding.md) .</span><span class="sxs-lookup"><span data-stu-id="5290e-122">This behavior should only be used in conjunction with either the [\<webHttpBinding>](webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="5290e-123">Para obtener más información sobre este comportamiento, vea <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span><span class="sxs-lookup"><span data-stu-id="5290e-123">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5290e-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="5290e-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [<span data-ttu-id="5290e-125">Integración de AJAX y compatibilidad de JSON</span><span class="sxs-lookup"><span data-stu-id="5290e-125">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="5290e-126">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="5290e-126">\<webHttp></span></span>](webhttp.md)
