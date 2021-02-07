---
description: 'Más información acerca de: <oneWay>'
title: <oneWay>
ms.date: 03/30/2017
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
ms.openlocfilehash: 8e3314dd14525b5f7585a7336c00b615da56d1c7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683845"
---
# \<oneWay>

<span data-ttu-id="0902d-102">Habilita el enrutamiento de paquetes y el uso de métodos unidireccionales para un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="0902d-102">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oneWay>**  
  
## <a name="syntax"></a><span data-ttu-id="0902d-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0902d-103">Syntax</span></span>  
  
```xml  
<oneWay packetRoutable="Boolean">
  <channelPoolSettings idleTimeout="TimeSpan"
                       leaseTimeout="TimeSpan"
                       maxOutboundConnectionsPerEndpoint="Integer" />
</oneWay>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0902d-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0902d-104">Attributes and Elements</span></span>  

 <span data-ttu-id="0902d-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0902d-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0902d-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="0902d-106">Attributes</span></span>  
  
|<span data-ttu-id="0902d-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="0902d-107">Attribute</span></span>|<span data-ttu-id="0902d-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="0902d-108">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="0902d-109">Un valor booleano que especifica si se habilita el enrutamiento del paquete.</span><span class="sxs-lookup"><span data-stu-id="0902d-109">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="0902d-110">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="0902d-110">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="0902d-111">Un entero que especifica el número máximo de canales que se pueden aceptar.</span><span class="sxs-lookup"><span data-stu-id="0902d-111">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0902d-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0902d-112">Child Elements</span></span>  
  
|<span data-ttu-id="0902d-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="0902d-113">Element</span></span>|<span data-ttu-id="0902d-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="0902d-114">Description</span></span>|  
|-------------|-----------------|  
|[\<channelPoolSettings>](channelpoolsettings.md)|<span data-ttu-id="0902d-115">Un objeto <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> que contiene propiedades del grupo de canales para el canal actual.</span><span class="sxs-lookup"><span data-stu-id="0902d-115">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0902d-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0902d-116">Parent Elements</span></span>  
  
|<span data-ttu-id="0902d-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="0902d-117">Element</span></span>|<span data-ttu-id="0902d-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="0902d-118">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="0902d-119">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="0902d-119">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0902d-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0902d-120">Remarks</span></span>  

 <span data-ttu-id="0902d-121">Para habilitar el enrutamiento de paquetes, se necesita una capa de conversión unidireccional, que proporciona este elemento.</span><span class="sxs-lookup"><span data-stu-id="0902d-121">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="0902d-122">Un usuario puede crear un enlace personalizado que coloque este enlace en una capa a través de un transporte consciente de sesión o de solicitud/respuesta para que se pueda realizar el enrutamiento de paquetes.</span><span class="sxs-lookup"><span data-stu-id="0902d-122">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="0902d-123">Este elemento también es útil cuando desea exponer los métodos unidireccionales de una manera más nativa.</span><span class="sxs-lookup"><span data-stu-id="0902d-123">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="0902d-124">Se pueden aplicar más transformaciones sobre esta capa, como Dúplex Compuesto y Mensajería de confianza.</span><span class="sxs-lookup"><span data-stu-id="0902d-124">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0902d-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="0902d-125">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
- <xref:System.ServiceModel.Configuration.OneWayElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="0902d-126">Enlaces</span><span class="sxs-lookup"><span data-stu-id="0902d-126">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="0902d-127">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="0902d-127">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="0902d-128">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="0902d-128">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
