---
title: "Vigencia personalizada | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 52806c07-b91c-48fe-b992-88a41924f51f
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Vigencia personalizada
En este ejemplo se muestra cómo escribir una extensión de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] para proporcionar servicios de duración personalizados para las instancias de servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] compartidas.  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
## Creación de instancias compartidas  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona varios modos de creación de instancias para las instancias de servicio.El modo Creación de instancias compartidas que se explica en este tema proporciona una manera de compartir una instancia de servicio entre varios canales.Los clientes pueden resolver la dirección del extremo de la instancia de forma local o usar un método generador en el servicio para obtener la dirección del extremo de una instancia en ejecución.Cuando tenga la dirección del extremo, puede crear un nuevo canal e iniciar la comunicación.El siguiente fragmento de código muestra el modo en que una aplicación cliente crea un canal nuevo para una instancia de servicio existente.  
  
```  
// Create the first channel.  
IEchoService proxy = channelFactory.CreateChannel();  
  
// Resolve the instance.  
EndpointAddress epa = ((IClientChannel)proxy).ResolveInstance();  
  
// Create new channel factory with the endpoint address resolved by   
// previous statement.  
ChannelFactory<IEchoService> channelFactory2 =  
                new ChannelFactory<IEchoService>("echoservice",  
                epa);  
  
// Create the second channel to the same instance.  
IEchoService proxy2 = channelFactory2.CreateChannel();  
  
```  
  
 A diferencia de los demás modos de creación de instancias, el modo de creación de instancias compartido tiene una sola manera de liberar las instancias de servicio.Cuando todos los canales se cierran para una instancia, el tiempo de ejecución de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] del servicio inicia un temporizador.Si nadie realiza una conexión antes de que el tiempo de espera expire, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] libera la instancia y reclama los recursos.Como parte del procedimiento de destrucción, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] invoca el método <xref:System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime.IsIdle%2A> de todas las implementaciones de <xref:System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime> antes de liberar la instancia.Si todas ellas devuelven `true`, la instancia se libera.De lo contrario, la implementación de <xref:System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime> es responsable de notificar al `Dispatcher` el estado de inactividad utilizando un método de devolución de llamada.  
  
 De forma predeterminada, el valor de tiempo de espera de inactividad de <xref:System.ServiceModel.InstanceContext> es de un minuto.Sin embargo, este ejemplo muestra cómo puede ampliarlo utilizando una extensión personalizada.  
  
## Ampliar InstanceContext  
 En [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], <xref:System.ServiceModel.InstanceContext> es el vínculo entre la instancia de servicio y `Dispatcher`.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] le permite extender estoe componente de runtime al agregar un nuevo estado o comportamiento usando su modelo de objeto extensible.El modelo de objeto extensible se utiliza en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para extender las clases de tiempo de ejecución existentes con una nueva funcionalidad o agregar nuevas características del estado a un objeto.Hay tres interfaces en el modelo de objetos extensible: `IExtensibleObject<T>`, `IExtension<T>` y `IExtensionCollection<T>`.  
  
 La interfaz `IExtensibleObject<T>` se implementa mediante objetos para permitir las extensiones que pueden personalizar su funcionalidad.  
  
 La interfaz `IExtension<T>` se implementa mediante objetos que pueden ser extensiones de clases de tipo `T`.  
  
 Y finalmente, la interfaz `IExtensionCollection<T>` es una colección de interfaces `IExtensions` que permite recuperar las interfaces `IExtensions` por su tipo.  
  
 Por consiguiente, para extender el <xref:System.ServiceModel.InstanceContext> debe implementar la interfaz `IExtension`.En este proyecto de ejemplo, la clase `CustomLeaseExtension` contiene esta implementación.  
  
```  
class CustomLeaseExtension : IExtension<InstanceContext>  
{  
}  
  
```  
  
 La interfaz `IExtension` tiene dos métodos: `Attach` y `Detach`.Como sus nombres indican, se llama a estos dos métodos cuando el tiempo de ejecución asocia y desasocia la extensión a una instancia de la clase <xref:System.ServiceModel.InstanceContext>.En este ejemplo, el método `Attach` se usa para realizar un seguimiento del objeto <xref:System.ServiceModel.InstanceContext> que pertenece a la instancia actual de la extensión.  
  
