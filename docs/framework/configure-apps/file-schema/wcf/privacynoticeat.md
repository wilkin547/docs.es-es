---
description: 'Más información acerca de: <privacyNoticeAt>'
title: <privacyNoticeAt>
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: 2e38d43becd783cc50afba5a029d3ab9905ec15a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683507"
---
# \<privacyNoticeAt>

<span data-ttu-id="f9e7e-102">Representa un elemento de configuración que especifica un aviso de privacidad usado en el enlace `wsFederationHttp`.</span><span class="sxs-lookup"><span data-stu-id="f9e7e-102">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<privacyNotice>**  
  
## <a name="syntax"></a><span data-ttu-id="f9e7e-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f9e7e-103">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="f9e7e-104">Tipo</span><span class="sxs-lookup"><span data-stu-id="f9e7e-104">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f9e7e-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f9e7e-105">Attributes and Elements</span></span>  

 <span data-ttu-id="f9e7e-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f9e7e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f9e7e-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="f9e7e-107">Attributes</span></span>  
  
|<span data-ttu-id="f9e7e-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="f9e7e-108">Attribute</span></span>|<span data-ttu-id="f9e7e-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="f9e7e-109">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="f9e7e-110">Una cadena que especifica el URI en el que el aviso de privacidad se encuentra.</span><span class="sxs-lookup"><span data-stu-id="f9e7e-110">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="f9e7e-111">Un entero que especifica la versión de este aviso de privacidad.</span><span class="sxs-lookup"><span data-stu-id="f9e7e-111">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f9e7e-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f9e7e-112">Child Elements</span></span>  

 <span data-ttu-id="f9e7e-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f9e7e-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f9e7e-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f9e7e-114">Parent Elements</span></span>  
  
|<span data-ttu-id="f9e7e-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="f9e7e-115">Element</span></span>|<span data-ttu-id="f9e7e-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="f9e7e-116">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="f9e7e-117">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="f9e7e-117">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f9e7e-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9e7e-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="f9e7e-119">Enlaces</span><span class="sxs-lookup"><span data-stu-id="f9e7e-119">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f9e7e-120">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="f9e7e-120">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="f9e7e-121">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="f9e7e-121">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
