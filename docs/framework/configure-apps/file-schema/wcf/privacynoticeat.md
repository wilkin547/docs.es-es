---
title: <privacyNoticeAt>
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: b1de2a304a5dc4295497ea1f3b395240cb5ca9bc
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254927"
---
# <a name="privacynoticeat"></a><span data-ttu-id="07d8d-101">\<privacyNoticeAt></span><span class="sxs-lookup"><span data-stu-id="07d8d-101">\<privacyNoticeAt></span></span>
<span data-ttu-id="07d8d-102">Representa un elemento de configuración que especifica un aviso de privacidad usado en el enlace `wsFederationHttp`.</span><span class="sxs-lookup"><span data-stu-id="07d8d-102">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
 <span data-ttu-id="07d8d-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="07d8d-103">\<system.serviceModel></span></span>  
<span data-ttu-id="07d8d-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="07d8d-104">\<bindings></span></span>  
<span data-ttu-id="07d8d-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="07d8d-105">\<customBinding></span></span>  
<span data-ttu-id="07d8d-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="07d8d-106">\<binding></span></span>  
<span data-ttu-id="07d8d-107">\<privacyNotice></span><span class="sxs-lookup"><span data-stu-id="07d8d-107">\<privacyNotice></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07d8d-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="07d8d-108">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="07d8d-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="07d8d-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="07d8d-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="07d8d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="07d8d-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="07d8d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="07d8d-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="07d8d-112">Attributes</span></span>  
  
|<span data-ttu-id="07d8d-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="07d8d-113">Attribute</span></span>|<span data-ttu-id="07d8d-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="07d8d-114">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="07d8d-115">Una cadena que especifica el URI en el que el aviso de privacidad se encuentra.</span><span class="sxs-lookup"><span data-stu-id="07d8d-115">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="07d8d-116">Un entero que especifica la versión de este aviso de privacidad.</span><span class="sxs-lookup"><span data-stu-id="07d8d-116">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="07d8d-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="07d8d-117">Child Elements</span></span>  
 <span data-ttu-id="07d8d-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="07d8d-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="07d8d-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="07d8d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="07d8d-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="07d8d-120">Element</span></span>|<span data-ttu-id="07d8d-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="07d8d-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="07d8d-122">\<binding></span><span class="sxs-lookup"><span data-stu-id="07d8d-122">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="07d8d-123">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="07d8d-123">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="07d8d-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="07d8d-124">See also</span></span>
- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="07d8d-125">Enlaces</span><span class="sxs-lookup"><span data-stu-id="07d8d-125">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="07d8d-126">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="07d8d-126">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="07d8d-127">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="07d8d-127">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="07d8d-128">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="07d8d-128">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
