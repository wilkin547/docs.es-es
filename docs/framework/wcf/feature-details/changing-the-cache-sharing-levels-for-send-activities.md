---
title: Cambiar los niveles de uso compartido de caché para actividades Send
ms.date: 03/30/2017
ms.assetid: 03926a64-753d-460e-ac06-2a4ff8e1bbf5
ms.openlocfilehash: 101aab98a7d34ad45ad29efbe252cff0814ca290
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185392"
---
# <a name="changing-the-cache-sharing-levels-for-send-activities"></a><span data-ttu-id="68954-102">Cambiar los niveles de uso compartido de caché para actividades Send</span><span class="sxs-lookup"><span data-stu-id="68954-102">Changing the Cache Sharing Levels for Send Activities</span></span>
<span data-ttu-id="68954-103">La extensión <xref:System.ServiceModel.Activities.SendMessageChannelCache> le permite personalizar los niveles de uso compartido de la memoria caché, la configuración de la memoria caché del generador de canales y la de la memoria caché del canal para los flujos de trabajo que envían mensajes a los puntos de conexión de servicio utilizando las actividades de mensajería de <xref:System.ServiceModel.Activities.Send>.</span><span class="sxs-lookup"><span data-stu-id="68954-103">The <xref:System.ServiceModel.Activities.SendMessageChannelCache> extension enables you to customize the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using <xref:System.ServiceModel.Activities.Send> messaging activities.</span></span> <span data-ttu-id="68954-104">Estos flujos de trabajo son normalmente flujos de trabajo del cliente pero podrían ser también servicios de flujo de trabajo que se hospedan en <xref:System.ServiceModel.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="68954-104">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span> <span data-ttu-id="68954-105">La memoria caché del generador de canales contiene objetos <xref:System.ServiceModel.ChannelFactory%601> almacenados en caché.</span><span class="sxs-lookup"><span data-stu-id="68954-105">The channel factory cache contains cached <xref:System.ServiceModel.ChannelFactory%601> objects.</span></span> <span data-ttu-id="68954-106">La memoria caché del canal contiene canales almacenados en memoria caché.</span><span class="sxs-lookup"><span data-stu-id="68954-106">The channel cache contains cached channels.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="68954-107">Los flujos de trabajo pueden usar las actividades de mensajería de <xref:System.ServiceModel.Activities.Send> para enviar mensajes o parámetros.</span><span class="sxs-lookup"><span data-stu-id="68954-107">Workflows can use <xref:System.ServiceModel.Activities.Send> messaging activities to send either messages or parameters.</span></span> <span data-ttu-id="68954-108">El tiempo de ejecución del flujo de trabajo agrega los generadores de canales a la memoria caché que crean canales de tipo <xref:System.ServiceModel.Channels.IRequestChannel> cuando se usa una actividad <xref:System.ServiceModel.Activities.ReceiveReply> con una actividad <xref:System.ServiceModel.Activities.Send> y <xref:System.ServiceModel.Channels.IOutputChannel> cuando se usa solo una actividad <xref:System.ServiceModel.Activities.Send> (sin <xref:System.ServiceModel.Activities.ReceiveReply>).</span><span class="sxs-lookup"><span data-stu-id="68954-108">The workflow runtime adds channel factories to the cache that create channels of type <xref:System.ServiceModel.Channels.IRequestChannel> when you use a <xref:System.ServiceModel.Activities.ReceiveReply> activity with a <xref:System.ServiceModel.Activities.Send> activity, and an <xref:System.ServiceModel.Channels.IOutputChannel> when just using a <xref:System.ServiceModel.Activities.Send> activity (no <xref:System.ServiceModel.Activities.ReceiveReply>).</span></span>  
  
