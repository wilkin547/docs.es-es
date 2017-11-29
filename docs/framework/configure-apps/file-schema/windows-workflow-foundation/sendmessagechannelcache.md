---
title: '&lt;sendMessageChannelCache&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 241e428e-5030-4b13-8a0a-69f05288d3d9
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1543142a8ff5fb77db48d0e479433c533e7eff83
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltsendmessagechannelcachegt"></a><span data-ttu-id="58786-102">&lt;sendMessageChannelCache&gt;</span><span class="sxs-lookup"><span data-stu-id="58786-102">&lt;sendMessageChannelCache&gt;</span></span>
<span data-ttu-id="58786-103">Un comportamiento de servicio que permite la personalización de la memoria caché de uso compartido de niveles, la configuración de la memoria de caché del generador de canales y la configuración de la memoria caché de canales para los flujos de trabajo que envían mensajes a extremos de servicio mediante actividades de mensajería de envío.</span><span class="sxs-lookup"><span data-stu-id="58786-103">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>  
  
<span data-ttu-id="58786-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="58786-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="58786-105">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="58786-105">\<behaviors></span></span>  
<span data-ttu-id="58786-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="58786-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="58786-107">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="58786-107">\<behavior></span></span>  
<span data-ttu-id="58786-108">\<sendMessageChannelCache ></span><span class="sxs-lookup"><span data-stu-id="58786-108">\<sendMessageChannelCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58786-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="58786-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <sendMessageChannelCache allowUnsafeCaching="Boolean">
        <channelSettings idleTimeout="TimeSpan"
                         leaseTimeout="TimeSpan" 
                         maxItemsInCache="Integer" />
        <factorySettings idleTimeout="TimeSpan" 
                         leaseTimeout="TimeSpan" 
                         maxItemsInCache="Integer" />
      </sendMessageChannelCache>
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="58786-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="58786-110">Attributes and Elements</span></span>  
 <span data-ttu-id="58786-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="58786-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="58786-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="58786-112">Attributes</span></span>  
  
|<span data-ttu-id="58786-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="58786-113">Attribute</span></span>|<span data-ttu-id="58786-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="58786-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="58786-115">allowUnsafeCaching</span><span class="sxs-lookup"><span data-stu-id="58786-115">allowUnsafeCaching</span></span>|<span data-ttu-id="58786-116">Un valor booleano que indica si debe activarse el almacenamiento en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="58786-116">A Boolean value that indicates whether to turn caching on.</span></span> <span data-ttu-id="58786-117">Si su servicio de flujo de trabajo tiene enlaces personalizados o los comportamientos personalizados, el almacenamiento en la memoria caché podría no ser seguro y, por consiguiente, está deshabilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="58786-117">If your workflow service has custom bindings or custom behaviors, caching could be unsecure and therefore is disabled by default.</span></span> <span data-ttu-id="58786-118">Sin embargo, si desea activar el almacenamiento en caché en establezca esta propiedad en **true**.</span><span class="sxs-lookup"><span data-stu-id="58786-118">However, if you want to turn caching on set this property to **true**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="58786-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="58786-119">Child Elements</span></span>  
  
|<span data-ttu-id="58786-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="58786-120">Element</span></span>|<span data-ttu-id="58786-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="58786-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="58786-122">\<channelSettings ></span><span class="sxs-lookup"><span data-stu-id="58786-122">\<channelSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/channelsettings.md)|<span data-ttu-id="58786-123">Especifica los valores de la memoria caché del canal.</span><span class="sxs-lookup"><span data-stu-id="58786-123">Specifies the settings of the channel cache.</span></span>|  
|[<span data-ttu-id="58786-124">\<factorySettings ></span><span class="sxs-lookup"><span data-stu-id="58786-124">\<factorySettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/factorysettings.md)|<span data-ttu-id="58786-125">Especifica los valores de la memoria caché del generador de canales.</span><span class="sxs-lookup"><span data-stu-id="58786-125">Specifies the settings of the channel factory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="58786-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="58786-126">Parent Elements</span></span>  
  
|<span data-ttu-id="58786-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="58786-127">Element</span></span>|<span data-ttu-id="58786-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="58786-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="58786-129">\<comportamiento > de \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="58786-129">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="58786-130">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="58786-130">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58786-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="58786-131">Remarks</span></span>  
 <span data-ttu-id="58786-132">Este comportamiento del servicio está orientado para los flujos de trabajo que envían mensajes a los extremos de servicio.</span><span class="sxs-lookup"><span data-stu-id="58786-132">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="58786-133">Estos flujos de trabajo son normalmente flujos de trabajo del cliente pero podrían ser también servicios de flujo de trabajo que se hospedan en <xref:System.ServiceModel.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="58786-133">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="58786-134">De manera predeterminada, en un flujo de trabajo hospedado por <xref:System.ServiceModel.WorkflowServiceHost>, la memoria caché usada por las actividades de mensajería de <xref:System.ServiceModel.Activities.Send> se comparte en todas las instancias de flujo de trabajo en <xref:System.ServiceModel.WorkflowServiceHost> (el almacenamiento en caché de nivel de host).</span><span class="sxs-lookup"><span data-stu-id="58786-134">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="58786-135">Para un flujo de trabajo del cliente que no esté hospedado por <xref:System.ServiceModel.WorkflowServiceHost>, la memoria caché está solo disponible para la instancia de flujo de trabajo (almacenamiento en caché en el nivel de instancia).</span><span class="sxs-lookup"><span data-stu-id="58786-135">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="58786-136">El almacenamiento en la memoria caché está deshabilitado de forma predeterminada para cualquier actividad de envío del flujo de trabajo que tenga definidos puntos de conexión en su configuración.</span><span class="sxs-lookup"><span data-stu-id="58786-136">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)]<span data-ttu-id="58786-137">Cómo cambiar la niveles de uso compartido de caché predeterminada y configuración para el generador de canales y la memoria caché del canal de caché, consulte [cambiar los niveles de uso compartido de caché para las actividades de envío](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span><span class="sxs-lookup"><span data-stu-id="58786-137"> how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="58786-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="58786-138">Example</span></span>  
 <span data-ttu-id="58786-139">En un servicio de flujo de trabajo hospedado, puede especificar la configuración de la memoria caché del generador y del canal en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="58786-139">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="58786-140">Para ello, agregue un comportamiento de servicio que contenga los valores de memoria caché para el generador y memoria caché del canal, y agregue este comportamiento de servicio a su servicio.</span><span class="sxs-lookup"><span data-stu-id="58786-140">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="58786-141">En el ejemplo siguiente se muestra el contenido de un archivo de configuración que contiene el **MyChannelCacheBehavior** comportamiento de servicio con la configuración de caché de memoria caché y canal de generador personalizado.</span><span class="sxs-lookup"><span data-stu-id="58786-141">The following example shows the contents of a configuration file that contains the **MyChannelCacheBehavior**  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="58786-142">Este comportamiento de servicio se agrega al servicio a través de la **behaviorConfiguarion** atributo.</span><span class="sxs-lookup"><span data-stu-id="58786-142">This service behavior is added to the service through the **behaviorConfiguarion** attribute.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="58786-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="58786-143">See Also</span></span>  
 <xref:System.ServiceModel.Activities.SendMessageChannelCache>  
 <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>  
 <xref:System.ServiceModel.Activities.Send>  
 [<span data-ttu-id="58786-144">Cambiar el uso compartido de caché niveles para las actividades de envío</span><span class="sxs-lookup"><span data-stu-id="58786-144">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
