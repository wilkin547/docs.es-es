---
title: <webScriptEndpoint>
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: b4bc33cf8ff4e703973efe7df49e9f1d2189302e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854812"
---
# <a name="webscriptendpoint"></a><span data-ttu-id="8f9e2-101">\<webScriptEndpoint></span><span class="sxs-lookup"><span data-stu-id="8f9e2-101">\<webScriptEndpoint></span></span>
<span data-ttu-id="8f9e2-102">Este elemento de configuración define un punto de conexión estándar con un enlace fijo [ \<de webHttpBinding >](webhttpbinding.md) que agrega automáticamente el comportamiento de [ \<> de enableWebScript](enablewebscript.md) .</span><span class="sxs-lookup"><span data-stu-id="8f9e2-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](enablewebscript.md) behavior.</span></span> <span data-ttu-id="8f9e2-103">Use este extremo cuando esté escribiendo un servicio al que se llama desde una aplicación AJAX de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="8f9e2-103">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
<span data-ttu-id="8f9e2-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8f9e2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8f9e2-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="8f9e2-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8f9e2-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> standardEndpoints**](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="8f9e2-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="8f9e2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> webScriptEndpoint**</span><span class="sxs-lookup"><span data-stu-id="8f9e2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webScriptEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f9e2-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8f9e2-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String" />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8f9e2-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8f9e2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8f9e2-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8f9e2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8f9e2-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="8f9e2-111">Attributes</span></span>  
  
|<span data-ttu-id="8f9e2-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="8f9e2-112">Attribute</span></span>|<span data-ttu-id="8f9e2-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="8f9e2-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8f9e2-114">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="8f9e2-114">webEndpointType</span></span>|<span data-ttu-id="8f9e2-115">Cadena que especifica el tipo de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="8f9e2-115">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8f9e2-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8f9e2-116">Child Elements</span></span>  
 <span data-ttu-id="8f9e2-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8f9e2-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8f9e2-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8f9e2-118">Parent Elements</span></span>  
  
|<span data-ttu-id="8f9e2-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="8f9e2-119">Element</span></span>|<span data-ttu-id="8f9e2-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="8f9e2-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8f9e2-121">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="8f9e2-121">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="8f9e2-122">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="8f9e2-122">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8f9e2-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f9e2-123">See also</span></span>

- <xref:System.ServiceModel.Description.WebScriptEndpoint>
- <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
