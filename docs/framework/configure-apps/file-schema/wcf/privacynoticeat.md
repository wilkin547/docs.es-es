---
title: '&lt;privacyNoticeAt&gt;'
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: 104b2b6399ea31273045e43be716947db110715d
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147322"
---
# <a name="ltprivacynoticeatgt"></a><span data-ttu-id="093d2-102">&lt;privacyNoticeAt&gt;</span><span class="sxs-lookup"><span data-stu-id="093d2-102">&lt;privacyNoticeAt&gt;</span></span>
<span data-ttu-id="093d2-103">Representa un elemento de configuración que especifica un aviso de privacidad usado en el enlace `wsFederationHttp`.</span><span class="sxs-lookup"><span data-stu-id="093d2-103">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
 <span data-ttu-id="093d2-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="093d2-104">\<system.serviceModel></span></span>  
<span data-ttu-id="093d2-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="093d2-105">\<bindings></span></span>  
<span data-ttu-id="093d2-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="093d2-106">\<customBinding></span></span>  
<span data-ttu-id="093d2-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="093d2-107">\<binding></span></span>  
<span data-ttu-id="093d2-108">\<privacyNotice ></span><span class="sxs-lookup"><span data-stu-id="093d2-108">\<privacyNotice></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="093d2-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="093d2-109">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="093d2-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="093d2-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="093d2-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="093d2-111">Attributes and Elements</span></span>  
 <span data-ttu-id="093d2-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="093d2-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="093d2-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="093d2-113">Attributes</span></span>  
  
|<span data-ttu-id="093d2-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="093d2-114">Attribute</span></span>|<span data-ttu-id="093d2-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="093d2-115">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="093d2-116">Una cadena que especifica el URI en el que el aviso de privacidad se encuentra.</span><span class="sxs-lookup"><span data-stu-id="093d2-116">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="093d2-117">Un entero que especifica la versión de este aviso de privacidad.</span><span class="sxs-lookup"><span data-stu-id="093d2-117">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="093d2-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="093d2-118">Child Elements</span></span>  
 <span data-ttu-id="093d2-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="093d2-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="093d2-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="093d2-120">Parent Elements</span></span>  
  
|<span data-ttu-id="093d2-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="093d2-121">Element</span></span>|<span data-ttu-id="093d2-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="093d2-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="093d2-123">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="093d2-123">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="093d2-124">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="093d2-124">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="093d2-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="093d2-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>  
 <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="093d2-126">Enlaces</span><span class="sxs-lookup"><span data-stu-id="093d2-126">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="093d2-127">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="093d2-127">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="093d2-128">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="093d2-128">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="093d2-129">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="093d2-129">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
