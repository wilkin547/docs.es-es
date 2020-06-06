---
title: <factorySettings>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 202aad17-1b8b-4c87-ad57-4ca5de18ed35
ms.openlocfilehash: afb129407bc9dff752375f6e9fd69c728a809b37
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152189"
---
# \<factorySettings>
<span data-ttu-id="783d0-101">Especifica los valores de la memoria caché del generador de canales.</span><span class="sxs-lookup"><span data-stu-id="783d0-101">Specifies the settings of the channel factory cache.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<sendMessageChannelCache>**](sendmessagechannelcache.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<factorySettings>**  
  
## <a name="syntax"></a><span data-ttu-id="783d0-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="783d0-102">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <sendMessageChannelCache allowUnsafeCaching="Boolean" >
        <factorySettings idleTimeout="TimeSpan"
                         leaseTimeout="TimeSpan"
                         maxItemsInCache="Integer" />
      </sendMessageChannelCache>
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="783d0-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="783d0-103">Attributes and Elements</span></span>  
 <span data-ttu-id="783d0-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="783d0-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="783d0-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="783d0-105">Attributes</span></span>  
  
|<span data-ttu-id="783d0-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="783d0-106">Attribute</span></span>|<span data-ttu-id="783d0-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="783d0-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="783d0-108">idleTimeout</span><span class="sxs-lookup"><span data-stu-id="783d0-108">idleTimeout</span></span>|<span data-ttu-id="783d0-109">Un valor TimeSpan que especifica el intervalo máximo de tiempo durante el cual el objeto puede seguir inactivo en la memoria caché antes de eliminarse.</span><span class="sxs-lookup"><span data-stu-id="783d0-109">A TimeSpan value that specifies the maximum interval of time for which the object can remain idle in the cache before being disposed.</span></span>|  
|<span data-ttu-id="783d0-110">leaseTimeout</span><span class="sxs-lookup"><span data-stu-id="783d0-110">leaseTimeout</span></span>|<span data-ttu-id="783d0-111">Un valor TimeSpan que especifica el intervalo de tiempo después del cual un objeto se quita de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="783d0-111">A TimeSpan value that specifies  the interval of time after which an object is removed from the cache.</span></span>|  
|<span data-ttu-id="783d0-112">maxItemsInCache</span><span class="sxs-lookup"><span data-stu-id="783d0-112">maxItemsInCache</span></span>|<span data-ttu-id="783d0-113">Un entero que especifica el número máximo de objetos que pueden almacenarse en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="783d0-113">An integer that specifies the maximum number of objects that can be in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="783d0-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="783d0-114">Child Elements</span></span>  
 <span data-ttu-id="783d0-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="783d0-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="783d0-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="783d0-116">Parent Elements</span></span>  
  
|<span data-ttu-id="783d0-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="783d0-117">Element</span></span>|<span data-ttu-id="783d0-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="783d0-118">Description</span></span>|  
|-------------|-----------------|  
|[\<sendMessageChannelCache>](sendmessagechannelcache.md)|<span data-ttu-id="783d0-119">Un comportamiento del servicio que permite personalizar los niveles de uso compartido de la memoria caché, la configuración de la memoria caché del generador de canales y la de la memoria caché del canal para los flujos de trabajo que envían mensajes a los extremos de servicio utilizando las actividades de mensajería de Enviar.</span><span class="sxs-lookup"><span data-stu-id="783d0-119">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="783d0-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="783d0-120">Remarks</span></span>  
 <span data-ttu-id="783d0-121">Este comportamiento del servicio está orientado para los flujos de trabajo que envían mensajes a los extremos de servicio.</span><span class="sxs-lookup"><span data-stu-id="783d0-121">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="783d0-122">Estos flujos de trabajo son normalmente flujos de trabajo del cliente pero podrían ser también servicios de flujo de trabajo que se hospedan en <xref:System.ServiceModel.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="783d0-122">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="783d0-123">De manera predeterminada, en un flujo de trabajo hospedado por <xref:System.ServiceModel.WorkflowServiceHost>, la memoria caché usada por las actividades de mensajería de <xref:System.ServiceModel.Activities.Send> se comparte en todas las instancias de flujo de trabajo en <xref:System.ServiceModel.WorkflowServiceHost> (el almacenamiento en caché de nivel de host).</span><span class="sxs-lookup"><span data-stu-id="783d0-123">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="783d0-124">Para un flujo de trabajo del cliente que no esté hospedado por <xref:System.ServiceModel.WorkflowServiceHost>, la memoria caché está solo disponible para la instancia de flujo de trabajo (almacenamiento en caché en el nivel de instancia).</span><span class="sxs-lookup"><span data-stu-id="783d0-124">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="783d0-125">El almacenamiento en la memoria caché está deshabilitado de forma predeterminada para cualquier actividad de envío del flujo de trabajo que tenga definidos extremos en su configuración.</span><span class="sxs-lookup"><span data-stu-id="783d0-125">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="783d0-126">Para obtener más información sobre cómo cambiar los niveles de uso compartido de caché y la configuración de caché predeterminados para el generador de canales y la memoria caché del canal, consulte [cambiar los niveles de uso compartido de caché para las actividades de envío](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span><span class="sxs-lookup"><span data-stu-id="783d0-126">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="783d0-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="783d0-127">Example</span></span>  
 <span data-ttu-id="783d0-128">En un servicio de flujo de trabajo hospedado, puede especificar la configuración de la memoria caché del generador y del canal en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="783d0-128">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="783d0-129">Para ello, agregue un comportamiento de servicio que contenga los valores de memoria caché para el generador y memoria caché del canal, y agregue este comportamiento de servicio a su servicio.</span><span class="sxs-lookup"><span data-stu-id="783d0-129">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="783d0-130">En el ejemplo siguiente se muestra el contenido de un archivo de configuración que contiene el `MyChannelCacheBehavior` comportamiento del servicio con la configuración personalizada de la memoria caché del generador y del canal.</span><span class="sxs-lookup"><span data-stu-id="783d0-130">The following example shows the contents of a configuration file that contains the `MyChannelCacheBehavior` service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="783d0-131">Este comportamiento del servicio se agrega al servicio a través del `behaviorConfiguration` atributo.</span><span class="sxs-lookup"><span data-stu-id="783d0-131">This service behavior is added to the service through the `behaviorConfiguration` attribute.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="783d0-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="783d0-132">See also</span></span>

- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- <xref:System.ServiceModel.Activities.ChannelCacheSettings>
- [<span data-ttu-id="783d0-133">Cambiar los niveles de uso compartido de caché para actividades Send</span><span class="sxs-lookup"><span data-stu-id="783d0-133">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
