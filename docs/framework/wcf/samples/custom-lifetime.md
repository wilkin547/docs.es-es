---
description: 'Más información acerca de: vigencia personalizada'
title: Vigencia personalizada
ms.date: 08/20/2018
ms.assetid: 52806c07-b91c-48fe-b992-88a41924f51f
ms.openlocfilehash: 24845aaa20e60f92e2add568c81ab3d6502ebedf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99732480"
---
# <a name="custom-lifetime"></a>Vigencia personalizada

Este ejemplo muestra cómo escribir una extensión de Windows Communication Foundation (WCF) para proporcionar servicios de duración personalizados para las instancias de servicio WCF compartidas.

> [!NOTE]
> El procedimiento de configuración y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.

## <a name="shared-instancing"></a>Instancias compartidas

WCF ofrece varios modos de creación de instancias para las instancias de servicio. El modo de creación de instancias compartido que se trata en este artículo proporciona una manera de compartir una instancia de servicio entre varios canales. Los clientes pueden ponerse en contacto con un Factory Method del servicio y crear un nuevo canal para iniciar la comunicación. En el fragmento de código siguiente se muestra cómo una aplicación cliente crea un canal nuevo en una instancia de servicio existente:

```csharp
// Create a header for the shared instance id
MessageHeader shareableInstanceContextHeader = MessageHeader.CreateHeader(
        CustomHeader.HeaderName,
        CustomHeader.HeaderNamespace,
        Guid.NewGuid().ToString());

// Create the channel factory
ChannelFactory<IEchoService> channelFactory =
    new ChannelFactory<IEchoService>("echoservice");

// Create the first channel
IEchoService proxy = channelFactory.CreateChannel();

// Call an operation to create shared service instance
using (new OperationContextScope((IClientChannel)proxy))
{
    OperationContext.Current.OutgoingMessageHeaders.Add(shareableInstanceContextHeader);
    Console.WriteLine("Service returned: " + proxy.Echo("Apple"));
}

((IChannel)proxy).Close();

// Create the second channel
IEchoService proxy2 = channelFactory.CreateChannel();

// Call an operation using the same header that will reuse the shared service instance
using (new OperationContextScope((IClientChannel)proxy2))
{
    OperationContext.Current.OutgoingMessageHeaders.Add(shareableInstanceContextHeader);
    Console.WriteLine("Service returned: " + proxy2.Echo("Apple"));
}
```

A diferencia de los demás modos de creación de instancias, el modo de creación de instancias compartido tiene una sola manera de liberar las instancias de servicio. De forma predeterminada, cuando todos los canales están cerrados para un <xref:System.ServiceModel.InstanceContext> , el tiempo de ejecución del servicio WCF comprueba si el servicio <xref:System.ServiceModel.InstanceContextMode> está configurado para <xref:System.ServiceModel.InstanceContextMode.PerCall> o <xref:System.ServiceModel.InstanceContextMode.PerSession> , y si es así, libera la instancia y notifica los recursos. Si <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> se utiliza un personalizado, WCF invoca el <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> método de la implementación del proveedor antes de liberar la instancia. Si <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> devuelve `true` , se libera la instancia de; en caso contrario, la <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementación es responsable de notificar el `Dispatcher` del estado de inactividad mediante un método de devolución de llamada. Esto se hace llamando al <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> método del proveedor.

Este ejemplo muestra cómo se puede retrasar la liberación del <xref:System.ServiceModel.InstanceContext> con un tiempo de espera de inactividad de 20 segundos.

## <a name="extending-the-instancecontext"></a>Ampliar InstanceContext

En WCF, <xref:System.ServiceModel.InstanceContext> es el vínculo entre la instancia de servicio y el `Dispatcher` . WCF le permite ampliar este componente en tiempo de ejecución agregando nuevo estado o comportamiento mediante su patrón de objeto extensible. El patrón de objeto extensible se utiliza en WCF para ampliar las clases en tiempo de ejecución existentes con nueva funcionalidad o agregar nuevas características de estado a un objeto. Hay tres interfaces en el patrón de objeto extensible: <xref:System.ServiceModel.IExtensibleObject%601>, <xref:System.ServiceModel.IExtension%601>y <xref:System.ServiceModel.IExtensionCollection%601>.

