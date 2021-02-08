---
description: 'Más información acerca de: <defaultPorts>'
title: <defaultPorts>
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 7cd0635568bf80734900f5e54f918150ea657322
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803911"
---
# \<defaultPorts>

<span data-ttu-id="978ed-102">Colección de puertos predeterminados que enumeran los puntos de conexión de comunicaciones predeterminados que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="978ed-102">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<useRequestHeadersForMetadataAddress>**](userequestheadersformetadataaddress.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultPorts>**  
  
## <a name="syntax"></a><span data-ttu-id="978ed-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="978ed-103">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="978ed-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="978ed-104">Attributes and Elements</span></span>  

 <span data-ttu-id="978ed-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="978ed-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="978ed-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="978ed-106">Attributes</span></span>  

 <span data-ttu-id="978ed-107">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="978ed-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="978ed-108">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="978ed-108">Child Elements</span></span>  
  
|<span data-ttu-id="978ed-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="978ed-109">Element</span></span>|<span data-ttu-id="978ed-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="978ed-110">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="978ed-111">\<add> de \<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="978ed-111">\<add> of \<defaultPorts></span></span>](add-of-defaultports.md)|<span data-ttu-id="978ed-112">Extremo de las comunicaciones predeterminado que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="978ed-112">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="978ed-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="978ed-113">Parent Elements</span></span>  
  
|<span data-ttu-id="978ed-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="978ed-114">Element</span></span>|<span data-ttu-id="978ed-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="978ed-115">Description</span></span>|  
|-------------|-----------------|  
|[\<useRequestHeadersForMetadataAddress>](userequestheadersformetadataaddress.md)|<span data-ttu-id="978ed-116">Lista de puertos predeterminados.</span><span class="sxs-lookup"><span data-stu-id="978ed-116">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="978ed-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="978ed-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
