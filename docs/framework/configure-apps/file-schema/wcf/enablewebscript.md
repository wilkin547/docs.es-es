---
title: '&lt;enableWebScript&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f6dc2654b8c51dad53c05a37f5febe15d6d69fd1
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltenablewebscriptgt"></a><span data-ttu-id="7ec27-102">&lt;enableWebScript&gt;</span><span class="sxs-lookup"><span data-stu-id="7ec27-102">&lt;enableWebScript&gt;</span></span>
<span data-ttu-id="7ec27-103">Este elemento habilita el comportamiento del punto de conexión que permite utilizar el servicio de las páginas web de AJAX de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="7ec27-103">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
 <span data-ttu-id="7ec27-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="7ec27-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7ec27-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="7ec27-105">\<behaviors></span></span>  
<span data-ttu-id="7ec27-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="7ec27-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="7ec27-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="7ec27-107">\<behavior></span></span>  
<span data-ttu-id="7ec27-108">\<enableWebScript ></span><span class="sxs-lookup"><span data-stu-id="7ec27-108">\<enableWebScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ec27-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7ec27-109">Syntax</span></span>  
  
```xml  
<enableWebScript />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7ec27-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7ec27-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7ec27-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7ec27-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7ec27-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="7ec27-112">Attributes</span></span>  
 <span data-ttu-id="7ec27-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7ec27-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7ec27-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7ec27-114">Child Elements</span></span>  
 <span data-ttu-id="7ec27-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7ec27-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7ec27-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7ec27-116">Parent Elements</span></span>  
  
|<span data-ttu-id="7ec27-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="7ec27-117">Element</span></span>|<span data-ttu-id="7ec27-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ec27-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7ec27-119">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="7ec27-119">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="7ec27-120">Especifica el conjunto de comportamientos del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="7ec27-120">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ec27-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7ec27-121">Remarks</span></span>  
 <span data-ttu-id="7ec27-122">Este comportamiento solo se debería usar junto con cualquiera el [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) enlace estándar, o la [ \<webMessageEncoding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="7ec27-122">This behavior should only be used in conjunction with either the [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="7ec27-123">Para obtener más información sobre este comportamiento, vea <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span><span class="sxs-lookup"><span data-stu-id="7ec27-123">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ec27-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ec27-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>  
 <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>  
 [<span data-ttu-id="7ec27-125">Integración de AJAX y compatibilidad de JSON</span><span class="sxs-lookup"><span data-stu-id="7ec27-125">AJAX Integration and JSON Support</span></span>](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)  
 [<span data-ttu-id="7ec27-126">\<webHttp ></span><span class="sxs-lookup"><span data-stu-id="7ec27-126">\<webHttp></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)