```  
InstanceContext owner;  
  
public void Attach(InstanceContext owner)  
{  
  this.owner = owner;   
}  
```  
  
 Además, debe agregar la implementación necesaria a la extensión para proporcionar compatibilidad con la duración extendida.Por consiguiente, la interfaz `ICustomLease` se declara con los métodos deseados y se implementa en la clase `CustomLeaseExtension`.  
  
```  
interface ICustomLease  
{  
    bool IsIdle { get; }          
    InstanceContextIdleCallback Callback { get; set; }  
}  
  
class CustomLeaseExtension : IExtension<InstanceContext>, ICustomLease  
{  
}  
  
```  
  
 Cuando [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] invoca el método <xref:System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime.IsIdle%2A> en la implementación de <xref:System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime>, esta llamada se enruta al método <xref:System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime.IsIdle%2A> de `CustomLeaseExtension`.A continuación, `CustomLeaseExtension` comprueba su estado privado para ver si el <xref:System.ServiceModel.InstanceContext> está inactivo.Si lo está, devuelve `true`.De lo contrario, inicia un temporizador con la duración extendida especificada.  
  
```  
public bool IsIdle  
{  
  get  
  {  
    lock (thisLock)  
    {  
      if (isIdle)  
      {  
        return true;  
      }  
      else  
      {  
        StartTimer();  
        return false;  
      }  
    }  
  }  
}  
  
```  
  
 En el evento `Elapsed` del temporizador, se llama a la función de devolución de llamada en el Distribuidor para iniciar otro ciclo de limpieza.  
  
```  
void idleTimer_Elapsed(object sender, ElapsedEventArgs args)  
{  
    idleTimer.Stop();  
    isIdle = true;    
    callback(owner);  
}  
  
```  
  
 No hay ninguna manera de renovar el temporizador en ejecución cuando llega un mensaje nuevo para la instancia que se va a pasar al estado inactivo.  
  
 En el ejemplo se implementa <xref:System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime> para interceptar las llamadas al método <xref:System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime.IsIdle%2A> y enrutarlas a `CustomLeaseExtension`.La implementación de <xref:System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime> está contenida en la clase `CustomLifetimeLease`.Se invoca al método <xref:System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime.IsIdle%2A> cuando [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] está a punto de liberar la instancia de servicio.Sin embargo, solo hay una instancia de una implementación de `ISharedSessionInstance` determinada en la colección de propiedades <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceContextLifetimes%2A> de ServiceBehavior.Esto significa que no hay ninguna manera de saber que el <xref:System.ServiceModel.InstanceContext> se está cerrando en el momento en que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] comprueba el método <xref:System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime.IsIdle%2A>.Por consiguiente, este ejemplo utiliza el bloqueo de subprocesos para serializar las solicitudes al método <xref:System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime.IsIdle%2A>.  
  
> [!IMPORTANT]
>  El uso del bloqueo de subprocesos no es una solución recomendada porque la serialización puede afectar de forma grave al rendimiento de la aplicación.  
  
 Una variable de miembro privado se utiliza en la clase `CustomLeaseExtension` para realizar el seguimiento del valor `IsIdle`.Cada vez que se recupera el valor de <xref:System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime>, se devuelve el miembro privado `IsIdle` y se restablece en `false`.Es esencial establecer este valor en `false` para asegurarse de que el Distribuidor llama al método <xref:System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime.NotifyIdle%2A>.  
  
```  
public bool IsIdle  
{  
    get   
    {  
       lock (thisLock)  
       {  
           bool idleCopy = isIdle;  
           isIdle = false;  
           return idleCopy;  
       }  
    }  
}  
  
```  
  
 Si la propiedad `ISharedSessionLifetime.IsIdle` devuelve `false`, el Distribuidor registra una función de devolución de llamada utilizando el método `NotifyIdle`.Este método recibe una referencia al <xref:System.ServiceModel.InstanceContext> que se va a liberar.Por consiguiente, el código de muestra puede consultar la extensión de tipo de `ICustomLease` y comprobar la propiedad `ICustomLease.IsIdle` en el estado extendido.  
  
