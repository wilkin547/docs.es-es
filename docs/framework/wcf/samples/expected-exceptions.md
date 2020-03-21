---
title: Excepciones esperadas
ms.date: 03/30/2017
ms.assetid: 299a6987-ae6b-43c6-987f-12b034b583ae
ms.openlocfilehash: f250e526b528adf0b67365ceb07f13e4087d773d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144714"
---
# <a name="expected-exceptions"></a><span data-ttu-id="a5cd0-102">Excepciones esperadas</span><span class="sxs-lookup"><span data-stu-id="a5cd0-102">Expected Exceptions</span></span>
<span data-ttu-id="a5cd0-103">Este ejemplo muestra cómo detectar las excepciones esperadas cuando se usa un cliente con tipo.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-103">This sample demonstrates how to catch expected exceptions when using a typed client.</span></span> <span data-ttu-id="a5cd0-104">Este ejemplo se basa en la [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md) que implementa un servicio de calculadora.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="a5cd0-105">En este ejemplo, el cliente es una aplicación de consola (.exe) y los Servicios de Internet Information Server (IIS) hospedan el servicio.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-105">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a5cd0-106">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="a5cd0-107">Este ejemplo muestra la detección y administración de dos tipos de excepciones esperadas que los programas correctos deben gestionar: `TimeoutException` y `CommunicationException`.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-107">This sample demonstrates catching and handling the two expected exception types that correct programs must handle: `TimeoutException` and `CommunicationException`.</span></span>  
  
 <span data-ttu-id="a5cd0-108">Las excepciones que se producen desde métodos de comunicación en un cliente de Windows Communication Foundation (WCF) son esperadas o inesperadas.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-108">Exceptions that are thrown from communication methods on a Windows Communication Foundation (WCF) client are either expected or unexpected.</span></span> <span data-ttu-id="a5cd0-109">Las inesperadas incluyen errores graves como `OutOfMemoryException` y errores de programación como `ArgumentNullException` o `InvalidOperationException`.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-109">Unexpected exceptions include catastrophic failures like `OutOfMemoryException` and programming errors like `ArgumentNullException` or `InvalidOperationException`.</span></span> <span data-ttu-id="a5cd0-110">Normalmente no hay ninguna manera útil de controlar errores inesperados, por lo que normalmente no debe detectarlos al llamar a un método de comunicación de cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-110">Typically there is no useful way to handle unexpected errors, so typically you should not catch them when calling a WCF client communication method.</span></span>  
  
 <span data-ttu-id="a5cd0-111">Las excepciones esperadas de los `TimeoutException` `CommunicationException`métodos de comunicación `CommunicationException`en un cliente WCF incluyen , , y cualquier clase derivada de .</span><span class="sxs-lookup"><span data-stu-id="a5cd0-111">Expected exceptions from communication methods on a WCF client include `TimeoutException`, `CommunicationException`, and any derived class of `CommunicationException`.</span></span> <span data-ttu-id="a5cd0-112">Estos indican un problema durante la comunicación que se puede controlar de forma segura mediante la anulación del cliente WCF y la notificación de un error de comunicación.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-112">These indicate a problem during communication that can be safely handled by aborting the WCF client and reporting a communication failure.</span></span> <span data-ttu-id="a5cd0-113">Dado que los factores externos pueden producir estos errores en cualquier aplicación, las aplicaciones correctas deben detectar estas excepciones y recuperarse cuando se produzcan.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-113">Because external factors can cause these errors in any application, correct applications must catch these exceptions and recover when they occur.</span></span>  
  
 <span data-ttu-id="a5cd0-114">Hay varias clases derivadas de `CommunicationException` que un cliente puede iniciar.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-114">There are several derived classes of `CommunicationException` that a client can throw.</span></span> <span data-ttu-id="a5cd0-115">En algunos casos, las aplicaciones detectan también algunas de ellas para que se gestionen de forma especial, pero deja que otras las gestionen como `CommunicationException`.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-115">In some cases, applications also catch some of these to do special handling, but let the others be handled as a `CommunicationException`.</span></span> <span data-ttu-id="a5cd0-116">Esto se puede lograr detectando el tipo de excepción más concreto primero y detectando a continuación `CommunicationException` en una cláusula catch posterior.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-116">This can be accomplished by catching the more specific exception type first and then catching `CommunicationException` in a later catch-clause.</span></span>  
  
 <span data-ttu-id="a5cd0-117">El código que llama a un método de comunicación de cliente debe detectar `TimeoutException` y `CommunicationException`.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-117">Code that calls a client communication method must catch the `TimeoutException` and `CommunicationException`.</span></span> <span data-ttu-id="a5cd0-118">Una manera de administrar tales errores es anular el cliente e informar del error de comunicación.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-118">One way to handle such errors is to abort the client and report the communication failure.</span></span>  
  
