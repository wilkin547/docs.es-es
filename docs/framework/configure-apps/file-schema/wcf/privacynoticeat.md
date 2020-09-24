---
title: <privacyNoticeAt>
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: 5e772e23b21c566c906be854e33b924698dcf3e0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158713"
---
# \<privacyNoticeAt>

<span data-ttu-id="c8154-101">Representa un elemento de configuración que especifica un aviso de privacidad usado en el enlace `wsFederationHttp`.</span><span class="sxs-lookup"><span data-stu-id="c8154-101">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<privacyNotice>**  
  
## <a name="syntax"></a><span data-ttu-id="c8154-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="c8154-102">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="c8154-103">Tipo</span><span class="sxs-lookup"><span data-stu-id="c8154-103">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c8154-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c8154-104">Attributes and Elements</span></span>  

 <span data-ttu-id="c8154-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c8154-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c8154-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="c8154-106">Attributes</span></span>  
  
|<span data-ttu-id="c8154-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="c8154-107">Attribute</span></span>|<span data-ttu-id="c8154-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="c8154-108">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="c8154-109">Una cadena que especifica el URI en el que el aviso de privacidad se encuentra.</span><span class="sxs-lookup"><span data-stu-id="c8154-109">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="c8154-110">Un entero que especifica la versión de este aviso de privacidad.</span><span class="sxs-lookup"><span data-stu-id="c8154-110">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c8154-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c8154-111">Child Elements</span></span>  

 <span data-ttu-id="c8154-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c8154-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c8154-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c8154-113">Parent Elements</span></span>  
  
|<span data-ttu-id="c8154-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="c8154-114">Element</span></span>|<span data-ttu-id="c8154-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="c8154-115">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="c8154-116">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="c8154-116">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c8154-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8154-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="c8154-118">Enlaces</span><span class="sxs-lookup"><span data-stu-id="c8154-118">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c8154-119">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="c8154-119">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="c8154-120">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="c8154-120">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
