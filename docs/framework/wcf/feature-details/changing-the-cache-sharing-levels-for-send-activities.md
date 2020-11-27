---
title: Cambiar los niveles de uso compartido de caché para actividades Send
ms.date: 03/30/2017
ms.assetid: 03926a64-753d-460e-ac06-2a4ff8e1bbf5
ms.openlocfilehash: cbb937ac47c93307db922b28e3df0ea694a77960
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262053"
---
# <a name="changing-the-cache-sharing-levels-for-send-activities"></a>Cambiar los niveles de uso compartido de caché para actividades Send

La extensión <xref:System.ServiceModel.Activities.SendMessageChannelCache> le permite personalizar los niveles de uso compartido de la memoria caché, la configuración de la memoria caché del generador de canales y la de la memoria caché del canal para los flujos de trabajo que envían mensajes a los puntos de conexión de servicio utilizando las actividades de mensajería de <xref:System.ServiceModel.Activities.Send>. Estos flujos de trabajo son normalmente flujos de trabajo del cliente pero podrían ser también servicios de flujo de trabajo que se hospedan en <xref:System.ServiceModel.WorkflowServiceHost>. La memoria caché del generador de canales contiene objetos <xref:System.ServiceModel.ChannelFactory%601> almacenados en caché. La memoria caché del canal contiene canales almacenados en memoria caché.  
  
> [!NOTE]
> Los flujos de trabajo pueden usar las actividades de mensajería de <xref:System.ServiceModel.Activities.Send> para enviar mensajes o parámetros. El tiempo de ejecución del flujo de trabajo agrega los generadores de canales a la memoria caché que crean canales de tipo <xref:System.ServiceModel.Channels.IRequestChannel> cuando se usa una actividad <xref:System.ServiceModel.Activities.ReceiveReply> con una actividad <xref:System.ServiceModel.Activities.Send> y <xref:System.ServiceModel.Channels.IOutputChannel> cuando se usa solo una actividad <xref:System.ServiceModel.Activities.Send> (sin <xref:System.ServiceModel.Activities.ReceiveReply>).  
  
## <a name="the-cache-sharing-levels"></a>Niveles de uso compartido de memoria caché  

 De manera predeterminada, en un flujo de trabajo hospedado por <xref:System.ServiceModel.WorkflowServiceHost>, la memoria caché usada por las actividades de mensajería de <xref:System.ServiceModel.Activities.Send> se comparte en todas las instancias de flujo de trabajo en <xref:System.ServiceModel.WorkflowServiceHost> (el almacenamiento en caché de nivel de host). Para un flujo de trabajo del cliente que no esté hospedado por <xref:System.ServiceModel.WorkflowServiceHost>, la memoria caché está solo disponible para la instancia de flujo de trabajo (almacenamiento en caché en el nivel de instancia). La memoria caché solo está disponible para las actividades <xref:System.ServiceModel.Activities.Send> que no usan puntos de conexión definidos en la configuración a menos que esté habilitado el almacenamiento en memoria caché no seguro.  
  
 A continuación, se enumeran los distintos niveles de uso compartido de la memoria caché disponibles para las actividades de <xref:System.ServiceModel.Activities.Send> en un flujo de trabajo y su uso recomendado:  
  
- **Nivel de host**: en el nivel de uso compartido de host, la memoria caché solo está disponible para las instancias de flujo de trabajo hospedadas en el host de servicio de flujo de trabajo. Además, la memoria caché también puede compartirse entre los hosts de servicio de flujo de trabajo en una memoria caché de todo el proceso.  
  
- **Nivel de instancia**: en el nivel de uso compartido de la instancia, la memoria caché está disponible para una instancia de flujo de trabajo determinada a lo largo de su duración, pero la memoria caché no está disponible para otras instancias de flujo de trabajo.  
  
- **Sin caché**: la memoria caché está desactivada de forma predeterminada si tiene un flujo de trabajo que usa extremos definidos en la configuración. También se recomienda mantener la memoria caché desactivada en este caso porque activarla podría no ser seguro. Por ejemplo, si se necesita una identidad diferente (con credenciales diferentes o usando la suplantación) para cada envío.  
  
