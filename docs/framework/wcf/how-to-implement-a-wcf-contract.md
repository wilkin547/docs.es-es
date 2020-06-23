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
# <a name="tutorial-implement-a-windows-communication-foundation-service-contract"></a>Tutorial: implementación de un contrato de servicio de Windows Communication Foundation

En este tutorial se describe el segundo de las cinco tareas necesarias para crear una aplicación básica de Windows Communication Foundation (WCF). Para obtener información general sobre los tutoriales, vea [Tutorial: Introducción a las aplicaciones de Windows Communication Foundation](getting-started-tutorial.md).

El siguiente paso para crear una aplicación WCF es agregar código para implementar la interfaz de servicio WCF que creó en el paso anterior. En este paso, creará una clase denominada `CalculatorService` que implementa la interfaz definida por el usuario `ICalculator` . Cada método del código siguiente llama a una operación de calculadora y escribe texto en la consola para probarlo.

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

## <a name="edit-appconfig"></a>Editar App.config

Edite **App.config** en **GettingStartedLib** para reflejar los cambios realizados en el código.

- Para los proyectos de Visual C#:
  - Cambie la línea 14 a`<service name="GettingStartedLib.CalculatorService">`
  - Cambie la línea 17 a`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`
  - Cambie la línea 22 a`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`

- Para proyectos de Visual Basic:
  - Cambie la línea 14 a`<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`
  - Cambie la línea 17 a`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`
  - Cambie la línea 22 a`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`

## <a name="compile-the-code"></a>Compilar el código

Compile la solución para comprobar que no hay ningún error de compilación. Si usa Visual Studio, en el menú **compilar** , seleccione **compilar solución** (o presione **Ctrl** + **MAYÚS** + **B**).

## <a name="next-steps"></a>Pasos siguientes

En este tutorial, ha aprendido a:
> [!div class="checklist"]
>
> - Agregue código para implementar el contrato de servicio de WCF.
> - Compile la solución.

Avance al siguiente tutorial para aprender a ejecutar el servicio WCF.

> [!div class="nextstepaction"]
> [Tutorial: hospedar y ejecutar un servicio WCF básico](how-to-host-and-run-a-basic-wcf-service.md)
