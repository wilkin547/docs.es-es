---
title: Sesión
ms.date: 03/30/2017
helpviewer_keywords:
- Sessions
ms.assetid: 36e1db50-008c-4b32-8d09-b56e790b8417
ms.openlocfilehash: 283c8b9641dcce8b0207d3be0024b57369d125ff
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84591467"
---
# <a name="session"></a><span data-ttu-id="65ae9-102">Sesión</span><span class="sxs-lookup"><span data-stu-id="65ae9-102">Session</span></span>
<span data-ttu-id="65ae9-103">El ejemplo de sesión muestra cómo implementar un contrato que requiere una sesión.</span><span class="sxs-lookup"><span data-stu-id="65ae9-103">The Session sample demonstrates how to implement a contract that requires a session.</span></span> <span data-ttu-id="65ae9-104">Una sesión proporciona el contexto para realizar varias operaciones.</span><span class="sxs-lookup"><span data-stu-id="65ae9-104">A session provides context for performing multiple operations.</span></span> <span data-ttu-id="65ae9-105">Esto permite a un servicio asociar el estado a una sesión determinada, de manera que las operaciones posteriores puedan usar el estado de una operación anterior.</span><span class="sxs-lookup"><span data-stu-id="65ae9-105">This allows a service to associate state with a given session, such that subsequent operations can use the state of a previous operation.</span></span> <span data-ttu-id="65ae9-106">Este ejemplo se basa en el [Introducción](getting-started-sample.md), que implementa un servicio de calculadora.</span><span class="sxs-lookup"><span data-stu-id="65ae9-106">This sample is based on the [Getting Started](getting-started-sample.md), which implements a calculator service.</span></span> <span data-ttu-id="65ae9-107">El contrato `ICalculator` se ha modificado para permitir que se realice un conjunto de operaciones aritméticas, mientras se mantiene un resultado en ejecución.</span><span class="sxs-lookup"><span data-stu-id="65ae9-107">The `ICalculator` contract has been modified to allow a set of arithmetic operations to be performed, while keeping a running result.</span></span> <span data-ttu-id="65ae9-108">El contrato `ICalculatorSession` define esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="65ae9-108">This functionality is defined by the `ICalculatorSession` contract.</span></span> <span data-ttu-id="65ae9-109">El servicio mantiene el estado para un cliente ya que se llama a varias operaciones de servicio para realizar un cálculo.</span><span class="sxs-lookup"><span data-stu-id="65ae9-109">The service maintains the state for a client as multiple service operations are called to perform a calculation.</span></span> <span data-ttu-id="65ae9-110">El cliente puede recuperar el resultado actual llamando a `Result()` y borrar el resultado para ponerlo a cero llamando a `Clear()`.</span><span class="sxs-lookup"><span data-stu-id="65ae9-110">The client can retrieve the current result by calling `Result()` and clear the result to zero by calling `Clear()`.</span></span>  
  
 <span data-ttu-id="65ae9-111">En este ejemplo, el cliente es una aplicación de consola (.exe) y los Servicios de Internet Information Server (IIS) hospedan el servicio.</span><span class="sxs-lookup"><span data-stu-id="65ae9-111">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="65ae9-112">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="65ae9-112">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="65ae9-113">Establecer <xref:System.ServiceModel.SessionMode> del contrato en `Required` garantiza que cuando el contrato se expone en un enlace en concreto, el enlace admita las sesiones.</span><span class="sxs-lookup"><span data-stu-id="65ae9-113">Setting the <xref:System.ServiceModel.SessionMode> of the contract to `Required` ensures that when the contract is exposed over a particular binding, the binding supports sessions.</span></span> <span data-ttu-id="65ae9-114">Si el enlace no admite sesiones, se producirá una excepción.</span><span class="sxs-lookup"><span data-stu-id="65ae9-114">If the binding does not support sessions an exception is thrown.</span></span> <span data-ttu-id="65ae9-115">La interfaz `ICalculatorSession` se define de tal forma que se pueda llamar a más operaciones, que modifica un resultado en ejecución, tal y como se muestra en el siguiente código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="65ae9-115">The `ICalculatorSession` interface is defined such that one or more operations can be called, which modifies a running result, as shown in the following sample code.</span></span>  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples", SessionMode=SessionMode.Required)]  
public interface ICalculatorSession  
{  
    [OperationContract(IsOneWay=true)]  
    void Clear();  
    [OperationContract(IsOneWay = true)]  
    void AddTo(double n);  
    [OperationContract(IsOneWay = true)]  
    void SubtractFrom(double n);  
    [OperationContract(IsOneWay = true)]  
    void MultiplyBy(double n);  
    [OperationContract(IsOneWay = true)]  
    void DivideBy(double n);  
    [OperationContract]  
    double Result();  
}  
```  
  
 <span data-ttu-id="65ae9-116">El servicio utiliza <xref:System.ServiceModel.InstanceContextMode> de <xref:System.ServiceModel.InstanceContextMode.PerSession> para enlazar un contexto de instancia de servicio determinado para cada sesión de entrada.</span><span class="sxs-lookup"><span data-stu-id="65ae9-116">The service uses a <xref:System.ServiceModel.InstanceContextMode> of <xref:System.ServiceModel.InstanceContextMode.PerSession> to bind a given service instance context to each incoming session.</span></span> <span data-ttu-id="65ae9-117">Esto permite al servicio mantener el resultado en ejecución para cada sesión en una variable del miembro local.</span><span class="sxs-lookup"><span data-stu-id="65ae9-117">This allows the service to maintain the running result for each session in a local member variable.</span></span>  
  
```csharp
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
public class CalculatorService : ICalculatorSession  
{  
    double result = 0.0D;  
  
    public void Clear()  
    {  result = 0.0D; }  
  
    public void AddTo(double n)  
    {  result += n;   }  
  
    public void SubtractFrom(double n)  
    {  result -= n;   }  
  
    public void MultiplyBy(double n)  
    {  result *= n;   }  
  
    public void DivideBy(double n)  
    {  result /= n;   }  
  
    public double Result()  
    {  return result; }  
}  
```  
  
 <span data-ttu-id="65ae9-118">Al ejecutar el ejemplo, el cliente realiza varias solicitudes al servidor y solicita el resultado, que se mostrará a continuación en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="65ae9-118">When you run the sample, the client makes several requests to the server and requests the result, which it then displays in the client console window.</span></span> <span data-ttu-id="65ae9-119">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="65ae9-119">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
(((0 + 100) - 50) * 17.65) / 2 = 441.25  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="65ae9-120">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="65ae9-120">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="65ae9-121">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="65ae9-121">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="65ae9-122">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="65ae9-122">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="65ae9-123">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="65ae9-123">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="65ae9-124">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="65ae9-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="65ae9-125">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="65ae9-125">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="65ae9-126">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="65ae9-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="65ae9-127">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="65ae9-127">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Session`  
