---
title: <add> de <defaultPorts>
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: 799715ef008274ead6b745e8ab97e769cb59e6b5
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55261609"
---
# <a name="add-of-defaultports"></a><span data-ttu-id="06c51-102">\<Agregar > de \<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="06c51-102">\<add> of \<defaultPorts></span></span>
<span data-ttu-id="06c51-103">punto de conexión de las comunicaciones predeterminado que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="06c51-103">A default communications endpoint that the client application listens to.</span></span>  
  
 <span data-ttu-id="06c51-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="06c51-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="06c51-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="06c51-105">\<behaviors></span></span>  
<span data-ttu-id="06c51-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="06c51-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="06c51-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="06c51-107">\<behavior></span></span>  
<span data-ttu-id="06c51-108">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="06c51-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="06c51-109">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="06c51-109">\<defaultPorts></span></span>  
<span data-ttu-id="06c51-110">\<add></span><span class="sxs-lookup"><span data-stu-id="06c51-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06c51-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="06c51-111">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="06c51-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="06c51-112">Attributes and Elements</span></span>  
 <span data-ttu-id="06c51-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="06c51-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="06c51-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="06c51-114">Attributes</span></span>  
  
|<span data-ttu-id="06c51-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="06c51-115">Attribute</span></span>|<span data-ttu-id="06c51-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="06c51-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="06c51-117">puerto</span><span class="sxs-lookup"><span data-stu-id="06c51-117">port</span></span>|<span data-ttu-id="06c51-118">Entero que especifica el número del puerto de comunicaciones predeterminado.</span><span class="sxs-lookup"><span data-stu-id="06c51-118">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="06c51-119">scheme</span><span class="sxs-lookup"><span data-stu-id="06c51-119">scheme</span></span>|<span data-ttu-id="06c51-120">Cadena que especifica el grupo de configuración del protocolo asociado a un puerto de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="06c51-120">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="06c51-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="06c51-121">Child Elements</span></span>  
 <span data-ttu-id="06c51-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="06c51-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="06c51-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="06c51-123">Parent Elements</span></span>  
  
|<span data-ttu-id="06c51-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="06c51-124">Element</span></span>|<span data-ttu-id="06c51-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="06c51-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="06c51-126">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="06c51-126">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="06c51-127">Colección de puertos predeterminados que enumeran los puntos de conexión de comunicaciones predeterminados que escucha la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="06c51-127">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="06c51-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="06c51-128">See also</span></span>
- <xref:System.ServiceModel.Configuration.DefaultPortElement>
