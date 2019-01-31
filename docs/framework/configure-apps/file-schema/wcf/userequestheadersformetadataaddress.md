---
title: <useRequestHeadersForMetadataAddress>
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: 842f989ab1f2f0b9e8fe08e8fd729f983e846ffc
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55261573"
---
# <a name="userequestheadersformetadataaddress"></a><span data-ttu-id="f8fc4-101">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="f8fc4-101">\<useRequestHeadersForMetadataAddress></span></span>
<span data-ttu-id="f8fc4-102">Habilita la recuperación de información de direcciones de metadatos de los encabezados de mensajes de solicitud.</span><span class="sxs-lookup"><span data-stu-id="f8fc4-102">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="f8fc4-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f8fc4-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="f8fc4-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="f8fc4-104">\<behaviors></span></span>  
<span data-ttu-id="f8fc4-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="f8fc4-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="f8fc4-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="f8fc4-106">\<behavior></span></span>  
<span data-ttu-id="f8fc4-107">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="f8fc4-107">\<useRequestHeadersForMetadataAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8fc4-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f8fc4-108">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f8fc4-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f8fc4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f8fc4-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f8fc4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f8fc4-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="f8fc4-111">Attributes</span></span>  
 <span data-ttu-id="f8fc4-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f8fc4-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f8fc4-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f8fc4-113">Child Elements</span></span>  
  
|<span data-ttu-id="f8fc4-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="f8fc4-114">Element</span></span>|<span data-ttu-id="f8fc4-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="f8fc4-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f8fc4-116">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="f8fc4-116">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="f8fc4-117">Colección de puertos predeterminados que enumeran los puntos de conexión de comunicaciones predeterminados que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="f8fc4-117">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f8fc4-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f8fc4-118">Parent Elements</span></span>  
  
|<span data-ttu-id="f8fc4-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="f8fc4-119">Element</span></span>|<span data-ttu-id="f8fc4-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="f8fc4-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f8fc4-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="f8fc4-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="f8fc4-122">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="f8fc4-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f8fc4-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8fc4-123">See also</span></span>
- <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
