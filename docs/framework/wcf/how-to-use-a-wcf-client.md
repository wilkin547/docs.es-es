---
title: 'Tutorial: Use un cliente de Windows Communication Foundation'
ms.date: 03/19/2019
helpviewer_keywords:
- WCF clients [WCF], using
dev_langs:
- CSharp
- VB
ms.assetid: 190349fc-0573-49c7-bb85-8e316df7f31f
ms.openlocfilehash: d2357c134aef8da204dcdb19d6c1fc93cfdc068c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184011"
---
# <a name="tutorial-use-a-windows-communication-foundation-client"></a>Tutorial: Use un cliente de Windows Communication Foundation

En este tutorial se describe la última de las cinco tareas necesarias para crear una aplicación básica de Windows Communication Foundation (WCF). Para obtener información general sobre los tutoriales, vea [Tutorial: Introducción a](getting-started-tutorial.md)las aplicaciones de Windows Communication Foundation .

Después de crear y configurar un proxy de Windows Communication Foundation (WCF), cree una instancia de cliente y compile la aplicación cliente. A continuación, se usa para comunicarse con el servicio WCF.

En este tutorial, aprenderá a:
> [!div class="checklist"]
>
> - Agregue código para usar el cliente WCF.
> - Pruebe el cliente WCF.

## <a name="add-code-to-use-the-wcf-client"></a>Agregar código para usar el cliente WCF

El código de cliente realiza los pasos siguientes:

- Crea una instancia del cliente WCF.
- Llama a las operaciones de servicio desde el proxy generado.
- Cierra el cliente una vez completada la llamada de operación.

Abra el archivo **Program.cs** o **Module1.vb** desde el proyecto **GettingStartedClient** y reemplace su código por el código siguiente:

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

Observe `using` la instrucción (para `Imports` Visual C-) o `GettingStartedClient.ServiceReference1`(para Visual Basic) que importa . Esta instrucción importa el código que Visual Studio generó con la función Agregar referencia de **servicio.** El código crea una instancia del proxy WCF y llama a cada una de las operaciones de servicio que expone el servicio de calculadora. A continuación, cierra el proxy y finaliza el programa.

## <a name="test-the-wcf-client"></a>Pruebe el cliente WCF

### <a name="test-the-application-from-visual-studio"></a>Pruebe la aplicación desde Visual Studio

1. Guarde y genere la solución.

2. Seleccione la carpeta **GettingStartedLib** y, a continuación, seleccione **Establecer como proyecto** de inicio en el menú contextual.

3. En **Proyectos**de inicio , seleccione **GettingStartedLib** en la lista desplegable y, a continuación, seleccione **Ejecutar** o presione **F5**.

### <a name="test-the-application-from-a-command-prompt"></a>Pruebe la aplicación desde un símbolo del sistema

1. Abra un símbolo del sistema como administrador y, a continuación, vaya al directorio de la solución de Visual Studio.

2. Para iniciar el servicio: escriba *GettingStartedHost-bin-Debug-GettingStartedHost.exe*.

3. Para iniciar el cliente: abra otro símbolo del sistema, desplácese hasta el directorio de la solución de Visual Studio y, a continuación, escriba *GettingStartedClient.*

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

Ahora ha completado todas las tareas en el WCF empezar tutorial. En este tutorial, ha aprendido a:

En este tutorial, aprenderá a:
> [!div class="checklist"]
>
> - Agregue código para usar el cliente WCF.
> - Pruebe el cliente WCF.

Si tiene problemas o errores en cualquiera de los pasos, siga los pasos del artículo de solución de problemas para solucionarlos.

> [!div class="nextstepaction"]
> [Solucionar problemas de los tutoriales de Introducción a WCF](troubleshooting-the-getting-started-tutorial.md)
