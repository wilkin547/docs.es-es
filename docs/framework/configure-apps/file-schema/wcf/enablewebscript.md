---
title: <enableWebScript>
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: 20c0057c80b668df97379d0168bb7c005d9927ce
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400388"
---
# \<enableWebScript>
<span data-ttu-id="1fabd-101">Este elemento habilita el comportamiento del extremo que permite utilizar el servicio de las páginas web de AJAX de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="1fabd-101">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<enableWebScript>**  
  
## <a name="syntax"></a><span data-ttu-id="1fabd-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1fabd-102">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1fabd-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1fabd-103">Attributes and Elements</span></span>  
 <span data-ttu-id="1fabd-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1fabd-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1fabd-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="1fabd-105">Attributes</span></span>  
 <span data-ttu-id="1fabd-106">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1fabd-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1fabd-107">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1fabd-107">Child Elements</span></span>  
 <span data-ttu-id="1fabd-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1fabd-108">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1fabd-109">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1fabd-109">Parent Elements</span></span>  
  
|<span data-ttu-id="1fabd-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="1fabd-110">Element</span></span>|<span data-ttu-id="1fabd-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="1fabd-111">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="1fabd-112">Especifica el conjunto de comportamientos del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="1fabd-112">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1fabd-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1fabd-113">Remarks</span></span>  
 <span data-ttu-id="1fabd-114">Este comportamiento solo se debe usar junto con el [\<webHttpBinding>](webhttpbinding.md) enlace estándar o el [\<webMessageEncoding>](webmessageencoding.md) elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="1fabd-114">This behavior should only be used in conjunction with either the [\<webHttpBinding>](webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="1fabd-115">Para obtener más información sobre este comportamiento, vea <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span><span class="sxs-lookup"><span data-stu-id="1fabd-115">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fabd-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1fabd-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [<span data-ttu-id="1fabd-117">Integración de AJAX y compatibilidad de JSON</span><span class="sxs-lookup"><span data-stu-id="1fabd-117">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [\<webHttp>](webhttp.md)
