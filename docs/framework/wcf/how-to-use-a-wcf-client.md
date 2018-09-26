---
title: Cómo usar un cliente de Windows Communication Foundation
ms.date: 09/14/2018
helpviewer_keywords:
- WCF clients [WCF], using
dev_langs:
- CSharp
- VB
ms.assetid: 190349fc-0573-49c7-bb85-8e316df7f31f
ms.openlocfilehash: 12e911fb899cb85121c129b762828cdda01e64f1
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "47193088"
---
# <a name="how-to-use-a-windows-communication-foundation-client"></a>Cómo usar un cliente de Windows Communication Foundation

Esta es la última de las seis tareas necesarias para crear una aplicación básica de Windows Communication Foundation (WCF). Para obtener información general de las seis tareas, vea el tema [Tutorial de introducción](../../../docs/framework/wcf/getting-started-tutorial.md).

Una vez que se ha creado y configurado un proxy de Windows Communication Foundation (WCF), se puede crear una instancia de cliente y la aplicación cliente se puede compilar y usar para comunicarse con el servicio WCF. En este tema se describe procedimientos para crear instancias y usar a un cliente de WCF. Este procedimiento hace tres cosas:

1.  Crea una instancia de un cliente de WCF.

2.  Llama a las operaciones de servicio desde el proxy generado.

3.  Cierra el cliente una vez completada la llamada de operación.

## <a name="use-a-windows-communication-foundation-client"></a>Usar a un cliente de Windows Communication Foundation

Abra el archivo Program.cs o Program.vb del proyecto GettingStartedClient y reemplace el código existente por el código siguiente:

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

            //Step 3: Closing the client gracefully closes the connection and cleans up resources.
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
Imports GettingStartedClientVB2.ServiceReference1

Module Module1

    Sub Main()
        ' Step 1: Create an instance of the WCF proxy
        Dim Client As New CalculatorClient()

        'Step 2: Call the service operations.
        'Call the Add service operation.
        Dim value1 As Double = 100D
        Dim value2 As Double = 15.99D
        Dim result As Double = Client.Add(value1, value2)
        Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)

        'Call the Subtract service operation.
        value1 = 145D
        value2 = 76.54D
        result = Client.Subtract(value1, value2)
        Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result)

        'Call the Multiply service operation.
        value1 = 9D
        value2 = 81.25D
        result = Client.Multiply(value1, value2)
        Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result)

        'Call the Divide service operation.
        value1 = 22D
        value2 = 7D
        result = Client.Divide(value1, value2)
        Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result)

        ' Step 3: Closing the client gracefully closes the connection and cleans up resources.
        Client.Close()

        Console.WriteLine()
        Console.WriteLine("Press <ENTER> to terminate client.")
        Console.ReadLine()

    End Sub

End Module
```

Tenga en cuenta la `using` o `Imports` instrucción que importa el `GettingStartedClient.ServiceReference1`. Esta operación importa el código generado por **Add Service Reference** en Visual Studio. El código crea una instancia del proxy de WCF y, a continuación, llama a cada una de las operaciones de servicio expuestas por el servicio de calculadora, cierra al proxy y finaliza.

Se ha completado el tutorial. Ha definido un contrato de servicio, implementado el contrato de servicio, generado un proxy WCF, configurado una aplicación cliente de WCF y a continuación usado el proxy para llamar a operaciones de servicio. Para probar la aplicación, ejecute primero GettingStartedHost para iniciar el servicio y, a continuación, ejecute después GettingStartedClient.

La salida de GettingStartedHost debe ser similar a:

```text
The service is ready.Press <ENTER> to terminate service.Received Add(100,15.99)Return: 115.99Received Subtract(145,76.54)Return: 68.46Received Multiply(9,81.25)Return: 731.25Received Divide(22,7)Return: 3.14285714285714
```

La salida de GettingStartedClient debe ser similar a:

```text
Add(100,15.99) = 115.99Subtract(145,76.54) = 68.46Multiply(9,81.25) = 731.25Divide(22,7) = 3.14285714285714Press <ENTER> to terminate client.
```

## <a name="see-also"></a>Vea también

- [Creación de clientes](../../../docs/framework/wcf/building-clients.md)
- [Cómo crear un cliente](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)
- [Tutorial de introducción](../../../docs/framework/wcf/getting-started-tutorial.md)
- [Programación básica de WCF](../../../docs/framework/wcf/basic-wcf-programming.md)
- [Creación de un contrato dúplex](../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)
- [Acceso a los servicios con un contrato dúplex](../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)
- [Introducción](../../../docs/framework/wcf/samples/getting-started-sample.md)
- [Probar internamente](../../../docs/framework/wcf/samples/self-host.md)