---
title: <defaultPorts>
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 89ebad118c1c9210357d8fd281c9216b7f64b450
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398070"
---
# <a name="defaultports"></a><span data-ttu-id="d0a2a-101">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="d0a2a-101">\<defaultPorts></span></span>
<span data-ttu-id="d0a2a-102">Colección de puertos predeterminados que enumeran los puntos de conexión de comunicaciones predeterminados que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="d0a2a-102">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="d0a2a-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d0a2a-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d0a2a-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d0a2a-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d0a2a-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d0a2a-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="d0a2a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d0a2a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="d0a2a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d0a2a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="d0a2a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> useRequestHeadersForMetadataAddress**](userequestheadersformetadataaddress.md)</span><span class="sxs-lookup"><span data-stu-id="d0a2a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<useRequestHeadersForMetadataAddress>**](userequestheadersformetadataaddress.md)</span></span>\
<span data-ttu-id="d0a2a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> defaultPorts**</span><span class="sxs-lookup"><span data-stu-id="d0a2a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultPorts>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0a2a-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d0a2a-110">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d0a2a-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d0a2a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d0a2a-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d0a2a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d0a2a-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="d0a2a-113">Attributes</span></span>  
 <span data-ttu-id="d0a2a-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d0a2a-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d0a2a-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d0a2a-115">Child Elements</span></span>  
  
|<span data-ttu-id="d0a2a-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="d0a2a-116">Element</span></span>|<span data-ttu-id="d0a2a-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d0a2a-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d0a2a-118">\<Agregar > de \<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="d0a2a-118">\<add> of \<defaultPorts></span></span>](add-of-defaultports.md)|<span data-ttu-id="d0a2a-119">Extremo de las comunicaciones predeterminado que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="d0a2a-119">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d0a2a-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d0a2a-120">Parent Elements</span></span>  
  
|<span data-ttu-id="d0a2a-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="d0a2a-121">Element</span></span>|<span data-ttu-id="d0a2a-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d0a2a-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d0a2a-123">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="d0a2a-123">\<useRequestHeadersForMetadataAddress></span></span>](userequestheadersformetadataaddress.md)|<span data-ttu-id="d0a2a-124">Lista de puertos predeterminados.</span><span class="sxs-lookup"><span data-stu-id="d0a2a-124">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d0a2a-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0a2a-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
