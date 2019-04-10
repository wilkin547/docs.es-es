---
title: <enableWebScript>
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: b2cdd29cda7f82ce555b0f6c1a963567b41ff81b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213004"
---
# <a name="enablewebscript"></a><span data-ttu-id="783a7-101">\<enableWebScript></span><span class="sxs-lookup"><span data-stu-id="783a7-101">\<enableWebScript></span></span>
<span data-ttu-id="783a7-102">Este elemento habilita el comportamiento del extremo que permite utilizar el servicio de las páginas web de AJAX de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="783a7-102">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
 <span data-ttu-id="783a7-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="783a7-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="783a7-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="783a7-104">\<behaviors></span></span>  
<span data-ttu-id="783a7-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="783a7-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="783a7-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="783a7-106">\<behavior></span></span>  
<span data-ttu-id="783a7-107">\<enableWebScript></span><span class="sxs-lookup"><span data-stu-id="783a7-107">\<enableWebScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="783a7-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="783a7-108">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="783a7-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="783a7-109">Attributes and Elements</span></span>  
 <span data-ttu-id="783a7-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="783a7-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="783a7-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="783a7-111">Attributes</span></span>  
 <span data-ttu-id="783a7-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="783a7-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="783a7-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="783a7-113">Child Elements</span></span>  
 <span data-ttu-id="783a7-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="783a7-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="783a7-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="783a7-115">Parent Elements</span></span>  
  
|<span data-ttu-id="783a7-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="783a7-116">Element</span></span>|<span data-ttu-id="783a7-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="783a7-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="783a7-118">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="783a7-118">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="783a7-119">Especifica el conjunto de comportamientos del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="783a7-119">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="783a7-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="783a7-120">Remarks</span></span>  
 <span data-ttu-id="783a7-121">Este comportamiento solo debe usarse junto con el [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) enlace estándar, o la [ \<webMessageEncoding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="783a7-121">This behavior should only be used in conjunction with either the [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="783a7-122">Para obtener más información sobre este comportamiento, vea <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span><span class="sxs-lookup"><span data-stu-id="783a7-122">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="783a7-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="783a7-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [<span data-ttu-id="783a7-124">Integración de AJAX y compatibilidad de JSON</span><span class="sxs-lookup"><span data-stu-id="783a7-124">AJAX Integration and JSON Support</span></span>](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="783a7-125">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="783a7-125">\<webHttp></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)
