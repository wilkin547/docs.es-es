---
title: '&lt;webHttp&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0b5388a680816bca6051525f5130308a3c7c2dc5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltwebhttpgt"></a><span data-ttu-id="1e483-102">&lt;webHttp&gt;</span><span class="sxs-lookup"><span data-stu-id="1e483-102">&lt;webHttp&gt;</span></span>
<span data-ttu-id="1e483-103">Este elemento especifica <xref:System.ServiceModel.Description.WebHttpBehavior> en un extremo a través de la configuración.</span><span class="sxs-lookup"><span data-stu-id="1e483-103">This element specifies the <xref:System.ServiceModel.Description.WebHttpBehavior> on an endpoint through configuration.</span></span> <span data-ttu-id="1e483-104">Este comportamiento, cuando se usa junto con el [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) enlace estándar, permite que el modelo de programación Web para un [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] servicio.</span><span class="sxs-lookup"><span data-stu-id="1e483-104">This behavior, when used in conjunction with the [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standard binding, enables the Web programming model for a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service.</span></span>  
  
 <span data-ttu-id="1e483-105">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="1e483-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="1e483-106">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="1e483-106">\<behaviors></span></span>  
<span data-ttu-id="1e483-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="1e483-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="1e483-108">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="1e483-108">\<behavior></span></span>  
<span data-ttu-id="1e483-109">\<webHttp ></span><span class="sxs-lookup"><span data-stu-id="1e483-109">\<webHttp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e483-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1e483-110">Syntax</span></span>  
  
```xml  
<webHttp />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1e483-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1e483-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1e483-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1e483-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1e483-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="1e483-113">Attributes</span></span>  
  
|<span data-ttu-id="1e483-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="1e483-114">Attribute</span></span>|<span data-ttu-id="1e483-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="1e483-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1e483-116">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="1e483-116">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="1e483-117">Cuando esta propiedad está establecida en `true`, la infraestructura de WCF determina el mejor formato que se debe usar.</span><span class="sxs-lookup"><span data-stu-id="1e483-117">When this property is set to `true`, the WCF infrastructure determines the best format to use.</span></span> <span data-ttu-id="1e483-118">La selección de formato automática está deshabilitada de forma predeterminada para la compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="1e483-118">Automatic format selection is disabled by default for backwards compatibility.</span></span> <span data-ttu-id="1e483-119">La selección de formato automática puede habilitarse mediante programación o a través de la configuración.</span><span class="sxs-lookup"><span data-stu-id="1e483-119">Automatic format selection can be enabled programmatically or through configuration.</span></span>|  
|<span data-ttu-id="1e483-120">defaultBodyStyle</span><span class="sxs-lookup"><span data-stu-id="1e483-120">defaultBodyStyle</span></span>|<span data-ttu-id="1e483-121">Especifica el estilo de cuerpo predeterminado de los mensajes devueltos.</span><span class="sxs-lookup"><span data-stu-id="1e483-121">Specifies the default body style of returned messages.</span></span> [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)]<span data-ttu-id="1e483-122"><xref:System.ServiceModel.Web.WebMessageBodyStyle> y [Web HTTP de WCF formato](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="1e483-122"> <xref:System.ServiceModel.Web.WebMessageBodyStyle> and [WCF Web HTTP Formatting](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="1e483-123">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="1e483-123">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="1e483-124">Especifica el formato de respuesta de salida predeterminado de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="1e483-124">Specifies the default outgoing response format for messages.</span></span> [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)]<span data-ttu-id="1e483-125">[Web HTTP de WCF formato](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="1e483-125"> [WCF Web HTTP Formatting](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="1e483-126">faultExceptionEnabled</span><span class="sxs-lookup"><span data-stu-id="1e483-126">faultExceptionEnabled</span></span>|<span data-ttu-id="1e483-127">Obtiene o establece la marca que especifica si se genera FaultException cuando se produce un error de servidor interno (código de estado HTTP: 500).</span><span class="sxs-lookup"><span data-stu-id="1e483-127">Gets or sets the flag that specifies whether a FaultException is generated when an internal server error (HTTP status code: 500) occurs.</span></span>|  
|<span data-ttu-id="1e483-128">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="1e483-128">helpEnabled</span></span>|<span data-ttu-id="1e483-129">Obtiene o establece un valor que determina si la página de Ayuda está habilitada.</span><span class="sxs-lookup"><span data-stu-id="1e483-129">Gets or sets a value that determines if the Help page is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1e483-130">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1e483-130">Child Elements</span></span>  
 <span data-ttu-id="1e483-131">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1e483-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1e483-132">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1e483-132">Parent Elements</span></span>  
  
|<span data-ttu-id="1e483-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="1e483-133">Element</span></span>|<span data-ttu-id="1e483-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="1e483-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1e483-135">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="1e483-135">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="1e483-136">Especifica el conjunto de comportamientos del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="1e483-136">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1e483-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e483-137">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WebHttpElement>  
 <xref:System.ServiceModel.Description.WebHttpBehavior>  
 [<span data-ttu-id="1e483-138">Integración de AJAX y compatibilidad de JSON</span><span class="sxs-lookup"><span data-stu-id="1e483-138">AJAX Integration and JSON Support</span></span>](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)  
 [<span data-ttu-id="1e483-139">\<webHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="1e483-139">\<webHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)
