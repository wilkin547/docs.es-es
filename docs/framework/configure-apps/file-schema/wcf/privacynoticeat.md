---
title: '&lt;privacyNoticeAt&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 63501539db4dc01d86eb675c28001dc960f1bf7f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltprivacynoticeatgt"></a><span data-ttu-id="7a769-102">&lt;privacyNoticeAt&gt;</span><span class="sxs-lookup"><span data-stu-id="7a769-102">&lt;privacyNoticeAt&gt;</span></span>
<span data-ttu-id="7a769-103">Representa un elemento de configuración que especifica un aviso de privacidad usado en el enlace `wsFederationHttp`.</span><span class="sxs-lookup"><span data-stu-id="7a769-103">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
 <span data-ttu-id="7a769-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="7a769-104">\<system.serviceModel></span></span>  
<span data-ttu-id="7a769-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="7a769-105">\<bindings></span></span>  
<span data-ttu-id="7a769-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="7a769-106">\<customBinding></span></span>  
<span data-ttu-id="7a769-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="7a769-107">\<binding></span></span>  
<span data-ttu-id="7a769-108">\<privacyNotice ></span><span class="sxs-lookup"><span data-stu-id="7a769-108">\<privacyNotice></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a769-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7a769-109">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"  
        version="Integer" />  
```  
  
## <a name="type"></a><span data-ttu-id="7a769-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="7a769-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7a769-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7a769-111">Attributes and Elements</span></span>  
 <span data-ttu-id="7a769-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7a769-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7a769-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="7a769-113">Attributes</span></span>  
  
|<span data-ttu-id="7a769-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="7a769-114">Attribute</span></span>|<span data-ttu-id="7a769-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a769-115">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="7a769-116">Una cadena que especifica el URI en el que el aviso de privacidad se encuentra.</span><span class="sxs-lookup"><span data-stu-id="7a769-116">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="7a769-117">Un entero que especifica la versión de este aviso de privacidad.</span><span class="sxs-lookup"><span data-stu-id="7a769-117">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7a769-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7a769-118">Child Elements</span></span>  
 <span data-ttu-id="7a769-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7a769-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7a769-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7a769-120">Parent Elements</span></span>  
  
|<span data-ttu-id="7a769-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="7a769-121">Element</span></span>|<span data-ttu-id="7a769-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a769-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7a769-123">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="7a769-123">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="7a769-124">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="7a769-124">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7a769-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a769-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>  
 <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="7a769-126">Enlaces</span><span class="sxs-lookup"><span data-stu-id="7a769-126">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="7a769-127">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="7a769-127">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="7a769-128">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="7a769-128">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="7a769-129">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="7a769-129">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
