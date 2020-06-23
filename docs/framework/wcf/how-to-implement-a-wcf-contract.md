---
title: 'Tutorial: implementación de un contrato de servicio de Windows Communication Foundation'
description: Obtenga información sobre cómo agregar código para implementar una interfaz de servicio WCF como parte de una serie de artículos que le ayudarán a empezar a crear una aplicación WCF.
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], implementing
ms.assetid: d5ab51ba-61ae-403e-b3c8-e2669e326806
ms.openlocfilehash: 89f97610cccd42c2a5d298baa667327d077fd472
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244652"
---
# <a name="tutorial-implement-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="864bc-103">Tutorial: implementación de un contrato de servicio de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="864bc-103">Tutorial: Implement a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="864bc-104">En este tutorial se describe el segundo de las cinco tareas necesarias para crear una aplicación básica de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="864bc-104">This tutorial describes the second of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="864bc-105">Para obtener información general sobre los tutoriales, vea [Tutorial: Introducción a las aplicaciones de Windows Communication Foundation](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="864bc-105">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="864bc-106">El siguiente paso para crear una aplicación WCF es agregar código para implementar la interfaz de servicio WCF que creó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="864bc-106">The next step for creating a WCF application is to add code to implement the WCF service interface that you created in the previous step.</span></span> <span data-ttu-id="864bc-107">En este paso, creará una clase denominada `CalculatorService` que implementa la interfaz definida por el usuario `ICalculator` .</span><span class="sxs-lookup"><span data-stu-id="864bc-107">In this step, you create a class named `CalculatorService` that implements the user-defined `ICalculator` interface.</span></span> <span data-ttu-id="864bc-108">Cada método del código siguiente llama a una operación de calculadora y escribe texto en la consola para probarlo.</span><span class="sxs-lookup"><span data-stu-id="864bc-108">Each method in the following code calls a calculator operation and writes text to the console to test it.</span></span>

<span data-ttu-id="864bc-109">En este tutorial, aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="864bc-109">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="864bc-110">Agregue código para implementar el contrato de servicio de WCF.</span><span class="sxs-lookup"><span data-stu-id="864bc-110">Add code to implement the WCF service contract.</span></span>
> - <span data-ttu-id="864bc-111">Compile la solución.</span><span class="sxs-lookup"><span data-stu-id="864bc-111">Build the solution.</span></span>

## <a name="add-code-to-implement-the-wcf-service-contract"></a><span data-ttu-id="864bc-112">Agregar código para implementar el contrato de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="864bc-112">Add code to implement the WCF service contract</span></span>

<span data-ttu-id="864bc-113">En **GettingStartedLib**, abra el archivo **Service1.CS** o **Service1. VB** y reemplace su código por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="864bc-113">In **GettingStartedLib**, open the **Service1.cs** or **Service1.vb** file and replace its code with the following code:</span></span>

```csharp
using System;
using System.ServiceModel;

namespace GettingStartedLib
{
    public class CalculatorService : ICalculator
    {
        public double Add(double n1, double n2)
        {
            double result = n1 + n2;
            Console.WriteLine("Received Add({0},{1})", n1, n2);
            // Code added to write output to the console window.
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Subtract(double n1, double n2)
        {
            double result = n1 - n2;
            Console.WriteLine("Received Subtract({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Multiply(double n1, double n2)
        {
            double result = n1 * n2;
            Console.WriteLine("Received Multiply({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Divide(double n1, double n2)
        {
            double result = n1 / n2;
            Console.WriteLine("Received Divide({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }
    }
}
```

```vb
Imports System.ServiceModel

Namespace GettingStartedLib

    Public Class CalculatorService
        Implements ICalculator

        Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Add
            Dim result As Double = n1 + n2
            ' Code added to write output to the console window.
            Console.WriteLine("Received Add({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result
        End Function

        Public Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Subtract
            Dim result As Double = n1 - n2
            Console.WriteLine("Received Subtract({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function

        Public Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Multiply
            Dim result As Double = n1 * n2
            Console.WriteLine("Received Multiply({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function

        Public Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Divide
            Dim result As Double = n1 / n2
            Console.WriteLine("Received Divide({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function
    End Class
End Namespace
```

## <a name="edit-appconfig"></a><span data-ttu-id="864bc-114">Editar App.config</span><span class="sxs-lookup"><span data-stu-id="864bc-114">Edit App.config</span></span>

<span data-ttu-id="864bc-115">Edite **App.config** en **GettingStartedLib** para reflejar los cambios realizados en el código.</span><span class="sxs-lookup"><span data-stu-id="864bc-115">Edit **App.config** in **GettingStartedLib** to reflect the changes you made to the code.</span></span>

- <span data-ttu-id="864bc-116">Para los proyectos de Visual C#:</span><span class="sxs-lookup"><span data-stu-id="864bc-116">For Visual C# projects:</span></span>
  - <span data-ttu-id="864bc-117">Cambie la línea 14 a`<service name="GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="864bc-117">Change line 14 to `<service name="GettingStartedLib.CalculatorService">`</span></span>
  - <span data-ttu-id="864bc-118">Cambie la línea 17 a`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="864bc-118">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
  - <span data-ttu-id="864bc-119">Cambie la línea 22 a`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="864bc-119">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span></span>

- <span data-ttu-id="864bc-120">Para proyectos de Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="864bc-120">For Visual Basic projects:</span></span>
  - <span data-ttu-id="864bc-121">Cambie la línea 14 a`<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="864bc-121">Change line 14 to `<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`</span></span>
  - <span data-ttu-id="864bc-122">Cambie la línea 17 a`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="864bc-122">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
  - <span data-ttu-id="864bc-123">Cambie la línea 22 a`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="864bc-123">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="864bc-124">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="864bc-124">Compile the code</span></span>

<span data-ttu-id="864bc-125">Compile la solución para comprobar que no hay ningún error de compilación.</span><span class="sxs-lookup"><span data-stu-id="864bc-125">Build the solution to verify there aren't any compilation errors.</span></span> <span data-ttu-id="864bc-126">Si usa Visual Studio, en el menú **compilar** , seleccione **compilar solución** (o presione **Ctrl** + **MAYÚS** + **B**).</span><span class="sxs-lookup"><span data-stu-id="864bc-126">If you're using Visual Studio, on the **Build** menu select **Build Solution** (or press **Ctrl**+**Shift**+**B**).</span></span>

## <a name="next-steps"></a><span data-ttu-id="864bc-127">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="864bc-127">Next steps</span></span>

<span data-ttu-id="864bc-128">En este tutorial, ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="864bc-128">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="864bc-129">Agregue código para implementar el contrato de servicio de WCF.</span><span class="sxs-lookup"><span data-stu-id="864bc-129">Add code to implement the WCF service contract.</span></span>
> - <span data-ttu-id="864bc-130">Compile la solución.</span><span class="sxs-lookup"><span data-stu-id="864bc-130">Build the solution.</span></span>

<span data-ttu-id="864bc-131">Avance al siguiente tutorial para aprender a ejecutar el servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="864bc-131">Advance to the next tutorial to learn how to run the WCF service.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="864bc-132">Tutorial: hospedar y ejecutar un servicio WCF básico</span><span class="sxs-lookup"><span data-stu-id="864bc-132">Tutorial: Host and run a basic WCF service</span></span>](how-to-host-and-run-a-basic-wcf-service.md)
