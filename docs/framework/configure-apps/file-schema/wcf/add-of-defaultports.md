---
description: 'Más información sobre: <add> de <defaultPorts>'
title: <add> de <defaultPorts>
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: 9db7afa5183b185eb842530b051d98236e7fa381
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803963"
---
# <a name="add-of-defaultports"></a><span data-ttu-id="927fb-103">\<add> de \<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="927fb-103">\<add> of \<defaultPorts></span></span>

<span data-ttu-id="927fb-104">Extremo de las comunicaciones predeterminado que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="927fb-104">A default communications endpoint that the client application listens to.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<useRequestHeadersForMetadataAddress>**](userequestheadersformetadataaddress.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultPorts>**](defaultports.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="927fb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="927fb-105">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="927fb-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="927fb-106">Attributes and Elements</span></span>  

 <span data-ttu-id="927fb-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="927fb-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="927fb-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="927fb-108">Attributes</span></span>  
  
|<span data-ttu-id="927fb-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="927fb-109">Attribute</span></span>|<span data-ttu-id="927fb-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="927fb-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="927fb-111">port</span><span class="sxs-lookup"><span data-stu-id="927fb-111">port</span></span>|<span data-ttu-id="927fb-112">Entero que especifica el número del puerto de comunicaciones predeterminado.</span><span class="sxs-lookup"><span data-stu-id="927fb-112">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="927fb-113">scheme</span><span class="sxs-lookup"><span data-stu-id="927fb-113">scheme</span></span>|<span data-ttu-id="927fb-114">Cadena que especifica el grupo de configuración del protocolo asociado a un puerto de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="927fb-114">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="927fb-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="927fb-115">Child Elements</span></span>  

 <span data-ttu-id="927fb-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="927fb-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="927fb-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="927fb-117">Parent Elements</span></span>  
  
|<span data-ttu-id="927fb-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="927fb-118">Element</span></span>|<span data-ttu-id="927fb-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="927fb-119">Description</span></span>|  
|-------------|-----------------|  
|[\<defaultPorts>](defaultports.md)|<span data-ttu-id="927fb-120">Colección de puertos predeterminados que enumeran los puntos de conexión de comunicaciones predeterminados que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="927fb-120">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="927fb-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="927fb-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElement>
