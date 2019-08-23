---
title: <add> de <defaultPorts>
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: d2723dad14a63c4b05fdb70157f7eb21d193d3ab
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926706"
---
# <a name="add-of-defaultports"></a><span data-ttu-id="bf2f6-102">\<Agregar > de \<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="bf2f6-102">\<add> of \<defaultPorts></span></span>
<span data-ttu-id="bf2f6-103">Extremo de las comunicaciones predeterminado que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="bf2f6-103">A default communications endpoint that the client application listens to.</span></span>  
  
 <span data-ttu-id="bf2f6-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="bf2f6-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="bf2f6-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="bf2f6-105">\<behaviors></span></span>  
<span data-ttu-id="bf2f6-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="bf2f6-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="bf2f6-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="bf2f6-107">\<behavior></span></span>  
<span data-ttu-id="bf2f6-108">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="bf2f6-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="bf2f6-109">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="bf2f6-109">\<defaultPorts></span></span>  
<span data-ttu-id="bf2f6-110">\<add></span><span class="sxs-lookup"><span data-stu-id="bf2f6-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf2f6-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bf2f6-111">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bf2f6-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bf2f6-112">Attributes and Elements</span></span>  
 <span data-ttu-id="bf2f6-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="bf2f6-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bf2f6-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="bf2f6-114">Attributes</span></span>  
  
|<span data-ttu-id="bf2f6-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="bf2f6-115">Attribute</span></span>|<span data-ttu-id="bf2f6-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="bf2f6-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bf2f6-117">port</span><span class="sxs-lookup"><span data-stu-id="bf2f6-117">port</span></span>|<span data-ttu-id="bf2f6-118">Entero que especifica el número del puerto de comunicaciones predeterminado.</span><span class="sxs-lookup"><span data-stu-id="bf2f6-118">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="bf2f6-119">scheme</span><span class="sxs-lookup"><span data-stu-id="bf2f6-119">scheme</span></span>|<span data-ttu-id="bf2f6-120">Cadena que especifica el grupo de configuración del protocolo asociado a un puerto de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="bf2f6-120">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bf2f6-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bf2f6-121">Child Elements</span></span>  
 <span data-ttu-id="bf2f6-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="bf2f6-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bf2f6-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bf2f6-123">Parent Elements</span></span>  
  
|<span data-ttu-id="bf2f6-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="bf2f6-124">Element</span></span>|<span data-ttu-id="bf2f6-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="bf2f6-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bf2f6-126">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="bf2f6-126">\<defaultPorts></span></span>](defaultports.md)|<span data-ttu-id="bf2f6-127">Colección de puertos predeterminados que enumeran los puntos de conexión de comunicaciones predeterminados que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="bf2f6-127">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bf2f6-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf2f6-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElement>
