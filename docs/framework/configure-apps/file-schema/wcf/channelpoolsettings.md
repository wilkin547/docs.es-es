---
title: <channelPoolSettings>
ms.date: 03/30/2017
ms.assetid: 4755f3d3-4213-4c68-ae7f-45b67d744459
ms.openlocfilehash: 8638d56ccb4aaa1c5ac735aa268823af2b1fbc6d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176076"
---
# \<channelPoolSettings>

<span data-ttu-id="eaf5f-101">Especifica los valores de grupo de canal para un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="eaf5f-101">Specifies the channel pool settings for a custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oneWay>**](oneway.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<channelPoolSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="eaf5f-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eaf5f-102">Syntax</span></span>  
  
```xml  
<channelPoolSettings idleTimeout="TimeSpan"
                     leaseTimeout="TimeSpan"
                     maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eaf5f-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="eaf5f-103">Attributes and Elements</span></span>  

 <span data-ttu-id="eaf5f-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="eaf5f-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eaf5f-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="eaf5f-105">Attributes</span></span>  
  
|<span data-ttu-id="eaf5f-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="eaf5f-106">Attribute</span></span>|<span data-ttu-id="eaf5f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="eaf5f-107">Description</span></span>|  
|---------------|-----------------|  
|`idleTimeout`|<span data-ttu-id="eaf5f-108"><xref:System.TimeSpan> positivo que especifica el tiempo máximo que los canales del grupo pueden estar inactivos antes de que desconectarse.</span><span class="sxs-lookup"><span data-stu-id="eaf5f-108">A positive <xref:System.TimeSpan> that specifies the maximum time the channels in the pool can be idle before being disconnected.</span></span> <span data-ttu-id="eaf5f-109">El valor predeterminado es 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="eaf5f-109">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="eaf5f-110"><xref:System.TimeSpan> que especifica el intervalo de tiempo después del cual un canal, cuando se devuelve al grupo, se cierra.</span><span class="sxs-lookup"><span data-stu-id="eaf5f-110">A <xref:System.TimeSpan> that specifies the interval of time after which a channel, when returned to the pool, is closed.</span></span> <span data-ttu-id="eaf5f-111">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="eaf5f-111">The default is 00:10:00.</span></span>|  
|`maxOutboundChannelsPerEndpoint`|<span data-ttu-id="eaf5f-112">Entero positivo que especifica el número máximo de canales que se pueden almacenar en el grupo para cada punto de conexión remoto.</span><span class="sxs-lookup"><span data-stu-id="eaf5f-112">A positive integer that specifies the maximum number of channels that can be stored in the pool for each remote endpoint.</span></span> <span data-ttu-id="eaf5f-113">El valor predeterminado es 10.</span><span class="sxs-lookup"><span data-stu-id="eaf5f-113">The default is 10.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eaf5f-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="eaf5f-114">Child Elements</span></span>  

 <span data-ttu-id="eaf5f-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="eaf5f-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eaf5f-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="eaf5f-116">Parent Elements</span></span>  
  
|<span data-ttu-id="eaf5f-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="eaf5f-117">Element</span></span>|<span data-ttu-id="eaf5f-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="eaf5f-118">Description</span></span>|  
|-------------|-----------------|  
|[\<oneWay>](oneway.md)|<span data-ttu-id="eaf5f-119">Habilita el enrutamiento del paquete para un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="eaf5f-119">Enables packet routing for a custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eaf5f-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="eaf5f-120">Remarks</span></span>  

 <span data-ttu-id="eaf5f-121">Las cuotas se utilizan como un mecanismo de la directiva para evitar el consumo excesivo de recursos .</span><span class="sxs-lookup"><span data-stu-id="eaf5f-121">Quotas are used as a policy mechanism to prevent the consumption of excessive resources.</span></span> <span data-ttu-id="eaf5f-122">Evitan los ataques por denegación de servicio (DoS), tanto malintencionados como involuntarios.</span><span class="sxs-lookup"><span data-stu-id="eaf5f-122">They prevent Denial of Service (DOS) attacks that are either malicious or unintentional.</span></span> <span data-ttu-id="eaf5f-123">Utilice este elemento al establecer las cuotas del canal en un canal personalizado.</span><span class="sxs-lookup"><span data-stu-id="eaf5f-123">Use this element when setting channel quotas on a custom channel.</span></span>  
  
 <span data-ttu-id="eaf5f-124">`ChannelPoolSettings` especifica tres cuotas:</span><span class="sxs-lookup"><span data-stu-id="eaf5f-124">`ChannelPoolSettings` specifies three quotas:</span></span>  
  
- <span data-ttu-id="eaf5f-125">La cuota `idleTimeout` se utiliza para mitigar los ataques por denegación de servicio (DoS) en el servidor basados en acaparar los recursos durante un período de tiempo extendido.</span><span class="sxs-lookup"><span data-stu-id="eaf5f-125">The `idleTimeout` quota is used to mitigate Denial of Service (DOS) attacks on the server that rely on tying up resources for an extended period of time.</span></span> <span data-ttu-id="eaf5f-126">Por parte del cliente, establecer el valor correcto puede aumentar la confiabilidad de conectar con el servicio.</span><span class="sxs-lookup"><span data-stu-id="eaf5f-126">On the client, setting the correct value can increase the reliability of connecting with the service.</span></span> <span data-ttu-id="eaf5f-127">El valor predeterminado está basado en una asignación de recursos conservadoramente modesta.</span><span class="sxs-lookup"><span data-stu-id="eaf5f-127">The default value is based on a conservatively modest allocation of resources.</span></span> <span data-ttu-id="eaf5f-128">Es conveniente para un entorno de desarrollo y escenarios de instalación pequeños.</span><span class="sxs-lookup"><span data-stu-id="eaf5f-128">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="eaf5f-129">Los administradores del servicio deberían revisar el valor si una instalación se está quedando sin recursos o si las conexiones se limitan a pesar de la disponibilidad de recursos adicionales.</span><span class="sxs-lookup"><span data-stu-id="eaf5f-129">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
- <span data-ttu-id="eaf5f-130">La cuota `leaseTimeout` se utiliza a para la integración con equilibradores de carga y para mejorar la confiabilidad.</span><span class="sxs-lookup"><span data-stu-id="eaf5f-130">The `leaseTimeout` quota is used to for integration with load balancers and for improving reliability.</span></span> <span data-ttu-id="eaf5f-131">El valor predeterminado está basado en una asignación de recursos conservadora.</span><span class="sxs-lookup"><span data-stu-id="eaf5f-131">The default value is based on a conservative allocation of resources.</span></span> <span data-ttu-id="eaf5f-132">Es conveniente para un entorno de desarrollo y escenarios de instalación pequeños.</span><span class="sxs-lookup"><span data-stu-id="eaf5f-132">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="eaf5f-133">Los administradores del servicio deberían revisar el valor si una instalación se está quedando sin recursos o si las conexiones se limitan a pesar de la disponibilidad de recursos adicionales.</span><span class="sxs-lookup"><span data-stu-id="eaf5f-133">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
- <span data-ttu-id="eaf5f-134">La cuota `maxOutboundChannelsPerEndpoint` establece los límites de la caché en el servidor y el cliente y se utiliza para mejorar la confiabilidad.</span><span class="sxs-lookup"><span data-stu-id="eaf5f-134">The `maxOutboundChannelsPerEndpoint` quota sets cache limits on both the server and the client and is used to improve reliability.</span></span> <span data-ttu-id="eaf5f-135">El valor predeterminado está basado en una asignación de recursos conservadoramente modesta que es conveniente para un entorno de desarrollo y para escenarios de instalación pequeños.</span><span class="sxs-lookup"><span data-stu-id="eaf5f-135">The default value is based on a conservatively modest allocation of resources that is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="eaf5f-136">Los administradores del servicio deberían revisar el valor si una instalación se está quedando sin recursos o si las conexiones se limitan a pesar de la disponibilidad de recursos adicionales.</span><span class="sxs-lookup"><span data-stu-id="eaf5f-136">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaf5f-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eaf5f-137">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
- <xref:System.ServiceModel.Configuration.OneWayElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [\<oneWay>](oneway.md)
- [<span data-ttu-id="eaf5f-138">Enlaces</span><span class="sxs-lookup"><span data-stu-id="eaf5f-138">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="eaf5f-139">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="eaf5f-139">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="eaf5f-140">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="eaf5f-140">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
