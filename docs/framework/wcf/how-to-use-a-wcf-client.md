---
title: 'Tutorial: uso de un cliente de Windows Communication Foundation'
ms.date: 03/19/2019
helpviewer_keywords:
- WCF clients [WCF], using
dev_langs:
- CSharp
- VB
ms.assetid: 190349fc-0573-49c7-bb85-8e316df7f31f
ms.openlocfilehash: d0ef525db16b2b2cedeea5fa03376fb4f3489a4a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346767"
---
# <a name="tutorial-use-a-windows-communication-foundation-client"></a><span data-ttu-id="88469-102">Tutorial: uso de un cliente de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="88469-102">Tutorial: Use a Windows Communication Foundation client</span></span>

<span data-ttu-id="88469-103">En este tutorial se describen las últimas cinco tareas necesarias para crear una aplicación básica de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="88469-103">This tutorial describes the last of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="88469-104">Para obtener información general sobre los tutoriales, vea [Tutorial: Introducción a las aplicaciones de Windows Communication Foundation](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="88469-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="88469-105">Después de crear y configurar un proxy de Windows Communication Foundation (WCF), cree una instancia de cliente y compile la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="88469-105">After you've created and configured a Windows Communication Foundation (WCF) proxy, you create a client instance and compile the client application.</span></span> <span data-ttu-id="88469-106">A continuación, Úsela para comunicarse con el servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="88469-106">You then use it to communicate with the WCF service.</span></span> 

<span data-ttu-id="88469-107">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="88469-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="88469-108">Agregue código para usar el cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="88469-108">Add code to use the WCF client.</span></span>
> - <span data-ttu-id="88469-109">Pruebe el cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="88469-109">Test the WCF client.</span></span>

## <a name="add-code-to-use-the-wcf-client"></a><span data-ttu-id="88469-110">Agregar código para usar el cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="88469-110">Add code to use the WCF client</span></span>

<span data-ttu-id="88469-111">El código de cliente realiza los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="88469-111">The client code does the following steps:</span></span>

- <span data-ttu-id="88469-112">Crea una instancia del cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="88469-112">Instantiates the WCF client.</span></span>
- <span data-ttu-id="88469-113">Llama a las operaciones de servicio desde el proxy generado.</span><span class="sxs-lookup"><span data-stu-id="88469-113">Calls the service operations from the generated proxy.</span></span>
- <span data-ttu-id="88469-114">Cierra el cliente una vez completada la llamada a la operación.</span><span class="sxs-lookup"><span data-stu-id="88469-114">Closes the client after the operation call is completed.</span></span>

<span data-ttu-id="88469-115">Abra el archivo **Program.CS** o **Module1. VB** desde el proyecto **GettingStartedClient** y reemplace su código por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="88469-115">Open the **Program.cs** or **Module1.vb** file from the **GettingStartedClient** project and replace its code with the following code:</span></span>

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

<span data-ttu-id="88469-116">Observe la instrucción `using` (para C#visual) o `Imports` (para Visual Basic) que importa `GettingStartedClient.ServiceReference1`.</span><span class="sxs-lookup"><span data-stu-id="88469-116">Notice the `using` (for Visual C#) or `Imports` (for Visual Basic) statement that imports `GettingStartedClient.ServiceReference1`.</span></span> <span data-ttu-id="88469-117">Esta instrucción importa el código generado por Visual Studio con la función **Agregar referencia de servicio** .</span><span class="sxs-lookup"><span data-stu-id="88469-117">This statement imports the code that Visual Studio generated with the **Add Service Reference** function.</span></span> <span data-ttu-id="88469-118">El código crea una instancia del proxy de WCF y llama a cada una de las operaciones de servicio que expone el servicio de la calculadora.</span><span class="sxs-lookup"><span data-stu-id="88469-118">The code instantiates the WCF proxy and calls each of the service operations that the calculator service exposes.</span></span> <span data-ttu-id="88469-119">A continuación, cierra el proxy y finaliza el programa.</span><span class="sxs-lookup"><span data-stu-id="88469-119">It then closes the proxy and ends the program.</span></span>

## <a name="test-the-wcf-client"></a><span data-ttu-id="88469-120">Prueba del cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="88469-120">Test the WCF client</span></span>

### <a name="test-the-application-from-visual-studio"></a><span data-ttu-id="88469-121">Prueba de la aplicación desde Visual Studio</span><span class="sxs-lookup"><span data-stu-id="88469-121">Test the application from Visual Studio</span></span>

1. <span data-ttu-id="88469-122">Guarde y compile la solución.</span><span class="sxs-lookup"><span data-stu-id="88469-122">Save and build the solution.</span></span>

2. <span data-ttu-id="88469-123">Seleccione la carpeta **GettingStartedLib** y, a continuación, seleccione **establecer como proyecto de inicio** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="88469-123">Select the **GettingStartedLib** folder, and then select **Set as Startup Project** from the shortcut menu.</span></span>

3. <span data-ttu-id="88469-124">En **proyectos de inicio**, seleccione **GettingStartedLib** en la lista desplegable y, a continuación, seleccione **Ejecutar** o presione **F5**.</span><span class="sxs-lookup"><span data-stu-id="88469-124">From **Startup Projects**, select **GettingStartedLib** from the drop-down list, then select **Run** or press **F5**.</span></span>

### <a name="test-the-application-from-a-command-prompt"></a><span data-ttu-id="88469-125">Prueba de la aplicación desde un símbolo del sistema</span><span class="sxs-lookup"><span data-stu-id="88469-125">Test the application from a command prompt</span></span>

1. <span data-ttu-id="88469-126">Abra un símbolo del sistema como administrador y vaya al directorio de la solución de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="88469-126">Open a command prompt as an administrator, and then navigate to your Visual Studio solution directory.</span></span> 

2. <span data-ttu-id="88469-127">Para iniciar el servicio: escriba *GettingStartedHost\bin\Debug\GettingStartedHost.exe*.</span><span class="sxs-lookup"><span data-stu-id="88469-127">To start the service: Enter *GettingStartedHost\bin\Debug\GettingStartedHost.exe*.</span></span>

3. <span data-ttu-id="88469-128">Para iniciar el cliente: Abra otro símbolo del sistema, navegue hasta el directorio de la solución de Visual Studio y escriba *GettingStartedClient\bin\Debug\GettingStartedClient.exe*.</span><span class="sxs-lookup"><span data-stu-id="88469-128">To start the client: Open another command prompt, navigate to your Visual Studio solution directory, then enter *GettingStartedClient\bin\Debug\GettingStartedClient.exe*.</span></span>

   <span data-ttu-id="88469-129">*GettingStartedHost. exe* genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="88469-129">*GettingStartedHost.exe* produces the following output:</span></span>

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

   <span data-ttu-id="88469-130">*GettingStartedClient. exe* genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="88469-130">*GettingStartedClient.exe* produces the following output:</span></span>

   ```text
   Add(100,15.99) = 115.99
   Subtract(145,76.54) = 68.46
   Multiply(9,81.25) = 731.25
   Divide(22,7) = 3.14285714285714

   Press <Enter> to terminate the client.
   ```

## <a name="next-steps"></a><span data-ttu-id="88469-131">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="88469-131">Next steps</span></span>

<span data-ttu-id="88469-132">Ya ha completado todas las tareas del tutorial de introducción a WCF.</span><span class="sxs-lookup"><span data-stu-id="88469-132">You've now completed all the tasks in the WCF get started tutorial.</span></span> <span data-ttu-id="88469-133">En este tutorial ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="88469-133">In this tutorial, you learned how to:</span></span>

<span data-ttu-id="88469-134">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="88469-134">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="88469-135">Agregue código para usar el cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="88469-135">Add code to use the WCF client.</span></span>
> - <span data-ttu-id="88469-136">Pruebe el cliente de WCF.</span><span class="sxs-lookup"><span data-stu-id="88469-136">Test the WCF client.</span></span>

<span data-ttu-id="88469-137">Si tiene problemas o errores en cualquiera de los pasos, siga los pasos descritos en el artículo de solución de problemas para corregirlos.</span><span class="sxs-lookup"><span data-stu-id="88469-137">If you have problems or errors in any of the steps, follow the steps in the troubleshooting article to fix them.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="88469-138">Solución de problemas de los tutoriales de introducción a WCF</span><span class="sxs-lookup"><span data-stu-id="88469-138">Troubleshoot the Get started with WCF tutorials</span></span>](troubleshooting-the-getting-started-tutorial.md)
