---
title: <enableWebScript>
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: 9c9bbb9ccc7879510ae3e2bee2fabd604fd52f65
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266655"
---
# <a name="enablewebscript"></a><span data-ttu-id="0e9fc-101">\<enableWebScript></span><span class="sxs-lookup"><span data-stu-id="0e9fc-101">\<enableWebScript></span></span>
<span data-ttu-id="0e9fc-102">Este elemento habilita el comportamiento del punto de conexión que permite utilizar el servicio de las páginas web de AJAX de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="0e9fc-102">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
 <span data-ttu-id="0e9fc-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0e9fc-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="0e9fc-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="0e9fc-104">\<behaviors></span></span>  
<span data-ttu-id="0e9fc-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="0e9fc-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="0e9fc-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="0e9fc-106">\<behavior></span></span>  
<span data-ttu-id="0e9fc-107">\<enableWebScript></span><span class="sxs-lookup"><span data-stu-id="0e9fc-107">\<enableWebScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e9fc-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0e9fc-108">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0e9fc-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0e9fc-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0e9fc-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0e9fc-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0e9fc-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="0e9fc-111">Attributes</span></span>  
 <span data-ttu-id="0e9fc-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0e9fc-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0e9fc-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0e9fc-113">Child Elements</span></span>  
 <span data-ttu-id="0e9fc-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0e9fc-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0e9fc-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0e9fc-115">Parent Elements</span></span>  
  
|<span data-ttu-id="0e9fc-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="0e9fc-116">Element</span></span>|<span data-ttu-id="0e9fc-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="0e9fc-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0e9fc-118">\<behavior></span><span class="sxs-lookup"><span data-stu-id="0e9fc-118">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="0e9fc-119">Especifica el conjunto de comportamientos del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="0e9fc-119">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e9fc-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0e9fc-120">Remarks</span></span>  
 <span data-ttu-id="0e9fc-121">Este comportamiento solo debe usarse junto con el [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) enlace estándar, o la [ \<webMessageEncoding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="0e9fc-121">This behavior should only be used in conjunction with either the [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="0e9fc-122">Para obtener más información sobre este comportamiento, vea <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span><span class="sxs-lookup"><span data-stu-id="0e9fc-122">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e9fc-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e9fc-123">See also</span></span>
- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [<span data-ttu-id="0e9fc-124">Integración de AJAX y compatibilidad de JSON</span><span class="sxs-lookup"><span data-stu-id="0e9fc-124">AJAX Integration and JSON Support</span></span>](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="0e9fc-125">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="0e9fc-125">\<webHttp></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)
