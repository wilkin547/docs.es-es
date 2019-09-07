---
title: <add> de <defaultPorts>
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: f5de2aa897a3bc37d08932451a2c7b94bc603b9e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400648"
---
# <a name="add-of-defaultports"></a><span data-ttu-id="85352-102">\<Agregar > de \<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="85352-102">\<add> of \<defaultPorts></span></span>
<span data-ttu-id="85352-103">Extremo de las comunicaciones predeterminado que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="85352-103">A default communications endpoint that the client application listens to.</span></span>  
  
<span data-ttu-id="85352-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="85352-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="85352-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="85352-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="85352-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="85352-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="85352-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="85352-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="85352-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="85352-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="85352-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> useRequestHeadersForMetadataAddress**](userequestheadersformetadataaddress.md)</span><span class="sxs-lookup"><span data-stu-id="85352-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<useRequestHeadersForMetadataAddress>**](userequestheadersformetadataaddress.md)</span></span>\
<span data-ttu-id="85352-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> defaultPorts**](defaultports.md)</span><span class="sxs-lookup"><span data-stu-id="85352-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultPorts>**](defaultports.md)</span></span>\
<span data-ttu-id="85352-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Agregar >**</span><span class="sxs-lookup"><span data-stu-id="85352-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85352-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="85352-112">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85352-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="85352-113">Attributes and Elements</span></span>  
 <span data-ttu-id="85352-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="85352-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85352-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="85352-115">Attributes</span></span>  
  
|<span data-ttu-id="85352-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="85352-116">Attribute</span></span>|<span data-ttu-id="85352-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="85352-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="85352-118">port</span><span class="sxs-lookup"><span data-stu-id="85352-118">port</span></span>|<span data-ttu-id="85352-119">Entero que especifica el número del puerto de comunicaciones predeterminado.</span><span class="sxs-lookup"><span data-stu-id="85352-119">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="85352-120">scheme</span><span class="sxs-lookup"><span data-stu-id="85352-120">scheme</span></span>|<span data-ttu-id="85352-121">Cadena que especifica el grupo de configuración del protocolo asociado a un puerto de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="85352-121">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="85352-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="85352-122">Child Elements</span></span>  
 <span data-ttu-id="85352-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="85352-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="85352-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="85352-124">Parent Elements</span></span>  
  
|<span data-ttu-id="85352-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="85352-125">Element</span></span>|<span data-ttu-id="85352-126">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="85352-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="85352-127">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="85352-127">\<defaultPorts></span></span>](defaultports.md)|<span data-ttu-id="85352-128">Colección de puertos predeterminados que enumeran los puntos de conexión de comunicaciones predeterminados que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="85352-128">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="85352-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="85352-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElement>
