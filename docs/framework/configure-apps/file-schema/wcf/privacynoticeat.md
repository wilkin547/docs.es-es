---
title: <privacyNoticeAt>
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: 2ff70d3a8636970434582e417e4549ab6b433fc1
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738765"
---
# <a name="privacynoticeat"></a><span data-ttu-id="24b54-101">\<privacyNoticeAt ></span><span class="sxs-lookup"><span data-stu-id="24b54-101">\<privacyNoticeAt></span></span>
<span data-ttu-id="24b54-102">Representa un elemento de configuración que especifica un aviso de privacidad usado en el enlace `wsFederationHttp`.</span><span class="sxs-lookup"><span data-stu-id="24b54-102">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
<span data-ttu-id="24b54-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="24b54-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="24b54-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="24b54-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="24b54-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**enlaces**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="24b54-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="24b54-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**customBinding**](custombinding.md) ></span><span class="sxs-lookup"><span data-stu-id="24b54-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="24b54-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**enlace** ></span><span class="sxs-lookup"><span data-stu-id="24b54-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="24b54-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<privacyNotice >**</span><span class="sxs-lookup"><span data-stu-id="24b54-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<privacyNotice>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24b54-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="24b54-109">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="24b54-110">Type</span><span class="sxs-lookup"><span data-stu-id="24b54-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="24b54-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="24b54-111">Attributes and Elements</span></span>  
 <span data-ttu-id="24b54-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="24b54-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="24b54-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="24b54-113">Attributes</span></span>  
  
|<span data-ttu-id="24b54-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="24b54-114">Attribute</span></span>|<span data-ttu-id="24b54-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="24b54-115">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="24b54-116">Una cadena que especifica el URI en el que el aviso de privacidad se encuentra.</span><span class="sxs-lookup"><span data-stu-id="24b54-116">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="24b54-117">Un entero que especifica la versión de este aviso de privacidad.</span><span class="sxs-lookup"><span data-stu-id="24b54-117">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="24b54-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="24b54-118">Child Elements</span></span>  
 <span data-ttu-id="24b54-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="24b54-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="24b54-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="24b54-120">Parent Elements</span></span>  
  
|<span data-ttu-id="24b54-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="24b54-121">Element</span></span>|<span data-ttu-id="24b54-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="24b54-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="24b54-123">\<> de enlace</span><span class="sxs-lookup"><span data-stu-id="24b54-123">\<binding></span></span>](bindings.md)|<span data-ttu-id="24b54-124">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="24b54-124">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="24b54-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="24b54-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="24b54-126">Enlaces</span><span class="sxs-lookup"><span data-stu-id="24b54-126">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="24b54-127">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="24b54-127">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="24b54-128">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="24b54-128">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="24b54-129">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="24b54-129">\<customBinding></span></span>](custombinding.md)
