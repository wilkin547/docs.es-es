---
title: '&lt;webScriptEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: b53b7cc3ce812b72830c0ad83c5cc2b42bfc25a7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltwebscriptendpointgt"></a><span data-ttu-id="88543-102">&lt;webScriptEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="88543-102">&lt;webScriptEndpoint&gt;</span></span>
<span data-ttu-id="88543-103">Este elemento de configuración define un extremo estándar con un fijo [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) enlace que automáticamente se agrega el [ \<enableWebScript >](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) comportamiento.</span><span class="sxs-lookup"><span data-stu-id="88543-103">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) behavior.</span></span> <span data-ttu-id="88543-104">Use este punto de conexión cuando esté escribiendo un servicio al que se llama desde una aplicación AJAX de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="88543-104">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
<span data-ttu-id="88543-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="88543-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="88543-106">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="88543-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88543-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="88543-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String"/>
    </webScriptEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="88543-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="88543-108">Attributes and Elements</span></span>  
 <span data-ttu-id="88543-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="88543-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="88543-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="88543-110">Attributes</span></span>  
  
|<span data-ttu-id="88543-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="88543-111">Attribute</span></span>|<span data-ttu-id="88543-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="88543-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="88543-113">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="88543-113">webEndpointType</span></span>|<span data-ttu-id="88543-114">Cadena que especifica el tipo de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="88543-114">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="88543-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="88543-115">Child Elements</span></span>  
 <span data-ttu-id="88543-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="88543-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="88543-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="88543-117">Parent Elements</span></span>  
  
|<span data-ttu-id="88543-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="88543-118">Element</span></span>|<span data-ttu-id="88543-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="88543-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="88543-120">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="88543-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="88543-121">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="88543-121">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="88543-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="88543-122">See Also</span></span>  
 <xref:System.ServiceModel.Description.WebScriptEndpoint>  
 <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
