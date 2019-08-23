---
title: <useRequestHeadersForMetadataAddress>
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: 84310d4ae5e04e76e4484f4fc606c9896239c776
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940550"
---
# <a name="userequestheadersformetadataaddress"></a><span data-ttu-id="28348-101">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="28348-101">\<useRequestHeadersForMetadataAddress></span></span>
<span data-ttu-id="28348-102">Habilita la recuperación de información de direcciones de metadatos de los encabezados de mensajes de solicitud.</span><span class="sxs-lookup"><span data-stu-id="28348-102">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="28348-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="28348-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="28348-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="28348-104">\<behaviors></span></span>  
<span data-ttu-id="28348-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="28348-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="28348-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="28348-106">\<behavior></span></span>  
<span data-ttu-id="28348-107">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="28348-107">\<useRequestHeadersForMetadataAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28348-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="28348-108">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="28348-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="28348-109">Attributes and Elements</span></span>  
 <span data-ttu-id="28348-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="28348-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="28348-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="28348-111">Attributes</span></span>  
 <span data-ttu-id="28348-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="28348-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="28348-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="28348-113">Child Elements</span></span>  
  
|<span data-ttu-id="28348-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="28348-114">Element</span></span>|<span data-ttu-id="28348-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="28348-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="28348-116">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="28348-116">\<defaultPorts></span></span>](defaultports.md)|<span data-ttu-id="28348-117">Colección de puertos predeterminados que enumeran los puntos de conexión de comunicaciones predeterminados que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="28348-117">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="28348-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="28348-118">Parent Elements</span></span>  
  
|<span data-ttu-id="28348-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="28348-119">Element</span></span>|<span data-ttu-id="28348-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="28348-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="28348-121">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="28348-121">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="28348-122">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="28348-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="28348-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="28348-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
