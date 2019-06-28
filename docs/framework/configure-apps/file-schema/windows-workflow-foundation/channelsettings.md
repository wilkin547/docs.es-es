---
title: <channelSettings>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 94a4457f-f43f-458d-a47e-2d11103ee75e
ms.openlocfilehash: f24efdf6e2ba99eb4fc20b81d238d33c60e6b35a
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/28/2019
ms.locfileid: "67422941"
---
# <a name="channelsettings"></a><span data-ttu-id="4a396-101">\<channelSettings></span><span class="sxs-lookup"><span data-stu-id="4a396-101">\<channelSettings></span></span>
<span data-ttu-id="4a396-102">Especifica los valores de la memoria caché del canal.</span><span class="sxs-lookup"><span data-stu-id="4a396-102">Specifies the settings of the channel cache.</span></span>  
  
<span data-ttu-id="4a396-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="4a396-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="4a396-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="4a396-104">\<behaviors></span></span>  
<span data-ttu-id="4a396-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="4a396-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="4a396-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="4a396-106">\<behavior></span></span>  
<span data-ttu-id="4a396-107">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="4a396-107">\<sendMessageChannelCache></span></span>  
<span data-ttu-id="4a396-108">\<channelSettings></span><span class="sxs-lookup"><span data-stu-id="4a396-108">\<channelSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a396-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4a396-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4a396-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4a396-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4a396-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4a396-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4a396-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="4a396-112">Attributes</span></span>  
  
|<span data-ttu-id="4a396-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="4a396-113">Attribute</span></span>|<span data-ttu-id="4a396-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="4a396-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4a396-115">idleTimeout</span><span class="sxs-lookup"><span data-stu-id="4a396-115">idleTimeout</span></span>|<span data-ttu-id="4a396-116">Un valor TimeSpan que especifica el intervalo máximo de tiempo durante el cual el objeto puede seguir inactivo en la memoria caché antes de eliminarse.</span><span class="sxs-lookup"><span data-stu-id="4a396-116">A TimeSpan value that specifies the maximum interval of time for which the object can remain idle in the cache before being disposed.</span></span>|  
|<span data-ttu-id="4a396-117">leaseTimeout</span><span class="sxs-lookup"><span data-stu-id="4a396-117">leaseTimeout</span></span>|<span data-ttu-id="4a396-118">Un valor TimeSpan que especifica el intervalo de tiempo después del cual se quita un objeto de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="4a396-118">A TimeSpan value that specifies  the interval of time after which an object is removed from the cache.</span></span>|  
|<span data-ttu-id="4a396-119">maxItemsInCache</span><span class="sxs-lookup"><span data-stu-id="4a396-119">maxItemsInCache</span></span>|<span data-ttu-id="4a396-120">Un entero que especifica el número máximo de objetos que pueden almacenarse en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="4a396-120">An integer that specifies the maximum number of objects that can be in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4a396-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4a396-121">Child Elements</span></span>  
 <span data-ttu-id="4a396-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4a396-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4a396-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4a396-123">Parent Elements</span></span>  
  
|<span data-ttu-id="4a396-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="4a396-124">Element</span></span>|<span data-ttu-id="4a396-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="4a396-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4a396-126">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="4a396-126">\<sendMessageChannelCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md)|<span data-ttu-id="4a396-127">Un comportamiento de servicio que permite la personalización de la memoria caché compartida niveles, la configuración de la memoria caché de fábrica de canales y la configuración de la memoria caché de canales para los flujos de trabajo que envían mensajes a puntos de conexión de servicio mediante actividades de mensajería de envío.</span><span class="sxs-lookup"><span data-stu-id="4a396-127">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a396-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4a396-128">Remarks</span></span>  
 <span data-ttu-id="4a396-129">Este comportamiento del servicio está orientado para los flujos de trabajo que envían mensajes a los extremos de servicio.</span><span class="sxs-lookup"><span data-stu-id="4a396-129">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="4a396-130">Estos flujos de trabajo son normalmente flujos de trabajo del cliente pero podrían ser también servicios de flujo de trabajo que se hospedan en <xref:System.ServiceModel.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="4a396-130">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="4a396-131">De manera predeterminada, en un flujo de trabajo hospedado por <xref:System.ServiceModel.WorkflowServiceHost>, la memoria caché usada por las actividades de mensajería de <xref:System.ServiceModel.Activities.Send> se comparte en todas las instancias de flujo de trabajo en <xref:System.ServiceModel.WorkflowServiceHost> (el almacenamiento en caché de nivel de host).</span><span class="sxs-lookup"><span data-stu-id="4a396-131">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="4a396-132">Para un flujo de trabajo del cliente que no esté hospedado por <xref:System.ServiceModel.WorkflowServiceHost>, la memoria caché está solo disponible para la instancia de flujo de trabajo (almacenamiento en caché en el nivel de instancia).</span><span class="sxs-lookup"><span data-stu-id="4a396-132">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="4a396-133">El almacenamiento en la memoria caché está deshabilitado de forma predeterminada para cualquier actividad de envío del flujo de trabajo que tenga definidos extremos en su configuración.</span><span class="sxs-lookup"><span data-stu-id="4a396-133">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="4a396-134">Para obtener más información sobre cómo cambiar la caché predeterminada de uso compartido de los niveles y opciones de caché para el generador de canales y la memoria caché del canal, consulte [cambiar los niveles de uso compartido de caché para actividades Send](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span><span class="sxs-lookup"><span data-stu-id="4a396-134">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a396-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4a396-135">Example</span></span>  
 <span data-ttu-id="4a396-136">En un servicio de flujo de trabajo hospedado, puede especificar la configuración de la memoria caché del generador y del canal en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4a396-136">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="4a396-137">Para ello, agregue un comportamiento de servicio que contenga los valores de memoria caché para el generador y memoria caché del canal, y agregue este comportamiento de servicio a su servicio.</span><span class="sxs-lookup"><span data-stu-id="4a396-137">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="4a396-138">El ejemplo siguiente muestra el contenido de un archivo de configuración que contiene el `MyChannelCacheBehavior` comportamiento del servicio con la configuración de caché de memoria caché y canal de generador personalizado.</span><span class="sxs-lookup"><span data-stu-id="4a396-138">The following example shows the contents of a configuration file that contains the `MyChannelCacheBehavior`  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="4a396-139">Este comportamiento del servicio se agrega al servicio mediante el `behaviorConfiguration` atributo.</span><span class="sxs-lookup"><span data-stu-id="4a396-139">This service behavior is added to the service through the `behaviorConfiguration` attribute.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4a396-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a396-140">See also</span></span>

- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- <xref:System.ServiceModel.Activities.ChannelCacheSettings>
- [<span data-ttu-id="4a396-141">Cambio de los niveles de uso compartido de caché para actividades Send</span><span class="sxs-lookup"><span data-stu-id="4a396-141">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
