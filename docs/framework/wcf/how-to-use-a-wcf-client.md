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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61928848"
---
# <a name="tutorial-use-a-windows-communication-foundation-client"></a>Tutorial: Usar a un cliente de Windows Communication Foundation

Este tutorial describen las últimas cinco tareas necesarias para crear una aplicación básica de Windows Communication Foundation (WCF). Para obtener información general de los tutoriales, consulte [Tutorial: Introducción a las aplicaciones de Windows Communication Foundation](getting-started-tutorial.md).

Una vez que haya creado y configurado a un proxy de Windows Communication Foundation (WCF), se crea una instancia de cliente y se compila la aplicación cliente. A continuación, se utiliza para comunicarse con el servicio WCF. 

En este tutorial aprenderá a:
> [!div class="checklist"]
> - Agregar código para usar al cliente de WCF.
> - Probar al cliente WCF.

## <a name="add-code-to-use-the-wcf-client"></a>Agregar código para usar al cliente de WCF

El código de cliente hace lo siguiente:
- Crea una instancia del cliente WCF.
- Llama a las operaciones de servicio desde el proxy generado.
- Cierra al cliente una vez completada la llamada de operación.

Abra el **Program.cs** o **Module1.vb** de archivos desde el **GettingStartedClient** del proyecto y reemplace su código con el código siguiente:

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

Tenga en cuenta la `using` (para Visual C#) o `Imports` (para Visual Basic) instrucción que importa `GettingStartedClient.ServiceReference1`. Esta instrucción importa el código generado por Visual Studio con el **Add Service Reference** función. El código crea una instancia del proxy de WCF y llama a cada una de las operaciones de servicio que expone el servicio de calculadora. A continuación, cierra al proxy y finaliza el programa.

## <a name="test-the-wcf-client"></a>Probar al cliente WCF

### <a name="test-the-application-from-visual-studio"></a>Probar la aplicación desde Visual Studio

1. Guarde y compile la solución.

2. Seleccione el **GettingStartedLib** carpeta y, a continuación, seleccione **establecer como proyecto de inicio** en el menú contextual.

3. Desde **proyectos de inicio**, seleccione **GettingStartedLib** en la lista desplegable, seleccione **ejecutar** o presione **F5**.

### <a name="test-the-application-from-a-command-prompt"></a>Probar la aplicación desde un símbolo del sistema

1. Abra un símbolo del sistema como administrador y, a continuación, navegue hasta el directorio de la solución de Visual Studio. 

2. Para iniciar el servicio: Escriba *GettingStartedHost\bin\Debug\GettingStartedHost.exe*.

3. Para iniciar al cliente: Abra otro símbolo del sistema, navegue hasta el directorio de la solución de Visual Studio y luego escriba *GettingStartedClient\bin\Debug\GettingStartedClient.exe*.

   *GettingStartedHost.exe* genera el siguiente resultado:

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

   *GettingStartedClient.exe* genera el siguiente resultado:

   ```text
   Add(100,15.99) = 115.99
   Subtract(145,76.54) = 68.46
   Multiply(9,81.25) = 731.25
   Divide(22,7) = 3.14285714285714

   Press <Enter> to terminate the client.
   ```

## <a name="next-steps"></a>Pasos siguientes

Ahora ha completado todas las tareas en el tutorial de introducción de get WCF. En este tutorial ha aprendido a:

En este tutorial aprenderá a:
> [!div class="checklist"]
> - Agregar código para usar al cliente de WCF.
> - Probar al cliente WCF.

Si tiene problemas o errores en cualquiera de los pasos, siga los pasos descritos en el artículo de solución de problemas para corregirlos.

> [!div class="nextstepaction"]
> [Solución de problemas de la operación Get a trabajar con los tutoriales WCF](troubleshooting-the-getting-started-tutorial.md)
