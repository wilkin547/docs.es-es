---
title: '&lt;webHttp&gt;'
ms.date: 03/30/2017
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
ms.openlocfilehash: b52259af5e05de5bf5dd42a2cd0bf4b01f3e46f9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597559"
---
# <a name="ltwebhttpgt"></a><span data-ttu-id="3701a-102">&lt;webHttp&gt;</span><span class="sxs-lookup"><span data-stu-id="3701a-102">&lt;webHttp&gt;</span></span>
<span data-ttu-id="3701a-103">Este elemento especifica <xref:System.ServiceModel.Description.WebHttpBehavior> en un punto de conexión a través de la configuración.</span><span class="sxs-lookup"><span data-stu-id="3701a-103">This element specifies the <xref:System.ServiceModel.Description.WebHttpBehavior> on an endpoint through configuration.</span></span> <span data-ttu-id="3701a-104">Este comportamiento, cuando se usa junto con el [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) enlace estándar, permite que el modelo de programación Web para un servicio de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="3701a-104">This behavior, when used in conjunction with the [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standard binding, enables the Web programming model for a Windows Communication Foundation (WCF) service.</span></span>  
  
 <span data-ttu-id="3701a-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3701a-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="3701a-106">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="3701a-106">\<behaviors></span></span>  
<span data-ttu-id="3701a-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="3701a-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="3701a-108">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="3701a-108">\<behavior></span></span>  
<span data-ttu-id="3701a-109">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="3701a-109">\<webHttp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3701a-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3701a-110">Syntax</span></span>  
  
```xml  
<webHttp />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3701a-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3701a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="3701a-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3701a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3701a-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="3701a-113">Attributes</span></span>  
  
|<span data-ttu-id="3701a-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="3701a-114">Attribute</span></span>|<span data-ttu-id="3701a-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="3701a-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3701a-116">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="3701a-116">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="3701a-117">Cuando esta propiedad está establecida en `true`, la infraestructura de WCF determina el mejor formato que se debe usar.</span><span class="sxs-lookup"><span data-stu-id="3701a-117">When this property is set to `true`, the WCF infrastructure determines the best format to use.</span></span> <span data-ttu-id="3701a-118">La selección de formato automática está deshabilitada de forma predeterminada para la compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="3701a-118">Automatic format selection is disabled by default for backwards compatibility.</span></span> <span data-ttu-id="3701a-119">La selección de formato automática puede habilitarse mediante programación o a través de la configuración.</span><span class="sxs-lookup"><span data-stu-id="3701a-119">Automatic format selection can be enabled programmatically or through configuration.</span></span>|  
|<span data-ttu-id="3701a-120">defaultBodyStyle</span><span class="sxs-lookup"><span data-stu-id="3701a-120">defaultBodyStyle</span></span>|<span data-ttu-id="3701a-121">Especifica el estilo de cuerpo predeterminado de los mensajes devueltos.</span><span class="sxs-lookup"><span data-stu-id="3701a-121">Specifies the default body style of returned messages.</span></span> <span data-ttu-id="3701a-122">Para obtener más información, consulte <xref:System.ServiceModel.Web.WebMessageBodyStyle> y [WCF Web HTTP formato](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="3701a-122">For more information, see <xref:System.ServiceModel.Web.WebMessageBodyStyle> and [WCF Web HTTP Formatting](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="3701a-123">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="3701a-123">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="3701a-124">Especifica el formato de respuesta de salida predeterminado de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="3701a-124">Specifies the default outgoing response format for messages.</span></span> <span data-ttu-id="3701a-125">Para obtener más información, consulte [WCF Web HTTP formato](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="3701a-125">For more information, see [WCF Web HTTP Formatting](../../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="3701a-126">faultExceptionEnabled</span><span class="sxs-lookup"><span data-stu-id="3701a-126">faultExceptionEnabled</span></span>|<span data-ttu-id="3701a-127">Obtiene o establece la marca que especifica si se genera FaultException cuando se produce un error de servidor interno (código de estado HTTP: 500).</span><span class="sxs-lookup"><span data-stu-id="3701a-127">Gets or sets the flag that specifies whether a FaultException is generated when an internal server error (HTTP status code: 500) occurs.</span></span>|  
|<span data-ttu-id="3701a-128">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="3701a-128">helpEnabled</span></span>|<span data-ttu-id="3701a-129">Obtiene o establece un valor que determina si la página de Ayuda está habilitada.</span><span class="sxs-lookup"><span data-stu-id="3701a-129">Gets or sets a value that determines if the Help page is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3701a-130">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3701a-130">Child Elements</span></span>  
 <span data-ttu-id="3701a-131">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3701a-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3701a-132">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3701a-132">Parent Elements</span></span>  
  
|<span data-ttu-id="3701a-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="3701a-133">Element</span></span>|<span data-ttu-id="3701a-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="3701a-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3701a-135">\<behavior></span><span class="sxs-lookup"><span data-stu-id="3701a-135">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="3701a-136">Especifica el conjunto de comportamientos del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="3701a-136">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3701a-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="3701a-137">See also</span></span>
- <xref:System.ServiceModel.Configuration.WebHttpElement>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [<span data-ttu-id="3701a-138">Integración de AJAX y compatibilidad de JSON</span><span class="sxs-lookup"><span data-stu-id="3701a-138">AJAX Integration and JSON Support</span></span>](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="3701a-139">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="3701a-139">\<webHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)
