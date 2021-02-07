---
description: 'Más información acerca de: <webHttpEndpoint>'
title: <webHttpEndpoint>
ms.date: 03/30/2017
ms.assetid: ecaaeb6f-ebd0-411d-8b53-92477cd45347
ms.openlocfilehash: d1bcda1fc97dece833c8163e5facbefe614af0ac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99682597"
---
# \<webHttpEndpoint>

<span data-ttu-id="8a6ce-102">Este elemento de configuración define un extremo estándar con un [\<webHttpBinding>](webhttpbinding.md) enlace fijo que agrega automáticamente el [\<webHttp>](webhttp.md) comportamiento.</span><span class="sxs-lookup"><span data-stu-id="8a6ce-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<webHttp>](webhttp.md) behavior.</span></span> <span data-ttu-id="8a6ce-103">Utilice este punto de conexión al escribir un servicio REST.</span><span class="sxs-lookup"><span data-stu-id="8a6ce-103">Use this endpoint when writing a REST service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webHttpEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="8a6ce-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8a6ce-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8a6ce-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8a6ce-105">Attributes and Elements</span></span>  

 <span data-ttu-id="8a6ce-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8a6ce-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8a6ce-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="8a6ce-107">Attributes</span></span>  
  
|<span data-ttu-id="8a6ce-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="8a6ce-108">Attribute</span></span>|<span data-ttu-id="8a6ce-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a6ce-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8a6ce-110">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="8a6ce-110">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="8a6ce-111">Valor booleano que indica si la selección de formato automática está habilitada.</span><span class="sxs-lookup"><span data-stu-id="8a6ce-111">A Boolean value that indicates whether automatic format selection is enabled.</span></span><br /><br /> <span data-ttu-id="8a6ce-112">Cuando la selección de formato automática está habilitada, la infraestructura analiza el encabezado `Accept` del mensaje de solicitud y determina el formato de la respuesta más adecuado.</span><span class="sxs-lookup"><span data-stu-id="8a6ce-112">When automatic format selection is enabled, the infrastructure parses the `Accept` header of the request message and determines the most appropriate response format.</span></span> <span data-ttu-id="8a6ce-113">Si el encabezado `Accept` no especifica un formato de respuesta adecuado, la infraestructura usa el `Content-Type` del mensaje de solicitud o el formato de respuesta predeterminado de la operación.</span><span class="sxs-lookup"><span data-stu-id="8a6ce-113">If the `Accept` header does not specify a suitable response format, the infrastructure uses the `Content-Type` of the request message or the default response format of the operation.</span></span>|  
|<span data-ttu-id="8a6ce-114">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="8a6ce-114">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="8a6ce-115">Un atributo que especifica el formato de respuesta saliente predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8a6ce-115">An attribute that specifies the default outgoing response format.</span></span> <span data-ttu-id="8a6ce-116">Este atributo es del tipo <xref:System.ServiceModel.Web.WebMessageFormat>.</span><span class="sxs-lookup"><span data-stu-id="8a6ce-116">This attribute is of the <xref:System.ServiceModel.Web.WebMessageFormat> type</span></span>|  
|<span data-ttu-id="8a6ce-117">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="8a6ce-117">helpEnabled</span></span>|<span data-ttu-id="8a6ce-118">Valor booleano que indica si la página de ayuda HTTP está habilitada para el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="8a6ce-118">A Boolean value that indicates whether the HTTP help page is enabled for the endpoint.</span></span>|  
|<span data-ttu-id="8a6ce-119">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="8a6ce-119">webEndpointType</span></span>|<span data-ttu-id="8a6ce-120">Cadena que especifica el tipo de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="8a6ce-120">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8a6ce-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8a6ce-121">Child Elements</span></span>  

 <span data-ttu-id="8a6ce-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8a6ce-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8a6ce-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8a6ce-123">Parent Elements</span></span>  
  
|<span data-ttu-id="8a6ce-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="8a6ce-124">Element</span></span>|<span data-ttu-id="8a6ce-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a6ce-125">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="8a6ce-126">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="8a6ce-126">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8a6ce-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a6ce-127">See also</span></span>

- <xref:System.ServiceModel.Description.WebHttpEndpoint>
- <xref:System.ServiceModel.Configuration.WebHttpEndpointElement>
