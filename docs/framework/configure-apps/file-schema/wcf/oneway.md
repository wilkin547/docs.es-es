---
title: <oneWay>
ms.date: 03/30/2017
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
ms.openlocfilehash: a5c773ea91de882920775ac8dc0ecc1da68a6c9f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738793"
---
# \<oneWay>
<span data-ttu-id="23941-101">Habilita el enrutamiento de paquetes y el uso de métodos unidireccionales para un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="23941-101">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oneWay>**  
  
## <a name="syntax"></a><span data-ttu-id="23941-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="23941-102">Syntax</span></span>  
  
```xml  
<oneWay packetRoutable="Boolean">
  <channelPoolSettings idleTimeout="TimeSpan"
                       leaseTimeout="TimeSpan"
                       maxOutboundConnectionsPerEndpoint="Integer" />
</oneWay>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="23941-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="23941-103">Attributes and Elements</span></span>  
 <span data-ttu-id="23941-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="23941-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="23941-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="23941-105">Attributes</span></span>  
  
|<span data-ttu-id="23941-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="23941-106">Attribute</span></span>|<span data-ttu-id="23941-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="23941-107">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="23941-108">Un valor booleano que especifica si se habilita el enrutamiento del paquete.</span><span class="sxs-lookup"><span data-stu-id="23941-108">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="23941-109">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="23941-109">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="23941-110">Un entero que especifica el número máximo de canales que se pueden aceptar.</span><span class="sxs-lookup"><span data-stu-id="23941-110">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="23941-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="23941-111">Child Elements</span></span>  
  
|<span data-ttu-id="23941-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="23941-112">Element</span></span>|<span data-ttu-id="23941-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="23941-113">Description</span></span>|  
|-------------|-----------------|  
|[\<channelPoolSettings>](channelpoolsettings.md)|<span data-ttu-id="23941-114">Un objeto <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> que contiene propiedades del grupo de canales para el canal actual.</span><span class="sxs-lookup"><span data-stu-id="23941-114">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="23941-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="23941-115">Parent Elements</span></span>  
  
|<span data-ttu-id="23941-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="23941-116">Element</span></span>|<span data-ttu-id="23941-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="23941-117">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="23941-118">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="23941-118">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23941-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="23941-119">Remarks</span></span>  
 <span data-ttu-id="23941-120">Para habilitar el enrutamiento de paquetes, se necesita una capa de conversión unidireccional, que proporciona este elemento.</span><span class="sxs-lookup"><span data-stu-id="23941-120">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="23941-121">Un usuario puede crear un enlace personalizado que coloque este enlace en una capa a través de un transporte consciente de sesión o de solicitud/respuesta para que se pueda realizar el enrutamiento de paquetes.</span><span class="sxs-lookup"><span data-stu-id="23941-121">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="23941-122">Este elemento también es útil cuando desea exponer los métodos unidireccionales de una manera más nativa.</span><span class="sxs-lookup"><span data-stu-id="23941-122">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="23941-123">Se pueden aplicar más transformaciones sobre esta capa, como Dúplex Compuesto y Mensajería de confianza.</span><span class="sxs-lookup"><span data-stu-id="23941-123">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23941-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="23941-124">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
- <xref:System.ServiceModel.Configuration.OneWayElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="23941-125">Enlaces</span><span class="sxs-lookup"><span data-stu-id="23941-125">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="23941-126">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="23941-126">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="23941-127">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="23941-127">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
