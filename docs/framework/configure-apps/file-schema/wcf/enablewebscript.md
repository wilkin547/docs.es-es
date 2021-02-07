---
description: 'Más información acerca de: <enableWebScript>'
title: <enableWebScript>
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: f357bf1ab726cd434a16b2daa9c8115afe7d4430
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725888"
---
# \<enableWebScript>

<span data-ttu-id="af20e-102">Este elemento habilita el comportamiento del extremo que permite utilizar el servicio de las páginas web de AJAX de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="af20e-102">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<enableWebScript>**  
  
## <a name="syntax"></a><span data-ttu-id="af20e-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="af20e-103">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af20e-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="af20e-104">Attributes and Elements</span></span>  

 <span data-ttu-id="af20e-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="af20e-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af20e-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="af20e-106">Attributes</span></span>  

 <span data-ttu-id="af20e-107">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="af20e-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="af20e-108">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="af20e-108">Child Elements</span></span>  

 <span data-ttu-id="af20e-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="af20e-109">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="af20e-110">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="af20e-110">Parent Elements</span></span>  
  
|<span data-ttu-id="af20e-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="af20e-111">Element</span></span>|<span data-ttu-id="af20e-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="af20e-112">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="af20e-113">Especifica el conjunto de comportamientos del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="af20e-113">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af20e-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="af20e-114">Remarks</span></span>  

 <span data-ttu-id="af20e-115">Este comportamiento solo se debe usar junto con el [\<webHttpBinding>](webhttpbinding.md) enlace estándar o el [\<webMessageEncoding>](webmessageencoding.md) elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="af20e-115">This behavior should only be used in conjunction with either the [\<webHttpBinding>](webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="af20e-116">Para obtener más información sobre este comportamiento, vea <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span><span class="sxs-lookup"><span data-stu-id="af20e-116">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af20e-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="af20e-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [<span data-ttu-id="af20e-118">Integración de AJAX y compatibilidad de JSON</span><span class="sxs-lookup"><span data-stu-id="af20e-118">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [\<webHttp>](webhttp.md)
