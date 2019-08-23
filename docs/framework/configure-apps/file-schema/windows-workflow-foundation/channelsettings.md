---
title: <channelSettings>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 94a4457f-f43f-458d-a47e-2d11103ee75e
ms.openlocfilehash: 9caf87bdf2029d273a9d6d7ac90b83ba72bafc7a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945830"
---
# <a name="channelsettings"></a><span data-ttu-id="33dc6-101">\<channelSettings></span><span class="sxs-lookup"><span data-stu-id="33dc6-101">\<channelSettings></span></span>
<span data-ttu-id="33dc6-102">Especifica los valores de la memoria caché del canal.</span><span class="sxs-lookup"><span data-stu-id="33dc6-102">Specifies the settings of the channel cache.</span></span>  
  
<span data-ttu-id="33dc6-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="33dc6-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="33dc6-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="33dc6-104">\<behaviors></span></span>  
<span data-ttu-id="33dc6-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="33dc6-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="33dc6-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="33dc6-106">\<behavior></span></span>  
<span data-ttu-id="33dc6-107">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="33dc6-107">\<sendMessageChannelCache></span></span>  
<span data-ttu-id="33dc6-108">\<channelSettings></span><span class="sxs-lookup"><span data-stu-id="33dc6-108">\<channelSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33dc6-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33dc6-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <sendMessageChannelCache allowUnsafeCaching="Boolean">
        <channelSettings idleTimeout="TimeSpan" 
                         leaseTimeout="TimeSpan" 
                         maxItemsInCache="Integer" />
      </sendMessageChannelCache>
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33dc6-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="33dc6-110">Attributes and Elements</span></span>  
 <span data-ttu-id="33dc6-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="33dc6-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33dc6-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="33dc6-112">Attributes</span></span>  
  
|<span data-ttu-id="33dc6-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="33dc6-113">Attribute</span></span>|<span data-ttu-id="33dc6-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="33dc6-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="33dc6-115">idleTimeout</span><span class="sxs-lookup"><span data-stu-id="33dc6-115">idleTimeout</span></span>|<span data-ttu-id="33dc6-116">Un valor TimeSpan que especifica el intervalo máximo de tiempo durante el cual el objeto puede seguir inactivo en la memoria caché antes de eliminarse.</span><span class="sxs-lookup"><span data-stu-id="33dc6-116">A TimeSpan value that specifies the maximum interval of time for which the object can remain idle in the cache before being disposed.</span></span>|  
|<span data-ttu-id="33dc6-117">leaseTimeout</span><span class="sxs-lookup"><span data-stu-id="33dc6-117">leaseTimeout</span></span>|<span data-ttu-id="33dc6-118">Valor TimeSpan que especifica el intervalo de tiempo después del cual un objeto se quita de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="33dc6-118">A TimeSpan value that specifies  the interval of time after which an object is removed from the cache.</span></span>|  
|<span data-ttu-id="33dc6-119">maxItemsInCache</span><span class="sxs-lookup"><span data-stu-id="33dc6-119">maxItemsInCache</span></span>|<span data-ttu-id="33dc6-120">Un entero que especifica el número máximo de objetos que pueden almacenarse en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="33dc6-120">An integer that specifies the maximum number of objects that can be in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="33dc6-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="33dc6-121">Child Elements</span></span>  
 <span data-ttu-id="33dc6-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="33dc6-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="33dc6-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="33dc6-123">Parent Elements</span></span>  
  
