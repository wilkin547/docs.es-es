---
title: <webHttpEndpoint>
ms.date: 03/30/2017
ms.assetid: ecaaeb6f-ebd0-411d-8b53-92477cd45347
ms.openlocfilehash: 866be522cb1c64142227a8d6a1a8f88551ca9105
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940469"
---
# <a name="webhttpendpoint"></a><span data-ttu-id="0a5db-101">\<webHttpEndpoint></span><span class="sxs-lookup"><span data-stu-id="0a5db-101">\<webHttpEndpoint></span></span>
<span data-ttu-id="0a5db-102">Este elemento de configuración define un punto de conexión estándar con un enlace fijo [ \<de webHttpBinding >](webhttpbinding.md) que agrega automáticamente el comportamiento de [ \<> webhttp](webhttp.md) .</span><span class="sxs-lookup"><span data-stu-id="0a5db-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<webHttp>](webhttp.md) behavior.</span></span> <span data-ttu-id="0a5db-103">Utilice este punto de conexión al escribir un servicio REST.</span><span class="sxs-lookup"><span data-stu-id="0a5db-103">Use this endpoint when writing a REST service.</span></span>  
  
<span data-ttu-id="0a5db-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0a5db-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0a5db-105">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="0a5db-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a5db-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0a5db-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0a5db-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0a5db-107">Attributes and Elements</span></span>  
 <span data-ttu-id="0a5db-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0a5db-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0a5db-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="0a5db-109">Attributes</span></span>  
  
|<span data-ttu-id="0a5db-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="0a5db-110">Attribute</span></span>|<span data-ttu-id="0a5db-111">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0a5db-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0a5db-112">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="0a5db-112">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="0a5db-113">Valor booleano que indica si la selección de formato automática está habilitada.</span><span class="sxs-lookup"><span data-stu-id="0a5db-113">A Boolean value that indicates whether automatic format selection is enabled.</span></span><br /><br /> <span data-ttu-id="0a5db-114">Cuando la selección de formato automática está habilitada, la infraestructura analiza el encabezado `Accept` del mensaje de solicitud y determina el formato de la respuesta más adecuado.</span><span class="sxs-lookup"><span data-stu-id="0a5db-114">When automatic format selection is enabled, the infrastructure parses the `Accept` header of the request message and determines the most appropriate response format.</span></span> <span data-ttu-id="0a5db-115">Si el encabezado `Accept` no especifica un formato de respuesta adecuado, la infraestructura usa el `Content-Type` del mensaje de solicitud o el formato de respuesta predeterminado de la operación.</span><span class="sxs-lookup"><span data-stu-id="0a5db-115">If the `Accept` header does not specify a suitable response format, the infrastructure uses the `Content-Type` of the request message or the default response format of the operation.</span></span>|  
|<span data-ttu-id="0a5db-116">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="0a5db-116">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="0a5db-117">Un atributo que especifica el formato de respuesta saliente predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0a5db-117">An attribute that specifies the default outgoing response format.</span></span> <span data-ttu-id="0a5db-118">Este atributo es del tipo <xref:System.ServiceModel.Web.WebMessageFormat>.</span><span class="sxs-lookup"><span data-stu-id="0a5db-118">This attribute is of the <xref:System.ServiceModel.Web.WebMessageFormat> type</span></span>|  
|<span data-ttu-id="0a5db-119">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="0a5db-119">helpEnabled</span></span>|<span data-ttu-id="0a5db-120">Valor booleano que indica si la página de ayuda HTTP está habilitada para el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="0a5db-120">A Boolean value that indicates whether the HTTP help page is enabled for the endpoint.</span></span>|  
|<span data-ttu-id="0a5db-121">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="0a5db-121">webEndpointType</span></span>|<span data-ttu-id="0a5db-122">Cadena que especifica el tipo de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="0a5db-122">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0a5db-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0a5db-123">Child Elements</span></span>  
 <span data-ttu-id="0a5db-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0a5db-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0a5db-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0a5db-125">Parent Elements</span></span>  
  
|<span data-ttu-id="0a5db-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="0a5db-126">Element</span></span>|<span data-ttu-id="0a5db-127">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0a5db-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0a5db-128">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="0a5db-128">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="0a5db-129">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="0a5db-129">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0a5db-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a5db-130">See also</span></span>

- <xref:System.ServiceModel.Description.WebHttpEndpoint>
- <xref:System.ServiceModel.Configuration.WebHttpEndpointElement>
