---
title: "C&#243;mo usar un cliente de Windows Communication Foundation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "clientes de WCF [WCF], utilizar"
ms.assetid: 190349fc-0573-49c7-bb85-8e316df7f31f
caps.latest.revision: 38
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 38
---
# C&#243;mo usar un cliente de Windows Communication Foundation
Es la última de las seis tareas necesarias para crear una aplicación básica de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].  Para obtener información general de las seis tareas, consulte el tema [Tutorial de introducción](../../../docs/framework/wcf/getting-started-tutorial.md).  
  
 Una vez creado y configurado un proxy de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], se puede crear una instancia de cliente y la aplicación de cliente se puede compilar y utilizar para comunicar con el servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  En este tema se describen los procedimientos para crear instancias y usar un cliente de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  Este procedimiento hace tres cosas:  
  
1.  Crea una instancia de un cliente de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
2.  Llama a las operaciones de servicio desde el proxy generado.  
  
3.  Cierra el cliente una vez completada la llamada de operación.  
  
### Uso de un cliente de Windows Communication Foundation  
  
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
  
     Observe la instrucción using o imports que importa GettingStartedClient.ServiceReference1.  Esto importa el código generado por Agregar referencia de servicio en Visual Studio.  El código crea una instancia del proxy de WCF y llama a cada una de las operaciones de servicio expuestas por el servicio de calculadora, cierra el proxy y finaliza.  
  
 Se ha completado el tutorial.  Ha definido un contrato de servicio, implementado el contrato de servicio, generado un proxy WCF, configurado una aplicación cliente de WCF y a continuación usado el proxy para llamar a operaciones de servicio.  Para probar la aplicación, ejecute primero GettingStartedHost para iniciar el servicio y ejecute después GettingStartedClient.  La salida de GettingStartedHost debe ser similar a:  
  
```Output  
  
            El servicio está listo.  Presione <ENTRAR> para terminar el servicio.  Suma recibida(100,15.99)  
Retorno: 115,99  
Resta recibida(145,76.54)  
Retorno: 68,46  
Multiplicación recibida(9,81.25)  
Retorno: 731,25  
División recibida(22,7)  
Retorno: 3,14285714285714    
```  
  
 La salida de GettingStartedClient debe ser similar a:  
  
```Output  
  
            Sumar(100;15,99) = 115,99  
Restar(145;76,54) = 68,46  
Multiplicar(9;81,25) = 731,25  
Dividir(22;7) = 3.14285714285714  
  
Presione <ENTRAR> para terminar el cliente.  
  
```  
  
## Vea también  
 [Creación de clientes](../../../docs/framework/wcf/building-clients.md)   
 [Cómo crear un cliente](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)   
 [Tutorial de introducción](../../../docs/framework/wcf/getting-started-tutorial.md)   
 [Programación básica de WCF](../../../docs/framework/wcf/basic-wcf-programming.md)   
 [Creación de un contrato dúplex](../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)   
 [Cómo: Obtener acceso a los servicios con un contrato dúplex](../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)   
 [Introducción:](../../../docs/framework/wcf/samples/getting-started-sample.md)   
 [Autohospedaje](../../../docs/framework/wcf/samples/self-host.md)