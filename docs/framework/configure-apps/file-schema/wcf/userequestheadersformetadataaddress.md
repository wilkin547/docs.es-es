---
description: 'Más información acerca de: <useRequestHeadersForMetadataAddress>'
title: <useRequestHeadersForMetadataAddress>
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: 53636b5890eb54095737e2ed62a75e9b81c1c1f1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664436"
---
# \<useRequestHeadersForMetadataAddress>

<span data-ttu-id="0b65e-102">Habilita la recuperación de información de direcciones de metadatos de los encabezados de mensajes de solicitud.</span><span class="sxs-lookup"><span data-stu-id="0b65e-102">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<useRequestHeadersForMetadataAddress>**  
  
## <a name="syntax"></a><span data-ttu-id="0b65e-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0b65e-103">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0b65e-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0b65e-104">Attributes and Elements</span></span>  

 <span data-ttu-id="0b65e-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0b65e-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0b65e-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="0b65e-106">Attributes</span></span>  

 <span data-ttu-id="0b65e-107">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0b65e-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0b65e-108">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0b65e-108">Child Elements</span></span>  
  
|<span data-ttu-id="0b65e-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="0b65e-109">Element</span></span>|<span data-ttu-id="0b65e-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="0b65e-110">Description</span></span>|  
|-------------|-----------------|  
|[\<defaultPorts>](defaultports.md)|<span data-ttu-id="0b65e-111">Colección de puertos predeterminados que enumeran los puntos de conexión de comunicaciones predeterminados que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="0b65e-111">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0b65e-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0b65e-112">Parent Elements</span></span>  
  
|<span data-ttu-id="0b65e-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="0b65e-113">Element</span></span>|<span data-ttu-id="0b65e-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="0b65e-114">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="0b65e-115">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="0b65e-115">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0b65e-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b65e-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
