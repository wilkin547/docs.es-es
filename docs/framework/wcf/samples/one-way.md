---
title: Unidireccional
ms.date: 03/30/2017
ms.assetid: 74e3e03d-cd15-4191-a6a5-1efa2dcb9e73
ms.openlocfilehash: 91bdc09e374b3a1c6d407d4bd95428fafaf3ecc1
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74714652"
---
# <a name="one-way"></a><span data-ttu-id="9c957-102">Unidireccional</span><span class="sxs-lookup"><span data-stu-id="9c957-102">One-Way</span></span>
<span data-ttu-id="9c957-103">Este ejemplo muestra un contacto del servicio con operaciones de servicio unidireccionales.</span><span class="sxs-lookup"><span data-stu-id="9c957-103">This sample demonstrates a service contact with one-way service operations.</span></span> <span data-ttu-id="9c957-104">El cliente no espera a que se completen las operaciones de servicio como en el caso de las operaciones de servicio bidireccionales.</span><span class="sxs-lookup"><span data-stu-id="9c957-104">The client does not wait for service operations to complete as is the case with two-way service operations.</span></span> <span data-ttu-id="9c957-105">Este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md) y utiliza el enlace de `wsHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="9c957-105">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) and uses the `wsHttpBinding` binding.</span></span> <span data-ttu-id="9c957-106">El servicio en este ejemplo es una aplicación de consola autohospedada que le permite observar el servicio que recibe y procesa las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="9c957-106">The service in this sample is a self-hosted console application to enable you to observe the service that receives and processes requests.</span></span> <span data-ttu-id="9c957-107">El cliente es también una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="9c957-107">The client is also a console application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9c957-108">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="9c957-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="9c957-109">Para crear un contrato de servicio unidireccional, defina su contrato de servicio, aplique la clase <xref:System.ServiceModel.OperationContractAttribute> a cada operación y establezca <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> en `true`, tal y como se muestra en el código de ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9c957-109">To create a one-way service contract, define your service contract, apply the <xref:System.ServiceModel.OperationContractAttribute> class to each operation, and set <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> to `true` as shown in the following sample code:</span></span>  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IOneWayCalculator  
{  
    [OperationContract(IsOneWay=true)]  
    void Add(double n1, double n2);  
    [OperationContract(IsOneWay = true)]  
    void Subtract(double n1, double n2);  
    [OperationContract(IsOneWay = true)]  
    void Multiply(double n1, double n2);  
    [OperationContract(IsOneWay = true)]  
    void Divide(double n1, double n2);  
}  
```  
  
 <span data-ttu-id="9c957-110">Para mostrar que el cliente no espera a que las operaciones de servicio se completen, el código de servicio en este ejemplo implementa un retraso de cinco segundos, tal y como se muestra en el código de ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9c957-110">To demonstrate that the client does not wait for the service operations to complete, the service code in this sample implements a five-second delay, as shown in the following sample code:</span></span>  
  
```csharp
// This service class implements the service contract.  
// This code writes output to the console window.  
 [ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Multiple,  
    InstanceContextMode = InstanceContextMode.PerCall)]  
public class CalculatorService : IOneWayCalculator  
{  
    public void Add(double n1, double n2)  
    {  
        Console.WriteLine("Received Add({0},{1}) - sleeping", n1, n2);  
        System.Threading.Thread.Sleep(1000 * 5);  
        double result = n1 + n2;  
        Console.WriteLine("Processing Add({0},{1}) - result: {2}", n1, n2, result);  
    }  
    ...  
}  
```  
  
 <span data-ttu-id="9c957-111">Cuando el cliente llama al servicio, la llamada se devuelve sin esperar a que la operación de servicio se complete.</span><span class="sxs-lookup"><span data-stu-id="9c957-111">When the client calls the service, the call returns without waiting for the service operation to complete.</span></span>  
  
 <span data-ttu-id="9c957-112">Al ejecutar el ejemplo, las actividades del servicio y del cliente se muestran en las ventanas de la consola del cliente y del servicio.</span><span class="sxs-lookup"><span data-stu-id="9c957-112">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="9c957-113">Puede ver los mensajes recibidos por el servicio desde el cliente.</span><span class="sxs-lookup"><span data-stu-id="9c957-113">You can see the service receive messages from the client.</span></span> <span data-ttu-id="9c957-114">Presione ENTRAR en cada ventana de la consola para cerrar el servicio y el cliente.</span><span class="sxs-lookup"><span data-stu-id="9c957-114">Press ENTER in each console window to shut down both the service and the client.</span></span>  
  
 <span data-ttu-id="9c957-115">El cliente finaliza delante del servicio, mostrando que un cliente no espera a que las operaciones de servicio unidireccional se completen.</span><span class="sxs-lookup"><span data-stu-id="9c957-115">The client finishes ahead of the service, demonstrating that a client does not wait for one-way service operations to complete.</span></span> <span data-ttu-id="9c957-116">El resultado del cliente es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="9c957-116">The client output is as follows:</span></span>  
  
```console  
Add(100,15.99)  
Subtract(145,76.54)  
Multiply(9,81.25)  
Divide(22,7)  
  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="9c957-117">Se muestra el siguiente resultado del servicio:</span><span class="sxs-lookup"><span data-stu-id="9c957-117">The following service output is shown:</span></span>  
  
```console  
The service is ready.  
Press <ENTER> to terminate service.  
  
