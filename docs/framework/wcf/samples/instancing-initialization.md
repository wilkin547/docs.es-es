---
title: Creación de instancias de inicialización
ms.date: 03/30/2017
ms.assetid: 154d049f-2140-4696-b494-c7e53f6775ef
ms.openlocfilehash: ee7d470cb80e913707ae6e92039061efde8fcb7f
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715801"
---
# <a name="instancing-initialization"></a>Creación de instancias de inicialización
Este ejemplo extiende el ejemplo de [agrupación](../../../../docs/framework/wcf/samples/pooling.md) definiendo una interfaz, `IObjectControl`, que personaliza la inicialización de un objeto mediante su activación y desactivación. El cliente invoca métodos que devuelven el objeto al grupo y que no devuelven el objeto al grupo.  
  
> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
## <a name="extensibility-points"></a>Puntos de extensibilidad  
 El primer paso para crear una extensión de Windows Communication Foundation (WCF) es decidir el punto de extensibilidad que se va a usar. En WCF, el término *EndpointDispatcher* hace referencia a un componente de tiempo de ejecución responsable de convertir los mensajes entrantes en invocaciones de método en el servicio del usuario y de convertir los valores devueltos de ese método en un mensaje saliente. Un servicio WCF crea un EndpointDispatcher para cada punto de conexión.  
  
 EndpointDispatcher proporciona la extensibilidad (para todos los mensajes recibidos o enviados por el servicio) del ámbito del extremo mediante la clase <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>. Esta clase le permite personalizar varias propiedades que controlan el comportamiento de EndpointDispatcher. Este ejemplo se centra en la propiedad <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> que señala al objeto que proporciona las instancias de la clase de servicio.  
  
## <a name="iinstanceprovider"></a>IInstanceProvider  
 En WCF, EndpointDispatcher crea instancias de una clase de servicio mediante un proveedor de instancias que implementa la interfaz <xref:System.ServiceModel.Dispatcher.IInstanceProvider>. Esta interfaz tiene solo dos métodos:  
  
- <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A>: cuando un mensaje llega, el distribuidor llama al método <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> para crear una instancia de la clase de servicio para procesar el mensaje. La propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> determina la frecuencia de las llamadas a este método. Por ejemplo, si la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> está establecida en <xref:System.ServiceModel.InstanceContextMode.PerCall?displayProperty=nameWithType>, se crea una nueva instancia de la clase de servicio para procesar cada mensaje que llega, por lo que se llamará a <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> siempre que llegue un mensaje.  
  
- <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A>: cuando la instancia del servicio termina de procesar el mensaje, EndpointDispatcher llama al método <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A>. Tal y como ocurre en el método <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A>, la frecuencia de las llamadas a este método está determinada por la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>.  
  
## <a name="the-object-pool"></a>Agrupación de objetos  
 La clase `ObjectPoolInstanceProvider` contiene la implementación para el grupo de objetos. Esta clase implementa la interfaz <xref:System.ServiceModel.Dispatcher.IInstanceProvider> para interactuar con el nivel de modelo de servicio. Cuando EndpointDispatcher llama al método <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A>, en lugar de crear una nueva instancia, la implementación personalizada busca un objeto existente en un grupo en memoria. Si hay uno disponible, se devuelve. De lo contrario, `ObjectPoolInstanceProvider` comprueba si la propiedad `ActiveObjectsCount` (número de objetos devueltos desde el grupo) ha alcanzado el tamaño máximo del grupo. Si no, se crea una nueva instancia y se devuelve al autor de la llamada y, como consecuencia, se incrementa `ActiveObjectsCount`. De lo contrario, se pone en la cola una solicitud de creación de objetos para un período configurado de tiempo. Se muestra la implementación para `GetObjectFromThePool` en el código de ejemplo siguiente.  
  
