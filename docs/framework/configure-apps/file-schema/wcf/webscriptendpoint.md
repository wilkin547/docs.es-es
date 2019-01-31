---
title: <webScriptEndpoint>
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: 3d95624c82388ed6219fc567dd2d3c17bedad7a1
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55255294"
---
# <a name="webscriptendpoint"></a><span data-ttu-id="f7b36-101">\<webScriptEndpoint></span><span class="sxs-lookup"><span data-stu-id="f7b36-101">\<webScriptEndpoint></span></span>
<span data-ttu-id="f7b36-102">Este elemento de configuración define un extremo estándar con un fijo [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) enlace que automáticamente se agrega el [ \<enableWebScript >](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) comportamiento.</span><span class="sxs-lookup"><span data-stu-id="f7b36-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) behavior.</span></span> <span data-ttu-id="f7b36-103">Use este punto de conexión cuando esté escribiendo un servicio al que se llama desde una aplicación AJAX de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="f7b36-103">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
<span data-ttu-id="f7b36-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f7b36-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f7b36-105">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="f7b36-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7b36-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f7b36-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String" />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f7b36-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f7b36-107">Attributes and Elements</span></span>  
 <span data-ttu-id="f7b36-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f7b36-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f7b36-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="f7b36-109">Attributes</span></span>  
  
|<span data-ttu-id="f7b36-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="f7b36-110">Attribute</span></span>|<span data-ttu-id="f7b36-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="f7b36-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f7b36-112">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="f7b36-112">webEndpointType</span></span>|<span data-ttu-id="f7b36-113">Cadena que especifica el tipo de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="f7b36-113">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f7b36-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f7b36-114">Child Elements</span></span>  
 <span data-ttu-id="f7b36-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f7b36-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f7b36-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f7b36-116">Parent Elements</span></span>  
  
|<span data-ttu-id="f7b36-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="f7b36-117">Element</span></span>|<span data-ttu-id="f7b36-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="f7b36-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f7b36-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="f7b36-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="f7b36-120">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="f7b36-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f7b36-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7b36-121">See also</span></span>
- <xref:System.ServiceModel.Description.WebScriptEndpoint>
- <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
