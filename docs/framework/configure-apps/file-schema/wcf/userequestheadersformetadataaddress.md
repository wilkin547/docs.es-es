---
title: <useRequestHeadersForMetadataAddress>
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: e0b46953924a3825420b719085e1210981da643a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399203"
---
# <a name="userequestheadersformetadataaddress"></a><span data-ttu-id="e7d09-101">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="e7d09-101">\<useRequestHeadersForMetadataAddress></span></span>
<span data-ttu-id="e7d09-102">Habilita la recuperación de información de direcciones de metadatos de los encabezados de mensajes de solicitud.</span><span class="sxs-lookup"><span data-stu-id="e7d09-102">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="e7d09-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e7d09-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e7d09-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e7d09-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e7d09-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e7d09-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="e7d09-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e7d09-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="e7d09-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e7d09-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="e7d09-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> useRequestHeadersForMetadataAddress**</span><span class="sxs-lookup"><span data-stu-id="e7d09-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<useRequestHeadersForMetadataAddress>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7d09-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e7d09-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e7d09-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e7d09-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e7d09-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e7d09-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e7d09-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="e7d09-112">Attributes</span></span>  
 <span data-ttu-id="e7d09-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e7d09-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e7d09-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e7d09-114">Child Elements</span></span>  
  
|<span data-ttu-id="e7d09-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="e7d09-115">Element</span></span>|<span data-ttu-id="e7d09-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e7d09-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e7d09-117">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="e7d09-117">\<defaultPorts></span></span>](defaultports.md)|<span data-ttu-id="e7d09-118">Colección de puertos predeterminados que enumeran los puntos de conexión de comunicaciones predeterminados que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="e7d09-118">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e7d09-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e7d09-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e7d09-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="e7d09-120">Element</span></span>|<span data-ttu-id="e7d09-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e7d09-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e7d09-122">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="e7d09-122">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="e7d09-123">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="e7d09-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e7d09-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7d09-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
