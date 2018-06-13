---
title: Evitar problemas mediante una declaración de instrucción
ms.date: 03/30/2017
ms.assetid: aff82a8d-933d-4bdc-b0c2-c2f7527204fb
ms.openlocfilehash: 14a0649c9996158f1503581c906d8dfd1a95ebc8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33503903"
---
# <a name="avoiding-problems-with-the-using-statement"></a><span data-ttu-id="ea78b-102">Evitar problemas mediante una declaración de instrucción</span><span class="sxs-lookup"><span data-stu-id="ea78b-102">Avoiding Problems with the Using Statement</span></span>
<span data-ttu-id="ea78b-103">Este ejemplo muestra cómo no debería utilizar el C# "utilizando" la instrucción para limpiar automáticamente los recursos al utilizar un cliente especificado.</span><span class="sxs-lookup"><span data-stu-id="ea78b-103">This sample demonstrates how you should not use the C# "using" statement to automatically clean up resources when using a typed client.</span></span> <span data-ttu-id="ea78b-104">En este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md) que implementa un servicio de calculadora.</span><span class="sxs-lookup"><span data-stu-id="ea78b-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="ea78b-105">En este ejemplo, el cliente es una aplicación de consola (.exe) y los Servicios de Internet Information Server (IIS) hospedan el servicio.</span><span class="sxs-lookup"><span data-stu-id="ea78b-105">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ea78b-106">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="ea78b-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="ea78b-107">Este ejemplo muestra dos de los problemas comunes que se producen al utilizar el C# "utilizando" la instrucción con clientes escritos a máquina, así como el código que limpia correctamente después de las excepciones.</span><span class="sxs-lookup"><span data-stu-id="ea78b-107">This sample shows two of the common problems that occur when using the C# "using" statement with typed clients, as well as code that correctly cleans up after exceptions.</span></span>  
  
 <span data-ttu-id="ea78b-108">La instrucción C# "utilizando" resulta en una llamada a `Dispose`().</span><span class="sxs-lookup"><span data-stu-id="ea78b-108">The C# "using" statement results in a call to `Dispose`().</span></span> <span data-ttu-id="ea78b-109">Esto es igual que `Close`(), que puede producir las excepciones cuando se produce un error en la red.</span><span class="sxs-lookup"><span data-stu-id="ea78b-109">This is the same as `Close`(), which may throw exceptions when a network error occurs.</span></span> <span data-ttu-id="ea78b-110">Dado que la llamada a `Dispose`() ocurre implícitamente en la llave de cierre del bloque "utilizando", es probable que este origen de excepciones pase inadvertido a las personas que escriben el código y a las que leen el código.</span><span class="sxs-lookup"><span data-stu-id="ea78b-110">Because the call to `Dispose`() happens implicitly at the closing brace of the "using" block, this source of exceptions is likely to go unnoticed both by people writing the code and reading the code.</span></span> <span data-ttu-id="ea78b-111">Esto representa un origen potencial de errores de aplicación.</span><span class="sxs-lookup"><span data-stu-id="ea78b-111">This represents a potential source of application errors.</span></span>  
  
 <span data-ttu-id="ea78b-112">El primer problema, mostrado en el método `DemonstrateProblemUsingCanThrow`, es que la llave de cierre inicia una excepción y el código no se ejecuta después de que la llave se cierre:</span><span class="sxs-lookup"><span data-stu-id="ea78b-112">The first problem, illustrated in the `DemonstrateProblemUsingCanThrow` method, is that the closing brace throws an exception and the code after the closing brace does not execute:</span></span>  
  
```csharp   
using (CalculatorClient client = new CalculatorClient())  
{  
    ...  
} // <-- this line might throw  
Console.WriteLine("Hope this code wasn't important, because it might not happen.");  
```  
  
 <span data-ttu-id="ea78b-113">Aun cuando nada dentro del bloque que se está utilizando produzca una excepción , o aunque todas las excepciones dentro del bloque que está siendo utilizando la detecten, `Console.Writeline` no podrían ocurrir porque la llamada implícita `Dispose`a la llave de cierre podría producir una excepción.</span><span class="sxs-lookup"><span data-stu-id="ea78b-113">Even if nothing inside the using block throws an exception or all exceptions inside the using block are caught, the `Console.Writeline` might not happen because the implicit `Dispose`() call at the closing brace might throw an exception.</span></span>  
  
 <span data-ttu-id="ea78b-114">El segundo problema, mostrado en el método `DemonstrateProblemUsingCanThrowAndMask`, es que otra implicación de la llave de cierre produzca una excepción:</span><span class="sxs-lookup"><span data-stu-id="ea78b-114">The second problem, illustrated in the `DemonstrateProblemUsingCanThrowAndMask` method, is another implication of the closing brace throwing an exception:</span></span>  
  
