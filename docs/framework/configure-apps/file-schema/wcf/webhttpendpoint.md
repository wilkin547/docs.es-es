---
title: <webHttpEndpoint>
ms.date: 03/30/2017
ms.assetid: ecaaeb6f-ebd0-411d-8b53-92477cd45347
ms.openlocfilehash: 8d4f55fd5b51ea77839b7fdbb930e937f5700417
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854802"
---
# <a name="webhttpendpoint"></a><span data-ttu-id="ef63e-101">\<webHttpEndpoint></span><span class="sxs-lookup"><span data-stu-id="ef63e-101">\<webHttpEndpoint></span></span>
<span data-ttu-id="ef63e-102">Este elemento de configuración define un punto de conexión estándar con un enlace fijo [ \<de webHttpBinding >](webhttpbinding.md) que agrega automáticamente el comportamiento de [ \<> webhttp](webhttp.md) .</span><span class="sxs-lookup"><span data-stu-id="ef63e-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<webHttp>](webhttp.md) behavior.</span></span> <span data-ttu-id="ef63e-103">Utilice este punto de conexión al escribir un servicio REST.</span><span class="sxs-lookup"><span data-stu-id="ef63e-103">Use this endpoint when writing a REST service.</span></span>  
  
<span data-ttu-id="ef63e-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ef63e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ef63e-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ef63e-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ef63e-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> standardEndpoints**](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="ef63e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="ef63e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> webHttpEndpoint**</span><span class="sxs-lookup"><span data-stu-id="ef63e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webHttpEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef63e-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ef63e-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ef63e-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ef63e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ef63e-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ef63e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ef63e-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="ef63e-111">Attributes</span></span>  
  
|<span data-ttu-id="ef63e-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="ef63e-112">Attribute</span></span>|<span data-ttu-id="ef63e-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ef63e-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ef63e-114">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="ef63e-114">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="ef63e-115">Valor booleano que indica si la selección de formato automática está habilitada.</span><span class="sxs-lookup"><span data-stu-id="ef63e-115">A Boolean value that indicates whether automatic format selection is enabled.</span></span><br /><br /> <span data-ttu-id="ef63e-116">Cuando la selección de formato automática está habilitada, la infraestructura analiza el encabezado `Accept` del mensaje de solicitud y determina el formato de la respuesta más adecuado.</span><span class="sxs-lookup"><span data-stu-id="ef63e-116">When automatic format selection is enabled, the infrastructure parses the `Accept` header of the request message and determines the most appropriate response format.</span></span> <span data-ttu-id="ef63e-117">Si el encabezado `Accept` no especifica un formato de respuesta adecuado, la infraestructura usa el `Content-Type` del mensaje de solicitud o el formato de respuesta predeterminado de la operación.</span><span class="sxs-lookup"><span data-stu-id="ef63e-117">If the `Accept` header does not specify a suitable response format, the infrastructure uses the `Content-Type` of the request message or the default response format of the operation.</span></span>|  
|<span data-ttu-id="ef63e-118">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="ef63e-118">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="ef63e-119">Un atributo que especifica el formato de respuesta saliente predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ef63e-119">An attribute that specifies the default outgoing response format.</span></span> <span data-ttu-id="ef63e-120">Este atributo es del tipo <xref:System.ServiceModel.Web.WebMessageFormat>.</span><span class="sxs-lookup"><span data-stu-id="ef63e-120">This attribute is of the <xref:System.ServiceModel.Web.WebMessageFormat> type</span></span>|  
|<span data-ttu-id="ef63e-121">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="ef63e-121">helpEnabled</span></span>|<span data-ttu-id="ef63e-122">Valor booleano que indica si la página de ayuda HTTP está habilitada para el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="ef63e-122">A Boolean value that indicates whether the HTTP help page is enabled for the endpoint.</span></span>|  
|<span data-ttu-id="ef63e-123">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="ef63e-123">webEndpointType</span></span>|<span data-ttu-id="ef63e-124">Cadena que especifica el tipo de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="ef63e-124">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ef63e-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ef63e-125">Child Elements</span></span>  
 <span data-ttu-id="ef63e-126">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ef63e-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ef63e-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ef63e-127">Parent Elements</span></span>  
  
|<span data-ttu-id="ef63e-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="ef63e-128">Element</span></span>|<span data-ttu-id="ef63e-129">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ef63e-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ef63e-130">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="ef63e-130">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="ef63e-131">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="ef63e-131">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ef63e-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef63e-132">See also</span></span>

- <xref:System.ServiceModel.Description.WebHttpEndpoint>
- <xref:System.ServiceModel.Configuration.WebHttpEndpointElement>