## <a name="changing-the-cache-sharing-level-for-a-client-workflow"></a>Cambiar el nivel de uso compartido de la memoria caché para un flujo de trabajo de cliente  

 Para establecer el uso compartido de la memoria caché en un flujo de trabajo del cliente, agregue una instancia de la clase <xref:System.ServiceModel.Activities.SendMessageChannelCache> como una extensión al conjunto que desee de instancias de flujo de trabajo. Este hecho da como resultado compartir la memoria caché por todas las instancias de flujo de trabajo. En los siguientes ejemplos de código se muestra cómo realizar estos pasos:  
  
 Primero, declare una instancia de tipo <xref:System.ServiceModel.Activities.SendMessageChannelCache>:  
  
```csharp  
// Create an instance of SendMessageChannelCache with default cache settings.  
static SendMessageChannelCache sharedChannelCacheExtension =  
    new SendMessageChannelCache();  
```  
  
 Luego, agregue la extensión de memoria caché a cada instancia de flujo de trabajo del cliente.  
  
```csharp
WorkflowApplication clientInstance1 = new WorkflowApplication(new clientWorkflow1());  
WorkflowApplication clientInstance2 = new WorkflowApplication(new clientWorkflow2());  
  
// Share the cache extension object
  
clientInstance1.Extensions.Add(sharedChannelCacheExtension);  
clientInstance2.Extensions.Add(sharedChannelCacheExtension);  
```  
  
## <a name="changing-the-cache-sharing-level-for-a-hosted-workflow-service"></a>Cambiar el nivel de uso compartido de la memoria caché para un servicio de flujo de trabajo hospedado  

 Para establecer el uso compartido de la memoria caché en un servicio del flujo de trabajo hospedado, agregue una instancia de la clase <xref:System.ServiceModel.Activities.SendMessageChannelCache> como extensión para todos los hosts de servicio de flujo de trabajo. Esto da como resultado compartir la memoria caché por todos los hosts de servicio de flujo de trabajo. En los siguientes ejemplos de código se muestra cómo realizar estos pasos.  
  
 Primero, declare una instancia del tipo <xref:System.ServiceModel.Activities.SendMessageChannelCache> en el nivel de clase.  
  
```csharp  
// Create static instance of SendMessageChannelCache with default cache settings.  
static SendMessageChannelCache sharedChannelCacheExtension = new  
    SendMessageChannelCache();  
```  
  
 A continuación, agregue la extensión de memoria caché estática a cada host de servicio de flujo de trabajo.  
  
```csharp  
WorkflowServiceHost host1 = new WorkflowServiceHost(new serviceWorkflow1(), new Uri(baseAddress1));  
WorkflowServiceHost host2 = new WorkflowServiceHost(new serviceWorkflow2(), new Uri(baseAddress2));  
  
// Share the static cache to get an AppDomain level cache.  
host1.WorkflowExtensions.Add(sharedChannelCacheExtension);  
host2.WorkflowExtensions.Add(sharedChannelCacheExtension);  
```  
  
 Para establecer el uso compartido de la memoria caché en un servicio del flujo de trabajo hospedado en el nivel de la instancia, agregue un delegado `Func<SendMessageChannelCache>` como una extensión al host de servicio de flujo de trabajo y asigne este delegado al código que crea instancias de una nueva instancia de la clase <xref:System.ServiceModel.Activities.SendMessageChannelCache>. Esto da como resultado una memoria caché diferente para cada instancia de flujo de trabajo, en lugar de una memoria caché única compartida por todas las instancias de flujo de trabajo en el host de servicio de flujo de trabajo. El siguiente ejemplo de código muestra cómo lograr esto utilizando una expresión lambda para definir directamente la extensión <xref:System.ServiceModel.Activities.SendMessageChannelCache> a la que el delegado señala.  
  
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
  
## <a name="customizing-cache-settings"></a>Personalizar la configuración de la memoria caché  

 Puede personalizar la configuración de la memoria caché para la memoria caché del generador de canales y del canal. La configuración de la memoria caché se define en la clase <xref:System.ServiceModel.Activities.ChannelCacheSettings>. La <xref:System.ServiceModel.Activities.SendMessageChannelCache> clase define la configuración de caché predeterminada para la memoria caché del generador de canales y la memoria caché del canal en su constructor sin parámetros. En la siguiente tabla se hace una lista de los valores predeterminados de la configuración de cada tipo de memoria caché.  
  
