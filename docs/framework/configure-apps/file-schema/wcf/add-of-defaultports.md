---
title: <add> de <defaultPorts>
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: 5200c8893a89488b72c2c71d1a3703bf2aad1235
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136752"
---
# <a name="add-of-defaultports"></a><span data-ttu-id="de18d-102">\<Agregar > de \<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="de18d-102">\<add> of \<defaultPorts></span></span>
<span data-ttu-id="de18d-103">Extremo de las comunicaciones predeterminado que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="de18d-103">A default communications endpoint that the client application listens to.</span></span>  
  
 <span data-ttu-id="de18d-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="de18d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="de18d-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="de18d-105">\<behaviors></span></span>  
<span data-ttu-id="de18d-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="de18d-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="de18d-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="de18d-107">\<behavior></span></span>  
<span data-ttu-id="de18d-108">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="de18d-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="de18d-109">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="de18d-109">\<defaultPorts></span></span>  
<span data-ttu-id="de18d-110">\<add></span><span class="sxs-lookup"><span data-stu-id="de18d-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de18d-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="de18d-111">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="de18d-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="de18d-112">Attributes and Elements</span></span>  
 <span data-ttu-id="de18d-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="de18d-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="de18d-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="de18d-114">Attributes</span></span>  
  
|<span data-ttu-id="de18d-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="de18d-115">Attribute</span></span>|<span data-ttu-id="de18d-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="de18d-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="de18d-117">puerto</span><span class="sxs-lookup"><span data-stu-id="de18d-117">port</span></span>|<span data-ttu-id="de18d-118">Entero que especifica el número del puerto de comunicaciones predeterminado.</span><span class="sxs-lookup"><span data-stu-id="de18d-118">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="de18d-119">scheme</span><span class="sxs-lookup"><span data-stu-id="de18d-119">scheme</span></span>|<span data-ttu-id="de18d-120">Cadena que especifica el grupo de configuración del protocolo asociado a un puerto de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="de18d-120">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="de18d-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="de18d-121">Child Elements</span></span>  
 <span data-ttu-id="de18d-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="de18d-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="de18d-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="de18d-123">Parent Elements</span></span>  
  
|<span data-ttu-id="de18d-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="de18d-124">Element</span></span>|<span data-ttu-id="de18d-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="de18d-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="de18d-126">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="de18d-126">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="de18d-127">Colección de puertos predeterminados que enumeran los puntos de conexión de comunicaciones predeterminados que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="de18d-127">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="de18d-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="de18d-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElement>