```csharp   
using (CalculatorClient client = new CalculatorClient())  
{  
    ...  
    throw new ApplicationException("Hope this exception was not important, because "+  
                                   "it might be masked by the Close exception.");  
} // <-- this line might throw an exception.  
```  
  
 <span data-ttu-id="ea78b-115">Dado que `Dispose`() se produce dentro de un bloque "finalmente", el `ApplicationException` nunca se ve fuera del bloque que se está utilizando si se produce un error `Dispose`() .</span><span class="sxs-lookup"><span data-stu-id="ea78b-115">Because the `Dispose`() occurs inside a "finally" block, the `ApplicationException` is never seen outside the using block if the `Dispose`() fails.</span></span> <span data-ttu-id="ea78b-116">Si el código fuera de debe conocer sobre cuando `ApplicationException` produce, la construcción "utilizando" puede producir los problemas enmascarando esta excepción.</span><span class="sxs-lookup"><span data-stu-id="ea78b-116">If the code outside must know about when the `ApplicationException` occurs, the "using" construct may cause problems by masking this exception.</span></span>  
  
 <span data-ttu-id="ea78b-117">Finalmente, el ejemplo muestra correctamente cómo limpiar cuando se producen excepciones en `DemonstrateCleanupWithExceptions`.</span><span class="sxs-lookup"><span data-stu-id="ea78b-117">Finally, the sample demonstrates how to clean up correctly when exceptions occur in `DemonstrateCleanupWithExceptions`.</span></span> <span data-ttu-id="ea78b-118">Esto utiliza un bloque prueba try/catch para crear informes errores y llamar`Abort`.</span><span class="sxs-lookup"><span data-stu-id="ea78b-118">This uses a try/catch block to report errors and call `Abort`.</span></span> <span data-ttu-id="ea78b-119">Consulte la [espera excepciones](../../../../docs/framework/wcf/samples/expected-exceptions.md) ejemplo para obtener más información acerca de cómo detectar excepciones de las llamadas de cliente.</span><span class="sxs-lookup"><span data-stu-id="ea78b-119">See the [Expected Exceptions](../../../../docs/framework/wcf/samples/expected-exceptions.md) sample for more details about catching exceptions from client calls.</span></span>  
  
```csharp   
try  
{  
    ...  
    client.Close();  
}  
catch (CommunicationException e)  
{  
    ...  
    client.Abort();  
}  
catch (TimeoutException e)  
{  
    ...  
    client.Abort();  
}  
catch (Exception e)  
{  
    ...  
    client.Abort();  
    throw;  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="ea78b-120">La instrucción en uso y ServiceHost: Muchas aplicaciones hospedadas en sí mismas hacen poco más que hospedar un servicio y ServiceHost.Close raramente produce una excepción, por lo que tales aplicaciones pueden utilizar sin ningún riesgo la instrucción en uso con ServiceHost.</span><span class="sxs-lookup"><span data-stu-id="ea78b-120">The using statement and ServiceHost: Many self-hosting applications do little more than host a service, and ServiceHost.Close rarely throws an exception, so such applications can safely use the using statement with ServiceHost.</span></span> <span data-ttu-id="ea78b-121">Sin embargo, sea consciente que ServiceHost.Close puede iniciar una`CommunicationException`, por lo que si su aplicación continúa después de cerrar ServiceHost, debería evitar la instrucción en uso y seguir el patrón previamente proporcionado.</span><span class="sxs-lookup"><span data-stu-id="ea78b-121">However, be aware that ServiceHost.Close can throw a `CommunicationException`, so if your application continues after closing the ServiceHost, you should avoid the using statement and follow the pattern previously given.</span></span>  
  
 <span data-ttu-id="ea78b-122">Al ejecutar el ejemplo, las respuestas y excepciones de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="ea78b-122">When you run the sample, the operation responses and exceptions are displayed in the client console window.</span></span>  
  
 <span data-ttu-id="ea78b-123">El proceso de cliente ejecuta tres escenarios, cada uno de los cuales intentan llamar `Divide`.</span><span class="sxs-lookup"><span data-stu-id="ea78b-123">The client process runs three scenarios, each of which attempts to call `Divide`.</span></span> <span data-ttu-id="ea78b-124">El primer escenario muestra un código que está omitido debido a una excepción de `Dispose`().</span><span class="sxs-lookup"><span data-stu-id="ea78b-124">The first scenario demonstrates code being skipped because of an exception from `Dispose`().</span></span> <span data-ttu-id="ea78b-125">El segundo escenario muestra una excepción importante enmascarándose debido a una excepción de `Dispose`().</span><span class="sxs-lookup"><span data-stu-id="ea78b-125">The second scenario demonstrates an important exception being masked because of an exception from `Dispose`().</span></span> <span data-ttu-id="ea78b-126">El tercer escenario muestra el proceso de limpieza correcto.</span><span class="sxs-lookup"><span data-stu-id="ea78b-126">The third scenario demonstrates correct clean up.</span></span>  
  
 <span data-ttu-id="ea78b-127">El resultado esperado del proceso de cliente es:</span><span class="sxs-lookup"><span data-stu-id="ea78b-127">The expected output from the client process is:</span></span>  
  
```  
=  
= Demonstrating problem:  closing brace of using statement can throw.  
=  
Got System.ServiceModel.CommunicationException from Divide.  
Got System.ServiceModel.Security.MessageSecurityException  
=  
= Demonstrating problem:  closing brace of using statement can mask other Exceptions.  
=  
Got System.ServiceModel.CommunicationException from Divide.  
Got System.ServiceModel.Security.MessageSecurityException  
=  
= Demonstrating cleanup with Exceptions.  
=  
Calling client.Add(0.0, 0.0);  
        client.Add(0.0, 0.0); returned 0  
Calling client.Divide(0.0, 0.0);  
Got System.ServiceModel.CommunicationException from Divide.  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ea78b-128">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="ea78b-128">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="ea78b-129">Asegúrese de que ha llevado a cabo la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ea78b-129">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="ea78b-130">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ea78b-130">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="ea78b-131">Para ejecutar el ejemplo en una configuración de equipo único o de varios, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ea78b-131">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ea78b-132">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="ea78b-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ea78b-133">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="ea78b-133">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ea78b-134">Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="ea78b-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ea78b-135">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="ea78b-135">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\UsingUsing`  
  
## <a name="see-also"></a><span data-ttu-id="ea78b-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea78b-136">See Also</span></span>
