---
title: 'Tutorial: Implementar un contrato de servicio de Windows Communication Foundation'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], implementing
ms.assetid: d5ab51ba-61ae-403e-b3c8-e2669e326806
ms.openlocfilehash: 05923dc0a2223da5e5fcda483abc1ee1dd2d643f
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928705"
---
# <a name="tutorial-implement-a-windows-communication-foundation-service-contract"></a>Tutorial: Implementar un contrato de servicio de Windows Communication Foundation

En este tutorial se describe el segundo de las cinco tareas necesarias para crear una aplicación básica de Windows Communication Foundation (WCF). Para obtener información general sobre los tutoriales, [vea Tutorial: Introducción a las aplicaciones](getting-started-tutorial.md)Windows Communication Foundation.

El siguiente paso para crear una aplicación WCF es agregar código para implementar la interfaz de servicio WCF que creó en el paso anterior. En este paso, creará una clase denominada `CalculatorService` que implementa la interfaz definida por `ICalculator` el usuario. Cada método del código siguiente llama a una operación de calculadora y escribe texto en la consola para probarlo. 

En este tutorial, aprenderá a:
> [!div class="checklist"]
>
> - Agregue código para implementar el contrato de servicio de WCF.
> - Compile la solución.

## <a name="add-code-to-implement-the-wcf-service-contract"></a>Agregar código para implementar el contrato de servicio de WCF

En **GettingStartedLib**, abra el archivo **Service1.CS** o **Service1. VB** y reemplace su código por el código siguiente:

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

## <a name="edit-appconfig"></a>Edición de App. config

Edite el **archivo app. config** en **GettingStartedLib** para reflejar los cambios realizados en el código.

- Para proyectos C# visuales:
  - Cambie la línea 14 a`<service name="GettingStartedLib.CalculatorService">`
  - Cambie la línea 17 a`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`
  - Cambie la línea 22 a`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`

- Para proyectos de Visual Basic:
  - Cambie la línea 14 a`<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`
  - Cambie la línea 17 a`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`
  - Cambie la línea 22 a`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`

## <a name="compile-the-code"></a>Compilar el código

Compile la solución para comprobar que no hay ningún error de compilación. Si usa Visual Studio, en el menú **compilar** , seleccione **compilar solución** (o presione **Ctrl**+**MAYÚS**+**B**).

## <a name="next-steps"></a>Pasos siguientes

En este tutorial aprendió lo siguiente:
> [!div class="checklist"]
>
> - Agregue código para implementar el contrato de servicio de WCF.
> - Compile la solución.

Avance al siguiente tutorial para aprender a ejecutar el servicio WCF.

> [!div class="nextstepaction"]
> [Tutorial: Hospedar y ejecutar un servicio WCF básico](how-to-host-and-run-a-basic-wcf-service.md)
