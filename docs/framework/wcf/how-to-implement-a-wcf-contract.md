---
title: 'Tutorial: Implementar un contrato de servicio de Windows Communication Foundation'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], implementing
ms.assetid: d5ab51ba-61ae-403e-b3c8-e2669e326806
ms.openlocfilehash: debdeeac7064f5bae21622b2d9de84a4d8a0e66f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184066"
---
# <a name="tutorial-implement-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="c3b10-102">Tutorial: Implementar un contrato de servicio de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="c3b10-102">Tutorial: Implement a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="c3b10-103">En este tutorial se describe la segunda de las cinco tareas necesarias para crear una aplicación básica de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="c3b10-103">This tutorial describes the second of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="c3b10-104">Para obtener información general sobre los tutoriales, vea [Tutorial: Introducción a](getting-started-tutorial.md)las aplicaciones de Windows Communication Foundation .</span><span class="sxs-lookup"><span data-stu-id="c3b10-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="c3b10-105">El siguiente paso para crear una aplicación WCF es agregar código para implementar la interfaz de servicio WCF que creó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="c3b10-105">The next step for creating a WCF application is to add code to implement the WCF service interface that you created in the previous step.</span></span> <span data-ttu-id="c3b10-106">En este paso, creará `CalculatorService` una clase denominada que `ICalculator` implemente la interfaz definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="c3b10-106">In this step, you create a class named `CalculatorService` that implements the user-defined `ICalculator` interface.</span></span> <span data-ttu-id="c3b10-107">Cada método del código siguiente llama a una operación de calculadora y escribe texto en la consola para probarlo.</span><span class="sxs-lookup"><span data-stu-id="c3b10-107">Each method in the following code calls a calculator operation and writes text to the console to test it.</span></span>

<span data-ttu-id="c3b10-108">En este tutorial, aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="c3b10-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="c3b10-109">Agregue código para implementar el contrato de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="c3b10-109">Add code to implement the WCF service contract.</span></span>
> - <span data-ttu-id="c3b10-110">Compile la solución.</span><span class="sxs-lookup"><span data-stu-id="c3b10-110">Build the solution.</span></span>

## <a name="add-code-to-implement-the-wcf-service-contract"></a><span data-ttu-id="c3b10-111">Agregar código para implementar el contrato de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="c3b10-111">Add code to implement the WCF service contract</span></span>

<span data-ttu-id="c3b10-112">En **GettingStartedLib**, abra el archivo **Service1.cs** o **Service1.vb** y reemplace su código por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="c3b10-112">In **GettingStartedLib**, open the **Service1.cs** or **Service1.vb** file and replace its code with the following code:</span></span>

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

## <a name="edit-appconfig"></a><span data-ttu-id="c3b10-113">Editar App.config</span><span class="sxs-lookup"><span data-stu-id="c3b10-113">Edit App.config</span></span>

<span data-ttu-id="c3b10-114">Edite **App.config** en **GettingStartedLib** para reflejar los cambios realizados en el código.</span><span class="sxs-lookup"><span data-stu-id="c3b10-114">Edit **App.config** in **GettingStartedLib** to reflect the changes you made to the code.</span></span>

- <span data-ttu-id="c3b10-115">Para los proyectos de Visual C.</span><span class="sxs-lookup"><span data-stu-id="c3b10-115">For Visual C# projects:</span></span>
  - <span data-ttu-id="c3b10-116">Cambie la línea 14 a`<service name="GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="c3b10-116">Change line 14 to `<service name="GettingStartedLib.CalculatorService">`</span></span>
  - <span data-ttu-id="c3b10-117">Cambie la línea 17 a`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="c3b10-117">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
  - <span data-ttu-id="c3b10-118">Cambie la línea 22 a`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="c3b10-118">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span></span>

- <span data-ttu-id="c3b10-119">Para proyectos de Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="c3b10-119">For Visual Basic projects:</span></span>
  - <span data-ttu-id="c3b10-120">Cambie la línea 14 a`<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="c3b10-120">Change line 14 to `<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`</span></span>
  - <span data-ttu-id="c3b10-121">Cambie la línea 17 a`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="c3b10-121">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
  - <span data-ttu-id="c3b10-122">Cambie la línea 22 a`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="c3b10-122">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="c3b10-123">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="c3b10-123">Compile the code</span></span>

<span data-ttu-id="c3b10-124">Compile la solución para comprobar que no hay errores de compilación.</span><span class="sxs-lookup"><span data-stu-id="c3b10-124">Build the solution to verify there aren't any compilation errors.</span></span> <span data-ttu-id="c3b10-125">Si usa Visual Studio, en el menú **Compilar,** seleccione **Compilar solución** (o presione **Ctrl**+**Shift**+**B**).</span><span class="sxs-lookup"><span data-stu-id="c3b10-125">If you're using Visual Studio, on the **Build** menu select **Build Solution** (or press **Ctrl**+**Shift**+**B**).</span></span>

## <a name="next-steps"></a><span data-ttu-id="c3b10-126">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="c3b10-126">Next steps</span></span>

<span data-ttu-id="c3b10-127">En este tutorial, ha aprendido a:</span><span class="sxs-lookup"><span data-stu-id="c3b10-127">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="c3b10-128">Agregue código para implementar el contrato de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="c3b10-128">Add code to implement the WCF service contract.</span></span>
> - <span data-ttu-id="c3b10-129">Compile la solución.</span><span class="sxs-lookup"><span data-stu-id="c3b10-129">Build the solution.</span></span>

<span data-ttu-id="c3b10-130">Avance al siguiente tutorial para aprender a ejecutar el servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="c3b10-130">Advance to the next tutorial to learn how to run the WCF service.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c3b10-131">Tutorial: Hospede y ejecute un servicio WCF básico</span><span class="sxs-lookup"><span data-stu-id="c3b10-131">Tutorial: Host and run a basic WCF service</span></span>](how-to-host-and-run-a-basic-wcf-service.md)
