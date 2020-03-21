---
title: <sendMessageChannelCache>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 241e428e-5030-4b13-8a0a-69f05288d3d9
ms.openlocfilehash: b68c6d2e526eb22328806558d7c167b7f2ed0820
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152006"
---
# <a name="sendmessagechannelcache"></a><span data-ttu-id="1d8c2-101">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="1d8c2-101">\<sendMessageChannelCache></span></span>
<span data-ttu-id="1d8c2-102">Un comportamiento del servicio que permite personalizar los niveles de uso compartido de la memoria caché, la configuración de la memoria caché del generador de canales y la de la memoria caché del canal para los flujos de trabajo que envían mensajes a los extremos de servicio utilizando las actividades de mensajería de Enviar.</span><span class="sxs-lookup"><span data-stu-id="1d8c2-102">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>  
  
<span data-ttu-id="1d8c2-103">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1d8c2-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1d8c2-104">&nbsp;&nbsp;[**\<Sistema.>De ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="1d8c2-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="1d8c2-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<comportamientos>**](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="1d8c2-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="1d8c2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="1d8c2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="1d8c2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comportamiento>**](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="1d8c2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="1d8c2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>sendMessageChannelCache**</span><span class="sxs-lookup"><span data-stu-id="1d8c2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sendMessageChannelCache>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d8c2-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1d8c2-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1d8c2-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1d8c2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1d8c2-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1d8c2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1d8c2-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="1d8c2-112">Attributes</span></span>  
  
|<span data-ttu-id="1d8c2-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="1d8c2-113">Attribute</span></span>|<span data-ttu-id="1d8c2-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="1d8c2-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1d8c2-115">allowUnsafeCaching</span><span class="sxs-lookup"><span data-stu-id="1d8c2-115">allowUnsafeCaching</span></span>|<span data-ttu-id="1d8c2-116">Un valor booleano que indica si debe activarse el almacenamiento en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="1d8c2-116">A Boolean value that indicates whether to turn caching on.</span></span> <span data-ttu-id="1d8c2-117">Si su servicio de flujo de trabajo tiene enlaces personalizados o los comportamientos personalizados, el almacenamiento en la memoria caché podría no ser seguro y, por consiguiente, está deshabilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1d8c2-117">If your workflow service has custom bindings or custom behaviors, caching could be unsecure and therefore is disabled by default.</span></span> <span data-ttu-id="1d8c2-118">Sin embargo, si desea activar el almacenamiento en caché, establezca esta propiedad en **true**.</span><span class="sxs-lookup"><span data-stu-id="1d8c2-118">However, if you want to turn caching on set this property to **true**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1d8c2-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1d8c2-119">Child Elements</span></span>  
  
|<span data-ttu-id="1d8c2-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="1d8c2-120">Element</span></span>|<span data-ttu-id="1d8c2-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="1d8c2-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1d8c2-122">\<channelSettings></span><span class="sxs-lookup"><span data-stu-id="1d8c2-122">\<channelSettings></span></span>](channelsettings.md)|<span data-ttu-id="1d8c2-123">Especifica los valores de la memoria caché del canal.</span><span class="sxs-lookup"><span data-stu-id="1d8c2-123">Specifies the settings of the channel cache.</span></span>|  
|[<span data-ttu-id="1d8c2-124">\<factorySettings></span><span class="sxs-lookup"><span data-stu-id="1d8c2-124">\<factorySettings></span></span>](factorysettings.md)|<span data-ttu-id="1d8c2-125">Especifica los valores de la memoria caché del generador de canales.</span><span class="sxs-lookup"><span data-stu-id="1d8c2-125">Specifies the settings of the channel factory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1d8c2-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1d8c2-126">Parent Elements</span></span>  
  
|<span data-ttu-id="1d8c2-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="1d8c2-127">Element</span></span>|<span data-ttu-id="1d8c2-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="1d8c2-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1d8c2-129">\<comportamiento> \<de serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="1d8c2-129">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="1d8c2-130">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="1d8c2-130">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d8c2-131">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1d8c2-131">Remarks</span></span>  
 <span data-ttu-id="1d8c2-132">Este comportamiento del servicio está orientado para los flujos de trabajo que envían mensajes a los extremos de servicio.</span><span class="sxs-lookup"><span data-stu-id="1d8c2-132">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="1d8c2-133">Estos flujos de trabajo son normalmente flujos de trabajo del cliente pero podrían ser también servicios de flujo de trabajo que se hospedan en <xref:System.ServiceModel.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="1d8c2-133">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="1d8c2-134">De manera predeterminada, en un flujo de trabajo hospedado por <xref:System.ServiceModel.WorkflowServiceHost>, la memoria caché usada por las actividades de mensajería de <xref:System.ServiceModel.Activities.Send> se comparte en todas las instancias de flujo de trabajo en <xref:System.ServiceModel.WorkflowServiceHost> (el almacenamiento en caché de nivel de host).</span><span class="sxs-lookup"><span data-stu-id="1d8c2-134">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="1d8c2-135">Para un flujo de trabajo del cliente que no esté hospedado por <xref:System.ServiceModel.WorkflowServiceHost>, la memoria caché está solo disponible para la instancia de flujo de trabajo (almacenamiento en caché en el nivel de instancia).</span><span class="sxs-lookup"><span data-stu-id="1d8c2-135">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="1d8c2-136">El almacenamiento en la memoria caché está deshabilitado de forma predeterminada para cualquier actividad de envío del flujo de trabajo que tenga definidos extremos en su configuración.</span><span class="sxs-lookup"><span data-stu-id="1d8c2-136">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="1d8c2-137">Para obtener más información sobre cómo cambiar los niveles de uso compartido de caché predeterminados y la configuración de caché para la fábrica de canales y la caché de canales, consulte Cambio de los niveles de uso compartido de [caché para las actividades](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)de envío .</span><span class="sxs-lookup"><span data-stu-id="1d8c2-137">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d8c2-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1d8c2-138">Example</span></span>  
 <span data-ttu-id="1d8c2-139">En un servicio de flujo de trabajo hospedado, puede especificar la configuración de la memoria caché del generador y del canal en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1d8c2-139">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="1d8c2-140">Para ello, agregue un comportamiento de servicio que contenga los valores de memoria caché para el generador y memoria caché del canal, y agregue este comportamiento de servicio a su servicio.</span><span class="sxs-lookup"><span data-stu-id="1d8c2-140">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="1d8c2-141">En el ejemplo siguiente se muestra el `MyChannelCacheBehavior` contenido de un archivo de configuración que contiene el comportamiento del servicio con la caché de fábrica personalizada y la configuración de caché de canal.</span><span class="sxs-lookup"><span data-stu-id="1d8c2-141">The following example shows the contents of a configuration file that contains the `MyChannelCacheBehavior`  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="1d8c2-142">Este comportamiento de servicio se `behaviorConfiguration` agrega al servicio a través del atributo.</span><span class="sxs-lookup"><span data-stu-id="1d8c2-142">This service behavior is added to the service through the `behaviorConfiguration` attribute.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1d8c2-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1d8c2-143">See also</span></span>

- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- [<span data-ttu-id="1d8c2-144">Cambiar los niveles de uso compartido de caché para actividades Send</span><span class="sxs-lookup"><span data-stu-id="1d8c2-144">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