|<span data-ttu-id="33dc6-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="33dc6-124">Element</span></span>|<span data-ttu-id="33dc6-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="33dc6-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33dc6-126">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="33dc6-126">\<sendMessageChannelCache></span></span>](sendmessagechannelcache.md)|<span data-ttu-id="33dc6-127">Un comportamiento del servicio que permite la personalización de los niveles de uso compartido de la memoria caché, la configuración de la memoria caché del generador de canales y la configuración de la memoria caché del canal para los flujos de trabajo que envían mensajes a los puntos de conexión de servicio mediante el envío de actividades de mensajería.</span><span class="sxs-lookup"><span data-stu-id="33dc6-127">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33dc6-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="33dc6-128">Remarks</span></span>  
 <span data-ttu-id="33dc6-129">Este comportamiento del servicio está orientado para los flujos de trabajo que envían mensajes a los extremos de servicio.</span><span class="sxs-lookup"><span data-stu-id="33dc6-129">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="33dc6-130">Estos flujos de trabajo son normalmente flujos de trabajo del cliente pero podrían ser también servicios de flujo de trabajo que se hospedan en <xref:System.ServiceModel.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="33dc6-130">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="33dc6-131">De manera predeterminada, en un flujo de trabajo hospedado por <xref:System.ServiceModel.WorkflowServiceHost>, la memoria caché usada por las actividades de mensajería de <xref:System.ServiceModel.Activities.Send> se comparte en todas las instancias de flujo de trabajo en <xref:System.ServiceModel.WorkflowServiceHost> (el almacenamiento en caché de nivel de host).</span><span class="sxs-lookup"><span data-stu-id="33dc6-131">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="33dc6-132">Para un flujo de trabajo del cliente que no esté hospedado por <xref:System.ServiceModel.WorkflowServiceHost>, la memoria caché está solo disponible para la instancia de flujo de trabajo (almacenamiento en caché en el nivel de instancia).</span><span class="sxs-lookup"><span data-stu-id="33dc6-132">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="33dc6-133">El almacenamiento en la memoria caché está deshabilitado de forma predeterminada para cualquier actividad de envío del flujo de trabajo que tenga definidos extremos en su configuración.</span><span class="sxs-lookup"><span data-stu-id="33dc6-133">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="33dc6-134">Para obtener más información sobre cómo cambiar los niveles de uso compartido de caché y la configuración de caché predeterminados para el generador de canales y la memoria caché del canal, consulte [cambiar los niveles de uso compartido de caché para las actividades de envío](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span><span class="sxs-lookup"><span data-stu-id="33dc6-134">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="33dc6-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="33dc6-135">Example</span></span>  
 <span data-ttu-id="33dc6-136">En un servicio de flujo de trabajo hospedado, puede especificar la configuración de la memoria caché del generador y del canal en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="33dc6-136">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="33dc6-137">Para ello, agregue un comportamiento de servicio que contenga los valores de memoria caché para el generador y memoria caché del canal, y agregue este comportamiento de servicio a su servicio.</span><span class="sxs-lookup"><span data-stu-id="33dc6-137">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="33dc6-138">En el ejemplo siguiente se muestra el contenido de un archivo de configuración `MyChannelCacheBehavior` que contiene el comportamiento del servicio con la configuración personalizada de la memoria caché del generador y del canal.</span><span class="sxs-lookup"><span data-stu-id="33dc6-138">The following example shows the contents of a configuration file that contains the `MyChannelCacheBehavior`  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="33dc6-139">Este comportamiento del servicio se agrega al servicio a través `behaviorConfiguration` del atributo.</span><span class="sxs-lookup"><span data-stu-id="33dc6-139">This service behavior is added to the service through the `behaviorConfiguration` attribute.</span></span>  
  
```xml  
<configuration>    
  <system.serviceModel>  
    <!-- List of other config sections here -->   
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="MyChannelCacheBehavior">  
          <sendMessageChannelCache allowUnsafeCaching ="false" >  
            <!-- Control only the host level settings -->   
            <factorySettings maxItemsInCache = "8" idleTimeout = "00:05:00" leaseTimeout="10:00:00" />  
            <channelSettings maxItemsInCache = "32" idleTimeout = "00:05:00" leaseTimeout="00:06:00" />  
          </sendMessageChannelCache>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service name="MyService" behaviorConfiguration="MyChannelCacheBehavior" />  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="33dc6-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="33dc6-140">See also</span></span>

- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- <xref:System.ServiceModel.Activities.ChannelCacheSettings>
- [<span data-ttu-id="33dc6-141">Cambio de los niveles de uso compartido de caché para actividades Send</span><span class="sxs-lookup"><span data-stu-id="33dc6-141">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