## <a name="the-cache-sharing-levels"></a><span data-ttu-id="68954-109">Niveles de uso compartido de memoria caché</span><span class="sxs-lookup"><span data-stu-id="68954-109">The Cache Sharing Levels</span></span>  
 <span data-ttu-id="68954-110">De manera predeterminada, en un flujo de trabajo hospedado por <xref:System.ServiceModel.WorkflowServiceHost>, la memoria caché usada por las actividades de mensajería de <xref:System.ServiceModel.Activities.Send> se comparte en todas las instancias de flujo de trabajo en <xref:System.ServiceModel.WorkflowServiceHost> (el almacenamiento en caché de nivel de host).</span><span class="sxs-lookup"><span data-stu-id="68954-110">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost> the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="68954-111">Para un flujo de trabajo del cliente que no esté hospedado por <xref:System.ServiceModel.WorkflowServiceHost>, la memoria caché está solo disponible para la instancia de flujo de trabajo (almacenamiento en caché en el nivel de instancia).</span><span class="sxs-lookup"><span data-stu-id="68954-111">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="68954-112">La memoria caché solo está disponible para las actividades <xref:System.ServiceModel.Activities.Send> que no usan puntos de conexión definidos en la configuración a menos que esté habilitado el almacenamiento en memoria caché no seguro.</span><span class="sxs-lookup"><span data-stu-id="68954-112">The cache is only available for <xref:System.ServiceModel.Activities.Send> activities that do not use endpoints defined in configuration unless unsafe caching is enabled.</span></span>  
  
 <span data-ttu-id="68954-113">A continuación, se enumeran los distintos niveles de uso compartido de la memoria caché disponibles para las actividades de <xref:System.ServiceModel.Activities.Send> en un flujo de trabajo y su uso recomendado:</span><span class="sxs-lookup"><span data-stu-id="68954-113">The following are the different cache sharing levels available for <xref:System.ServiceModel.Activities.Send> activities in a workflow and their recommended use:</span></span>  
  
- <span data-ttu-id="68954-114">Nivel de **host:** en el nivel de uso compartido del host, la memoria caché solo está disponible para las instancias de flujo de trabajo hospedadas en el host del servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="68954-114">**Host Level**: In the host sharing level, the cache is available only to the workflow instances hosted in the workflow service host.</span></span> <span data-ttu-id="68954-115">Además, la memoria caché también puede compartirse entre los hosts de servicio de flujo de trabajo en una memoria caché de todo el proceso.</span><span class="sxs-lookup"><span data-stu-id="68954-115">A cache can also be shared between workflow service hosts in a process-wide cache.</span></span>  
  
- <span data-ttu-id="68954-116">Nivel de **instancia:** en el nivel de uso compartido de instancias, la memoria caché está disponible para una instancia de flujo de trabajo determinada a lo largo de su vida útil, pero la memoria caché no está disponible para otras instancias de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="68954-116">**Instance Level**: In the instance sharing level, the cache is available to a particular workflow instance throughout its lifetime but the cache is not available to other workflow instances.</span></span>  
  
- <span data-ttu-id="68954-117">**Sin caché:** la memoria caché está desactivada de forma predeterminada si tiene un flujo de trabajo que utiliza puntos de conexión definidos en la configuración.</span><span class="sxs-lookup"><span data-stu-id="68954-117">**No Cache**: The cache is turned off by default if you have a workflow that uses endpoints defined in configuration.</span></span> <span data-ttu-id="68954-118">También se recomienda mantener la memoria caché desactivada en este caso porque activarla podría no ser seguro.</span><span class="sxs-lookup"><span data-stu-id="68954-118">It is also recommended to keep the cache turned off in this case because turning it on could be unsecure.</span></span> <span data-ttu-id="68954-119">Por ejemplo, si se necesita una identidad diferente (con credenciales diferentes o usando la suplantación) para cada envío.</span><span class="sxs-lookup"><span data-stu-id="68954-119">For example, if a different identity (different credentials or using impersonation) is required for each send.</span></span>  
  
## <a name="changing-the-cache-sharing-level-for-a-client-workflow"></a><span data-ttu-id="68954-120">Cambiar el nivel de uso compartido de la memoria caché para un flujo de trabajo de cliente</span><span class="sxs-lookup"><span data-stu-id="68954-120">Changing the Cache Sharing Level for a Client Workflow</span></span>  
 <span data-ttu-id="68954-121">Para establecer el uso compartido de la memoria caché en un flujo de trabajo del cliente, agregue una instancia de la clase <xref:System.ServiceModel.Activities.SendMessageChannelCache> como una extensión al conjunto que desee de instancias de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="68954-121">To set the cache sharing in a client workflow, add an instance of the <xref:System.ServiceModel.Activities.SendMessageChannelCache> class as an extension to the desired set of workflow instances.</span></span> <span data-ttu-id="68954-122">Este hecho da como resultado compartir la memoria caché por todas las instancias de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="68954-122">This results in sharing the cache across all the workflow instances.</span></span> <span data-ttu-id="68954-123">En los siguientes ejemplos de código se muestra cómo realizar estos pasos:</span><span class="sxs-lookup"><span data-stu-id="68954-123">The following code examples show how to perform these steps.</span></span>  
  
 <span data-ttu-id="68954-124">Primero, declare una instancia de tipo <xref:System.ServiceModel.Activities.SendMessageChannelCache>:</span><span class="sxs-lookup"><span data-stu-id="68954-124">First, declare an instance of type <xref:System.ServiceModel.Activities.SendMessageChannelCache>.</span></span>  
  