```csharp
private object GetObjectFromThePool()  
{  
    bool didNotTimeout =   
       availableCount.WaitOne(creationTimeout, true);  
    if(didNotTimeout)  
    {  
         object obj = null;  
         lock (poolLock)  
        {  
             if (pool.Count != 0)  
             {  
                   obj = pool.Pop();  
                   activeObjectsCount++;  
             }  
             else if (pool.Count == 0)  
             {  
                   if (activeObjectsCount < maxPoolSize)  
                   {  
                        obj = CreateNewPoolObject();  
                        activeObjectsCount++;  
  
                        #if (DEBUG)  
                        WritePoolMessage(  
                             ResourceHelper.GetString("MsgNewObject"));  
                       #endif  
                   }                          
            }  
           idleTimer.Stop();  
      }  
     // Call the Activate method if possible.  
    if (obj is IObjectControl)  
   {  
         ((IObjectControl)obj).Activate();  
   }  
   return obj;  
}  
throw new TimeoutException(  
ResourceHelper.GetString("ExObjectCreationTimeout"));  
}  
```  
  
 La implementación `ReleaseInstance` personalizada agrega la instancia liberada de nuevo al grupo y disminuye el valor de `ActiveObjectsCount`. EndpointDispatcher puede llamar a estos métodos desde subprocesos diferentes y, por consiguiente, se necesita tener acceso sincronizado a los miembros de nivel de clase en la clase `ObjectPoolInstanceProvider`.  
  
```csharp
public void ReleaseInstance(InstanceContext instanceContext, object instance)  
{  
    lock (poolLock)  
    {  
        // Check whether the object can be pooled.   
        // Call the Deactivate method if possible.  
        if (instance is IObjectControl)  
        {  
            IObjectControl objectControl = (IObjectControl)instance;  
            objectControl.Deactivate();  
  
            if (objectControl.CanBePooled)  
            {  
                pool.Push(instance);  
  
                #if(DEBUG)  
                WritePoolMessage(  
                    ResourceHelper.GetString("MsgObjectPooled"));  
                #endif                          
            }  
            else  
            {  
                #if(DEBUG)  
                WritePoolMessage(  
                    ResourceHelper.GetString("MsgObjectWasNotPooled"));  
                #endif  
            }  
        }  
        else  
        {  
            pool.Push(instance);  
  
            #if(DEBUG)  
            WritePoolMessage(  
                ResourceHelper.GetString("MsgObjectPooled"));  
            #endif   
        }  
  
        activeObjectsCount--;  
  
        if (activeObjectsCount == 0)  
        {  
            idleTimer.Start();                       
        }  
    }  
  
    availableCount.Release(1);  
}  
```  
  
 El método `ReleaseInstance` proporciona una característica de *inicialización de limpieza* . Normalmente el grupo mantiene un número mínimo de objetos para la duración del grupo. Sin embargo, puede haber períodos de uso excesivo que requieren la creación de objetos adicionales en el grupo para alcanzar el límite máximo especificado en la configuración. Finalmente, cuando el grupo se vuelve menos activo, esos objetos adicionales pueden suponer una sobrecarga adicional. Por consiguiente, cuando `activeObjectsCount` llega a cero, se inicia un temporizador inactivo que activa y realiza un ciclo de limpieza.  
  
```csharp  
if (activeObjectsCount == 0)  
{  
    idleTimer.Start();   
}  
```  
  
 Las extensiones de nivel de ServiceModel se enlazan utilizando los comportamientos siguientes:  
  
- Comportamientos del servicio: permiten la personalización del tiempo de ejecución completo del servicio.  
  
- Comportamientos del punto de conexión: permiten la personalización de un punto de conexión de servicio determinado, incluido EndpointDispatcher.  
  
- Comportamientos del contrato: permiten la personalización de las clases <xref:System.ServiceModel.Dispatcher.ClientRuntime> o <xref:System.ServiceModel.Dispatcher.DispatchRuntime> en el cliente o el servicio respectivamente.  
  
