---
title: <pnrpPeerResolver>
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: d3e88d7f2dd991091d3d7abdc715e125ddc9ac56
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738779"
---
# \<pnrpPeerResolver>
<span data-ttu-id="8cd4b-101">Especifica que la resolución de PNRP (Protocolo de resolución de nombres de mismo nivel) será utilizada como resolución.</span><span class="sxs-lookup"><span data-stu-id="8cd4b-101">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="8cd4b-102">Este elemento es opcional porque PNRP es la resolución predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8cd4b-102">This element is optional because PNRP is the default resolver.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<pnrpResolver>**  
  
## <a name="syntax"></a><span data-ttu-id="8cd4b-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8cd4b-103">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8cd4b-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8cd4b-104">Attributes and Elements</span></span>  
 <span data-ttu-id="8cd4b-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8cd4b-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8cd4b-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="8cd4b-106">Attributes</span></span>  
  
|<span data-ttu-id="8cd4b-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="8cd4b-107">Attribute</span></span>|<span data-ttu-id="8cd4b-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="8cd4b-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8cd4b-109">resolverType</span><span class="sxs-lookup"><span data-stu-id="8cd4b-109">resolverType</span></span>|<span data-ttu-id="8cd4b-110">Una cadena que especifica la resolución que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="8cd4b-110">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="8cd4b-111">Este atributo es opcional.</span><span class="sxs-lookup"><span data-stu-id="8cd4b-111">This attribute is optional.</span></span> <span data-ttu-id="8cd4b-112">Si no se establece, o si está establecido en una cadena vacía, se utiliza PNRP.</span><span class="sxs-lookup"><span data-stu-id="8cd4b-112">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8cd4b-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8cd4b-113">Child Elements</span></span>  
 <span data-ttu-id="8cd4b-114">None</span><span class="sxs-lookup"><span data-stu-id="8cd4b-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8cd4b-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8cd4b-115">Parent Elements</span></span>  
  
|<span data-ttu-id="8cd4b-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="8cd4b-116">Element</span></span>|<span data-ttu-id="8cd4b-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="8cd4b-117">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="8cd4b-118">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="8cd4b-118">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8cd4b-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8cd4b-119">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="see-also"></a><span data-ttu-id="8cd4b-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8cd4b-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>
- <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="8cd4b-121">Enlaces</span><span class="sxs-lookup"><span data-stu-id="8cd4b-121">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="8cd4b-122">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="8cd4b-122">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="8cd4b-123">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="8cd4b-123">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="8cd4b-124">Resoluciones del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="8cd4b-124">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
