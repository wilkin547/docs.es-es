---
description: 'Más información acerca de: <sendMessageChannelCache>'
title: <sendMessageChannelCache>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 241e428e-5030-4b13-8a0a-69f05288d3d9
ms.openlocfilehash: 2c77372bb44df74a1d2186500367c5164e1e5042
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739786"
---
# \<sendMessageChannelCache>

<span data-ttu-id="166d5-102">Un comportamiento del servicio que permite personalizar los niveles de uso compartido de la memoria caché, la configuración de la memoria caché del generador de canales y la de la memoria caché del canal para los flujos de trabajo que envían mensajes a los extremos de servicio utilizando las actividades de mensajería de Enviar.</span><span class="sxs-lookup"><span data-stu-id="166d5-102">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sendMessageChannelCache>**  
  
## <a name="syntax"></a><span data-ttu-id="166d5-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="166d5-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="166d5-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="166d5-104">Attributes and Elements</span></span>  

 <span data-ttu-id="166d5-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="166d5-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="166d5-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="166d5-106">Attributes</span></span>  
  
|<span data-ttu-id="166d5-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="166d5-107">Attribute</span></span>|<span data-ttu-id="166d5-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="166d5-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="166d5-109">allowUnsafeCaching</span><span class="sxs-lookup"><span data-stu-id="166d5-109">allowUnsafeCaching</span></span>|<span data-ttu-id="166d5-110">Un valor booleano que indica si debe activarse el almacenamiento en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="166d5-110">A Boolean value that indicates whether to turn caching on.</span></span> <span data-ttu-id="166d5-111">Si su servicio de flujo de trabajo tiene enlaces personalizados o los comportamientos personalizados, el almacenamiento en la memoria caché podría no ser seguro y, por consiguiente, está deshabilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="166d5-111">If your workflow service has custom bindings or custom behaviors, caching could be unsecure and therefore is disabled by default.</span></span> <span data-ttu-id="166d5-112">Sin embargo, si desea activar el almacenamiento en caché, establezca esta propiedad en **true**.</span><span class="sxs-lookup"><span data-stu-id="166d5-112">However, if you want to turn caching on set this property to **true**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="166d5-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="166d5-113">Child Elements</span></span>  
  
|<span data-ttu-id="166d5-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="166d5-114">Element</span></span>|<span data-ttu-id="166d5-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="166d5-115">Description</span></span>|  
|-------------|-----------------|  
|[\<channelSettings>](channelsettings.md)|<span data-ttu-id="166d5-116">Especifica los valores de la memoria caché del canal.</span><span class="sxs-lookup"><span data-stu-id="166d5-116">Specifies the settings of the channel cache.</span></span>|  
|[\<factorySettings>](factorysettings.md)|<span data-ttu-id="166d5-117">Especifica los valores de la memoria caché del generador de canales.</span><span class="sxs-lookup"><span data-stu-id="166d5-117">Specifies the settings of the channel factory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="166d5-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="166d5-118">Parent Elements</span></span>  
  
|<span data-ttu-id="166d5-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="166d5-119">Element</span></span>|<span data-ttu-id="166d5-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="166d5-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="166d5-121">\<behavior> de \<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="166d5-121">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="166d5-122">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="166d5-122">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="166d5-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="166d5-123">Remarks</span></span>  

 <span data-ttu-id="166d5-124">Este comportamiento del servicio está orientado para los flujos de trabajo que envían mensajes a los extremos de servicio.</span><span class="sxs-lookup"><span data-stu-id="166d5-124">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="166d5-125">Estos flujos de trabajo son normalmente flujos de trabajo del cliente pero podrían ser también servicios de flujo de trabajo que se hospedan en <xref:System.ServiceModel.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="166d5-125">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="166d5-126">De manera predeterminada, en un flujo de trabajo hospedado por <xref:System.ServiceModel.WorkflowServiceHost>, la memoria caché usada por las actividades de mensajería de <xref:System.ServiceModel.Activities.Send> se comparte en todas las instancias de flujo de trabajo en <xref:System.ServiceModel.WorkflowServiceHost> (el almacenamiento en caché de nivel de host).</span><span class="sxs-lookup"><span data-stu-id="166d5-126">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="166d5-127">Para un flujo de trabajo del cliente que no esté hospedado por <xref:System.ServiceModel.WorkflowServiceHost>, la memoria caché está solo disponible para la instancia de flujo de trabajo (almacenamiento en caché en el nivel de instancia).</span><span class="sxs-lookup"><span data-stu-id="166d5-127">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="166d5-128">El almacenamiento en la memoria caché está deshabilitado de forma predeterminada para cualquier actividad de envío del flujo de trabajo que tenga definidos extremos en su configuración.</span><span class="sxs-lookup"><span data-stu-id="166d5-128">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="166d5-129">Para obtener más información sobre cómo cambiar los niveles de uso compartido de caché y la configuración de caché predeterminados para el generador de canales y la memoria caché del canal, consulte [cambiar los niveles de uso compartido de caché para las actividades de envío](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span><span class="sxs-lookup"><span data-stu-id="166d5-129">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="166d5-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="166d5-130">Example</span></span>  

 <span data-ttu-id="166d5-131">En un servicio de flujo de trabajo hospedado, puede especificar la configuración de la memoria caché del generador y del canal en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="166d5-131">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="166d5-132">Para ello, agregue un comportamiento de servicio que contenga los valores de memoria caché para el generador y memoria caché del canal, y agregue este comportamiento de servicio a su servicio.</span><span class="sxs-lookup"><span data-stu-id="166d5-132">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="166d5-133">En el ejemplo siguiente se muestra el contenido de un archivo de configuración que contiene el `MyChannelCacheBehavior`  comportamiento del servicio con la configuración personalizada de la memoria caché del generador y del canal.</span><span class="sxs-lookup"><span data-stu-id="166d5-133">The following example shows the contents of a configuration file that contains the `MyChannelCacheBehavior`  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="166d5-134">Este comportamiento del servicio se agrega al servicio a través del `behaviorConfiguration` atributo.</span><span class="sxs-lookup"><span data-stu-id="166d5-134">This service behavior is added to the service through the `behaviorConfiguration` attribute.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="166d5-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="166d5-135">See also</span></span>

- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- [<span data-ttu-id="166d5-136">Cambiar los niveles de uso compartido de caché para actividades Send</span><span class="sxs-lookup"><span data-stu-id="166d5-136">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