```csharp  
// Create an instance of SendMessageChannelCache with default cache settings.  
static SendMessageChannelCache sharedChannelCacheExtension =  
    new SendMessageChannelCache();  
```  
  
 <span data-ttu-id="68954-125">Luego, agregue la extensión de memoria caché a cada instancia de flujo de trabajo del cliente.</span><span class="sxs-lookup"><span data-stu-id="68954-125">Next, add the cache extension to each client workflow instance.</span></span>  
  
```csharp
WorkflowApplication clientInstance1 = new WorkflowApplication(new clientWorkflow1());  
WorkflowApplication clientInstance2 = new WorkflowApplication(new clientWorkflow2());  
  
// Share the cache extension object
  
clientInstance1.Extensions.Add(sharedChannelCacheExtension);  
clientInstance2.Extensions.Add(sharedChannelCacheExtension);  
```  
  
## <a name="changing-the-cache-sharing-level-for-a-hosted-workflow-service"></a><span data-ttu-id="68954-126">Cambiar el nivel de uso compartido de la memoria caché para un servicio de flujo de trabajo hospedado</span><span class="sxs-lookup"><span data-stu-id="68954-126">Changing the Cache Sharing Level for a Hosted Workflow Service</span></span>  
 <span data-ttu-id="68954-127">Para establecer el uso compartido de la memoria caché en un servicio del flujo de trabajo hospedado, agregue una instancia de la clase <xref:System.ServiceModel.Activities.SendMessageChannelCache> como extensión para todos los hosts de servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="68954-127">To set the cache sharing in a hosted workflow service, add an instance of the <xref:System.ServiceModel.Activities.SendMessageChannelCache> class as an extension to all the workflow service hosts.</span></span> <span data-ttu-id="68954-128">Esto da como resultado compartir la memoria caché por todos los hosts de servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="68954-128">This results in sharing the cache across all the workflow service hosts.</span></span> <span data-ttu-id="68954-129">En los siguientes ejemplos de código se muestra cómo realizar estos pasos.</span><span class="sxs-lookup"><span data-stu-id="68954-129">The following code examples show to perform these steps.</span></span>  
  
 <span data-ttu-id="68954-130">Primero, declare una instancia del tipo <xref:System.ServiceModel.Activities.SendMessageChannelCache> en el nivel de clase.</span><span class="sxs-lookup"><span data-stu-id="68954-130">First, declare an instance  of type <xref:System.ServiceModel.Activities.SendMessageChannelCache> at the class level.</span></span>  
  
```csharp  
// Create static instance of SendMessageChannelCache with default cache settings.  
static SendMessageChannelCache sharedChannelCacheExtension = new  
    SendMessageChannelCache();  
```  
  
 <span data-ttu-id="68954-131">A continuación, agregue la extensión de memoria caché estática a cada host de servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="68954-131">Next, add the static cache extension to each workflow service host.</span></span>  
  
