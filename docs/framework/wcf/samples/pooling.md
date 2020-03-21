---
title: Agrupación
ms.date: 03/30/2017
ms.assetid: 688dfb30-b79a-4cad-a687-8302f8a9ad6a
ms.openlocfilehash: 46abc2c9c667ea7614581d7fafaa8e174db7f14f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183406"
---
# <a name="pooling"></a>Agrupación
En este ejemplo se muestra cómo ampliar Windows Communication Foundation (WCF) para admitir la agrupación de objetos. El ejemplo muestra cómo crear un atributo que es sintáctica y semánticamente similar a la funcionalidad del atributo `ObjectPoolingAttribute` de Enterprise Services. La agrupación de objetos puede aumentar de manera considerable el rendimiento de una aplicación. Sin embargo, puede tener el efecto contrario si no se utiliza correctamente. La agrupación de objetos ayuda a reducir la sobrecarga que supone volver a crear objetos usados con frecuencia que requieren inicialización extensa. Sin embargo, si una llamada a un método en un objeto agrupado necesita una cantidad considerable de tiempo para completarse, la agrupación de objetos pone en la cola solicitudes adicionales en cuanto se alcance el tamaño máximo del grupo. Así, puede ser que no se preste servicio a algunas solicitudes de creación de objetos produciendo una excepción de tiempo de espera agotado.  
  
> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 El primer paso para crear una extensión WCF es decidir el punto de extensibilidad que se va a usar.  
  
 En WCF, el término *distribuidor* hace referencia a un componente en tiempo de ejecución responsable de convertir los mensajes entrantes en invocaciones de método en el servicio del usuario y de convertir los valores devueltos de ese método en un mensaje saliente. Un servicio WCF crea un distribuidor para cada extremo. Un cliente WCF debe usar un distribuidor si el contrato asociado a ese cliente es un contrato dúplex.  
  
 Los distribuidores de extremos y canales proporcionan extensibilidad para canales y contratos exponiendo varias propiedades que controlan el comportamiento del distribuidor. La propiedad <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.DispatchRuntime%2A> también le permite inspeccionar, modificar o personalizar el proceso de distribución. Este ejemplo se centra en la propiedad <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> que señala al objeto que proporciona las instancias de la clase de servicio.  
  
## <a name="the-iinstanceprovider"></a>IInstanceProvider  
 En WCF, el distribuidor crea instancias <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A>de la clase <xref:System.ServiceModel.Dispatcher.IInstanceProvider> de servicio mediante un , que implementa la interfaz. Esta interfaz tiene tres métodos:  
  
- <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29>: cuando un mensaje llega, el distribuidor llama al método <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29> para crear una instancia de la clase de servicio para procesar el mensaje. La propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> determina la frecuencia de las llamadas a este método. Por ejemplo, si la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> está establecida en <xref:System.ServiceModel.InstanceContextMode.PerCall>, se crea una nueva instancia de la clase de servicio para procesar cada mensaje que llegue, por lo que se llama a <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29> siempre que llegue un mensaje.  
  
- <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%29>: es idéntico al método anterior, excepto por el hecho de que se invoca cuando no hay ningún argumento de mensaje.  
  
- <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%28System.ServiceModel.InstanceContext%2CSystem.Object%29>: cuando ha transcurrido la duración de una instancia de servicio, el distribuidor llama al método <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%28System.ServiceModel.InstanceContext%2CSystem.Object%29>. Tal y como ocurre en el método <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29>, la frecuencia de las llamadas a este método está determinada por la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>.  
  
