---
title: '&lt;webScriptEndpoint&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 855a0fc0727bf0559b922317d439f7550f18d9ca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltwebscriptendpointgt"></a><span data-ttu-id="6b4c4-102">&lt;webScriptEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="6b4c4-102">&lt;webScriptEndpoint&gt;</span></span>
<span data-ttu-id="6b4c4-103">Este elemento de configuración define un extremo estándar con un fijo [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) enlace que automáticamente se agrega el [ \<enableWebScript >](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) comportamiento.</span><span class="sxs-lookup"><span data-stu-id="6b4c4-103">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) behavior.</span></span> <span data-ttu-id="6b4c4-104">Use este punto de conexión cuando esté escribiendo un servicio al que se llama desde una aplicación AJAX de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="6b4c4-104">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
<span data-ttu-id="6b4c4-105">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="6b4c4-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="6b4c4-106">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="6b4c4-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b4c4-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6b4c4-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String"/>
    </webScriptEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6b4c4-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6b4c4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6b4c4-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6b4c4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6b4c4-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="6b4c4-110">Attributes</span></span>  
  
|<span data-ttu-id="6b4c4-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="6b4c4-111">Attribute</span></span>|<span data-ttu-id="6b4c4-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="6b4c4-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6b4c4-113">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="6b4c4-113">webEndpointType</span></span>|<span data-ttu-id="6b4c4-114">Cadena que especifica el tipo de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="6b4c4-114">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6b4c4-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6b4c4-115">Child Elements</span></span>  
 <span data-ttu-id="6b4c4-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6b4c4-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6b4c4-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6b4c4-117">Parent Elements</span></span>  
  
|<span data-ttu-id="6b4c4-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="6b4c4-118">Element</span></span>|<span data-ttu-id="6b4c4-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="6b4c4-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6b4c4-120">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="6b4c4-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="6b4c4-121">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="6b4c4-121">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6b4c4-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b4c4-122">See Also</span></span>  
 <xref:System.ServiceModel.Description.WebScriptEndpoint>  
 <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
