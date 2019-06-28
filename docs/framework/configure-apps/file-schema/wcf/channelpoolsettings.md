---
title: <channelPoolSettings>
ms.date: 03/30/2017
ms.assetid: 4755f3d3-4213-4c68-ae7f-45b67d744459
ms.openlocfilehash: 70f7452a22ae08d6eccd7d3644bdc8df45087ae0
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423185"
---
# <a name="channelpoolsettings"></a><span data-ttu-id="c742c-101">\<channelPoolSettings></span><span class="sxs-lookup"><span data-stu-id="c742c-101">\<channelPoolSettings></span></span>
<span data-ttu-id="c742c-102">Especifica los valores de grupo de canal para un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="c742c-102">Specifies the channel pool settings for a custom binding.</span></span>  
  
 <span data-ttu-id="c742c-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c742c-103">\<system.serviceModel></span></span>  
<span data-ttu-id="c742c-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="c742c-104">\<bindings></span></span>  
<span data-ttu-id="c742c-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="c742c-105">\<customBinding></span></span>  
<span data-ttu-id="c742c-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="c742c-106">\<binding></span></span>  
<span data-ttu-id="c742c-107">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="c742c-107">\<oneWay></span></span>  
<span data-ttu-id="c742c-108">\<channelPoolSettings></span><span class="sxs-lookup"><span data-stu-id="c742c-108">\<channelPoolSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c742c-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c742c-109">Syntax</span></span>  
  
