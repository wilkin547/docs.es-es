---
description: 'Más información sobre: reentrante de ConcurrencyMode'
title: ConcurrencyMode reentrante
ms.date: 03/30/2017
ms.assetid: b2046c38-53d8-4a6c-a084-d6c7091d92b1
ms.openlocfilehash: f423722d87a8ab9567e0631afbb6bff68fd22b7a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99778521"
---
# <a name="concurrencymode-reentrant"></a><span data-ttu-id="ca150-103">ConcurrencyMode reentrante</span><span class="sxs-lookup"><span data-stu-id="ca150-103">ConcurrencyMode Reentrant</span></span>

<span data-ttu-id="ca150-104">Este ejemplo muestra la necesidad y las implicaciones de utilizar ConcurrencyMode.Reentrant en una implementación del servicio.</span><span class="sxs-lookup"><span data-stu-id="ca150-104">This sample demonstrates the necessity and implications of using ConcurrencyMode.Reentrant on a service implementation.</span></span> <span data-ttu-id="ca150-105">ConcurrencyMode.Reentrant implica que el servicio (o la devolución de llamada) procesa solo uno mensaje en una hora determinada (análogo a `ConcurencyMode.Single`).</span><span class="sxs-lookup"><span data-stu-id="ca150-105">ConcurrencyMode.Reentrant implies that the service (or callback) processes only one message at a given time (analogous to `ConcurencyMode.Single`).</span></span> <span data-ttu-id="ca150-106">Para garantizar la seguridad para subprocesos, Windows Communication Foundation (WCF) bloquea el `InstanceContext` procesamiento de un mensaje de modo que no se pueda procesar ningún otro mensaje.</span><span class="sxs-lookup"><span data-stu-id="ca150-106">To ensure thread safety, Windows Communication Foundation (WCF) locks the `InstanceContext` processing a message so that no other messages can be processed.</span></span> <span data-ttu-id="ca150-107">En el caso del modo reentrante, `InstanceContext` se desbloquea justo antes de que el servicio haga una llamada de salida por la que permite la llamada subsiguiente, (que puede ser reentrante como se muestra en el ejemplo) para obtener el bloqueo la próxima vez que entre al servicio.</span><span class="sxs-lookup"><span data-stu-id="ca150-107">In case of Reentrant mode, the `InstanceContext` is unlocked just before the service makes an outgoing call thereby allowing the subsequent call, (which can be reentrant as demonstrated in the sample) to get the lock next time it comes in to the service.</span></span> <span data-ttu-id="ca150-108">Para mostrar el comportamiento, el ejemplo muestra cómo un cliente y el servicio pueden enviar los mensajes entre sí utilizando un contrato dúplex.</span><span class="sxs-lookup"><span data-stu-id="ca150-108">To demonstrate the behavior, the sample shows how a client and service can send messages between each other using a duplex contract.</span></span>  
  
 <span data-ttu-id="ca150-109">El contrato definido es un contrato dúplex con el método `Ping` siendo implementado por el servicio y el método de devolución de llamada`Pong`siendo implementado por el cliente.</span><span class="sxs-lookup"><span data-stu-id="ca150-109">The contract defined is a duplex contract with the `Ping` method being implemented by the service and the callback method `Pong` being implemented by the client.</span></span> <span data-ttu-id="ca150-110">Un cliente invoca el método del servidor `Ping` con un recuento del paso que inicia así la llamada.</span><span class="sxs-lookup"><span data-stu-id="ca150-110">A client invokes the server's `Ping` method with a tick count thereby initiating the call.</span></span> <span data-ttu-id="ca150-111">El servicio comprueba si el recuento del paso no es igual a 0 y a continuación, invoca las devoluciones de llamada el método `Pong` disminuyendo el recuento del paso.</span><span class="sxs-lookup"><span data-stu-id="ca150-111">The service checks whether the tick count is not equal to 0 and then invokes the callbacks `Pong` method while decrementing the tick count.</span></span> <span data-ttu-id="ca150-112">El código siguiente realiza esta operación en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ca150-112">This is done by the following code in the sample.</span></span>  
  