```csharp  
WorkflowServiceHost host1 = new WorkflowServiceHost(new serviceWorkflow1(), new Uri(baseAddress1));  
WorkflowServiceHost host2 = new WorkflowServiceHost(new serviceWorkflow2(), new Uri(baseAddress2));  
  
// Share the static cache to get an AppDomain level cache.  
host1.WorkflowExtensions.Add(sharedChannelCacheExtension);  
host2.WorkflowExtensions.Add(sharedChannelCacheExtension);  
```  
  
 <span data-ttu-id="68954-132">Para establecer el uso compartido de la memoria caché en un servicio del flujo de trabajo hospedado en el nivel de la instancia, agregue un delegado `Func<SendMessageChannelCache>` como una extensión al host de servicio de flujo de trabajo y asigne este delegado al código que crea instancias de una nueva instancia de la clase <xref:System.ServiceModel.Activities.SendMessageChannelCache>.</span><span class="sxs-lookup"><span data-stu-id="68954-132">To set the cache sharing in a hosted workflow service to the instance level, add a `Func<SendMessageChannelCache>` delegate as an extension to the workflow service host and assign this delegate to the code that instantiates a new instance of the <xref:System.ServiceModel.Activities.SendMessageChannelCache> class.</span></span> <span data-ttu-id="68954-133">Esto da como resultado una memoria caché diferente para cada instancia de flujo de trabajo, en lugar de una memoria caché única compartida por todas las instancias de flujo de trabajo en el host de servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="68954-133">This results in a different cache for each individual workflow instance, instead of a single cache shared by all workflow instances in the workflow service host.</span></span> <span data-ttu-id="68954-134">El siguiente ejemplo de código muestra cómo lograr esto utilizando una expresión lambda para definir directamente la extensión <xref:System.ServiceModel.Activities.SendMessageChannelCache> a la que el delegado señala.</span><span class="sxs-lookup"><span data-stu-id="68954-134">The following code example shows how to achieve this by using a lambda expression to directly define the <xref:System.ServiceModel.Activities.SendMessageChannelCache> extension that the delegate points to.</span></span>  
  
```csharp
serviceHost.WorkflowExtensions.Add(() => new SendMessageChannelCache  
{  
    // Use FactorySettings property to add custom factory cache settings.  
    FactorySettings = new ChannelCacheSettings
    { MaxItemsInCache = 5, },  
    // Use ChannelSettings property to add custom channel cache settings.  
    ChannelSettings = new ChannelCacheSettings
    { MaxItemsInCache = 10 },  
});  
```  
  
## <a name="customizing-cache-settings"></a><span data-ttu-id="68954-135">Personalizar la configuración de la memoria caché</span><span class="sxs-lookup"><span data-stu-id="68954-135">Customizing Cache Settings</span></span>  
 <span data-ttu-id="68954-136">Puede personalizar la configuración de la memoria caché para la memoria caché del generador de canales y del canal.</span><span class="sxs-lookup"><span data-stu-id="68954-136">You can customize the cache settings for the channel factory cache and the channel cache.</span></span> <span data-ttu-id="68954-137">La configuración de la memoria caché se define en la clase <xref:System.ServiceModel.Activities.ChannelCacheSettings>.</span><span class="sxs-lookup"><span data-stu-id="68954-137">The cache settings are defined in the <xref:System.ServiceModel.Activities.ChannelCacheSettings> class.</span></span> <span data-ttu-id="68954-138">La <xref:System.ServiceModel.Activities.SendMessageChannelCache> clase define la configuración de caché predeterminada para la caché de generador de canales y la caché de canales en su constructor sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="68954-138">The <xref:System.ServiceModel.Activities.SendMessageChannelCache> class defines default cache settings for the channel factory cache and the channel cache in its parameterless constructor.</span></span> <span data-ttu-id="68954-139">En la siguiente tabla se hace una lista de los valores predeterminados de la configuración de cada tipo de memoria caché.</span><span class="sxs-lookup"><span data-stu-id="68954-139">The following table lists the default values of these cache settings for each type of cache.</span></span>  
  
