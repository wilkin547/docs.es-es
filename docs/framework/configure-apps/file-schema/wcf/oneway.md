---
title: '&lt;oneWay&gt;'
ms.date: 03/30/2017
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
ms.openlocfilehash: c909bce5b54976a215a59ca8fd9f097f574acd80
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54600302"
---
# <a name="ltonewaygt"></a><span data-ttu-id="f3ffb-102">&lt;oneWay&gt;</span><span class="sxs-lookup"><span data-stu-id="f3ffb-102">&lt;oneWay&gt;</span></span>
<span data-ttu-id="f3ffb-103">Habilita el enrutamiento de paquetes y el uso de métodos unidireccionales para un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="f3ffb-103">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
 <span data-ttu-id="f3ffb-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f3ffb-104">\<system.serviceModel></span></span>  
<span data-ttu-id="f3ffb-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="f3ffb-105">\<bindings></span></span>  
<span data-ttu-id="f3ffb-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="f3ffb-106">\<customBinding></span></span>  
<span data-ttu-id="f3ffb-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="f3ffb-107">\<binding></span></span>  
<span data-ttu-id="f3ffb-108">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="f3ffb-108">\<oneWay></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3ffb-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f3ffb-109">Syntax</span></span>  
  
```xml  
<oneWay packetRoutable="Boolean">
  <channelPoolSettings idleTimeout="TimeSpan"
                       leaseTimeout="TimeSpan"
                       maxOutboundConnectionsPerEndpopint="Integer" />
</oneWay>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f3ffb-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f3ffb-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f3ffb-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f3ffb-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f3ffb-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="f3ffb-112">Attributes</span></span>  
  
|<span data-ttu-id="f3ffb-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="f3ffb-113">Attribute</span></span>|<span data-ttu-id="f3ffb-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3ffb-114">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="f3ffb-115">Un valor booleano que especifica si se habilita el enrutamiento del paquete.</span><span class="sxs-lookup"><span data-stu-id="f3ffb-115">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="f3ffb-116">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="f3ffb-116">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="f3ffb-117">Un entero que especifica el número máximo de canales que se pueden aceptar.</span><span class="sxs-lookup"><span data-stu-id="f3ffb-117">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f3ffb-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f3ffb-118">Child Elements</span></span>  
  
|<span data-ttu-id="f3ffb-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="f3ffb-119">Element</span></span>|<span data-ttu-id="f3ffb-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3ffb-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f3ffb-121">\<channelPoolSettings></span><span class="sxs-lookup"><span data-stu-id="f3ffb-121">\<channelPoolSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/channelpoolsettings.md)|<span data-ttu-id="f3ffb-122">Un objeto <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> que contiene propiedades del grupo de canales para el canal actual.</span><span class="sxs-lookup"><span data-stu-id="f3ffb-122">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f3ffb-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f3ffb-123">Parent Elements</span></span>  
  
|<span data-ttu-id="f3ffb-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="f3ffb-124">Element</span></span>|<span data-ttu-id="f3ffb-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3ffb-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f3ffb-126">\<binding></span><span class="sxs-lookup"><span data-stu-id="f3ffb-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="f3ffb-127">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="f3ffb-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3ffb-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f3ffb-128">Remarks</span></span>  
 <span data-ttu-id="f3ffb-129">Para habilitar el enrutamiento de paquetes, se necesita una capa de conversión unidireccional, que proporciona este elemento.</span><span class="sxs-lookup"><span data-stu-id="f3ffb-129">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="f3ffb-130">Un usuario puede crear un enlace personalizado que coloque este enlace en una capa a través de un transporte consciente de sesión o de solicitud/respuesta para que se pueda realizar el enrutamiento de paquetes.</span><span class="sxs-lookup"><span data-stu-id="f3ffb-130">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="f3ffb-131">Este elemento también es útil cuando desea exponer los métodos unidireccionales de una manera más nativa.</span><span class="sxs-lookup"><span data-stu-id="f3ffb-131">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="f3ffb-132">Se pueden aplicar más transformaciones sobre esta capa, como Dúplex Compuesto y Mensajería de confianza.</span><span class="sxs-lookup"><span data-stu-id="f3ffb-132">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3ffb-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3ffb-133">See also</span></span>
- <xref:System.ServiceModel.Channels.OneWayBindingElement>
- <xref:System.ServiceModel.Configuration.OneWayElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="f3ffb-134">Enlaces</span><span class="sxs-lookup"><span data-stu-id="f3ffb-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="f3ffb-135">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="f3ffb-135">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="f3ffb-136">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="f3ffb-136">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="f3ffb-137">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="f3ffb-137">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
