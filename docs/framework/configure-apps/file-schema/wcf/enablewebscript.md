---
title: <enableWebScript>
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: 11378e6cc8cbe8e631fd77ab74c91a616099df52
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190090"
---
# \<enableWebScript>

<span data-ttu-id="eb4aa-101">Este elemento habilita el comportamiento del extremo que permite utilizar el servicio de las páginas web de AJAX de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="eb4aa-101">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<enableWebScript>**  
  
## <a name="syntax"></a><span data-ttu-id="eb4aa-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eb4aa-102">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb4aa-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="eb4aa-103">Attributes and Elements</span></span>  

 <span data-ttu-id="eb4aa-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="eb4aa-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb4aa-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="eb4aa-105">Attributes</span></span>  

 <span data-ttu-id="eb4aa-106">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="eb4aa-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="eb4aa-107">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="eb4aa-107">Child Elements</span></span>  

 <span data-ttu-id="eb4aa-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="eb4aa-108">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eb4aa-109">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="eb4aa-109">Parent Elements</span></span>  
  
|<span data-ttu-id="eb4aa-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="eb4aa-110">Element</span></span>|<span data-ttu-id="eb4aa-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="eb4aa-111">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="eb4aa-112">Especifica el conjunto de comportamientos del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="eb4aa-112">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb4aa-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="eb4aa-113">Remarks</span></span>  

 <span data-ttu-id="eb4aa-114">Este comportamiento solo se debe usar junto con el [\<webHttpBinding>](webhttpbinding.md) enlace estándar o el [\<webMessageEncoding>](webmessageencoding.md) elemento de enlace.</span><span class="sxs-lookup"><span data-stu-id="eb4aa-114">This behavior should only be used in conjunction with either the [\<webHttpBinding>](webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="eb4aa-115">Para obtener más información sobre este comportamiento, vea <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span><span class="sxs-lookup"><span data-stu-id="eb4aa-115">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb4aa-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eb4aa-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [<span data-ttu-id="eb4aa-117">Integración de AJAX y compatibilidad de JSON</span><span class="sxs-lookup"><span data-stu-id="eb4aa-117">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [\<webHttp>](webhttp.md)
