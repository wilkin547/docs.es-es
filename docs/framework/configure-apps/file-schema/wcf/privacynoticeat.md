---
title: <privacyNoticeAt>
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: 2ff70d3a8636970434582e417e4549ab6b433fc1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738765"
---
# \<privacyNoticeAt>
<span data-ttu-id="c52d7-101">Representa un elemento de configuración que especifica un aviso de privacidad usado en el enlace `wsFederationHttp`.</span><span class="sxs-lookup"><span data-stu-id="c52d7-101">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<privacyNotice>**  
  
## <a name="syntax"></a><span data-ttu-id="c52d7-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c52d7-102">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="c52d7-103">Tipo</span><span class="sxs-lookup"><span data-stu-id="c52d7-103">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c52d7-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c52d7-104">Attributes and Elements</span></span>  
 <span data-ttu-id="c52d7-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c52d7-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c52d7-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="c52d7-106">Attributes</span></span>  
  
|<span data-ttu-id="c52d7-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="c52d7-107">Attribute</span></span>|<span data-ttu-id="c52d7-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="c52d7-108">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="c52d7-109">Una cadena que especifica el URI en el que el aviso de privacidad se encuentra.</span><span class="sxs-lookup"><span data-stu-id="c52d7-109">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="c52d7-110">Un entero que especifica la versión de este aviso de privacidad.</span><span class="sxs-lookup"><span data-stu-id="c52d7-110">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c52d7-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c52d7-111">Child Elements</span></span>  
 <span data-ttu-id="c52d7-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c52d7-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c52d7-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c52d7-113">Parent Elements</span></span>  
  
|<span data-ttu-id="c52d7-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="c52d7-114">Element</span></span>|<span data-ttu-id="c52d7-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="c52d7-115">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="c52d7-116">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="c52d7-116">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c52d7-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c52d7-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="c52d7-118">Enlaces</span><span class="sxs-lookup"><span data-stu-id="c52d7-118">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c52d7-119">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="c52d7-119">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="c52d7-120">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="c52d7-120">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
