---
title: "Cómo usar un cliente de Windows Communication Foundation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF clients [WCF], using
ms.assetid: 190349fc-0573-49c7-bb85-8e316df7f31f
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0330c386730c6b0436196bb5b85162bc4621c214
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-windows-communication-foundation-client"></a>Cómo usar un cliente de Windows Communication Foundation
Es la última de las seis tareas necesarias para crear una aplicación básica de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]. Para obtener información general de las seis de las tareas, consulte la [Tutorial de introducción](../../../docs/framework/wcf/getting-started-tutorial.md) tema.  
  
 Una vez creado y configurado un proxy de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], se puede crear una instancia de cliente y la aplicación de cliente se puede compilar y utilizar para comunicar con el servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. En este tema se describen los procedimientos para crear instancias y usar un cliente de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. Este procedimiento hace tres cosas:  
  
1.  Crea una instancia de un cliente de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
2.  Llama a las operaciones de servicio desde el proxy generado.  
  
3.  Cierra el cliente una vez completada la llamada de operación.  
  
### <a name="to-use-a-windows-communication-foundation-client"></a>Uso de un cliente de Windows Communication Foundation  
  
1.  Abra el archivo Program.cs o Program.vb del proyecto GettingStartedClient y reemplace el código existente por el código siguiente:  
  
    ```  
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
  
    ```  
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
  
     Observe la instrucción using o imports que importa GettingStartedClient.ServiceReference1. Esto importa el código generado por Agregar referencia de servicio en Visual Studio. El código crea una instancia del proxy de WCF y llama a cada una de las operaciones de servicio expuestas por el servicio de calculadora, cierra el proxy y finaliza.  
  
 Se ha completado el tutorial. Ha definido un contrato de servicio, implementado el contrato de servicio, generado un proxy WCF, configurado una aplicación cliente de WCF y a continuación usado el proxy para llamar a operaciones de servicio. Para probar la aplicación, ejecute primero GettingStartedHost para iniciar el servicio y ejecute después GettingStartedClient. La salida de GettingStartedHost debe ser similar a:  
  
```Output  
The service is ready.Press <ENTER> to terminate service.Received Add(100,15.99)Return: 115.99Received Subtract(145,76.54)Return: 68.46Received Multiply(9,81.25)Return: 731.25Received Divide(22,7)Return: 3.14285714285714  
```  
  
 La salida de GettingStartedClient debe ser similar a:  
  
```Output  
Add(100,15.99) = 115.99Subtract(145,76.54) = 68.46Multiply(9,81.25) = 731.25Divide(22,7) = 3.14285714285714Press <ENTER> to terminate client.  
```  
  
## <a name="see-also"></a>Vea también  
 [Creación de clientes](../../../docs/framework/wcf/building-clients.md)  
 [Cómo crear un cliente](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [Tutorial de introducción](../../../docs/framework/wcf/getting-started-tutorial.md)  
 [Programación básica de WCF](../../../docs/framework/wcf/basic-wcf-programming.md)  
 [Creación de un contrato dúplex](../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)  
 [Acceso a los servicios con un contrato dúplex](../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)  
 [Introducción](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [Probar internamente](../../../docs/framework/wcf/samples/self-host.md)
