---
title: '&lt;channelSettings&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 94a4457f-f43f-458d-a47e-2d11103ee75e
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f045665565a29f0248bf2e05bd1b285d59d6c375
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltchannelsettingsgt"></a><span data-ttu-id="60fe5-102">&lt;channelSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="60fe5-102">&lt;channelSettings&gt;</span></span>
<span data-ttu-id="60fe5-103">Especifica los valores de la memoria caché del canal.</span><span class="sxs-lookup"><span data-stu-id="60fe5-103">Specifies the settings of the channel cache.</span></span>  
  
<span data-ttu-id="60fe5-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="60fe5-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="60fe5-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="60fe5-105">\<behaviors></span></span>  
<span data-ttu-id="60fe5-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="60fe5-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="60fe5-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="60fe5-107">\<behavior></span></span>  
<span data-ttu-id="60fe5-108">\<sendMessageChannelCache ></span><span class="sxs-lookup"><span data-stu-id="60fe5-108">\<sendMessageChannelCache></span></span>  
<span data-ttu-id="60fe5-109">\<channelSettings ></span><span class="sxs-lookup"><span data-stu-id="60fe5-109">\<channelSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60fe5-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="60fe5-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="60fe5-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="60fe5-111">Attributes and Elements</span></span>  
 <span data-ttu-id="60fe5-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="60fe5-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="60fe5-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="60fe5-113">Attributes</span></span>  
  
|<span data-ttu-id="60fe5-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="60fe5-114">Attribute</span></span>|<span data-ttu-id="60fe5-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="60fe5-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="60fe5-116">idleTimeout</span><span class="sxs-lookup"><span data-stu-id="60fe5-116">idleTimeout</span></span>|<span data-ttu-id="60fe5-117">Un valor TimeSpan que especifica el intervalo máximo de tiempo durante el cual el objeto puede seguir inactivo en la memoria caché antes de eliminarse.</span><span class="sxs-lookup"><span data-stu-id="60fe5-117">A TimeSpan value that specifies the maximum interval of time for which the object can remain idle in the cache before being disposed.</span></span>|  
|<span data-ttu-id="60fe5-118">leaseTimeout</span><span class="sxs-lookup"><span data-stu-id="60fe5-118">leaseTimeout</span></span>|<span data-ttu-id="60fe5-119">Valor TimeSpan que especifica el intervalo de tiempo tras el cual un objeto se quita de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="60fe5-119">A TimeSpan value that specifies  the interval of time after which an object is removed from the cache.</span></span>|  
|<span data-ttu-id="60fe5-120">maxItemsInCache</span><span class="sxs-lookup"><span data-stu-id="60fe5-120">maxItemsInCache</span></span>|<span data-ttu-id="60fe5-121">Un entero que especifica el número máximo de objetos que pueden almacenarse en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="60fe5-121">An integer that specifies the maximum number of objects that can be in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="60fe5-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="60fe5-122">Child Elements</span></span>  
 <span data-ttu-id="60fe5-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="60fe5-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="60fe5-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="60fe5-124">Parent Elements</span></span>  
  
|<span data-ttu-id="60fe5-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="60fe5-125">Element</span></span>|<span data-ttu-id="60fe5-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="60fe5-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="60fe5-127">\<sendMessageChannelCache ></span><span class="sxs-lookup"><span data-stu-id="60fe5-127">\<sendMessageChannelCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md)|<span data-ttu-id="60fe5-128">Un comportamiento de servicio que permite la personalización de la memoria caché de uso compartido de niveles, la configuración de la memoria de caché del generador de canales y la configuración de la memoria caché de canales para los flujos de trabajo que envían mensajes a extremos de servicio mediante actividades de mensajería de envío.</span><span class="sxs-lookup"><span data-stu-id="60fe5-128">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60fe5-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="60fe5-129">Remarks</span></span>  
 <span data-ttu-id="60fe5-130">Este comportamiento del servicio está orientado para los flujos de trabajo que envían mensajes a los extremos de servicio.</span><span class="sxs-lookup"><span data-stu-id="60fe5-130">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="60fe5-131">Estos flujos de trabajo son normalmente flujos de trabajo del cliente pero podrían ser también servicios de flujo de trabajo que se hospedan en <xref:System.ServiceModel.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="60fe5-131">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="60fe5-132">De manera predeterminada, en un flujo de trabajo hospedado por <xref:System.ServiceModel.WorkflowServiceHost>, la memoria caché usada por las actividades de mensajería de <xref:System.ServiceModel.Activities.Send> se comparte en todas las instancias de flujo de trabajo en <xref:System.ServiceModel.WorkflowServiceHost> (el almacenamiento en caché de nivel de host).</span><span class="sxs-lookup"><span data-stu-id="60fe5-132">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="60fe5-133">Para un flujo de trabajo del cliente que no esté hospedado por <xref:System.ServiceModel.WorkflowServiceHost>, la memoria caché está solo disponible para la instancia de flujo de trabajo (almacenamiento en caché en el nivel de instancia).</span><span class="sxs-lookup"><span data-stu-id="60fe5-133">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="60fe5-134">El almacenamiento en la memoria caché está deshabilitado de forma predeterminada para cualquier actividad de envío del flujo de trabajo que tenga definidos puntos de conexión en su configuración.</span><span class="sxs-lookup"><span data-stu-id="60fe5-134">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)]<span data-ttu-id="60fe5-135">Cómo cambiar la niveles de uso compartido de caché predeterminada y configuración para el generador de canales y la memoria caché del canal de caché, consulte [cambiar los niveles de uso compartido de caché para las actividades de envío](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span><span class="sxs-lookup"><span data-stu-id="60fe5-135"> how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="60fe5-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="60fe5-136">Example</span></span>  
 <span data-ttu-id="60fe5-137">En un servicio de flujo de trabajo hospedado, puede especificar la configuración de la memoria caché del generador y del canal en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="60fe5-137">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="60fe5-138">Para ello, agregue un comportamiento de servicio que contenga los valores de memoria caché para el generador y memoria caché del canal, y agregue este comportamiento de servicio a su servicio.</span><span class="sxs-lookup"><span data-stu-id="60fe5-138">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="60fe5-139">En el ejemplo siguiente se muestra el contenido de un archivo de configuración que contiene el **MyChannelCacheBehavior** comportamiento de servicio con la configuración de caché de memoria caché y canal de generador personalizado.</span><span class="sxs-lookup"><span data-stu-id="60fe5-139">The following example shows the contents of a configuration file that contains the **MyChannelCacheBehavior**  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="60fe5-140">Este comportamiento de servicio se agrega al servicio a través de la **behaviorConfiguarion** atributo.</span><span class="sxs-lookup"><span data-stu-id="60fe5-140">This service behavior is added to the service through the **behaviorConfiguarion** attribute.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="60fe5-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="60fe5-141">See Also</span></span>  
 <xref:System.ServiceModel.Activities.SendMessageChannelCache>  
 <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>  
 <xref:System.ServiceModel.Activities.Send>  
 <xref:System.ServiceModel.Activities.ChannelCacheSettings>  
 [<span data-ttu-id="60fe5-142">Cambio de los niveles de uso compartido de caché para actividades Send</span><span class="sxs-lookup"><span data-stu-id="60fe5-142">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