```csharp
public void Ping(int ticks)  
{  
     Console.WriteLine("Ping: Ticks = " + ticks);  
     //Keep pinging back and forth till Ticks reaches 0.  
     if (ticks != 0)  
     {  
         OperationContext.Current.GetCallbackChannel<IPingPongCallback>().Pong((ticks - 1));  
     }  
}  
```  
  
 La implementación `Pong` de la devolución de llamada tiene la misma lógica que la implementación `Ping`. Es decir, comprueba si el contador no es cero y, a continuación, invoca el método `Ping` en el canal de devolución de llamada (en este caso, es el canal que fue utilizado para enviar el mensaje `Ping` original) con el contador disminuido en 1. El momento en que el contador llegue a 0, el método vuelve y desempaqueta de nuevo todas las respuestas a la primera llamada realizada por el cliente que inició la llamada. <span data-ttu-id="ca150-116">Esto se muestra en la implementación de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="ca150-116">This is shown in the callback implementation.</span></span>  
  
```csharp
public void Pong(int ticks)  
{  
    Console.WriteLine("Pong: Ticks = " + ticks);  
    if (ticks != 0)  
    {  
        //Retrieve the Callback  Channel (in this case the Channel which was used to send the  
        //original message) and make an outgoing call until ticks reaches 0.  
        IPingPong channel = OperationContext.Current.GetCallbackChannel<IPingPong>();  
        channel.Ping((ticks - 1));  
    }  
}  
```  
  
 `Ping` y los métodos `Pong` son solicitud/respuesta, lo cual significa que la primera llamada a `Ping` no vuelve hasta que la llamada `CallbackChannel<T>.Pong()`se devuelve. En el cliente, el método `Pong` no puede devolverse hasta que la siguiente llamada `Ping` que se realizó se devuelva. <span data-ttu-id="ca150-119">Dado que la devolución de llamada y el servicio deben realizar llamadas de salida de solicitud/respuesta antes de poder responder a la solicitud pendiente, las implementaciones se deben marcar con el comportamiento de ConcurrencyMode.Reentrant.</span><span class="sxs-lookup"><span data-stu-id="ca150-119">Because both the callback and the service must make outgoing request/reply calls before they can reply for the pending request, both the implementations must be marked with the ConcurrencyMode.Reentrant behavior.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ca150-120">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="ca150-120">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="ca150-121">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ca150-121">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="ca150-122">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ca150-122">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="ca150-123">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ca150-123">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="ca150-124">Muestra</span><span class="sxs-lookup"><span data-stu-id="ca150-124">Demonstrates</span></span>  

 <span data-ttu-id="ca150-125">Para ejecutar el ejemplo, compile los proyectos de servidor y cliente.</span><span class="sxs-lookup"><span data-stu-id="ca150-125">To run the sample, build the client and server projects.</span></span> <span data-ttu-id="ca150-126">A continuación, abra dos ventanas de comandos y cambie los directorios a los \<sample> directorios \CS\Service\bin\debug y \<sample> \CS\Client\bin\debug.</span><span class="sxs-lookup"><span data-stu-id="ca150-126">Then open two command windows and change the directories to the \<sample>\CS\Service\bin\debug and \<sample>\CS\Client\bin\debug directories.</span></span> <span data-ttu-id="ca150-127">A continuación, inicie el servicio escribiendo `service.exe` y, a continuación, invoque el Client.exe con el valor inicial de los tics pasados como argumento de entrada.</span><span class="sxs-lookup"><span data-stu-id="ca150-127">Then start the service by typing `service.exe` and then invoke the Client.exe with the initial value of ticks passed as an input argument.</span></span> <span data-ttu-id="ca150-128">Se muestra un resultado del ejemplo para 10 pasos.</span><span class="sxs-lookup"><span data-stu-id="ca150-128">A sample output for 10 ticks is shown.</span></span>  
  
```console  
Prompt>Service.exe  
ServiceHost Started. Press Enter to terminate service.  
Ping: Ticks = 10  
Ping: Ticks = 8  
Ping: Ticks = 6  
Ping: Ticks = 4  
Ping: Ticks = 2  
Ping: Ticks = 0  
  
Prompt>Client.exe 10  
Pong: Ticks = 9  
Pong: Ticks = 7  
Pong: Ticks = 5  
Pong: Ticks = 3  
Pong: Ticks = 1  
```  
  
> [!IMPORTANT]
> <span data-ttu-id="ca150-129">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="ca150-129">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ca150-130">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="ca150-130">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="ca150-131">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="ca150-131">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ca150-132">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="ca150-132">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Reentrant`  
