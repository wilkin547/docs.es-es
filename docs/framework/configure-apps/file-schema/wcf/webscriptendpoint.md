---
description: 'Más información acerca de: <webScriptEndpoint>'
title: <webScriptEndpoint>
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: eef4eb8e8e7345492f967c85b6245f733a4c824f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99682506"
---
# \<webScriptEndpoint>

<span data-ttu-id="14695-102">Este elemento de configuración define un extremo estándar con un [\<webHttpBinding>](webhttpbinding.md) enlace fijo que agrega automáticamente el [\<enableWebScript>](enablewebscript.md) comportamiento.</span><span class="sxs-lookup"><span data-stu-id="14695-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](enablewebscript.md) behavior.</span></span> <span data-ttu-id="14695-103">Use este extremo cuando esté escribiendo un servicio al que se llama desde una aplicación AJAX de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="14695-103">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webScriptEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="14695-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="14695-104">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String" />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14695-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="14695-105">Attributes and Elements</span></span>  

 <span data-ttu-id="14695-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="14695-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14695-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="14695-107">Attributes</span></span>  
  
|<span data-ttu-id="14695-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="14695-108">Attribute</span></span>|<span data-ttu-id="14695-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="14695-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="14695-110">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="14695-110">webEndpointType</span></span>|<span data-ttu-id="14695-111">Cadena que especifica el tipo de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="14695-111">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="14695-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="14695-112">Child Elements</span></span>  

 <span data-ttu-id="14695-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="14695-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="14695-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="14695-114">Parent Elements</span></span>  
  
|<span data-ttu-id="14695-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="14695-115">Element</span></span>|<span data-ttu-id="14695-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="14695-116">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="14695-117">Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.</span><span class="sxs-lookup"><span data-stu-id="14695-117">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="14695-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="14695-118">See also</span></span>

- <xref:System.ServiceModel.Description.WebScriptEndpoint>
- <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
