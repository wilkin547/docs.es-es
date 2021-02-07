---
description: 'Más información acerca de: <pnrpPeerResolver>'
title: <pnrpPeerResolver>
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: 4af6a63312fa300cfa33e578f01b8e07267ad3a1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683546"
---
# \<pnrpPeerResolver>

<span data-ttu-id="937b5-102">Especifica que la resolución de PNRP (Protocolo de resolución de nombres de mismo nivel) será utilizada como resolución.</span><span class="sxs-lookup"><span data-stu-id="937b5-102">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="937b5-103">Este elemento es opcional porque PNRP es la resolución predeterminada.</span><span class="sxs-lookup"><span data-stu-id="937b5-103">This element is optional because PNRP is the default resolver.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<pnrpResolver>**  
  
## <a name="syntax"></a><span data-ttu-id="937b5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="937b5-104">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="937b5-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="937b5-105">Attributes and Elements</span></span>  

 <span data-ttu-id="937b5-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="937b5-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="937b5-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="937b5-107">Attributes</span></span>  
  
|<span data-ttu-id="937b5-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="937b5-108">Attribute</span></span>|<span data-ttu-id="937b5-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="937b5-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="937b5-110">resolverType</span><span class="sxs-lookup"><span data-stu-id="937b5-110">resolverType</span></span>|<span data-ttu-id="937b5-111">Una cadena que especifica la resolución que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="937b5-111">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="937b5-112">Este atributo es opcional.</span><span class="sxs-lookup"><span data-stu-id="937b5-112">This attribute is optional.</span></span> <span data-ttu-id="937b5-113">Si no se establece, o si está establecido en una cadena vacía, se utiliza PNRP.</span><span class="sxs-lookup"><span data-stu-id="937b5-113">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="937b5-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="937b5-114">Child Elements</span></span>  

 <span data-ttu-id="937b5-115">None</span><span class="sxs-lookup"><span data-stu-id="937b5-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="937b5-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="937b5-116">Parent Elements</span></span>  
  
|<span data-ttu-id="937b5-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="937b5-117">Element</span></span>|<span data-ttu-id="937b5-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="937b5-118">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="937b5-119">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="937b5-119">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="937b5-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="937b5-120">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="see-also"></a><span data-ttu-id="937b5-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="937b5-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>
- <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="937b5-122">Enlaces</span><span class="sxs-lookup"><span data-stu-id="937b5-122">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="937b5-123">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="937b5-123">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="937b5-124">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="937b5-124">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="937b5-125">Resoluciones del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="937b5-125">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
