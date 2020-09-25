---
title: <webHttp>
ms.date: 03/30/2017
ms.assetid: 1f9d0754-d41e-44ce-a298-e51cb3096c64
ms.openlocfilehash: 716d960e2d5f896976c22a60d419d9b165b36178
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202466"
---
# \<webHttp>

<span data-ttu-id="658e1-101">Este elemento especifica <xref:System.ServiceModel.Description.WebHttpBehavior> en un punto de conexión a través de la configuración.</span><span class="sxs-lookup"><span data-stu-id="658e1-101">This element specifies the <xref:System.ServiceModel.Description.WebHttpBehavior> on an endpoint through configuration.</span></span> <span data-ttu-id="658e1-102">Este comportamiento, cuando se usa junto con el [\<webHttpBinding>](webhttpbinding.md) enlace estándar, habilita el modelo de programación web para un servicio de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="658e1-102">This behavior, when used in conjunction with the [\<webHttpBinding>](webhttpbinding.md) standard binding, enables the Web programming model for a Windows Communication Foundation (WCF) service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webHttp>**  
  
## <a name="syntax"></a><span data-ttu-id="658e1-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="658e1-103">Syntax</span></span>  
  
```xml  
<webHttp />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="658e1-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="658e1-104">Attributes and Elements</span></span>  

 <span data-ttu-id="658e1-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="658e1-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="658e1-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="658e1-106">Attributes</span></span>  
  
|<span data-ttu-id="658e1-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="658e1-107">Attribute</span></span>|<span data-ttu-id="658e1-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="658e1-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="658e1-109">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="658e1-109">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="658e1-110">Cuando esta propiedad está establecida en `true`, la infraestructura de WCF determina el mejor formato que se debe usar.</span><span class="sxs-lookup"><span data-stu-id="658e1-110">When this property is set to `true`, the WCF infrastructure determines the best format to use.</span></span> <span data-ttu-id="658e1-111">La selección de formato automática está deshabilitada de forma predeterminada para la compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="658e1-111">Automatic format selection is disabled by default for backwards compatibility.</span></span> <span data-ttu-id="658e1-112">La selección de formato automática puede habilitarse mediante programación o a través de la configuración.</span><span class="sxs-lookup"><span data-stu-id="658e1-112">Automatic format selection can be enabled programmatically or through configuration.</span></span>|  
|<span data-ttu-id="658e1-113">defaultBodyStyle</span><span class="sxs-lookup"><span data-stu-id="658e1-113">defaultBodyStyle</span></span>|<span data-ttu-id="658e1-114">Especifica el estilo de cuerpo predeterminado de los mensajes devueltos.</span><span class="sxs-lookup"><span data-stu-id="658e1-114">Specifies the default body style of returned messages.</span></span> <span data-ttu-id="658e1-115">Para obtener más información, consulte <xref:System.ServiceModel.Web.WebMessageBodyStyle> y el [formato de web http de WCF](../../../wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="658e1-115">For more information, see <xref:System.ServiceModel.Web.WebMessageBodyStyle> and [WCF Web HTTP Formatting](../../../wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="658e1-116">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="658e1-116">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="658e1-117">Especifica el formato de respuesta de salida predeterminado de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="658e1-117">Specifies the default outgoing response format for messages.</span></span> <span data-ttu-id="658e1-118">Para obtener más información, consulte [formato de web http de WCF](../../../wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="658e1-118">For more information, see [WCF Web HTTP Formatting](../../../wcf/feature-details/wcf-web-http-formatting.md).</span></span>|  
|<span data-ttu-id="658e1-119">faultExceptionEnabled</span><span class="sxs-lookup"><span data-stu-id="658e1-119">faultExceptionEnabled</span></span>|<span data-ttu-id="658e1-120">Obtiene o establece la marca que especifica si se genera FaultException cuando se produce un error de servidor interno (código de estado HTTP: 500).</span><span class="sxs-lookup"><span data-stu-id="658e1-120">Gets or sets the flag that specifies whether a FaultException is generated when an internal server error (HTTP status code: 500) occurs.</span></span>|  
|<span data-ttu-id="658e1-121">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="658e1-121">helpEnabled</span></span>|<span data-ttu-id="658e1-122">Obtiene o establece un valor que determina si la página de Ayuda está habilitada.</span><span class="sxs-lookup"><span data-stu-id="658e1-122">Gets or sets a value that determines if the Help page is enabled.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="658e1-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="658e1-123">Child Elements</span></span>  

 <span data-ttu-id="658e1-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="658e1-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="658e1-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="658e1-125">Parent Elements</span></span>  
  
|<span data-ttu-id="658e1-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="658e1-126">Element</span></span>|<span data-ttu-id="658e1-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="658e1-127">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="658e1-128">Especifica el conjunto de comportamientos del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="658e1-128">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="658e1-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="658e1-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpElement>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [<span data-ttu-id="658e1-130">Integración de AJAX y compatibilidad de JSON</span><span class="sxs-lookup"><span data-stu-id="658e1-130">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [\<webHttpBinding>](webhttpbinding.md)