Received Add(100,15.99) - sleeping  
Received Subtract(145,76.54) - sleeping  
Received Multiply(9,81.25) - sleeping  
Received Divide(22,7) - sleeping  
Processing Add(100,15.99) - result: 115.99  
Processing Subtract(145,76.54) - result: 68.46  
Processing Multiply(9,81.25) - result: 731.25  
Processing Divide(22,7) - result: 3.14285714285714  
```  
  
> [!NOTE]
> <span data-ttu-id="9c957-118">HTTP es, por definición, un protocolo de solicitud/respuesta; cuando se realiza una solicitud, se devuelve una respuesta.</span><span class="sxs-lookup"><span data-stu-id="9c957-118">HTTP is, by definition, a request/response protocol; when a request is made, a response is returned.</span></span> <span data-ttu-id="9c957-119">Esto es verdad incluso para una operación de servicio unidireccional que se expone sobre HTTP.</span><span class="sxs-lookup"><span data-stu-id="9c957-119">This is true even for a one-way service operation that is exposed over HTTP.</span></span> <span data-ttu-id="9c957-120">Cuando se llama a la operación, el servicio devuelve un código de estado HTTP de 202 antes de que se ejecute la operación de servicio.</span><span class="sxs-lookup"><span data-stu-id="9c957-120">When the operation is called, the service returns an HTTP status code of 202 before the service operation has executed.</span></span> <span data-ttu-id="9c957-121">Este código de estado significa que se ha aceptado el procesamiento de la solicitud, pero no se ha completado aún.</span><span class="sxs-lookup"><span data-stu-id="9c957-121">This status code means that the request has been accepted for processing, but the processing has not yet been completed.</span></span> <span data-ttu-id="9c957-122">El cliente que llamó a la operación se bloquea hasta que recibe la respuesta 202 del servicio.</span><span class="sxs-lookup"><span data-stu-id="9c957-122">The client that called the operation blocks until it receives the 202 response from the service.</span></span> <span data-ttu-id="9c957-123">Esto puede producir comportamientos inesperados cuando se envían mensajes unidireccionales usando un enlace que se configura para usar sesiones.</span><span class="sxs-lookup"><span data-stu-id="9c957-123">This can cause some unexpected behavior when multiple one-way messages are sent using a binding that is configured to use sessions.</span></span> <span data-ttu-id="9c957-124">El enlace `wsHttpBinding` que se usa en este ejemplo se configura para utilizar sesiones de forma predeterminada a fin de establecer un contexto de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9c957-124">The `wsHttpBinding` binding used in this sample is configured to use sessions by default to establish a security context.</span></span> <span data-ttu-id="9c957-125">De forma predeterminada, se garantiza que los mensajes en una sesión lleguen en el orden en el que se enviaron.</span><span class="sxs-lookup"><span data-stu-id="9c957-125">By default, messages in a session are guaranteed to arrive in the order in which they are sent.</span></span> <span data-ttu-id="9c957-126">Debido a esto, cuando se envía el segundo mensaje en una sesión, no se procesa hasta que se haya procesado el primero.</span><span class="sxs-lookup"><span data-stu-id="9c957-126">Because of this, when the second message in a session is sent, it is not processed until the first message has been processed.</span></span> <span data-ttu-id="9c957-127">El resultado es que el cliente no recibe la respuesta 202 para un mensaje hasta que el procesamiento del mensaje anterior se haya completado.</span><span class="sxs-lookup"><span data-stu-id="9c957-127">The result of this is that the client does not receive the 202 response for a message until the processing of the previous message has been completed.</span></span> <span data-ttu-id="9c957-128">Parece, por tanto, que el cliente se bloquea en cada llamada de operación subsiguiente.</span><span class="sxs-lookup"><span data-stu-id="9c957-128">The client therefore appears to block on each subsequent operation call.</span></span> <span data-ttu-id="9c957-129">Para evitar este comportamiento, este ejemplo configura el tiempo de ejecución para enviar mensajes a la vez a distintas instancias para el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="9c957-129">To avoid this behavior, this sample configures the runtime to dispatch messages concurrently to distinct instances for processing.</span></span> <span data-ttu-id="9c957-130">El ejemplo establece <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> en `PerCall` para que otra instancia diferente pueda procesar cada mensaje.</span><span class="sxs-lookup"><span data-stu-id="9c957-130">The sample sets <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> to `PerCall` so that each message can be processed by a different instance.</span></span> <span data-ttu-id="9c957-131"><xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> se establece en `Multiple` para permitir que más de un subproceso envíe mensajes al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="9c957-131"><xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> is set to `Multiple` to allow more than one thread to dispatch messages at a time.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="9c957-132">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="9c957-132">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="9c957-133">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9c957-133">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="9c957-134">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9c957-134">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="9c957-135">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9c957-135">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9c957-136">Ejecute el servicio antes de ejecutar el cliente y ciérrelo antes de cerrar el servicio.</span><span class="sxs-lookup"><span data-stu-id="9c957-136">Run the service before you run the client and shut down the client before shutting down the service.</span></span> <span data-ttu-id="9c957-137">Esto evita una excepción del cliente cuando el cliente no puede cerrar la sesión de seguridad correctamente porque se haya cerrado el servicio.</span><span class="sxs-lookup"><span data-stu-id="9c957-137">This avoids a client exception when the client cannot close the security session cleanly because the service is gone.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="9c957-138">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="9c957-138">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9c957-139">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="9c957-139">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="9c957-140">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c957-140">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9c957-141">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="9c957-141">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Oneway`  
