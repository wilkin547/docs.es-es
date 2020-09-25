---
title: <webHttpEndpoint>
ms.date: 03/30/2017
ms.assetid: ecaaeb6f-ebd0-411d-8b53-92477cd45347
ms.openlocfilehash: 3282871bf8dbd25726ada7003d3066b9a42e2366
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177987"
---
# \<webHttpEndpoint>

<span data-ttu-id="51559-101">Este elemento de configuración define un extremo estándar con un [\<webHttpBinding>](webhttpbinding.md) enlace fijo que agrega automáticamente el [\<webHttp>](webhttp.md) comportamiento.</span><span class="sxs-lookup"><span data-stu-id="51559-101">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<webHttp>](webhttp.md) behavior.</span></span> <span data-ttu-id="51559-102">Utilice este punto de conexión al escribir un servicio REST.</span><span class="sxs-lookup"><span data-stu-id="51559-102">Use this endpoint when writing a REST service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webHttpEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="51559-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="51559-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="51559-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="51559-104">Attributes and Elements</span></span>  

 <span data-ttu-id="51559-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="51559-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="51559-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="51559-106">Attributes</span></span>  
  
|<span data-ttu-id="51559-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="51559-107">Attribute</span></span>|<span data-ttu-id="51559-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="51559-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="51559-109">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="51559-109">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="51559-110">Valor booleano que indica si la selección de formato automática está habilitada.</span><span class="sxs-lookup"><span data-stu-id="51559-110">A Boolean value that indicates whether automatic format selection is enabled.</span></span><br /><br /> <span data-ttu-id="51559-111">Cuando la selección de formato automática está habilitada, la infraestructura analiza el encabezado `Accept` del mensaje de solicitud y determina el formato de la respuesta más adecuado.</span><span class="sxs-lookup"><span data-stu-id="51559-111">When automatic format selection is enabled, the infrastructure parses the `Accept` header of the request message and determines the most appropriate response format.</span></span> <span data-ttu-id="51559-112">Si el encabezado `Accept` no especifica un formato de respuesta adecuado, la infraestructura usa el `Content-Type` del mensaje de solicitud o el formato de respuesta predeterminado de la operación.</span><span class="sxs-lookup"><span data-stu-id="51559-112">If the `Accept` header does not specify a suitable response format, the infrastructure uses the `Content-Type` of the request message or the default response format of the operation.</span></span>|  
|<span data-ttu-id="51559-113">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="51559-113">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="51559-114">Un atributo que especifica el formato de respuesta saliente predeterminado.</span><span class="sxs-lookup"><span data-stu-id="51559-114">An attribute that specifies the default outgoing response format.</span></span> <span data-ttu-id="51559-115">Este atributo es del tipo <xref:System.ServiceModel.Web.WebMessageFormat>.</span><span class="sxs-lookup"><span data-stu-id="51559-115">This attribute is of the <xref:System.ServiceModel.Web.WebMessageFormat> type</span></span>|  
|<span data-ttu-id="51559-116">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="51559-116">helpEnabled</span></span>|<span data-ttu-id="51559-117">Valor booleano que indica si la página de ayuda HTTP está habilitada para el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="51559-117">A Boolean value that indicates whether the HTTP help page is enabled for the endpoint.</span></span>|  
|<span data-ttu-id="51559-118">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="51559-118">webEndpointType</span></span>|<span data-ttu-id="51559-119">Cadena que especifica el tipo de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="51559-119">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="51559-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="51559-120">Child Elements</span></span>  

 <span data-ttu-id="51559-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="51559-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="51559-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="51559-122">Parent Elements</span></span>  
  
|<span data-ttu-id="51559-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="51559-123">Element</span></span>|<span data-ttu-id="51559-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="51559-124">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="51559-125">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="51559-125">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="51559-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="51559-126">See also</span></span>

- <xref:System.ServiceModel.Description.WebHttpEndpoint>
- <xref:System.ServiceModel.Configuration.WebHttpEndpointElement>