La <xref:System.ServiceModel.IExtensibleObject%601> interfaz se implementa mediante objetos para permitir extensiones que personalizan su funcionalidad.

La interfaz <xref:System.ServiceModel.IExtension%601> se implementa mediante objetos que pueden ser extensiones de clases de tipo `T`.

Y, por último, la <xref:System.ServiceModel.IExtensionCollection%601> interfaz es una colección de <xref:System.ServiceModel.IExtension%601> implementaciones que permite recuperar una implementación de <xref:System.ServiceModel.IExtension%601> por su tipo.

Por lo tanto, para extender el <xref:System.ServiceModel.InstanceContext> , debe implementar la <xref:System.ServiceModel.IExtension%601> interfaz. En este proyecto de ejemplo, la `CustomLeaseExtension` clase contiene esta implementación.

```csharp
class CustomLeaseExtension : IExtension<InstanceContext>
{
}
```

La interfaz <xref:System.ServiceModel.IExtension%601> tiene dos métodos: <xref:System.ServiceModel.IExtension%601.Attach%2A> y <xref:System.ServiceModel.IExtension%601.Detach%2A>. Como sus nombres indican, se llama a estos dos métodos cuando el tiempo de ejecución asocia y desasocia la extensión a una instancia de la clase <xref:System.ServiceModel.InstanceContext>. En este ejemplo, el método `Attach` se usa para realizar un seguimiento del objeto <xref:System.ServiceModel.InstanceContext> que pertenece a la instancia actual de la extensión.

```csharp
InstanceContext owner;

public void Attach(InstanceContext owner)
{
    this.owner = owner;
}
```

Además, debe agregar la implementación necesaria a la extensión para proporcionar compatibilidad con la duración extendida. Por consiguiente, la `ICustomLease` interfaz se declara con los métodos deseados y se implementa en la `CustomLeaseExtension` clase.

```csharp
interface ICustomLease
{
    bool IsIdle { get; }
    InstanceContextIdleCallback Callback { get; set; }
}

class CustomLeaseExtension : IExtension<InstanceContext>, ICustomLease
{
}
```

Cuando WCF invoca el <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> método en la <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementación, esta llamada se enruta al <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> método de `CustomLeaseExtension` . A continuación, `CustomLeaseExtension` comprueba su estado privado para ver si <xref:System.ServiceModel.InstanceContext> está inactivo. Si está inactivo, devuelve `true` . De lo contrario, inicia un temporizador con la duración extendida especificada.

```csharp
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

En el evento del temporizador `Elapsed` , se llama a la función de devolución de llamada en el distribuidor para iniciar otro ciclo de limpieza.

```csharp
void idleTimer_Elapsed(object sender, ElapsedEventArgs args)
{
    lock (thisLock)
    {
        StopTimer();
        isIdle = true;
        Utility.WriteMessageToConsole(
            ResourceHelper.GetString("MsgLeaseExpired"));
        callback(owner);
    }
}
```

No hay ninguna manera de renovar el temporizador en ejecución cuando llega un mensaje nuevo para que la instancia se mueva al estado inactivo.

En el ejemplo se implementa <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> para interceptar las llamadas al método <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> y enrutarlas a `CustomLeaseExtension`. La implementación de <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> está contenida en la clase `CustomLifetimeLease`. El <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> método se invoca cuando WCF está a punto de liberar la instancia de servicio. Sin embargo, solo hay una instancia de una implementación de `ISharedSessionInstance` determinada en la colección de propiedades <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> de ServiceBehavior. Esto significa que no hay ninguna manera de saber si el <xref:System.ServiceModel.InstanceContext> está cerrado en el momento en que WCF comprueba el <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> método. Por consiguiente, este ejemplo usa el bloqueo de subprocesos para serializar las solicitudes al <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> método.

> [!IMPORTANT]
> El uso del bloqueo de subprocesos no es una solución recomendada porque la serialización puede afectar de forma grave al rendimiento de la aplicación.

Se usa un campo de miembro privado en la `CustomLifetimeLease` clase para realizar un seguimiento del estado de inactividad y lo devuelve el <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> método. Cada vez que <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> se llama al método, `isIdle` se devuelve el campo y se restablece en `false` .  Es esencial establecer este valor en `false` para asegurarse de que el Distribuidor llama al método <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A>.

```csharp
public bool IsIdle(InstanceContext instanceContext)
{
    get
    {
        lock (thisLock)
        {
            //...
            bool idleCopy = isIdle;
            isIdle = false;
            return idleCopy;
        }
    }
}
```

Si el <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType> método devuelve `false` , el distribuidor registra una función de devolución de llamada mediante el <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> método. Este método recibe una referencia al <xref:System.ServiceModel.InstanceContext> que se va a liberar. Por lo tanto, el código de ejemplo puede consultar la `ICustomLease` extensión de tipo y comprobar la `ICustomLease.IsIdle` propiedad en el estado extendido.

```csharp
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

