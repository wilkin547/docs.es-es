---
title: <webScriptEndpoint>
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: 5e3ca9c4a43432d7f5da6d8816b6a2b984851050
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177848"
---
# \<webScriptEndpoint>

<span data-ttu-id="e72a5-101">Este elemento de configuración define un extremo estándar con un [\<webHttpBinding>](webhttpbinding.md) enlace fijo que agrega automáticamente el [\<enableWebScript>](enablewebscript.md) comportamiento.</span><span class="sxs-lookup"><span data-stu-id="e72a5-101">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](enablewebscript.md) behavior.</span></span> <span data-ttu-id="e72a5-102">Use este extremo cuando esté escribiendo un servicio al que se llama desde una aplicación AJAX de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="e72a5-102">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webScriptEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="e72a5-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e72a5-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String" />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e72a5-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e72a5-104">Attributes and Elements</span></span>  

 <span data-ttu-id="e72a5-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e72a5-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e72a5-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="e72a5-106">Attributes</span></span>  
  
|<span data-ttu-id="e72a5-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="e72a5-107">Attribute</span></span>|<span data-ttu-id="e72a5-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="e72a5-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e72a5-109">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="e72a5-109">webEndpointType</span></span>|<span data-ttu-id="e72a5-110">Cadena que especifica el tipo de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="e72a5-110">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e72a5-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e72a5-111">Child Elements</span></span>  

 <span data-ttu-id="e72a5-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e72a5-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e72a5-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e72a5-113">Parent Elements</span></span>  
  
|<span data-ttu-id="e72a5-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="e72a5-114">Element</span></span>|<span data-ttu-id="e72a5-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="e72a5-115">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="e72a5-116">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="e72a5-116">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e72a5-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e72a5-117">See also</span></span>

- <xref:System.ServiceModel.Description.WebScriptEndpoint>
- <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
