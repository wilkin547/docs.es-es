---
description: 'Más información acerca de: <webHttp>'
title: <webHttp>
ms.date: 03/30/2017
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
ms.openlocfilehash: acd8d77e00828d132d076c867ff3164ca1ba7230
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664384"
---
# \<webHttp>

<span data-ttu-id="f9860-102">Este elemento especifica <xref:System.ServiceModel.Description.WebHttpBehavior> en un punto de conexión a través de la configuración.</span><span class="sxs-lookup"><span data-stu-id="f9860-102">This element specifies the <xref:System.ServiceModel.Description.WebHttpBehavior> on an endpoint through configuration.</span></span> <span data-ttu-id="f9860-103">Este comportamiento, cuando se usa junto con el [\<webHttpBinding>](webhttpbinding.md) enlace estándar, habilita el modelo de programación web para un servicio de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="f9860-103">This behavior, when used in conjunction with the [\<webHttpBinding>](webhttpbinding.md) standard binding, enables the Web programming model for a Windows Communication Foundation (WCF) service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webHttp>**  
  
## <a name="syntax"></a><span data-ttu-id="f9860-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f9860-104">Syntax</span></span>  
  
```xml  
<webHttp />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f9860-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f9860-105">Attributes and Elements</span></span>  

 <span data-ttu-id="f9860-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f9860-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f9860-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="f9860-107">Attributes</span></span>  
  
|<span data-ttu-id="f9860-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="f9860-108">Attribute</span></span>|<span data-ttu-id="f9860-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="f9860-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f9860-110">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="f9860-110">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="f9860-111">Cuando esta propiedad está establecida en `true`, la infraestructura de WCF determina el mejor formato que se debe usar.</span><span class="sxs-lookup"><span data-stu-id="f9860-111">When this property is set to `true`, the WCF infrastructure determines the best format to use.</span></span> <span data-ttu-id="f9860-112">La selección de formato automática está deshabilitada de forma predeterminada para la compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="f9860-112">Automatic format selection is disabled by default for backwards compatibility.</span></span> <span data-ttu-id="f9860-113">La selección de formato automática puede habilitarse mediante programación o a través de la configuración.</span><span class="sxs-lookup"><span data-stu-id="f9860-113">Automatic format selection can be enabled programmatically or through configuration.</span></span>|  
|<span data-ttu-id="f9860-114">defaultBodyStyle</span><span class="sxs-lookup"><span data-stu-id="f9860-114">defaultBodyStyle</span></span>|<span data-ttu-id="f9860-115">Especifica el estilo de cuerpo predeterminado de los mensajes devueltos.</span><span class="sxs-lookup"><span data-stu-id="f9860-115">Specifies the default body style of returned messages.</span></span> <span data-ttu-id="f9860-116">Para obtener más información, consulte <xref:System.ServiceModel.Web.WebMessageBodyStyle> y el [formato de web http de WCF](../../../wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="f9860-116">For more information, see <xref:System.ServiceModel.Web.WebMessageBodyStyle> and [WCF Web HTTP Formatting](../../../wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="f9860-117">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="f9860-117">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="f9860-118">Especifica el formato de respuesta de salida predeterminado de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="f9860-118">Specifies the default outgoing response format for messages.</span></span> <span data-ttu-id="f9860-119">Para obtener más información, consulte [formato de web http de WCF](../../../wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="f9860-119">For more information, see [WCF Web HTTP Formatting](../../../wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="f9860-120">faultExceptionEnabled</span><span class="sxs-lookup"><span data-stu-id="f9860-120">faultExceptionEnabled</span></span>|<span data-ttu-id="f9860-121">Obtiene o establece la marca que especifica si se genera FaultException cuando se produce un error de servidor interno (código de estado HTTP: 500).</span><span class="sxs-lookup"><span data-stu-id="f9860-121">Gets or sets the flag that specifies whether a FaultException is generated when an internal server error (HTTP status code: 500) occurs.</span></span>|  
|<span data-ttu-id="f9860-122">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="f9860-122">helpEnabled</span></span>|<span data-ttu-id="f9860-123">Obtiene o establece un valor que determina si la página de Ayuda está habilitada.</span><span class="sxs-lookup"><span data-stu-id="f9860-123">Gets or sets a value that determines if the Help page is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f9860-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f9860-124">Child Elements</span></span>  

 <span data-ttu-id="f9860-125">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f9860-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f9860-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f9860-126">Parent Elements</span></span>  
  
|<span data-ttu-id="f9860-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="f9860-127">Element</span></span>|<span data-ttu-id="f9860-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="f9860-128">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="f9860-129">Especifica el conjunto de comportamientos del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="f9860-129">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f9860-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9860-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpElement>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [<span data-ttu-id="f9860-131">Integración de AJAX y compatibilidad de JSON</span><span class="sxs-lookup"><span data-stu-id="f9860-131">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [\<webHttpBinding>](webhttpbinding.md)
