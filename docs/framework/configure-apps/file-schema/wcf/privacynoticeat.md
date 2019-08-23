---
title: <privacyNoticeAt>
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: f7349bf61082c5d8e5bd4249e01b8835a1861cb9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934257"
---
# <a name="privacynoticeat"></a><span data-ttu-id="63bce-101">\<privacyNoticeAt></span><span class="sxs-lookup"><span data-stu-id="63bce-101">\<privacyNoticeAt></span></span>
<span data-ttu-id="63bce-102">Representa un elemento de configuración que especifica un aviso de privacidad usado en el enlace `wsFederationHttp`.</span><span class="sxs-lookup"><span data-stu-id="63bce-102">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
 <span data-ttu-id="63bce-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="63bce-103">\<system.serviceModel></span></span>  
<span data-ttu-id="63bce-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="63bce-104">\<bindings></span></span>  
<span data-ttu-id="63bce-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="63bce-105">\<customBinding></span></span>  
<span data-ttu-id="63bce-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="63bce-106">\<binding></span></span>  
<span data-ttu-id="63bce-107">\<privacyNotice></span><span class="sxs-lookup"><span data-stu-id="63bce-107">\<privacyNotice></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63bce-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="63bce-108">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="63bce-109">Type</span><span class="sxs-lookup"><span data-stu-id="63bce-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="63bce-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="63bce-110">Attributes and Elements</span></span>  
 <span data-ttu-id="63bce-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="63bce-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="63bce-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="63bce-112">Attributes</span></span>  
  
|<span data-ttu-id="63bce-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="63bce-113">Attribute</span></span>|<span data-ttu-id="63bce-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="63bce-114">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="63bce-115">Una cadena que especifica el URI en el que el aviso de privacidad se encuentra.</span><span class="sxs-lookup"><span data-stu-id="63bce-115">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="63bce-116">Un entero que especifica la versión de este aviso de privacidad.</span><span class="sxs-lookup"><span data-stu-id="63bce-116">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="63bce-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="63bce-117">Child Elements</span></span>  
 <span data-ttu-id="63bce-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="63bce-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="63bce-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="63bce-119">Parent Elements</span></span>  
  
|<span data-ttu-id="63bce-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="63bce-120">Element</span></span>|<span data-ttu-id="63bce-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="63bce-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="63bce-122">\<binding></span><span class="sxs-lookup"><span data-stu-id="63bce-122">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="63bce-123">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="63bce-123">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="63bce-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="63bce-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="63bce-125">Enlaces</span><span class="sxs-lookup"><span data-stu-id="63bce-125">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="63bce-126">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="63bce-126">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="63bce-127">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="63bce-127">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="63bce-128">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="63bce-128">\<customBinding></span></span>](custombinding.md)
