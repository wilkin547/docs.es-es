---
title: 'Tutorial: Usar a un cliente de Windows Communication Foundation'
ms.date: 03/19/2019
helpviewer_keywords:
- WCF clients [WCF], using
dev_langs:
- CSharp
- VB
ms.assetid: 190349fc-0573-49c7-bb85-8e316df7f31f
ms.openlocfilehash: fa9aa3612a8dc72623fc4ea4b1ea337ac773fa26
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59169980"
---
# <a name="tutorial-use-a-windows-communication-foundation-client"></a><span data-ttu-id="18ddf-102">Tutorial: Usar a un cliente de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="18ddf-102">Tutorial: Use a Windows Communication Foundation client</span></span>

<span data-ttu-id="18ddf-103">Este tutorial describen las últimas cinco tareas necesarias para crear una aplicación básica de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="18ddf-103">This tutorial describes the last of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="18ddf-104">Para obtener información general de los tutoriales, consulte [Tutorial: Introducción a las aplicaciones de Windows Communication Foundation](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="18ddf-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="18ddf-105">Una vez que haya creado y configurado a un proxy de Windows Communication Foundation (WCF), se crea una instancia de cliente y se compila la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="18ddf-105">After you've created and configured a Windows Communication Foundation (WCF) proxy, you create a client instance and compile the client application.</span></span> <span data-ttu-id="18ddf-106">A continuación, se utiliza para comunicarse con el servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="18ddf-106">You then use it to communicate with the WCF service.</span></span> 

<span data-ttu-id="18ddf-107">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="18ddf-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="18ddf-108">Agregar código para usar al cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="18ddf-108">Add code to use the WCF client.</span></span>
> - <span data-ttu-id="18ddf-109">Probar al cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="18ddf-109">Test the WCF client.</span></span>

## <a name="add-code-to-use-the-wcf-client"></a><span data-ttu-id="18ddf-110">Agregar código para usar al cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="18ddf-110">Add code to use the WCF client</span></span>

<span data-ttu-id="18ddf-111">El código de cliente hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="18ddf-111">The client code does the following steps:</span></span>
- <span data-ttu-id="18ddf-112">Crea una instancia del cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="18ddf-112">Instantiates the WCF client.</span></span>
- <span data-ttu-id="18ddf-113">Llama a las operaciones de servicio desde el proxy generado.</span><span class="sxs-lookup"><span data-stu-id="18ddf-113">Calls the service operations from the generated proxy.</span></span>
- <span data-ttu-id="18ddf-114">Cierra al cliente una vez completada la llamada de operación.</span><span class="sxs-lookup"><span data-stu-id="18ddf-114">Closes the client after the operation call is completed.</span></span>

<span data-ttu-id="18ddf-115">Abra el **Program.cs** o **Module1.vb** de archivos desde el **GettingStartedClient** del proyecto y reemplace su código con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="18ddf-115">Open the **Program.cs** or **Module1.vb** file from the **GettingStartedClient** project and replace its code with the following code:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using GettingStartedClient.ServiceReference1;

namespace GettingStartedClient
{
    class Program
    {
        static void Main(string[] args)
        {
            //Step 1: Create an instance of the WCF proxy.
            CalculatorClient client = new CalculatorClient();

            // Step 2: Call the service operations.
            // Call the Add service operation.
            double value1 = 100.00D;
            double value2 = 15.99D;
            double result = client.Add(value1, value2);
            Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);

            // Call the Subtract service operation.
            value1 = 145.00D;
            value2 = 76.54D;
            result = client.Subtract(value1, value2);
            Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);

            // Call the Multiply service operation.
            value1 = 9.00D;
            value2 = 81.25D;
            result = client.Multiply(value1, value2);
            Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);

            // Call the Divide service operation.
            value1 = 22.00D;
            value2 = 7.00D;
            result = client.Divide(value1, value2);
            Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);

            // Step 3: Close the client to gracefully close the connection and clean up resources.
            Console.WriteLine("\nPress <Enter> to terminate the client.");
            Console.ReadLine();
            client.Close();
        }
    }
}
```

```vb
Imports System
Imports System.Collections.Generic
Imports System.Text
Imports System.ServiceModel
Imports GettingStartedClient.ServiceReference1

Module Module1

    Sub Main()
        ' Step 1: Create an instance of the WCF proxy.
        Dim Client As New CalculatorClient()

        ' Step 2: Call the service operations.
        ' Call the Add service operation.
        Dim value1 As Double = 100D
        Dim value2 As Double = 15.99D
        Dim result As Double = Client.Add(value1, value2)
        Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)

        ' Call the Subtract service operation.
        value1 = 145D
        value2 = 76.54D
        result = Client.Subtract(value1, value2)
        Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result)

        ' Call the Multiply service operation.
        value1 = 9D
        value2 = 81.25D
        result = Client.Multiply(value1, value2)
        Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result)

        ' Call the Divide service operation.
        value1 = 22D
        value2 = 7D
        result = Client.Divide(value1, value2)
        Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result)

        ' Step 3: Close the client to gracefully close the connection and clean up resources.
        Console.WriteLine()
        Console.WriteLine("Press <Enter> to terminate the client.")
        Console.ReadLine()
        Client.Close()

    End Sub

