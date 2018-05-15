---
title: '&lt;webHttpEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: ecaaeb6f-ebd0-411d-8b53-92477cd45347
ms.openlocfilehash: 46691a36b62898583132b5668b06de5659926d66
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltwebhttpendpointgt"></a><span data-ttu-id="795d9-102">&lt;webHttpEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="795d9-102">&lt;webHttpEndpoint&gt;</span></span>
<span data-ttu-id="795d9-103">Este elemento de configuración define un extremo estándar con un fijo [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) enlace que automáticamente se agrega el [ \<webHttp >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) comportamiento.</span><span class="sxs-lookup"><span data-stu-id="795d9-103">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) binding that automatically adds the [\<webHttp>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) behavior.</span></span> <span data-ttu-id="795d9-104">Utilice este punto de conexión al escribir un servicio REST.</span><span class="sxs-lookup"><span data-stu-id="795d9-104">Use this endpoint when writing a REST service.</span></span>  
  
<span data-ttu-id="795d9-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="795d9-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="795d9-106">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="795d9-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="795d9-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="795d9-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <webHttpEndpoint>
      <standardEndpoint automaticFormatSelectionEnabled="String" 
                        defaultOutgoingResponseFormat="Xml/Json" 
                        helpEnabled="Boolean" 
                        webEndpointType="String"/>
    </webHttpEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="795d9-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="795d9-108">Attributes and Elements</span></span>  
 <span data-ttu-id="795d9-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="795d9-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="795d9-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="795d9-110">Attributes</span></span>  
  
|<span data-ttu-id="795d9-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="795d9-111">Attribute</span></span>|<span data-ttu-id="795d9-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="795d9-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="795d9-113">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="795d9-113">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="795d9-114">Valor booleano que indica si la selección de formato automática está habilitada.</span><span class="sxs-lookup"><span data-stu-id="795d9-114">A Boolean value that indicates whether automatic format selection is enabled.</span></span><br /><br /> <span data-ttu-id="795d9-115">Cuando la selección de formato automática está habilitada, la infraestructura analiza el encabezado `Accept` del mensaje de solicitud y determina el formato de la respuesta más adecuado.</span><span class="sxs-lookup"><span data-stu-id="795d9-115">When automatic format selection is enabled, the infrastructure parses the `Accept` header of the request message and determines the most appropriate response format.</span></span> <span data-ttu-id="795d9-116">Si el encabezado `Accept` no especifica un formato de respuesta adecuado, la infraestructura usa el `Content-Type` del mensaje de solicitud o el formato de respuesta predeterminado de la operación.</span><span class="sxs-lookup"><span data-stu-id="795d9-116">If the `Accept` header does not specify a suitable response format, the infrastructure uses the `Content-Type` of the request message or the default response format of the operation.</span></span>|  
|<span data-ttu-id="795d9-117">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="795d9-117">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="795d9-118">Un atributo que especifica el formato de respuesta saliente predeterminado.</span><span class="sxs-lookup"><span data-stu-id="795d9-118">An attribute that specifies the default outgoing response format.</span></span> <span data-ttu-id="795d9-119">Este atributo es del tipo <xref:System.ServiceModel.Web.WebMessageFormat>.</span><span class="sxs-lookup"><span data-stu-id="795d9-119">This attribute is of the <xref:System.ServiceModel.Web.WebMessageFormat> type</span></span>|  
|<span data-ttu-id="795d9-120">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="795d9-120">helpEnabled</span></span>|<span data-ttu-id="795d9-121">Valor booleano que indica si la página de ayuda HTTP está habilitada para el extremo.</span><span class="sxs-lookup"><span data-stu-id="795d9-121">A Boolean value that indicates whether the HTTP help page is enabled for the endpoint.</span></span>|  
|<span data-ttu-id="795d9-122">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="795d9-122">webEndpointType</span></span>|<span data-ttu-id="795d9-123">Cadena que especifica el tipo de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="795d9-123">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="795d9-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="795d9-124">Child Elements</span></span>  
 <span data-ttu-id="795d9-125">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="795d9-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="795d9-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="795d9-126">Parent Elements</span></span>  
  
|<span data-ttu-id="795d9-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="795d9-127">Element</span></span>|<span data-ttu-id="795d9-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="795d9-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="795d9-129">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="795d9-129">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="795d9-130">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="795d9-130">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="795d9-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="795d9-131">See Also</span></span>  
 <xref:System.ServiceModel.Description.WebHttpEndpoint>  
 <xref:System.ServiceModel.Configuration.WebHttpEndpointElement>
