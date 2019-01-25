---
title: '&lt;channelPoolSettings&gt;'
ms.date: 03/30/2017
ms.assetid: 4755f3d3-4213-4c68-ae7f-45b67d744459
ms.openlocfilehash: 666602bde75cd21b5b3d16bd4d5e6cf63c12d593
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554964"
---
# <a name="ltchannelpoolsettingsgt"></a><span data-ttu-id="3848a-102">&lt;channelPoolSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="3848a-102">&lt;channelPoolSettings&gt;</span></span>
<span data-ttu-id="3848a-103">Especifica los valores de grupo de canal para un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="3848a-103">Specifies the channel pool settings for a custom binding.</span></span>  
  
 <span data-ttu-id="3848a-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3848a-104">\<system.serviceModel></span></span>  
<span data-ttu-id="3848a-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="3848a-105">\<bindings></span></span>  
<span data-ttu-id="3848a-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="3848a-106">\<customBinding></span></span>  
<span data-ttu-id="3848a-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="3848a-107">\<binding></span></span>  
<span data-ttu-id="3848a-108">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="3848a-108">\<oneWay></span></span>  
<span data-ttu-id="3848a-109">\<channelPoolSettings></span><span class="sxs-lookup"><span data-stu-id="3848a-109">\<channelPoolSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3848a-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3848a-110">Syntax</span></span>  
  