End Module
```

<span data-ttu-id="18ddf-116">Tenga en cuenta la `using` (para Visual C#) o `Imports` (para Visual Basic) instrucción que importa `GettingStartedClient.ServiceReference1`.</span><span class="sxs-lookup"><span data-stu-id="18ddf-116">Notice the `using` (for Visual C#) or `Imports` (for Visual Basic) statement that imports `GettingStartedClient.ServiceReference1`.</span></span> <span data-ttu-id="18ddf-117">Esta instrucción importa el código generado por Visual Studio con el **Add Service Reference** función.</span><span class="sxs-lookup"><span data-stu-id="18ddf-117">This statement imports the code that Visual Studio generated with the **Add Service Reference** function.</span></span> <span data-ttu-id="18ddf-118">El código crea una instancia del proxy de WCF y llama a cada una de las operaciones de servicio que expone el servicio de calculadora.</span><span class="sxs-lookup"><span data-stu-id="18ddf-118">The code instantiates the WCF proxy and calls each of the service operations that the calculator service exposes.</span></span> <span data-ttu-id="18ddf-119">A continuación, cierra al proxy y finaliza el programa.</span><span class="sxs-lookup"><span data-stu-id="18ddf-119">It then closes the proxy and ends the program.</span></span>

## <a name="test-the-wcf-client"></a><span data-ttu-id="18ddf-120">Probar al cliente WCF</span><span class="sxs-lookup"><span data-stu-id="18ddf-120">Test the WCF client</span></span>

### <a name="test-the-application-from-visual-studio"></a><span data-ttu-id="18ddf-121">Probar la aplicación desde Visual Studio</span><span class="sxs-lookup"><span data-stu-id="18ddf-121">Test the application from Visual Studio</span></span>

1. <span data-ttu-id="18ddf-122">Guarde y compile la solución.</span><span class="sxs-lookup"><span data-stu-id="18ddf-122">Save and build the solution.</span></span>

2. <span data-ttu-id="18ddf-123">Seleccione el **GettingStartedLib** carpeta y, a continuación, seleccione **establecer como proyecto de inicio** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="18ddf-123">Select the **GettingStartedLib** folder, and then select **Set as Startup Project** from the shortcut menu.</span></span>

3. <span data-ttu-id="18ddf-124">Desde **proyectos de inicio**, seleccione **GettingStartedLib** en la lista desplegable, seleccione **ejecutar** o presione **F5**.</span><span class="sxs-lookup"><span data-stu-id="18ddf-124">From **Startup Projects**, select **GettingStartedLib** from the drop-down list, then select **Run** or press **F5**.</span></span>

### <a name="test-the-application-from-a-command-prompt"></a><span data-ttu-id="18ddf-125">Probar la aplicación desde un símbolo del sistema</span><span class="sxs-lookup"><span data-stu-id="18ddf-125">Test the application from a command prompt</span></span>

1. <span data-ttu-id="18ddf-126">Abra un símbolo del sistema como administrador y, a continuación, navegue hasta el directorio de la solución de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="18ddf-126">Open a command prompt as an administrator, and then navigate to your Visual Studio solution directory.</span></span> 

2. <span data-ttu-id="18ddf-127">Para iniciar el servicio: Escriba *GettingStartedHost\bin\Debug\GettingStartedHost.exe*.</span><span class="sxs-lookup"><span data-stu-id="18ddf-127">To start the service: Enter *GettingStartedHost\bin\Debug\GettingStartedHost.exe*.</span></span>

3. <span data-ttu-id="18ddf-128">Para iniciar al cliente: Abra otro símbolo del sistema, navegue hasta el directorio de la solución de Visual Studio y luego escriba *GettingStartedClient\bin\Debug\GettingStartedClient.exe*.</span><span class="sxs-lookup"><span data-stu-id="18ddf-128">To start the client: Open another command prompt, navigate to your Visual Studio solution directory, then enter *GettingStartedClient\bin\Debug\GettingStartedClient.exe*.</span></span>

   <span data-ttu-id="18ddf-129">*GettingStartedHost.exe* genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="18ddf-129">*GettingStartedHost.exe* produces the following output:</span></span>

   ```text
   The service is ready.
   Press <Enter> to terminate the service.

   Received Add(100,15.99)
   Return: 115.99
   Received Subtract(145,76.54)
   Return: 68.46
   Received Multiply(9,81.25)
   Return: 731.25
   Received Divide(22,7)
   Return: 3.14285714285714
   ```

   <span data-ttu-id="18ddf-130">*GettingStartedClient.exe* genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="18ddf-130">*GettingStartedClient.exe* produces the following output:</span></span>

   ```text
   Add(100,15.99) = 115.99
   Subtract(145,76.54) = 68.46
   Multiply(9,81.25) = 731.25
   Divide(22,7) = 3.14285714285714

   Press <Enter> to terminate the client.
   ```

## <a name="next-steps"></a><span data-ttu-id="18ddf-131">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="18ddf-131">Next steps</span></span>

<span data-ttu-id="18ddf-132">Ahora ha completado todas las tareas en el tutorial de introducción de get WCF.</span><span class="sxs-lookup"><span data-stu-id="18ddf-132">You've now completed all the tasks in the WCF get started tutorial.</span></span> <span data-ttu-id="18ddf-133">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="18ddf-133">In this tutorial, you learned how to:</span></span>

<span data-ttu-id="18ddf-134">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="18ddf-134">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="18ddf-135">Agregar código para usar al cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="18ddf-135">Add code to use the WCF client.</span></span>
> - <span data-ttu-id="18ddf-136">Probar al cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="18ddf-136">Test the WCF client.</span></span>

<span data-ttu-id="18ddf-137">Si tiene problemas o errores en cualquiera de los pasos, siga los pasos descritos en el artículo de solución de problemas para corregirlos.</span><span class="sxs-lookup"><span data-stu-id="18ddf-137">If you have problems or errors in any of the steps, follow the steps in the troubleshooting article to fix them.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="18ddf-138">Solución de problemas de la operación Get a trabajar con los tutoriales WCF</span><span class="sxs-lookup"><span data-stu-id="18ddf-138">Troubleshoot the Get started with WCF tutorials</span></span>](troubleshooting-the-getting-started-tutorial.md)
