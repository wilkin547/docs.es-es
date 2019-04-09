---
title: <privacyNoticeAt>
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: e2ce2111e4bb26cc6a51b4a772b1d8a4d3238c70
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59200771"
---
# <a name="privacynoticeat"></a><span data-ttu-id="83f79-101">\<privacyNoticeAt></span><span class="sxs-lookup"><span data-stu-id="83f79-101">\<privacyNoticeAt></span></span>
<span data-ttu-id="83f79-102">Representa un elemento de configuración que especifica un aviso de privacidad usado en el enlace `wsFederationHttp`.</span><span class="sxs-lookup"><span data-stu-id="83f79-102">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
 <span data-ttu-id="83f79-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="83f79-103">\<system.serviceModel></span></span>  
<span data-ttu-id="83f79-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="83f79-104">\<bindings></span></span>  
<span data-ttu-id="83f79-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="83f79-105">\<customBinding></span></span>  
<span data-ttu-id="83f79-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="83f79-106">\<binding></span></span>  
<span data-ttu-id="83f79-107">\<privacyNotice></span><span class="sxs-lookup"><span data-stu-id="83f79-107">\<privacyNotice></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83f79-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="83f79-108">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="83f79-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="83f79-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="83f79-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="83f79-110">Attributes and Elements</span></span>  
 <span data-ttu-id="83f79-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="83f79-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="83f79-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="83f79-112">Attributes</span></span>  
  
|<span data-ttu-id="83f79-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="83f79-113">Attribute</span></span>|<span data-ttu-id="83f79-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="83f79-114">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="83f79-115">Una cadena que especifica el URI en el que el aviso de privacidad se encuentra.</span><span class="sxs-lookup"><span data-stu-id="83f79-115">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="83f79-116">Un entero que especifica la versión de este aviso de privacidad.</span><span class="sxs-lookup"><span data-stu-id="83f79-116">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="83f79-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="83f79-117">Child Elements</span></span>  
 <span data-ttu-id="83f79-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="83f79-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="83f79-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="83f79-119">Parent Elements</span></span>  
  
|<span data-ttu-id="83f79-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="83f79-120">Element</span></span>|<span data-ttu-id="83f79-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="83f79-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="83f79-122">\<binding></span><span class="sxs-lookup"><span data-stu-id="83f79-122">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="83f79-123">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="83f79-123">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="83f79-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="83f79-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="83f79-125">Enlaces</span><span class="sxs-lookup"><span data-stu-id="83f79-125">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="83f79-126">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="83f79-126">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="83f79-127">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="83f79-127">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="83f79-128">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="83f79-128">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
