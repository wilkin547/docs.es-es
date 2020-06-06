---
title: <useRequestHeadersForMetadataAddress>
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: e0b46953924a3825420b719085e1210981da643a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399203"
---
# \<useRequestHeadersForMetadataAddress>
<span data-ttu-id="3cce0-101">Habilita la recuperación de información de direcciones de metadatos de los encabezados de mensajes de solicitud.</span><span class="sxs-lookup"><span data-stu-id="3cce0-101">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<useRequestHeadersForMetadataAddress>**  
  
## <a name="syntax"></a><span data-ttu-id="3cce0-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3cce0-102">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3cce0-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3cce0-103">Attributes and Elements</span></span>  
 <span data-ttu-id="3cce0-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3cce0-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3cce0-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="3cce0-105">Attributes</span></span>  
 <span data-ttu-id="3cce0-106">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3cce0-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3cce0-107">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3cce0-107">Child Elements</span></span>  
  
|<span data-ttu-id="3cce0-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="3cce0-108">Element</span></span>|<span data-ttu-id="3cce0-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cce0-109">Description</span></span>|  
|-------------|-----------------|  
|[\<defaultPorts>](defaultports.md)|<span data-ttu-id="3cce0-110">Colección de puertos predeterminados que enumeran los puntos de conexión de comunicaciones predeterminados que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="3cce0-110">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3cce0-111">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3cce0-111">Parent Elements</span></span>  
  
|<span data-ttu-id="3cce0-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="3cce0-112">Element</span></span>|<span data-ttu-id="3cce0-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cce0-113">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="3cce0-114">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="3cce0-114">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3cce0-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3cce0-115">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