## <a name="the-object-pool"></a>Agrupación de objetos  
 Una implementación <xref:System.ServiceModel.Dispatcher.IInstanceProvider> personalizada proporciona la semántica de la agrupación de objetos necesaria para un servicio. Por consiguiente, este ejemplo tiene un tipo `ObjectPoolingInstanceProvider` que proporciona implementación personalizada de <xref:System.ServiceModel.Dispatcher.IInstanceProvider> para la agrupación. Cuando `Dispatcher` llama al método <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%28System.ServiceModel.InstanceContext%2CSystem.ServiceModel.Channels.Message%29>, en lugar de crear una nueva instancia, la implementación personalizada busca un objeto existente en un grupo en memoria. Si hay uno disponible, se devuelve. De lo contrario, se crea un nuevo objeto. Se muestra la implementación para `GetInstance` en el código de ejemplo siguiente.  
  
```csharp  
object IInstanceProvider.GetInstance(InstanceContext instanceContext, Message message)  
{  
    object obj = null;  
  
    lock (poolLock)  
    {  
        if (pool.Count > 0)  
        {  
            obj = pool.Pop();  
        }  
        else  
        {  
            obj = CreateNewPoolObject();  
        }  
        activeObjectsCount++;  
    }  
  
    WritePoolMessage(ResourceHelper.GetString("MsgNewObject"));  
  
    idleTimer.Stop();  
  
    return obj;
}  
```  
  
 La implementación `ReleaseInstance` personalizada agrega la instancia liberada de nuevo al grupo y disminuye el valor de `ActiveObjectsCount`. `Dispatcher` puede llamar a estos métodos desde subprocesos diferentes, por lo que se necesita tener acceso sincronizado a los miembros del nivel de clase en la clase `ObjectPoolingInstanceProvider`.  
  
```csharp  
void IInstanceProvider.ReleaseInstance(InstanceContext instanceContext, object instance)  
{  
    lock (poolLock)  
    {  
        pool.Push(instance);  
        activeObjectsCount--;  
  
        WritePoolMessage(  
        ResourceHelper.GetString("MsgObjectPooled"));  
  
        // When the service goes completely idle (no requests
        // are being processed), the idle timer is started  
        if (activeObjectsCount == 0)  
            idleTimer.Start();
    }  
}  
```  
  
 El `ReleaseInstance` método proporciona una característica de "limpieza de inicialización". Normalmente el grupo mantiene un número mínimo de objetos para la duración del grupo. Sin embargo, puede haber períodos de uso excesivo que requieren la creación de objetos adicionales en el grupo para alcanzar el límite máximo especificado en la configuración. Finalmente, cuando el grupo se vuelve menos activo, esos objetos adicionales pueden suponer una sobrecarga adicional. Por consiguiente, cuando `activeObjectsCount` llega a cero, se inicia un temporizador inactivo que activa y realiza un ciclo de limpieza.  
  
## <a name="adding-the-behavior"></a>Adición del comportamiento  
 Las extensiones de nivel de distribuidor se enlazan utilizando los comportamientos siguientes:  
  
- Comportamientos de servicio. Permiten la personalización de todo el tiempo de ejecución del servicio.  
  
- Comportamientos del extremo. Permiten la personalización de los puntos de conexión del servicio, específicamente un distribuidor de canales y de puntos de conexión.  
  
- Comportamientos de contrato. Éstos permiten la personalización de las clases <xref:System.ServiceModel.Dispatcher.ClientRuntime> y <xref:System.ServiceModel.Dispatcher.DispatchRuntime> en el cliente y el servicio respectivamente.  
  
 Se debe crear un comportamiento de servicio para una extensión de agrupación de objetos. Los comportamientos de servicio se crean implementando la interfaz <xref:System.ServiceModel.Description.IServiceBehavior>. Hay varias maneras de hacer que el modelo de servicio sea consciente de los comportamientos personalizados:  
  
- Utilizar un atributo personalizado.  
  
- Agregarlo de manera imperativa a la colección de comportamientos de la descripción del servicio.  
  