```xml  
<channelPoolSettings idleTimeout="TimeSpan"
                     leaseTimeout="TimeSpan"
                     maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c742c-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c742c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c742c-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c742c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c742c-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="c742c-112">Attributes</span></span>  
  
|<span data-ttu-id="c742c-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="c742c-113">Attribute</span></span>|<span data-ttu-id="c742c-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="c742c-114">Description</span></span>|  
|---------------|-----------------|  
|`idleTimeout`|<span data-ttu-id="c742c-115"><xref:System.TimeSpan> positivo que especifica el tiempo máximo que los canales del grupo pueden estar inactivos antes de que desconectarse.</span><span class="sxs-lookup"><span data-stu-id="c742c-115">A positive <xref:System.TimeSpan> that specifies the maximum time the channels in the pool can be idle before being disconnected.</span></span> <span data-ttu-id="c742c-116">El valor predeterminado es 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="c742c-116">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="c742c-117"><xref:System.TimeSpan> que especifica el intervalo de tiempo después del cual un canal, cuando se devuelve al grupo, se cierra.</span><span class="sxs-lookup"><span data-stu-id="c742c-117">A <xref:System.TimeSpan> that specifies the interval of time after which a channel, when returned to the pool, is closed.</span></span> <span data-ttu-id="c742c-118">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="c742c-118">The default is 00:10:00.</span></span>|  
|`maxOutboundChannelsPerEndpoint`|<span data-ttu-id="c742c-119">Entero positivo que especifica el número máximo de canales que se pueden almacenar en el grupo para cada punto de conexión remoto.</span><span class="sxs-lookup"><span data-stu-id="c742c-119">A positive integer that specifies the maximum number of channels that can be stored in the pool for each remote endpoint.</span></span> <span data-ttu-id="c742c-120">El valor predeterminado es 10.</span><span class="sxs-lookup"><span data-stu-id="c742c-120">The default is 10.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c742c-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c742c-121">Child Elements</span></span>  
 <span data-ttu-id="c742c-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c742c-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c742c-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c742c-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c742c-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="c742c-124">Element</span></span>|<span data-ttu-id="c742c-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="c742c-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c742c-126">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="c742c-126">\<oneWay></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)|<span data-ttu-id="c742c-127">Habilita el enrutamiento del paquete para un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="c742c-127">Enables packet routing for a custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c742c-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c742c-128">Remarks</span></span>  
 <span data-ttu-id="c742c-129">Las cuotas se utilizan como un mecanismo de la directiva para evitar el consumo excesivo de recursos .</span><span class="sxs-lookup"><span data-stu-id="c742c-129">Quotas are used as a policy mechanism to prevent the consumption of excessive resources.</span></span> <span data-ttu-id="c742c-130">Evitan los ataques por denegación de servicio (DoS), tanto malintencionados como involuntarios.</span><span class="sxs-lookup"><span data-stu-id="c742c-130">They prevent Denial of Service (DOS) attacks that are either malicious or unintentional.</span></span> <span data-ttu-id="c742c-131">Utilice este elemento al establecer las cuotas del canal en un canal personalizado.</span><span class="sxs-lookup"><span data-stu-id="c742c-131">Use this element when setting channel quotas on a custom channel.</span></span>  
  
 <span data-ttu-id="c742c-132">`ChannelPoolSettings` especifica tres cuotas:</span><span class="sxs-lookup"><span data-stu-id="c742c-132">`ChannelPoolSettings` specifies three quotas:</span></span>  
  
- <span data-ttu-id="c742c-133">La cuota `idleTimeout` se utiliza para mitigar los ataques por denegación de servicio (DoS) en el servidor basados en acaparar los recursos durante un período de tiempo extendido.</span><span class="sxs-lookup"><span data-stu-id="c742c-133">The `idleTimeout` quota is used to mitigate Denial of Service (DOS) attacks on the server that rely on tying up resources for an extended period of time.</span></span> <span data-ttu-id="c742c-134">Por parte del cliente, establecer el valor correcto puede aumentar la confiabilidad de conectar con el servicio.</span><span class="sxs-lookup"><span data-stu-id="c742c-134">On the client, setting the correct value can increase the reliability of connecting with the service.</span></span> <span data-ttu-id="c742c-135">El valor predeterminado está basado en una asignación de recursos conservadoramente modesta.</span><span class="sxs-lookup"><span data-stu-id="c742c-135">The default value is based on a conservatively modest allocation of resources.</span></span> <span data-ttu-id="c742c-136">Es conveniente para un entorno de desarrollo y escenarios de instalación pequeños.</span><span class="sxs-lookup"><span data-stu-id="c742c-136">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="c742c-137">Los administradores del servicio deberían revisar el valor si una instalación se está quedando sin recursos o si las conexiones se limitan a pesar de la disponibilidad de recursos adicionales.</span><span class="sxs-lookup"><span data-stu-id="c742c-137">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
- <span data-ttu-id="c742c-138">La cuota `leaseTimeout` se utiliza a para la integración con equilibradores de carga y para mejorar la confiabilidad.</span><span class="sxs-lookup"><span data-stu-id="c742c-138">The `leaseTimeout` quota is used to for integration with load balancers and for improving reliability.</span></span> <span data-ttu-id="c742c-139">El valor predeterminado está basado en una asignación de recursos conservadora.</span><span class="sxs-lookup"><span data-stu-id="c742c-139">The default value is based on a conservative allocation of resources.</span></span> <span data-ttu-id="c742c-140">Es conveniente para un entorno de desarrollo y escenarios de instalación pequeños.</span><span class="sxs-lookup"><span data-stu-id="c742c-140">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="c742c-141">Los administradores del servicio deberían revisar el valor si una instalación se está quedando sin recursos o si las conexiones se limitan a pesar de la disponibilidad de recursos adicionales.</span><span class="sxs-lookup"><span data-stu-id="c742c-141">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
- <span data-ttu-id="c742c-142">La cuota `maxOutboundChannelsPerEndpoint` establece los límites de la caché en el servidor y el cliente y se utiliza para mejorar la confiabilidad.</span><span class="sxs-lookup"><span data-stu-id="c742c-142">The `maxOutboundChannelsPerEndpoint` quota sets cache limits on both the server and the client and is used to improve reliability.</span></span> <span data-ttu-id="c742c-143">El valor predeterminado está basado en una asignación de recursos conservadoramente modesta que es conveniente para un entorno de desarrollo y para escenarios de instalación pequeños.</span><span class="sxs-lookup"><span data-stu-id="c742c-143">The default value is based on a conservatively modest allocation of resources that is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="c742c-144">Los administradores del servicio deberían revisar el valor si una instalación se está quedando sin recursos o si las conexiones se limitan a pesar de la disponibilidad de recursos adicionales.</span><span class="sxs-lookup"><span data-stu-id="c742c-144">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c742c-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="c742c-145">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
- <xref:System.ServiceModel.Configuration.OneWayElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="c742c-146">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="c742c-146">\<oneWay></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)
- [<span data-ttu-id="c742c-147">Enlaces</span><span class="sxs-lookup"><span data-stu-id="c742c-147">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="c742c-148">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="c742c-148">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="c742c-149">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="c742c-149">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="c742c-150">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="c742c-150">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
