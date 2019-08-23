---
title: <webHttp>
ms.date: 03/30/2017
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
ms.openlocfilehash: 366def5d0f4cc82b0ff0a5127701b0b5a6adb6a0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940503"
---
# <a name="webhttp"></a><span data-ttu-id="76bb3-101">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="76bb3-101">\<webHttp></span></span>
<span data-ttu-id="76bb3-102">Este elemento especifica <xref:System.ServiceModel.Description.WebHttpBehavior> en un punto de conexión a través de la configuración.</span><span class="sxs-lookup"><span data-stu-id="76bb3-102">This element specifies the <xref:System.ServiceModel.Description.WebHttpBehavior> on an endpoint through configuration.</span></span> <span data-ttu-id="76bb3-103">Este comportamiento, cuando se usa junto con [ \<webHttpBinding >](webhttpbinding.md) enlace estándar, habilita el modelo de programación web para un servicio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="76bb3-103">This behavior, when used in conjunction with the [\<webHttpBinding>](webhttpbinding.md) standard binding, enables the Web programming model for a Windows Communication Foundation (WCF) service.</span></span>  
  
 <span data-ttu-id="76bb3-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="76bb3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="76bb3-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="76bb3-105">\<behaviors></span></span>  
<span data-ttu-id="76bb3-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="76bb3-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="76bb3-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="76bb3-107">\<behavior></span></span>  
<span data-ttu-id="76bb3-108">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="76bb3-108">\<webHttp></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76bb3-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="76bb3-109">Syntax</span></span>  
  
```xml  
<webHttp />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="76bb3-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="76bb3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="76bb3-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="76bb3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="76bb3-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="76bb3-112">Attributes</span></span>  
  
|<span data-ttu-id="76bb3-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="76bb3-113">Attribute</span></span>|<span data-ttu-id="76bb3-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="76bb3-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="76bb3-115">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="76bb3-115">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="76bb3-116">Cuando esta propiedad está establecida en `true`, la infraestructura de WCF determina el mejor formato que se debe usar.</span><span class="sxs-lookup"><span data-stu-id="76bb3-116">When this property is set to `true`, the WCF infrastructure determines the best format to use.</span></span> <span data-ttu-id="76bb3-117">La selección de formato automática está deshabilitada de forma predeterminada para la compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="76bb3-117">Automatic format selection is disabled by default for backwards compatibility.</span></span> <span data-ttu-id="76bb3-118">La selección de formato automática puede habilitarse mediante programación o a través de la configuración.</span><span class="sxs-lookup"><span data-stu-id="76bb3-118">Automatic format selection can be enabled programmatically or through configuration.</span></span>|  
|<span data-ttu-id="76bb3-119">defaultBodyStyle</span><span class="sxs-lookup"><span data-stu-id="76bb3-119">defaultBodyStyle</span></span>|<span data-ttu-id="76bb3-120">Especifica el estilo de cuerpo predeterminado de los mensajes devueltos.</span><span class="sxs-lookup"><span data-stu-id="76bb3-120">Specifies the default body style of returned messages.</span></span> <span data-ttu-id="76bb3-121">Para obtener más información, <xref:System.ServiceModel.Web.WebMessageBodyStyle> consulte y el [formato de web http de WCF](../../../wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="76bb3-121">For more information, see <xref:System.ServiceModel.Web.WebMessageBodyStyle> and [WCF Web HTTP Formatting](../../../wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="76bb3-122">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="76bb3-122">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="76bb3-123">Especifica el formato de respuesta de salida predeterminado de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="76bb3-123">Specifies the default outgoing response format for messages.</span></span> <span data-ttu-id="76bb3-124">Para obtener más información, consulte [formato de web http de WCF](../../../wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="76bb3-124">For more information, see [WCF Web HTTP Formatting](../../../wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="76bb3-125">faultExceptionEnabled</span><span class="sxs-lookup"><span data-stu-id="76bb3-125">faultExceptionEnabled</span></span>|<span data-ttu-id="76bb3-126">Obtiene o establece la marca que especifica si se genera FaultException cuando se produce un error de servidor interno (código de estado HTTP: 500).</span><span class="sxs-lookup"><span data-stu-id="76bb3-126">Gets or sets the flag that specifies whether a FaultException is generated when an internal server error (HTTP status code: 500) occurs.</span></span>|  
|<span data-ttu-id="76bb3-127">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="76bb3-127">helpEnabled</span></span>|<span data-ttu-id="76bb3-128">Obtiene o establece un valor que determina si la página de Ayuda está habilitada.</span><span class="sxs-lookup"><span data-stu-id="76bb3-128">Gets or sets a value that determines if the Help page is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="76bb3-129">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="76bb3-129">Child Elements</span></span>  
 <span data-ttu-id="76bb3-130">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="76bb3-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="76bb3-131">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="76bb3-131">Parent Elements</span></span>  
  
|<span data-ttu-id="76bb3-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="76bb3-132">Element</span></span>|<span data-ttu-id="76bb3-133">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="76bb3-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="76bb3-134">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="76bb3-134">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="76bb3-135">Especifica el conjunto de comportamientos del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="76bb3-135">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="76bb3-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="76bb3-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpElement>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [<span data-ttu-id="76bb3-137">Integración de AJAX y compatibilidad de JSON</span><span class="sxs-lookup"><span data-stu-id="76bb3-137">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="76bb3-138">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="76bb3-138">\<webHttpBinding></span></span>](webhttpbinding.md)