|<span data-ttu-id="68954-140">Configuración</span><span class="sxs-lookup"><span data-stu-id="68954-140">Settings</span></span>|<span data-ttu-id="68954-141">LeaseTimeout (min)</span><span class="sxs-lookup"><span data-stu-id="68954-141">LeaseTimeout (min)</span></span>|<span data-ttu-id="68954-142">IdleTimeout (min)</span><span class="sxs-lookup"><span data-stu-id="68954-142">IdleTimeout (min)</span></span>|<span data-ttu-id="68954-143">MaxItemsInCache</span><span class="sxs-lookup"><span data-stu-id="68954-143">MaxItemsInCache</span></span>|  
|-|-|-|-|  
|<span data-ttu-id="68954-144">Valor predeterminado de la memoria caché del generador</span><span class="sxs-lookup"><span data-stu-id="68954-144">Factory Cache Default</span></span>|<span data-ttu-id="68954-145">TimeSpan.MaxValue</span><span class="sxs-lookup"><span data-stu-id="68954-145">TimeSpan.MaxValue</span></span>|<span data-ttu-id="68954-146">2</span><span class="sxs-lookup"><span data-stu-id="68954-146">2</span></span>|<span data-ttu-id="68954-147">16</span><span class="sxs-lookup"><span data-stu-id="68954-147">16</span></span>|  
|<span data-ttu-id="68954-148">Valor predeterminado de la memoria caché del canal</span><span class="sxs-lookup"><span data-stu-id="68954-148">Channel Cache Default</span></span>|<span data-ttu-id="68954-149">5</span><span class="sxs-lookup"><span data-stu-id="68954-149">5</span></span>|<span data-ttu-id="68954-150">2</span><span class="sxs-lookup"><span data-stu-id="68954-150">2</span></span>|<span data-ttu-id="68954-151">16</span><span class="sxs-lookup"><span data-stu-id="68954-151">16</span></span>|  
  
 <span data-ttu-id="68954-152">Para personalizar la configuración de la memoria caché del generador y del canal, cree instancias de la clase <xref:System.ServiceModel.Activities.SendMessageChannelCache> con el constructor parametrizado <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> y pase una nueva instancia de <xref:System.ServiceModel.Activities.ChannelCacheSettings> con valores personalizados a cada uno de los parámetros `factorySettings` y `channelSettings`.</span><span class="sxs-lookup"><span data-stu-id="68954-152">To customize the factory cache and channel cache settings, instantiate the <xref:System.ServiceModel.Activities.SendMessageChannelCache> class using the parameterized constructor <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> and pass a new instance of the <xref:System.ServiceModel.Activities.ChannelCacheSettings> with custom values to each of the `factorySettings` and `channelSettings` parameters.</span></span> <span data-ttu-id="68954-153">A continuación, agregue la nueva instancia de esta clase como una extensión a un host de servicio de flujo de trabajo o una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="68954-153">Next, add the new instance of this class as an extension to a workflow service host or a workflow instance.</span></span> <span data-ttu-id="68954-154">El siguiente ejemplo de código muestra cómo realizar estos pasos para una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="68954-154">The following code example shows how to perform these steps for a workflow instance.</span></span>  
  
```csharp  
ChannelCacheSettings factorySettings = new ChannelCacheSettings{  
                        MaxItemsInCache = 5,
                        IdleTimeout = TimeSpan.FromMinutes(5),
                        LeaseTimeout = TimeSpan.FromMinutes(20)};  
  
ChannelCacheSettings channelSettings = new ChannelCacheSettings{  
                        MaxItemsInCache = 5,
                        IdleTimeout = TimeSpan.FromMinutes(2),  
                        LeaseTimeout = TimeSpan.FromMinutes(10) };  
  
SendMessageChannelCache customChannelCacheExtension =
    new SendMessageChannelCache(factorySettings, channelSettings);  
  
clientInstance.Extensions.Add(customChannelCacheExtension);  
```  
  
 <span data-ttu-id="68954-155">Para permitir el almacenamiento en caché cuando su servicio del flujo de trabajo tiene los extremos definidos en la configuración, cree instancias de la clase <xref:System.ServiceModel.Activities.SendMessageChannelCache> usando el constructor parametrizado <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> con el parámetro `allowUnsafeCaching` definido en `true`.</span><span class="sxs-lookup"><span data-stu-id="68954-155">To enable caching when your workflow service has endpoints defined in configuration, instantiate the <xref:System.ServiceModel.Activities.SendMessageChannelCache> class using the parameterized constructor <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> with the `allowUnsafeCaching` parameter set to `true`.</span></span> <span data-ttu-id="68954-156">A continuación, agregue la nueva instancia de esta clase como una extensión a un host de servicio de flujo de trabajo o una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="68954-156">Next, add the new instance of this class as an extension to a workflow service host or a workflow instance.</span></span> <span data-ttu-id="68954-157">El siguiente ejemplo de código muestra cómo habilitar el almacenamiento en caché para una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="68954-157">The following code example shows how to enable caching for a workflow instance.</span></span>  
  