Antes de que `ICustomLease.IsIdle` se Compruebe la propiedad, debe establecerse la propiedad de devolución de llamada, ya que es esencial para `CustomLeaseExtension` que notifique al distribuidor cuando se vuelve inactiva. Si `ICustomLease.IsIdle` devuelve `true`, el miembro privado `isIdle` simplemente se establece en `CustomLifetimeLease` como `true` y llama al método de devolución de llamada. Dado que el código contiene un bloqueo, otros subprocesos no pueden cambiar el valor de este miembro privado. Y la próxima vez que el distribuidor llama a <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A?displayProperty=nameWithType> , devuelve `true` y permite que el distribuidor libere la instancia.

Ahora que el fundamento de la extensión personalizada está completado, tiene que enlazarse con el modelo de servicio. Para enlazar la `CustomLeaseExtension` implementación a <xref:System.ServiceModel.InstanceContext> , WCF proporciona la <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> interfaz para realizar el arranque de <xref:System.ServiceModel.InstanceContext> . En el ejemplo, la clase `CustomLeaseInitializer` implementa esta interfaz y agrega una instancia de `CustomLeaseExtension` a la colección de la propiedad <xref:System.ServiceModel.InstanceContext.Extensions%2A> desde la única inicialización del método. El Distribuidor llama a este método inicializando la instancia de <xref:System.ServiceModel.InstanceContext>.

```csharp
public void InitializeInstanceContext(InstanceContext instanceContext,
    System.ServiceModel.Channels.Message message, IContextChannel channel)

    //...

    IExtension<InstanceContext> customLeaseExtension =
        new CustomLeaseExtension(timeout, headerId);
    instanceContext.Extensions.Add(customLeaseExtension);
}
```

 Por último, la <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementación se enlaza al modelo de servicio mediante la <xref:System.ServiceModel.Description.IServiceBehavior> implementación de. Esta implementación se coloca en la clase `CustomLeaseTimeAttribute` y también deriva de la clase base <xref:System.Attribute> para exponer este comportamiento como un atributo.

```csharp
public void ApplyDispatchBehavior(ServiceDescription description,
           ServiceHostBase serviceHostBase)
{
    CustomLifetimeLease customLease = new CustomLifetimeLease(timeout);

    foreach (ChannelDispatcherBase cdb in serviceHostBase.ChannelDispatchers)
    {
        ChannelDispatcher cd = cdb as ChannelDispatcher;

        if (cd != null)
        {
            foreach (EndpointDispatcher ed in cd.Endpoints)
            {
                ed.DispatchRuntime.InstanceContextProvider = customLease;
            }
        }
    }
}
```

Este comportamiento se puede agregar a una clase de servicio de ejemplo agregándolo con el atributo `CustomLeaseTime`.

```csharp
[CustomLeaseTime(Timeout = 20000)]
public class EchoService : IEchoService
{
  //…
}
```

Al ejecutar el ejemplo, las solicitudes y las respuestas de operación se muestran tanto en la ventanas de la consola del cliente como del servicio. Presione Entrar en cada ventana de la consola para cerrar el servicio y el cliente.

### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo

1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).

2. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).

3. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Lifetime`