- Extender el archivo de configuración.  
  
 Este ejemplo utiliza un atributo personalizado. Cuando se construye <xref:System.ServiceModel.ServiceHost>, examina los atributos utilizados en la definición de tipo del servicio y agrega los comportamientos disponibles a la colección de comportamientos de la descripción del servicio.  
  
 La interfaz <xref:System.ServiceModel.Description.IServiceBehavior> tiene tres métodos: <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A>, <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A> y <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A>. Se usa el método <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A> para garantizar que se pueda aplicar el comportamiento al servicio. En este ejemplo, la implementación asegura que el servicio no se ha configurado con <xref:System.ServiceModel.InstanceContextMode.Single>. Se usa el método <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A> para configurar los enlaces del servicio. No es necesario en este escenario. <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A> se utiliza para configurar los distribuidores del servicio. WCF llama a este <xref:System.ServiceModel.ServiceHost> método cuando se inicializa. Los parámetros siguientes se pasan a este método:  
  
- `Description`: este argumento proporciona la descripción del servicio para el servicio completo. Esto se puede utilizar para inspeccionar los datos de la descripción sobre los extremos, contratos, enlaces y otros datos del servicio.  
  
- `ServiceHostBase`: este argumento proporciona <xref:System.ServiceModel.ServiceHostBase> que se inicializa en este momento.  
  
 En la implementación personalizada <xref:System.ServiceModel.Description.IServiceBehavior>, se crea una nueva instancia de `ObjectPoolingInstanceProvider` y se asigna a la propiedad <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> en cada <xref:System.ServiceModel.Dispatcher.DispatchRuntime> en ServiceHostBase.  
  
```csharp  
void IServiceBehavior.ApplyDispatchBehavior(ServiceDescription description, ServiceHostBase serviceHostBase)  
{  
    // Create an instance of the ObjectPoolInstanceProvider.  
    ObjectPoolingInstanceProvider instanceProvider = new  
           ObjectPoolingInstanceProvider(description.ServiceType,
                                                    minPoolSize);  
  
    // Forward the call if we created a ServiceThrottlingBehavior.  
    if (this.throttlingBehavior != null)  
    {  
        ((IServiceBehavior)this.throttlingBehavior).ApplyDispatchBehavior(description, serviceHostBase);  
    }  
  
    // In case there was already a ServiceThrottlingBehavior
    // (this.throttlingBehavior==null), it should have initialized
    // a single ServiceThrottle on all ChannelDispatchers.
    // As we loop through the ChannelDispatchers, we verify that
    // and modify the ServiceThrottle to guard MaxPoolSize.  
    ServiceThrottle throttle = null;  
  
    foreach (ChannelDispatcherBase cdb in
            serviceHostBase.ChannelDispatchers)  
    {  
        ChannelDispatcher cd = cdb as ChannelDispatcher;  
        if (cd != null)  
        {  
            // Make sure there is exactly one throttle used by all
            // endpoints. If there were others, we could not enforce
            // MaxPoolSize.  
            if ((this.throttlingBehavior == null) &&
                        (this.maxPoolSize != Int32.MaxValue))  
            {  
                throttle ??= cd.ServiceThrottle;
                if (cd.ServiceThrottle == null)  
                {  
                    throw new
InvalidOperationException(ResourceHelper.GetString("ExNullThrottle"));  
                }  
                if (throttle != cd.ServiceThrottle)  
                {  
                    throw new InvalidOperationException(ResourceHelper.GetString("ExDifferentThrottle"));  
                }  
             }  
  
             foreach (EndpointDispatcher ed in cd.Endpoints)  
             {  
                 // Assign it to DispatchBehavior in each endpoint.  
                 ed.DispatchRuntime.InstanceProvider =
                                      instanceProvider;  
             }  
         }  
     }  
  
     // Set the MaxConcurrentInstances to limit the number of items
     // that will ever be requested from the pool.  
     if ((throttle != null) && (throttle.MaxConcurrentInstances >
                                      this.maxPoolSize))  
     {  
         throttle.MaxConcurrentInstances = this.maxPoolSize;  
     }  
}  
```  
  
 Además de una implementación <xref:System.ServiceModel.Description.IServiceBehavior>, la clase <xref:System.EnterpriseServices.ObjectPoolingAttribute> cuenta con varios miembros para personalizar el grupo de objetos mediante los argumentos de atributo. Estos miembros incluyen <xref:System.EnterpriseServices.ObjectPoolingAttribute.MaxPoolSize%2A>, <xref:System.EnterpriseServices.ObjectPoolingAttribute.MinPoolSize%2A> y <xref:System.EnterpriseServices.ObjectPoolingAttribute.CreationTimeout%2A>, para que coincida con el conjunto de características de objetos proporcionado por .NET Enterprise Services.  
  
 El comportamiento de agrupación de objetos ahora se puede agregar a un `ObjectPooling` servicio WCF anotando la implementación del servicio con el atributo personalizado recién creado.  
  
