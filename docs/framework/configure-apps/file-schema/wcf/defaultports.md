---
title: <defaultPorts>
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 08ca8a2bfcf5b905152f7e64a45cbae4992a7b78
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192378"
---
# \<defaultPorts>

<span data-ttu-id="9715b-101">Colección de puertos predeterminados que enumeran los puntos de conexión de comunicaciones predeterminados que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="9715b-101">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<useRequestHeadersForMetadataAddress>**](userequestheadersformetadataaddress.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultPorts>**  
  
## <a name="syntax"></a><span data-ttu-id="9715b-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9715b-102">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9715b-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9715b-103">Attributes and Elements</span></span>  

 <span data-ttu-id="9715b-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9715b-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9715b-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="9715b-105">Attributes</span></span>  

 <span data-ttu-id="9715b-106">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9715b-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9715b-107">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9715b-107">Child Elements</span></span>  
  
|<span data-ttu-id="9715b-108">Elemento</span><span class="sxs-lookup"><span data-stu-id="9715b-108">Element</span></span>|<span data-ttu-id="9715b-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="9715b-109">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9715b-110">\<add> de \<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="9715b-110">\<add> of \<defaultPorts></span></span>](add-of-defaultports.md)|<span data-ttu-id="9715b-111">Extremo de las comunicaciones predeterminado que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="9715b-111">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9715b-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9715b-112">Parent Elements</span></span>  
  
|<span data-ttu-id="9715b-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="9715b-113">Element</span></span>|<span data-ttu-id="9715b-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="9715b-114">Description</span></span>|  
|-------------|-----------------|  
|[\<useRequestHeadersForMetadataAddress>](userequestheadersformetadataaddress.md)|<span data-ttu-id="9715b-115">Lista de puertos predeterminados.</span><span class="sxs-lookup"><span data-stu-id="9715b-115">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9715b-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9715b-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
