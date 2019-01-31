---
title: <oneWay>
ms.date: 03/30/2017
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
ms.openlocfilehash: 35631cc4b120169e0cadb80c6beba26ab9eafd7a
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283275"
---
# <a name="oneway"></a><span data-ttu-id="8fda6-101">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="8fda6-101">\<oneWay></span></span>
<span data-ttu-id="8fda6-102">Habilita el enrutamiento de paquetes y el uso de métodos unidireccionales para un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="8fda6-102">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
 <span data-ttu-id="8fda6-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="8fda6-103">\<system.serviceModel></span></span>  
<span data-ttu-id="8fda6-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="8fda6-104">\<bindings></span></span>  
<span data-ttu-id="8fda6-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="8fda6-105">\<customBinding></span></span>  
<span data-ttu-id="8fda6-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="8fda6-106">\<binding></span></span>  
<span data-ttu-id="8fda6-107">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="8fda6-107">\<oneWay></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fda6-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8fda6-108">Syntax</span></span>  
  
```xml  
<oneWay packetRoutable="Boolean">
  <channelPoolSettings idleTimeout="TimeSpan"
                       leaseTimeout="TimeSpan"
                       maxOutboundConnectionsPerEndpopint="Integer" />
</oneWay>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8fda6-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8fda6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8fda6-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8fda6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8fda6-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="8fda6-111">Attributes</span></span>  
  
|<span data-ttu-id="8fda6-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="8fda6-112">Attribute</span></span>|<span data-ttu-id="8fda6-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="8fda6-113">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="8fda6-114">Un valor booleano que especifica si se habilita el enrutamiento del paquete.</span><span class="sxs-lookup"><span data-stu-id="8fda6-114">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="8fda6-115">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="8fda6-115">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="8fda6-116">Un entero que especifica el número máximo de canales que se pueden aceptar.</span><span class="sxs-lookup"><span data-stu-id="8fda6-116">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8fda6-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8fda6-117">Child Elements</span></span>  
  
|<span data-ttu-id="8fda6-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="8fda6-118">Element</span></span>|<span data-ttu-id="8fda6-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="8fda6-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8fda6-120">\<channelPoolSettings></span><span class="sxs-lookup"><span data-stu-id="8fda6-120">\<channelPoolSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/channelpoolsettings.md)|<span data-ttu-id="8fda6-121">Un objeto <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> que contiene propiedades del grupo de canales para el canal actual.</span><span class="sxs-lookup"><span data-stu-id="8fda6-121">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8fda6-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8fda6-122">Parent Elements</span></span>  
  
|<span data-ttu-id="8fda6-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="8fda6-123">Element</span></span>|<span data-ttu-id="8fda6-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="8fda6-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8fda6-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="8fda6-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="8fda6-126">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="8fda6-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8fda6-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8fda6-127">Remarks</span></span>  
 <span data-ttu-id="8fda6-128">Para habilitar el enrutamiento de paquetes, se necesita una capa de conversión unidireccional, que proporciona este elemento.</span><span class="sxs-lookup"><span data-stu-id="8fda6-128">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="8fda6-129">Un usuario puede crear un enlace personalizado que coloque este enlace en una capa a través de un transporte consciente de sesión o de solicitud/respuesta para que se pueda realizar el enrutamiento de paquetes.</span><span class="sxs-lookup"><span data-stu-id="8fda6-129">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="8fda6-130">Este elemento también es útil cuando desea exponer los métodos unidireccionales de una manera más nativa.</span><span class="sxs-lookup"><span data-stu-id="8fda6-130">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="8fda6-131">Se pueden aplicar más transformaciones sobre esta capa, como Dúplex Compuesto y Mensajería de confianza.</span><span class="sxs-lookup"><span data-stu-id="8fda6-131">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fda6-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="8fda6-132">See also</span></span>
- <xref:System.ServiceModel.Channels.OneWayBindingElement>
- <xref:System.ServiceModel.Configuration.OneWayElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="8fda6-133">Enlaces</span><span class="sxs-lookup"><span data-stu-id="8fda6-133">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="8fda6-134">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="8fda6-134">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="8fda6-135">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="8fda6-135">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="8fda6-136">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="8fda6-136">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