- Comportamientos de la operación: permiten la personalización de las clases <xref:System.ServiceModel.Dispatcher.ClientOperation> o <xref:System.ServiceModel.Dispatcher.DispatchOperation> en el cliente o el servicio respectivamente.  
  
 Con el objetivo de una extensión de agrupación de objetos, se puede crear un comportamiento de punto de conexión o de servicio. En este ejemplo, utilizamos un comportamiento de servicio, que aplica la capacidad de agrupación de objetos a cada punto de conexión del servicio. Los comportamientos de servicio se crean implementando la interfaz <xref:System.ServiceModel.Description.IServiceBehavior>. Hay varias maneras de hacer que ServiceModel sea consciente de los comportamientos personalizados:  
  
- Utilizar un atributo personalizado.  
  
- Agregarlo de manera imperativa a la colección de comportamientos de la descripción del servicio.  
  
- Extender el archivo de configuración.  
  
 Este ejemplo utiliza un atributo personalizado. Cuando se construye <xref:System.ServiceModel.ServiceHost>, examina los atributos utilizados en la definición de tipo del servicio y agrega los comportamientos disponibles a la colección de comportamientos de la descripción del servicio.  
  
 La interfaz <xref:System.ServiceModel.Description.IServiceBehavior> tiene tres métodos: <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A>`,` <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A>`,` y <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A>. WCF llama a estos métodos cuando se inicializa el <xref:System.ServiceModel.ServiceHost>. Primero se llama a <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A?displayProperty=nameWithType>; permite inspeccionar el servicio para ver si hay incoherencias. Después se llama a <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A?displayProperty=nameWithType>; este método solo se necesita en escenarios muy avanzados. En último lugar se llama a <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A?displayProperty=nameWithType>, que es responsable de configurar el tiempo de ejecución. Los parámetros siguientes se pasan a <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A?displayProperty=nameWithType>:  
  
- `Description`: este parámetro proporciona la descripción del servicio para todo el servicio. Esto se puede utilizar para inspeccionar los datos de la descripción sobre los extremos del servicio, los contratos, enlaces y otros datos asociados al servicio.  
  
- `ServiceHostBase`: este parámetro proporciona <xref:System.ServiceModel.ServiceHostBase> que se inicializa actualmente.  
  
 En la implementación <xref:System.ServiceModel.Description.IServiceBehavior> personalizada, se crea una nueva instancia de `ObjectPoolInstanceProvider` y se asigna a la propiedad <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> en cada <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> que está adjuntada a <xref:System.ServiceModel.ServiceHostBase>.  
  
```csharp
public void ApplyDispatchBehavior(ServiceDescription description, ServiceHostBase serviceHostBase)  
{  
    if (enabled)  
    {  
        // Create an instance of the ObjectPoolInstanceProvider.  
        instanceProvider = new ObjectPoolInstanceProvider(description.ServiceType,  
        maxPoolSize, minPoolSize, creationTimeout);  
  
        // Assign our instance provider to Dispatch behavior in each   
        // endpoint.  
        foreach (ChannelDispatcherBase cdb in serviceHostBase.ChannelDispatchers)  
        {  
             ChannelDispatcher cd = cdb as ChannelDispatcher;  
             if (cd != null)  
             {  
                 foreach (EndpointDispatcher ed in cd.Endpoints)  
                 {  
                        ed.DispatchRuntime.InstanceProvider = instanceProvider;  
                 }  
             }  
         }  
     }  
}   
```  
  
 Además de una implementación <xref:System.ServiceModel.Description.IServiceBehavior>, la clase `ObjectPoolingAttribute` cuenta con varios miembros para personalizar el grupo de objetos mediante los argumentos de atributo. Estos miembros incluyen `MaxSize`, `MinSize`, `Enabled` y `CreationTimeout`, para que coincida con el conjunto de características de agrupación de objetos proporcionada por .NET Enterprise Services.  
  
 El comportamiento de la agrupación de objetos se puede Agregar ahora a un servicio WCF mediante la anotación de la implementación del servicio con el atributo de `ObjectPooling` personalizado recién creado.  
  
