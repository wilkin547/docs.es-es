---
title: <webScriptEndpoint>
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: 9619c27c8c6d41250eeaeccabebe611e94b7d874
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769738"
---
# <a name="webscriptendpoint"></a><span data-ttu-id="dae4d-101">\<webScriptEndpoint></span><span class="sxs-lookup"><span data-stu-id="dae4d-101">\<webScriptEndpoint></span></span>
<span data-ttu-id="dae4d-102">Este elemento de configuración define un extremo estándar con un fijo [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) enlace que automáticamente se agrega el [ \<enableWebScript >](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) comportamiento.</span><span class="sxs-lookup"><span data-stu-id="dae4d-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) behavior.</span></span> <span data-ttu-id="dae4d-103">Use este extremo cuando esté escribiendo un servicio al que se llama desde una aplicación AJAX de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="dae4d-103">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
<span data-ttu-id="dae4d-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="dae4d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="dae4d-105">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="dae4d-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dae4d-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dae4d-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String" />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dae4d-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="dae4d-107">Attributes and Elements</span></span>  
 <span data-ttu-id="dae4d-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="dae4d-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dae4d-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="dae4d-109">Attributes</span></span>  
  
|<span data-ttu-id="dae4d-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="dae4d-110">Attribute</span></span>|<span data-ttu-id="dae4d-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="dae4d-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dae4d-112">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="dae4d-112">webEndpointType</span></span>|<span data-ttu-id="dae4d-113">Cadena que especifica el tipo de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="dae4d-113">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dae4d-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="dae4d-114">Child Elements</span></span>  
 <span data-ttu-id="dae4d-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="dae4d-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dae4d-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="dae4d-116">Parent Elements</span></span>  
  
|<span data-ttu-id="dae4d-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="dae4d-117">Element</span></span>|<span data-ttu-id="dae4d-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="dae4d-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dae4d-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="dae4d-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="dae4d-120">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="dae4d-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dae4d-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="dae4d-121">See also</span></span>

- <xref:System.ServiceModel.Description.WebScriptEndpoint>
- <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
