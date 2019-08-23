---
title: <webScriptEndpoint>
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: cc69029d9830fd12df5a4070f11847fadf4c60bb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940405"
---
# <a name="webscriptendpoint"></a><span data-ttu-id="e418b-101">\<webScriptEndpoint></span><span class="sxs-lookup"><span data-stu-id="e418b-101">\<webScriptEndpoint></span></span>
<span data-ttu-id="e418b-102">Este elemento de configuración define un punto de conexión estándar con un enlace fijo [ \<de webHttpBinding >](webhttpbinding.md) que agrega automáticamente el comportamiento de [ \<> de enableWebScript](enablewebscript.md) .</span><span class="sxs-lookup"><span data-stu-id="e418b-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](enablewebscript.md) behavior.</span></span> <span data-ttu-id="e418b-103">Use este extremo cuando esté escribiendo un servicio al que se llama desde una aplicación AJAX de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="e418b-103">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
<span data-ttu-id="e418b-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e418b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e418b-105">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="e418b-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e418b-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e418b-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String" />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e418b-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e418b-107">Attributes and Elements</span></span>  
 <span data-ttu-id="e418b-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e418b-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e418b-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="e418b-109">Attributes</span></span>  
  
|<span data-ttu-id="e418b-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="e418b-110">Attribute</span></span>|<span data-ttu-id="e418b-111">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e418b-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e418b-112">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="e418b-112">webEndpointType</span></span>|<span data-ttu-id="e418b-113">Cadena que especifica el tipo de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="e418b-113">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e418b-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e418b-114">Child Elements</span></span>  
 <span data-ttu-id="e418b-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e418b-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e418b-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e418b-116">Parent Elements</span></span>  
  
|<span data-ttu-id="e418b-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="e418b-117">Element</span></span>|<span data-ttu-id="e418b-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e418b-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e418b-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="e418b-119">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="e418b-120">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="e418b-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e418b-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="e418b-121">See also</span></span>

- <xref:System.ServiceModel.Description.WebScriptEndpoint>
- <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