|Configuración|LeaseTimeout (min)|IdleTimeout (min)|MaxItemsInCache|  
|-|-|-|-|  
|Valor predeterminado de la memoria caché del generador|TimeSpan.MaxValue|2|16|  
|Valor predeterminado de la memoria caché del canal|5|2|16|  
  
 Para personalizar la configuración de la memoria caché del generador y del canal, cree instancias de la clase <xref:System.ServiceModel.Activities.SendMessageChannelCache> con el constructor parametrizado <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> y pase una nueva instancia de <xref:System.ServiceModel.Activities.ChannelCacheSettings> con valores personalizados a cada uno de los parámetros `factorySettings` y `channelSettings`. A continuación, agregue la nueva instancia de esta clase como una extensión a un host de servicio de flujo de trabajo o una instancia de flujo de trabajo. El siguiente ejemplo de código muestra cómo realizar estos pasos para una instancia de flujo de trabajo.  
  
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
  
 Para permitir el almacenamiento en caché cuando su servicio del flujo de trabajo tiene los extremos definidos en la configuración, cree instancias de la clase <xref:System.ServiceModel.Activities.SendMessageChannelCache> usando el constructor parametrizado <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> con el parámetro `allowUnsafeCaching` definido en `true`. A continuación, agregue la nueva instancia de esta clase como una extensión a un host de servicio de flujo de trabajo o una instancia de flujo de trabajo. El siguiente ejemplo de código muestra cómo habilitar el almacenamiento en caché para una instancia de flujo de trabajo.  
  
```csharp  
SendMessageChannelCache customChannelCacheExtension =
    new SendMessageChannelCache{ AllowUnsafeCaching = true };  
  
clientInstance.Extensions.Add(customChannelCacheExtension);  
```  
  
 Para deshabilitar por completo la memoria caché para los generadores de canales y los canales, deshabilite la memoria caché del generador de canales. Al hacerlo se desactivará la memoria caché del canal ya que los canales son propiedad de sus respectivos generadores de canales. Para deshabilitar la memoria caché del generador de canales, pase el parámetro `factorySettings` al constructor <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> inicializado en una instancia de <xref:System.ServiceModel.Activities.ChannelCacheSettings> con un valor de 0 para <xref:System.ServiceModel.Activities.ChannelCacheSettings.MaxItemsInCache%2A>. El ejemplo de código siguiente muestra cómo hacerlo.  
  
```csharp  
// Disable the factory cache. This results in the channel cache to be turned off as well.  
ChannelCacheSettings factorySettings = new ChannelCacheSettings  
    { MaxItemsInCache = 0 };  
  
ChannelCacheSettings channelSettings = new ChannelCacheSettings();  
  
SendMessageChannelCache customChannelCacheExtension =
    new SendMessageChannelCache(factorySettings, channelSettings);
  
clientInstance.Extensions.Add(customChannelCacheExtension);  
```  
  
 Puede decidir usar sólo la memoria caché del generador de canales y deshabilitar la memoria caché del canal pasando el parámetro `channelSettings` al constructor <xref:System.ServiceModel.Activities.SendMessageChannelCache.%23ctor%2A> inicializado para una instancia de <xref:System.ServiceModel.Activities.ChannelCacheSettings> con un valor 0 para <xref:System.ServiceModel.Activities.ChannelCacheSettings.MaxItemsInCache%2A>. El ejemplo de código siguiente muestra cómo hacerlo.  
  
```csharp  
ChannelCacheSettings factorySettings = new ChannelCacheSettings();  
// Disable only the channel cache.  
ChannelCacheSettings channelSettings = new ChannelCacheSettings  
    { MaxItemsInCache = 0};  
  
SendMessageChannelCache customChannelCacheExtension =
    new SendMessageChannelCache(factorySettings, channelSettings);
  
clientInstance.Extensions.Add(customChannelCacheExtension);  
```  
  
 En un servicio de flujo de trabajo hospedado, puede especificar la configuración de la memoria caché del generador y del canal en el archivo de configuración de la aplicación. Para ello, agregue un comportamiento de servicio que contenga los valores de memoria caché para el generador y memoria caché del canal, y agregue este comportamiento de servicio a su servicio. En el ejemplo siguiente se muestra el contenido de un archivo de configuración que contiene el `MyChannelCacheBehavior` comportamiento del servicio con la configuración personalizada de la memoria caché del generador y del canal. Este comportamiento del servicio se agrega al servicio a través del `behaviorConfiguration` atributo.  
  
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