```csharp  
[ObjectPooling(MaxSize=1024, MinSize=10, CreationTimeout=30000]      
public class PoolService : IPoolService  
{  
  // …  
}  
```  
  
## <a name="hooking-activation-and-deactivation"></a>Activación y desactivación de enlace  
 El objetivo principal de la agrupación de objetos es optimizar los objetos de corta duración con una creación e inicialización relativamente cara. Por consiguiente, puede aumentar considerablemente el rendimiento de una aplicación si se utiliza correctamente. Dado que el objeto se devuelve desde el grupo, al constructor se llama solo una vez. Sin embargo, algunas aplicaciones requieren cierto nivel de control para que puedan inicializar y limpiar los recursos utilizados durante un contexto único. Por ejemplo, un objeto que está siendo utilizado por un conjunto de cálculos puede restablecer los campos privados antes de procesar el cálculo siguiente. Enterprise Services habilitó este tipo de inicialización específica del contexto permitiendo al desarrollador de objetos invalidar los métodos `Activate` y `Deactivate` de la clase base <xref:System.EnterpriseServices.ServicedComponent>.  
  
 El conjunto de objetos llama al método `Activate` justo antes de devolver el objeto. Se llama a `Deactivate` cuando el objeto vuelve al conjunto. La clase base <xref:System.EnterpriseServices.ServicedComponent> también tiene una propiedad `boolean` llamada `CanBePooled`, que se puede utilizar para notificar al grupo si el objeto puede agruparse más adelante.  
  
 Para imitar esta funcionalidad, el ejemplo declara una interfaz pública (`IObjectControl`) que tiene los miembros mencionados anteriormente. Las clases de servicio implementan esta interfaz con objeto de proporcionar inicialización específica de contexto. Se debe modificar la implementación <xref:System.ServiceModel.Dispatcher.IInstanceProvider> para cumplir estos requisitos. Ahora, cada vez que obtenga un objeto llamando al método `GetInstance`, debe comprobar si el objeto implementa `IObjectControl.` si lo hace, debe llamar al método `Activate` adecuadamente.  
  
```csharp  
if (obj is IObjectControl)  
{  
    ((IObjectControl)obj).Activate();  
}  
```  
  
 Al devolver un objeto al grupo, se requiere una comprobación para la propiedad `CanBePooled` antes de volver a agregar el objeto al grupo.  
  
```csharp  
if (instance is IObjectControl)  
{  
    IObjectControl objectControl = (IObjectControl)instance;  
    objectControl.Deactivate();  
    if (objectControl.CanBePooled)  
    {  
       pool.Push(instance);  
    }  
}  
```  
  
 Dado que el programador del servicio puede decidir si se puede agrupar un objeto, el recuento de objetos en el grupo a una hora determinada puede estar por debajo del tamaño mínimo. Por consiguiente, debe comprobar si el recuento de objetos ha caído por debajo del nivel mínimo y realizar la inicialización necesaria en el procedimiento de limpieza.  
  
```csharp  
// Remove the surplus objects.  
if (pool.Count > minPoolSize)  
{  
  // Clean the surplus objects.  
}                      
else if (pool.Count < minPoolSize)  
{  
  // Reinitialize the missing objects.  
  while(pool.Count != minPoolSize)  
  {  
    pool.Push(CreateNewPoolObject());  
  }  
}  
```  
  
 Al ejecutar el ejemplo, las solicitudes y las respuestas de operación se muestran tanto en la ventanas de la consola del cliente como del servicio. Presione ENTRAR en cada ventana de la consola para cerrar el servicio y el cliente.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. Este ejemplo se encuentra en el siguiente directorio.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Initialization`  