```csharp  
[ObjectPooling(MaxPoolSize=1024, MinPoolSize=10, CreationTimeout=30000)]
public class PoolService : IPoolService  
{  
  // …  
}  
```  
  
## <a name="running-the-sample"></a>Ejecutar el ejemplo  
 El ejemplo muestra la mejora en el rendimiento que puede obtenerse usando la agrupación de objetos en algunos escenarios.  
  
 La aplicación de servicio implementa dos servicios: `WorkService` y `ObjectPooledWorkService`. Ambos servicios comparten la misma implementación: requieren una inicialización cara y después exponen un método `DoWork()` que es relativamente barato. La única diferencia es que `ObjectPooledWorkService` tiene la agrupación de objetos configurada:  
  
```csharp  
[ObjectPooling(MinPoolSize = 0, MaxPoolSize = 5)]  
public class ObjectPooledWorkService : IDoWork  
{  
    public ObjectPooledWorkService()  
    {  
        Thread.Sleep(5000);  
        ColorConsole.WriteLine(ConsoleColor.Blue, "ObjectPooledWorkService instance created.");  
    }  
  
    public void DoWork()  
    {  
        ColorConsole.WriteLine(ConsoleColor.Blue, "ObjectPooledWorkService.GetData() completed.");  
    }
}  
```  
  
 Al ejecutar el cliente, sincroniza llamando a `WorkService` cinco veces. Después, sincroniza llamando a `ObjectPooledWorkService` cinco veces. A continuación, se muestra la diferencia en cuanto a tiempo:  
  
```console
Press <ENTER> to start the client.  
  
Calling WorkService:  
1 - DoWork() Done  
2 - DoWork() Done  
3 - DoWork() Done  
4 - DoWork() Done  
5 - DoWork() Done  
Calling WorkService took: 26722 ms.  
Calling ObjectPooledWorkService:  
1 - DoWork() Done  
2 - DoWork() Done  
3 - DoWork() Done  
4 - DoWork() Done  
5 - DoWork() Done  
Calling ObjectPooledWorkService took: 5323 ms.  
Press <ENTER> to exit.  
```  
  
> [!NOTE]
> La primera vez que el cliente se ejecuta, parece que ambos servicios tardan la misma cantidad de tiempo. Si vuelve a ejecutar el ejemplo, puede ver que `ObjectPooledWorkService` devuelve mucho más rápido porque ya existe una instancia de ese objeto en el grupo.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado el procedimiento de instalación única [para los ejemplos](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)de Windows Communication Foundation .  
  
2. Para compilar la solución, siga las instrucciones de Creación de [ejemplos](../../../../docs/framework/wcf/samples/building-the-samples.md)de Windows Communication Foundation .  
  
3. Para ejecutar el ejemplo en una configuración de uno o entre equipos, siga las instrucciones de Ejecución de [los ejemplos](../../../../docs/framework/wcf/samples/running-the-samples.md)de Windows Communication Foundation .  
  
> [!NOTE]
> Si usa Svcutil.exe para regenerar la configuración de este ejemplo, asegúrese de que modifica el nombre del extremo en la configuración del cliente para que coincida con el código de cliente.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Pooling`  