```xml  
<channelPoolSettings idleTimeout="TimeSpan"
                     leaseTimeout="TimeSpan"
                     maxOutboundConnectionsPerEndpopint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3848a-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3848a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="3848a-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3848a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3848a-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="3848a-113">Attributes</span></span>  
  
|<span data-ttu-id="3848a-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="3848a-114">Attribute</span></span>|<span data-ttu-id="3848a-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="3848a-115">Description</span></span>|  
|---------------|-----------------|  
|`idleTimeout`|<span data-ttu-id="3848a-116"><xref:System.TimeSpan> positivo que especifica el tiempo máximo que los canales del grupo pueden estar inactivos antes de que desconectarse.</span><span class="sxs-lookup"><span data-stu-id="3848a-116">A positive <xref:System.TimeSpan> that specifies the maximum time the channels in the pool can be idle before being disconnected.</span></span> <span data-ttu-id="3848a-117">El valor predeterminado es 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="3848a-117">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="3848a-118"><xref:System.TimeSpan> que especifica el intervalo de tiempo después del cual un canal, cuando se devuelve al grupo, se cierra.</span><span class="sxs-lookup"><span data-stu-id="3848a-118">A <xref:System.TimeSpan> that specifies the interval of time after which a channel, when returned to the pool, is closed.</span></span> <span data-ttu-id="3848a-119">El valor predeterminado es 00:10:00.</span><span class="sxs-lookup"><span data-stu-id="3848a-119">The default is 00:10:00.</span></span>|  
|`maxOutboundChannelsPerEndpoint`|<span data-ttu-id="3848a-120">Entero positivo que especifica el número máximo de canales que se pueden almacenar en el grupo para cada extremo remoto.</span><span class="sxs-lookup"><span data-stu-id="3848a-120">A positive integer that specifies the maximum number of channels that can be stored in the pool for each remote endpoint.</span></span> <span data-ttu-id="3848a-121">El valor predeterminado es 10.</span><span class="sxs-lookup"><span data-stu-id="3848a-121">The default is 10.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3848a-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3848a-122">Child Elements</span></span>  
 <span data-ttu-id="3848a-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3848a-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3848a-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3848a-124">Parent Elements</span></span>  
  
|<span data-ttu-id="3848a-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="3848a-125">Element</span></span>|<span data-ttu-id="3848a-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="3848a-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3848a-127">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="3848a-127">\<oneWay></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)|<span data-ttu-id="3848a-128">Habilita el enrutamiento del paquete para un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="3848a-128">Enables packet routing for a custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3848a-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3848a-129">Remarks</span></span>  
 <span data-ttu-id="3848a-130">Las cuotas se utilizan como un mecanismo de la directiva para evitar el consumo excesivo de recursos .</span><span class="sxs-lookup"><span data-stu-id="3848a-130">Quotas are used as a policy mechanism to prevent the consumption of excessive resources.</span></span> <span data-ttu-id="3848a-131">Evitan los ataques por denegación de servicio (DoS), tanto malintencionados como involuntarios.</span><span class="sxs-lookup"><span data-stu-id="3848a-131">They prevent Denial of Service (DOS) attacks that are either malicious or unintentional.</span></span> <span data-ttu-id="3848a-132">Utilice este elemento al establecer las cuotas del canal en un canal personalizado.</span><span class="sxs-lookup"><span data-stu-id="3848a-132">Use this element when setting channel quotas on a custom channel.</span></span>  
  
 <span data-ttu-id="3848a-133">`ChannelPoolSettings` especifica tres cuotas:</span><span class="sxs-lookup"><span data-stu-id="3848a-133">`ChannelPoolSettings` specifies three quotas:</span></span>  
  
-   <span data-ttu-id="3848a-134">La cuota `idleTimeout` se utiliza para mitigar los ataques por denegación de servicio (DoS) en el servidor basados en acaparar los recursos durante un período de tiempo extendido.</span><span class="sxs-lookup"><span data-stu-id="3848a-134">The `idleTimeout` quota is used to mitigate Denial of Service (DOS) attacks on the server that rely on tying up resources for an extended period of time.</span></span> <span data-ttu-id="3848a-135">Por parte del cliente, establecer el valor correcto puede aumentar la confiabilidad de conectar con el servicio.</span><span class="sxs-lookup"><span data-stu-id="3848a-135">On the client, setting the correct value can increase the reliability of connecting with the service.</span></span> <span data-ttu-id="3848a-136">El valor predeterminado está basado en una asignación de recursos conservadoramente modesta.</span><span class="sxs-lookup"><span data-stu-id="3848a-136">The default value is based on a conservatively modest allocation of resources.</span></span> <span data-ttu-id="3848a-137">Es conveniente para un entorno de desarrollo y escenarios de instalación pequeños.</span><span class="sxs-lookup"><span data-stu-id="3848a-137">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="3848a-138">Los administradores del servicio deberían revisar el valor si una instalación se está quedando sin recursos o si las conexiones se limitan a pesar de la disponibilidad de recursos adicionales.</span><span class="sxs-lookup"><span data-stu-id="3848a-138">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
-   <span data-ttu-id="3848a-139">La cuota `leaseTimeout` se utiliza a para la integración con equilibradores de carga y para mejorar la confiabilidad.</span><span class="sxs-lookup"><span data-stu-id="3848a-139">The `leaseTimeout` quota is used to for integration with load balancers and for improving reliability.</span></span> <span data-ttu-id="3848a-140">El valor predeterminado está basado en una asignación de recursos conservadora.</span><span class="sxs-lookup"><span data-stu-id="3848a-140">The default value is based on a conservative allocation of resources.</span></span> <span data-ttu-id="3848a-141">Es conveniente para un entorno de desarrollo y escenarios de instalación pequeños.</span><span class="sxs-lookup"><span data-stu-id="3848a-141">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="3848a-142">Los administradores del servicio deberían revisar el valor si una instalación se está quedando sin recursos o si las conexiones se limitan a pesar de la disponibilidad de recursos adicionales.</span><span class="sxs-lookup"><span data-stu-id="3848a-142">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
-   <span data-ttu-id="3848a-143">La cuota `maxOutboundChannelsPerEndpoint` establece los límites de la caché en el servidor y el cliente y se utiliza para mejorar la confiabilidad.</span><span class="sxs-lookup"><span data-stu-id="3848a-143">The `maxOutboundChannelsPerEndpoint` quota sets cache limits on both the server and the client and is used to improve reliability.</span></span> <span data-ttu-id="3848a-144">El valor predeterminado está basado en una asignación de recursos conservadoramente modesta que es conveniente para un entorno de desarrollo y para escenarios de instalación pequeños.</span><span class="sxs-lookup"><span data-stu-id="3848a-144">The default value is based on a conservatively modest allocation of resources that is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="3848a-145">Los administradores del servicio deberían revisar el valor si una instalación se está quedando sin recursos o si las conexiones se limitan a pesar de la disponibilidad de recursos adicionales.</span><span class="sxs-lookup"><span data-stu-id="3848a-145">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3848a-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="3848a-146">See also</span></span>
- <xref:System.ServiceModel.Channels.OneWayBindingElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
- <xref:System.ServiceModel.Configuration.OneWayElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="3848a-147">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="3848a-147">\<oneWay></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)
- [<span data-ttu-id="3848a-148">Enlaces</span><span class="sxs-lookup"><span data-stu-id="3848a-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="3848a-149">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="3848a-149">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="3848a-150">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="3848a-150">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="3848a-151">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="3848a-151">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
