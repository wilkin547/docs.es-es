---
title: 'Tutorial: Implementar un contrato de servicio de Windows Communication Foundation'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], implementing
ms.assetid: d5ab51ba-61ae-403e-b3c8-e2669e326806
ms.openlocfilehash: fa8c5457c636d7f37215f0d4b4fdbb1c96c9481e
ms.sourcegitcommit: 7156c0b9e4ce4ce5ecf48ce3d925403b638b680c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2019
ms.locfileid: "58463623"
---
# <a name="tutorial-implement-a-windows-communication-foundation-service-contract"></a>Tutorial: Implementar un contrato de servicio de Windows Communication Foundation

Este tutorial describe al segundo de cinco tareas necesarias para crear una aplicación básica de Windows Communication Foundation (WCF). Para obtener información general de los tutoriales, consulte [Tutorial: Introducción a las aplicaciones de Windows Communication Foundation](getting-started-tutorial.md).

El siguiente paso para crear una aplicación de WCF es agregar código para implementar la interfaz de servicio WCF que creó en el paso anterior. En este paso, creará una clase denominada `CalculatorService` que implementa definido por el usuario `ICalculator` interfaz. Cada método en el código siguiente llama a una operación de calculadora y escribe texto en la consola para probarlo. 

En este tutorial aprenderá a:
> [!div class="checklist"]
> - Agregue código para implementar el contrato de servicio WCF.
> - Compile la solución.

## <a name="add-code-to-implement-the-wcf-service-contract"></a>Agregue código para implementar el contrato de servicio WCF

En **GettingStartedLib**, abra el **Service1.cs** o **Service1.vb** de archivo y reemplace su código con el código siguiente:

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

## <a name="edit-appconfig"></a>Edición de App.config

Editar **App.config** en **GettingStartedLib** para reflejar los cambios realizados en el código.
- Para Visual C# proyectos:
  - Cambie la línea 14 a `<service name="GettingStartedLib.CalculatorService">`
  - Cambie la línea 17 a `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`
  - Cambie la línea 22 en `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`

- Para proyectos de Visual Basic:
  - Cambie la línea 14 a `<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`
  - Cambie la línea 17 a `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`
  - Cambie la línea 22 en `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`

## <a name="compile-the-code"></a>Compilar el código

Compile la solución para comprobar que no haya errores de compilación. Si usa Visual Studio, en el **compilar** menú, seleccione **compilar solución** (o presione **Ctrl**+**MAYÚS** + **B**).

## <a name="next-steps"></a>Pasos siguientes

En este tutorial ha aprendido a:
> [!div class="checklist"]
> - Agregue código para implementar el contrato de servicio WCF.
> - Compile la solución.

En el siguiente tutorial para aprender a ejecutar el servicio WCF.

> [!div class="nextstepaction"]
> [Tutorial: Hospedar y ejecutar un servicio WCF básico](how-to-host-and-run-a-basic-wcf-service.md)