```csharp  
SendMessageChannelCache customChannelCacheExtension =
    new SendMessageChannelCache{ AllowUnsafeCaching = true };  
  
clientInstance.Extensions.Add(customChannelCacheExtension);  
```  
  
 <span data-ttu-id="68954-158">Para deshabilitar por completo la memoria caché para los generadores de canales y los canales, deshabilite la memoria caché del generador de canales.</span><span class="sxs-lookup"><span data-stu-id="68954-158">To disable the cache completely for the channel factories and the channels, disable the channel factory cache.</span></span> <span data-ttu-id="68954-159">Al hacerlo se desactivará la memoria caché del canal ya que los canales son propiedad de sus respectivos generadores de canales.</span><span class="sxs-lookup"><span data-stu-id="68954-159">Doing so also turns off the channel cache as the channels are owned by their corresponding channel factories.</span></span> <span data-ttu-id="68954-160">Para deshabilitar la memoria caché del generador de canales, pase el parámetro `factorySettings` al constructor <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> inicializado en una instancia de <xref:System.ServiceModel.Activities.ChannelCacheSettings> con un valor de 0 para <xref:System.ServiceModel.Activities.ChannelCacheSettings.MaxItemsInCache%2A>.</span><span class="sxs-lookup"><span data-stu-id="68954-160">To disable the channel factory cache, pass the `factorySettings` parameter to the <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> constructor initialized to a <xref:System.ServiceModel.Activities.ChannelCacheSettings> instance with a <xref:System.ServiceModel.Activities.ChannelCacheSettings.MaxItemsInCache%2A> value of 0.</span></span> <span data-ttu-id="68954-161">El ejemplo de código siguiente muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="68954-161">The following code example shows this.</span></span>  
  
```csharp  
// Disable the factory cache. This results in the channel cache to be turned off as well.  
ChannelCacheSettings factorySettings = new ChannelCacheSettings  
    { MaxItemsInCache = 0 };  
  
ChannelCacheSettings channelSettings = new ChannelCacheSettings();  
  
SendMessageChannelCache customChannelCacheExtension =
    new SendMessageChannelCache(factorySettings, channelSettings);
  
clientInstance.Extensions.Add(customChannelCacheExtension);  
```  
  
 <span data-ttu-id="68954-162">Puede decidir usar sólo la memoria caché del generador de canales y deshabilitar la memoria caché del canal pasando el parámetro `channelSettings` al constructor <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> inicializado para una instancia de <xref:System.ServiceModel.Activities.ChannelCacheSettings> con un valor 0 para <xref:System.ServiceModel.Activities.ChannelCacheSettings.MaxItemsInCache%2A>.</span><span class="sxs-lookup"><span data-stu-id="68954-162">You can choose to use only the channel factory cache and disable the channel cache by passing the `channelSettings` parameter to the <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> constructor initialized to a <xref:System.ServiceModel.Activities.ChannelCacheSettings> instance with a <xref:System.ServiceModel.Activities.ChannelCacheSettings.MaxItemsInCache%2A> value of 0.</span></span> <span data-ttu-id="68954-163">El ejemplo de código siguiente muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="68954-163">The following code example shows this.</span></span>  
  
```csharp  
ChannelCacheSettings factorySettings = new ChannelCacheSettings();  
// Disable only the channel cache.  
ChannelCacheSettings channelSettings = new ChannelCacheSettings  
    { MaxItemsInCache = 0};  
  
SendMessageChannelCache customChannelCacheExtension =
    new SendMessageChannelCache(factorySettings, channelSettings);
  
clientInstance.Extensions.Add(customChannelCacheExtension);  
```  
  
 <span data-ttu-id="68954-164">En un servicio de flujo de trabajo hospedado, puede especificar la configuración de la memoria caché del generador y del canal en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="68954-164">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="68954-165">Para ello, agregue un comportamiento de servicio que contenga los valores de memoria caché para el generador y memoria caché del canal, y agregue este comportamiento de servicio a su servicio.</span><span class="sxs-lookup"><span data-stu-id="68954-165">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="68954-166">En el ejemplo siguiente se muestra el `MyChannelCacheBehavior` contenido de un archivo de configuración que contiene el comportamiento del servicio con la caché de fábrica personalizada y la configuración de caché de canal.</span><span class="sxs-lookup"><span data-stu-id="68954-166">The following example shows the contents of a configuration file that contains the `MyChannelCacheBehavior` service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="68954-167">Este comportamiento de servicio se `behaviorConfiguration` agrega al servicio a través del atributo.</span><span class="sxs-lookup"><span data-stu-id="68954-167">This service behavior is added to the service through the `behaviorConfiguration` attribute.</span></span>  
  
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
