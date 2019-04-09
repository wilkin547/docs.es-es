---
title: <webHttpEndpoint>
ms.date: 03/30/2017
ms.assetid: ecaaeb6f-ebd0-411d-8b53-92477cd45347
ms.openlocfilehash: 6fb31fca6ac38f6cb92ef087cc277a4d5066521c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182460"
---
# <a name="webhttpendpoint"></a><span data-ttu-id="7b360-101">\<webHttpEndpoint></span><span class="sxs-lookup"><span data-stu-id="7b360-101">\<webHttpEndpoint></span></span>
<span data-ttu-id="7b360-102">Este elemento de configuración define un extremo estándar con un fijo [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) enlace que automáticamente se agrega el [ \<webHttp >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) comportamiento.</span><span class="sxs-lookup"><span data-stu-id="7b360-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) binding that automatically adds the [\<webHttp>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) behavior.</span></span> <span data-ttu-id="7b360-103">Utilice este punto de conexión al escribir un servicio REST.</span><span class="sxs-lookup"><span data-stu-id="7b360-103">Use this endpoint when writing a REST service.</span></span>  
  
<span data-ttu-id="7b360-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="7b360-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7b360-105">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="7b360-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b360-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7b360-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webHttpEndpoint>
      <standardEndpoint automaticFormatSelectionEnabled="String"
                        defaultOutgoingResponseFormat="Xml/Json"
                        helpEnabled="Boolean"
                        webEndpointType="String" />
    </webHttpEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7b360-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7b360-107">Attributes and Elements</span></span>  
 <span data-ttu-id="7b360-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7b360-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7b360-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="7b360-109">Attributes</span></span>  
  
|<span data-ttu-id="7b360-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="7b360-110">Attribute</span></span>|<span data-ttu-id="7b360-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="7b360-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7b360-112">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="7b360-112">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="7b360-113">Valor booleano que indica si la selección de formato automática está habilitada.</span><span class="sxs-lookup"><span data-stu-id="7b360-113">A Boolean value that indicates whether automatic format selection is enabled.</span></span><br /><br /> <span data-ttu-id="7b360-114">Cuando la selección de formato automática está habilitada, la infraestructura analiza el encabezado `Accept` del mensaje de solicitud y determina el formato de la respuesta más adecuado.</span><span class="sxs-lookup"><span data-stu-id="7b360-114">When automatic format selection is enabled, the infrastructure parses the `Accept` header of the request message and determines the most appropriate response format.</span></span> <span data-ttu-id="7b360-115">Si el encabezado `Accept` no especifica un formato de respuesta adecuado, la infraestructura usa el `Content-Type` del mensaje de solicitud o el formato de respuesta predeterminado de la operación.</span><span class="sxs-lookup"><span data-stu-id="7b360-115">If the `Accept` header does not specify a suitable response format, the infrastructure uses the `Content-Type` of the request message or the default response format of the operation.</span></span>|  
|<span data-ttu-id="7b360-116">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="7b360-116">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="7b360-117">Un atributo que especifica el formato de respuesta saliente predeterminado.</span><span class="sxs-lookup"><span data-stu-id="7b360-117">An attribute that specifies the default outgoing response format.</span></span> <span data-ttu-id="7b360-118">Este atributo es del tipo <xref:System.ServiceModel.Web.WebMessageFormat>.</span><span class="sxs-lookup"><span data-stu-id="7b360-118">This attribute is of the <xref:System.ServiceModel.Web.WebMessageFormat> type</span></span>|  
|<span data-ttu-id="7b360-119">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="7b360-119">helpEnabled</span></span>|<span data-ttu-id="7b360-120">Valor booleano que indica si la página de ayuda HTTP está habilitada para el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="7b360-120">A Boolean value that indicates whether the HTTP help page is enabled for the endpoint.</span></span>|  
|<span data-ttu-id="7b360-121">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="7b360-121">webEndpointType</span></span>|<span data-ttu-id="7b360-122">Cadena que especifica el tipo de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="7b360-122">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7b360-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7b360-123">Child Elements</span></span>  
 <span data-ttu-id="7b360-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7b360-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7b360-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7b360-125">Parent Elements</span></span>  
  
|<span data-ttu-id="7b360-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="7b360-126">Element</span></span>|<span data-ttu-id="7b360-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="7b360-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7b360-128">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="7b360-128">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="7b360-129">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="7b360-129">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7b360-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b360-130">See also</span></span>

- <xref:System.ServiceModel.Description.WebHttpEndpoint>
- <xref:System.ServiceModel.Configuration.WebHttpEndpointElement>
