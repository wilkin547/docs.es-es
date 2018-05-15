---
title: '&lt;Unidireccional&gt;'
ms.date: 03/30/2017
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
ms.openlocfilehash: f9a5631501b3879463606f526485314efd5eff2b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltonewaygt"></a><span data-ttu-id="36136-102">&lt;Unidireccional&gt;</span><span class="sxs-lookup"><span data-stu-id="36136-102">&lt;oneWay&gt;</span></span>
<span data-ttu-id="36136-103">Habilita el enrutamiento de paquetes y el uso de métodos unidireccionales para un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="36136-103">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
 <span data-ttu-id="36136-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="36136-104">\<system.serviceModel></span></span>  
<span data-ttu-id="36136-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="36136-105">\<bindings></span></span>  
<span data-ttu-id="36136-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="36136-106">\<customBinding></span></span>  
<span data-ttu-id="36136-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="36136-107">\<binding></span></span>  
<span data-ttu-id="36136-108">\<oneWay ></span><span class="sxs-lookup"><span data-stu-id="36136-108">\<oneWay></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36136-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="36136-109">Syntax</span></span>  
  
```xml  
<oneWay packetRoutable="Boolean">  
        <channelPoolSettings  
           idleTimeout"TimeSpan"  
          leaseTimeout"TimeSpan"  
          maxOutboundConnectionsPerEndpopint="Integer" />  
```  
  
```xml  
</oneWay>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="36136-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="36136-110">Attributes and Elements</span></span>  
 <span data-ttu-id="36136-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="36136-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="36136-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="36136-112">Attributes</span></span>  
  
|<span data-ttu-id="36136-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="36136-113">Attribute</span></span>|<span data-ttu-id="36136-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="36136-114">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="36136-115">Un valor booleano que especifica si se habilita el enrutamiento del paquete.</span><span class="sxs-lookup"><span data-stu-id="36136-115">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="36136-116">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="36136-116">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="36136-117">Un entero que especifica el número máximo de canales que se pueden aceptar.</span><span class="sxs-lookup"><span data-stu-id="36136-117">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="36136-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="36136-118">Child Elements</span></span>  
  
|<span data-ttu-id="36136-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="36136-119">Element</span></span>|<span data-ttu-id="36136-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="36136-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36136-121">\<channelPoolSettings ></span><span class="sxs-lookup"><span data-stu-id="36136-121">\<channelPoolSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/channelpoolsettings.md)|<span data-ttu-id="36136-122">Un objeto <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> que contiene propiedades del grupo de canales para el canal actual.</span><span class="sxs-lookup"><span data-stu-id="36136-122">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="36136-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="36136-123">Parent Elements</span></span>  
  
|<span data-ttu-id="36136-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="36136-124">Element</span></span>|<span data-ttu-id="36136-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="36136-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36136-126">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="36136-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="36136-127">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="36136-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36136-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="36136-128">Remarks</span></span>  
 <span data-ttu-id="36136-129">Para habilitar el enrutamiento de paquetes, se necesita una capa de conversión unidireccional, que proporciona este elemento.</span><span class="sxs-lookup"><span data-stu-id="36136-129">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="36136-130">Un usuario puede crear un enlace personalizado que coloque este enlace en una capa a través de un transporte consciente de sesión o de solicitud/respuesta para que se pueda realizar el enrutamiento de paquetes.</span><span class="sxs-lookup"><span data-stu-id="36136-130">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="36136-131">Este elemento también es útil cuando desea exponer los métodos unidireccionales de una manera más nativa.</span><span class="sxs-lookup"><span data-stu-id="36136-131">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="36136-132">Se pueden aplicar más transformaciones sobre esta capa, como Dúplex Compuesto y Mensajería de confianza.</span><span class="sxs-lookup"><span data-stu-id="36136-132">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36136-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="36136-133">See Also</span></span>  
 <xref:System.ServiceModel.Channels.OneWayBindingElement>  
 <xref:System.ServiceModel.Configuration.OneWayElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="36136-134">Enlaces</span><span class="sxs-lookup"><span data-stu-id="36136-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="36136-135">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="36136-135">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="36136-136">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="36136-136">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="36136-137">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="36136-137">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