```  
public void NotifyIdle(InstanceContextIdleCallback callback,   
            InstanceContext instanceContext)  
{  
    lock (thisLock)  
    {  
       ICustomLease customLease =  
           instanceContext.Extensions.Find<ICustomLease>();  
       customLease.Callback = callback;   
       isIdle = customLease.IsIdle;  
       if (isIdle)  
       {  
             callback(instanceContext);  
       }  
    }   
}  
  
```  
  
 Antes de que se compruebe la propiedad `ICustomLease.IsIdle`, tiene que establecerse la propiedad Callback porque es esencial para que `CustomLeaseExtension` notifique al Distribuidor cuando pase a estar inactivo.Si `ICustomLease.IsIdle` devuelve `true`, el miembro privado `isIdle` simplemente se establece en `CustomLifetimeLease` como `true` y llama al método de devolución de llamada.Dado que el código contiene un bloqueo, otros subprocesos no pueden cambiar el valor de este miembro privado.Y la siguiente vez que el Distribuidor compruebe la interfaz `ISharedSessionLifetime.IsIdle`, devuelve `true` y permite que el Distribuidor libere la instancia.  
  
 Ahora que el fundamento de la extensión personalizada está completado, tiene que enlazarse con el modelo de servicio.Para enlazar la implementación de `CustomLeaseExtension` en el <xref:System.ServiceModel.InstanceContext>, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona la interfaz de <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> para realizar la secuencia de arranque de <xref:System.ServiceModel.InstanceContext>.En el ejemplo, la clase `CustomLeaseInitializer` implementa esta interfaz y agrega una instancia de `CustomLeaseExtension` a la colección de la propiedad <xref:System.ServiceModel.InstanceContext.Extensions%2A> desde la única inicialización del método.El Distribuidor llama a este método inicializando la instancia de <xref:System.ServiceModel.InstanceContext>.  
  
```  
public void Initialize(InstanceContext instanceContext, Message message)  
{  
  IExtension<InstanceContext> customLeaseExtension =  
    new CustomLeaseExtension(timeout);  
  instanceContext.Extensions.Add(customLeaseExtension);  
}  
```  
  
 Finalmente, las implementaciones de <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> y <xref:System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime> se enlazan con el modelo de servicio utilizando la implementación de <xref:System.ServiceModel.Description.IServiceBehavior>.Esta implementación se coloca en la clase `CustomLeaseTimeAttribute` y también deriva de la clase base `Attribute` para exponer este comportamiento como un atributo.En el método `IServiceBehavior.ApplyBehavior`, las instancias de las implementaciones de <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> y <xref:System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime> se agregan respectivamente a las colecciones de propiedades <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceContextLifetimes%2A> y <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceContextInitializers%2A> del espacio de nombres <xref:System.ServiceModel.Dispatcher>.  
  
```  
public void ApplyBehavior(ServiceDescription description,   
           ServiceHostBase serviceHostBase,   
           Collection<DispatchBehavior> behaviors,  
           Collection<BindingParameterCollection> parameters)  
{  
    CustomLifetimeLease customLease = new CustomLifetimeLease();  
    CustomLeaseInitializer initializer =   
                new CustomLeaseInitializer(timeout);  
  
    foreach (DispatchBehavior dispatchBehavior in behaviors)  
    {  
        dispatchBehavior.InstanceContextLifetimes.Add(customLease);  
        dispatchBehavior.InstanceContextInitializers.Add(initializer);  
    }  
}  
  
```  
  
 Este comportamiento se puede agregar a una clase de servicio de ejemplo agregándolo con el atributo `CustomLeaseTime`.  
  
```  
[ServiceBehavior(InstanceContextMode=InstanceContextMode.Shareable)]  
[CustomLeaseTime(Timeout = 20000)]  
public class EchoService : IEchoService  
{  
  //…  
}  
```  
  
 Al ejecutar el ejemplo, las solicitudes y las respuestas de operación se muestran tanto en la ventanas de la consola del cliente como del servicio.Presione Entrar en cada ventana de la consola para cerrar el servicio y el cliente.  
  
#### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que ha realizado [Procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Para compilar el código C\# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Para ejecutar el ejemplo en una configuración con un único equipo o con varios, siga las instrucciones de [Ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Lifetime`  
  
## Vea también