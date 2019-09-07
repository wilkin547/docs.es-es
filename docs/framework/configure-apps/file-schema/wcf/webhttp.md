---
title: <webHttp>
ms.date: 03/30/2017
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
ms.openlocfilehash: 00644d248e6fb85d7cf712620e6ac74405e6b0c3
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399159"
---
# <a name="webhttp"></a><span data-ttu-id="6be91-101">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="6be91-101">\<webHttp></span></span>
<span data-ttu-id="6be91-102">Este elemento especifica <xref:System.ServiceModel.Description.WebHttpBehavior> en un punto de conexión a través de la configuración.</span><span class="sxs-lookup"><span data-stu-id="6be91-102">This element specifies the <xref:System.ServiceModel.Description.WebHttpBehavior> on an endpoint through configuration.</span></span> <span data-ttu-id="6be91-103">Este comportamiento, cuando se usa junto con [ \<webHttpBinding >](webhttpbinding.md) enlace estándar, habilita el modelo de programación web para un servicio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="6be91-103">This behavior, when used in conjunction with the [\<webHttpBinding>](webhttpbinding.md) standard binding, enables the Web programming model for a Windows Communication Foundation (WCF) service.</span></span>  
  
<span data-ttu-id="6be91-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6be91-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6be91-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="6be91-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="6be91-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="6be91-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="6be91-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="6be91-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="6be91-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="6be91-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="6be91-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> webhttp**</span><span class="sxs-lookup"><span data-stu-id="6be91-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webHttp>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6be91-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6be91-110">Syntax</span></span>  
  
```xml  
<webHttp />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6be91-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6be91-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6be91-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6be91-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6be91-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="6be91-113">Attributes</span></span>  
  
|<span data-ttu-id="6be91-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="6be91-114">Attribute</span></span>|<span data-ttu-id="6be91-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="6be91-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6be91-116">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="6be91-116">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="6be91-117">Cuando esta propiedad está establecida en `true`, la infraestructura de WCF determina el mejor formato que se debe usar.</span><span class="sxs-lookup"><span data-stu-id="6be91-117">When this property is set to `true`, the WCF infrastructure determines the best format to use.</span></span> <span data-ttu-id="6be91-118">La selección de formato automática está deshabilitada de forma predeterminada para la compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="6be91-118">Automatic format selection is disabled by default for backwards compatibility.</span></span> <span data-ttu-id="6be91-119">La selección de formato automática puede habilitarse mediante programación o a través de la configuración.</span><span class="sxs-lookup"><span data-stu-id="6be91-119">Automatic format selection can be enabled programmatically or through configuration.</span></span>|  
|<span data-ttu-id="6be91-120">defaultBodyStyle</span><span class="sxs-lookup"><span data-stu-id="6be91-120">defaultBodyStyle</span></span>|<span data-ttu-id="6be91-121">Especifica el estilo de cuerpo predeterminado de los mensajes devueltos.</span><span class="sxs-lookup"><span data-stu-id="6be91-121">Specifies the default body style of returned messages.</span></span> <span data-ttu-id="6be91-122">Para obtener más información, <xref:System.ServiceModel.Web.WebMessageBodyStyle> consulte y el [formato de web http de WCF](../../../wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="6be91-122">For more information, see <xref:System.ServiceModel.Web.WebMessageBodyStyle> and [WCF Web HTTP Formatting](../../../wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="6be91-123">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="6be91-123">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="6be91-124">Especifica el formato de respuesta de salida predeterminado de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="6be91-124">Specifies the default outgoing response format for messages.</span></span> <span data-ttu-id="6be91-125">Para obtener más información, consulte [formato de web http de WCF](../../../wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="6be91-125">For more information, see [WCF Web HTTP Formatting](../../../wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="6be91-126">faultExceptionEnabled</span><span class="sxs-lookup"><span data-stu-id="6be91-126">faultExceptionEnabled</span></span>|<span data-ttu-id="6be91-127">Obtiene o establece la marca que especifica si se genera FaultException cuando se produce un error de servidor interno (código de estado HTTP: 500).</span><span class="sxs-lookup"><span data-stu-id="6be91-127">Gets or sets the flag that specifies whether a FaultException is generated when an internal server error (HTTP status code: 500) occurs.</span></span>|  
|<span data-ttu-id="6be91-128">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="6be91-128">helpEnabled</span></span>|<span data-ttu-id="6be91-129">Obtiene o establece un valor que determina si la página de Ayuda está habilitada.</span><span class="sxs-lookup"><span data-stu-id="6be91-129">Gets or sets a value that determines if the Help page is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6be91-130">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6be91-130">Child Elements</span></span>  
 <span data-ttu-id="6be91-131">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6be91-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6be91-132">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6be91-132">Parent Elements</span></span>  
  
|<span data-ttu-id="6be91-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="6be91-133">Element</span></span>|<span data-ttu-id="6be91-134">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="6be91-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6be91-135">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="6be91-135">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="6be91-136">Especifica el conjunto de comportamientos del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="6be91-136">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6be91-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="6be91-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpElement>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [<span data-ttu-id="6be91-138">Integración de AJAX y compatibilidad de JSON</span><span class="sxs-lookup"><span data-stu-id="6be91-138">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="6be91-139">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="6be91-139">\<webHttpBinding></span></span>](webhttpbinding.md)