```csharp
try  
{  
    ...  
    double result = client.Add(value1, value2);  
    ...  
    client.Close();  
}  
catch (TimeoutException exception)  
{  
    Console.WriteLine("Got {0}", exception.GetType());  
    client.Abort();  
}  
catch (CommunicationException exception)  
{  
    Console.WriteLine("Got {0}", exception.GetType());  
    client.Abort();  
}  
```  
  
 <span data-ttu-id="a5cd0-119">Si se produce una excepción esperada, el cliente podrá utilizarse después o no.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-119">If an expected exception occurs, the client may or may not be usable afterwards.</span></span> <span data-ttu-id="a5cd0-120">Para determinar si el cliente todavía se puede utilizar, compruebe que la propiedad `State` sea `CommunicationState`.Opened.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-120">To determine if the client is still usable, check that the `State` property is `CommunicationState`.Opened.</span></span> <span data-ttu-id="a5cd0-121">Si está abierta aún, se podría utilizar.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-121">If it is still opened, then it is still usable.</span></span> <span data-ttu-id="a5cd0-122">De lo contrario debería anular el cliente y liberar todas las referencias a él.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-122">Otherwise you should abort the client and release all references to it.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="a5cd0-123">Puede observar que, en ocasiones, los clientes que tienen una sesión no se pueden usar después de una excepción. Los clientes que no tienen una sesión se pueden seguir usando después de una excepción.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-123">You may observe that clients that have a session are often no longer usable after an exception, and clients that do not have a session are often still usable after an exception.</span></span> <span data-ttu-id="a5cd0-124">Sin embargo, no se garantiza ninguno de ellos, de manera que si intenta continuar usando el cliente después de una excepción, la aplicación debería comprobar la propiedad `State` para comprobar que el cliente sigue abierto.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-124">However, neither of these is guaranteed, so if you want to try to continue using the client after an exception your application should check the `State` property to verify the client is still opened.</span></span>  
  
 <span data-ttu-id="a5cd0-125">Al ejecutar el ejemplo, las respuestas y excepciones de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-125">When you run the sample, the operation responses and exceptions are displayed in the client console window.</span></span>  
  
 <span data-ttu-id="a5cd0-126">El proceso de cliente ejecuta dos escenarios, cada uno de los cuales intenta llamar a `Add` seguido por `Divide`.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-126">The client process runs two scenarios, each of which attempts to call `Add` followed by `Divide`.</span></span> <span data-ttu-id="a5cd0-127">El primer escenario simula un problema de la red anulando el cliente antes de realizar la llamada a `Divide`.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-127">The first scenario simulates a network issue by aborting the client before making the call to `Divide`.</span></span> <span data-ttu-id="a5cd0-128">El segundo escenario produce una condición de tiempo de espera agotado definiendo un tiempo de espera demasiado corto para que el método pueda completarse.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-128">The second scenario causes a timeout condition by setting the timeout too short for the method to complete.</span></span> <span data-ttu-id="a5cd0-129">El resultado esperado del proceso de cliente es:</span><span class="sxs-lookup"><span data-stu-id="a5cd0-129">The expected output from the client process is:</span></span>  
  
```output
Add(100,15.99) = 115.99  
Simulated network problem occurs...  
Got System.ServiceModel.CommunicationObjectAbortedException  
Add(100,15.99) = 115.99  
Set timeout too short for method to complete...  
Got System.TimeoutException  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a5cd0-130">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="a5cd0-130">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="a5cd0-131">Asegúrese de que ha realizado el procedimiento de instalación única [para los ejemplos](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)de Windows Communication Foundation .</span><span class="sxs-lookup"><span data-stu-id="a5cd0-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="a5cd0-132">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a5cd0-132">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="a5cd0-133">Para ejecutar el ejemplo en una configuración de uno o entre equipos, siga las instrucciones de Ejecución de [los ejemplos](../../../../docs/framework/wcf/samples/running-the-samples.md)de Windows Communication Foundation .</span><span class="sxs-lookup"><span data-stu-id="a5cd0-133">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a5cd0-134">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-134">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a5cd0-135">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-135">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="a5cd0-136">Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="a5cd0-136">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a5cd0-137">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="a5cd0-137">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\ExpectedExceptions`  
