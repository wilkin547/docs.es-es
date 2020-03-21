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
# <a name="tutorial-implement-a-windows-communication-foundation-service-contract"></a>Tutorial: Implementar un contrato de servicio de Windows Communication Foundation

En este tutorial se describe la segunda de las cinco tareas necesarias para crear una aplicación básica de Windows Communication Foundation (WCF). Para obtener información general sobre los tutoriales, vea [Tutorial: Introducción a](getting-started-tutorial.md)las aplicaciones de Windows Communication Foundation .

El siguiente paso para crear una aplicación WCF es agregar código para implementar la interfaz de servicio WCF que creó en el paso anterior. En este paso, creará `CalculatorService` una clase denominada que `ICalculator` implemente la interfaz definida por el usuario. Cada método del código siguiente llama a una operación de calculadora y escribe texto en la consola para probarlo.

En este tutorial, aprenderá a:
> [!div class="checklist"]
>
> - Agregue código para implementar el contrato de servicio WCF.
> - Compile la solución.

## <a name="add-code-to-implement-the-wcf-service-contract"></a>Agregar código para implementar el contrato de servicio WCF

En **GettingStartedLib**, abra el archivo **Service1.cs** o **Service1.vb** y reemplace su código por el código siguiente:

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

## <a name="edit-appconfig"></a>Editar App.config

Edite **App.config** en **GettingStartedLib** para reflejar los cambios realizados en el código.

- Para los proyectos de Visual C.
  - Cambie la línea 14 a`<service name="GettingStartedLib.CalculatorService">`
  - Cambie la línea 17 a`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`
  - Cambie la línea 22 a`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`

- Para proyectos de Visual Basic:
  - Cambie la línea 14 a`<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`
  - Cambie la línea 17 a`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`
  - Cambie la línea 22 a`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`

## <a name="compile-the-code"></a>Compilar el código

Compile la solución para comprobar que no hay errores de compilación. Si usa Visual Studio, en el menú **Compilar,** seleccione **Compilar solución** (o presione **Ctrl**+**Shift**+**B**).

## <a name="next-steps"></a>Pasos siguientes

En este tutorial, ha aprendido a:
> [!div class="checklist"]
>
> - Agregue código para implementar el contrato de servicio WCF.
> - Compile la solución.

Avance al siguiente tutorial para aprender a ejecutar el servicio WCF.

> [!div class="nextstepaction"]
> [Tutorial: Hospede y ejecute un servicio WCF básico](how-to-host-and-run-a-basic-wcf-service.md)
