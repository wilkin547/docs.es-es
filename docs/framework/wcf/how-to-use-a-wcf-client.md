---
title: "Cómo usar un cliente de Windows Communication Foundation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF clients [WCF], using
ms.assetid: 190349fc-0573-49c7-bb85-8e316df7f31f
caps.latest.revision: "38"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0d9d2fb363aa753edc6d2d4002a948fbb35b75ad
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-use-a-windows-communication-foundation-client"></a><span data-ttu-id="554a0-102">Cómo usar un cliente de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="554a0-102">How to: Use a Windows Communication Foundation Client</span></span>
<span data-ttu-id="554a0-103">Es la última de las seis tareas necesarias para crear una aplicación básica de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="554a0-103">This is the last of six tasks required to create a basic [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] application.</span></span> <span data-ttu-id="554a0-104">Para obtener información general de las seis de las tareas, consulte la [Tutorial de introducción](../../../docs/framework/wcf/getting-started-tutorial.md) tema.</span><span class="sxs-lookup"><span data-stu-id="554a0-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>  
  
 <span data-ttu-id="554a0-105">Una vez creado y configurado un proxy de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], se puede crear una instancia de cliente y la aplicación de cliente se puede compilar y utilizar para comunicar con el servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="554a0-105">Once a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] proxy has been created and configured, a client instance can be created and the client application can be compiled and used to communicate with the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="554a0-106">En este tema se describen los procedimientos para crear instancias y usar un cliente de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="554a0-106">This topic describes procedures for instantiating and using a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client.</span></span> <span data-ttu-id="554a0-107">Este procedimiento hace tres cosas:</span><span class="sxs-lookup"><span data-stu-id="554a0-107">This procedure does three things:</span></span>  
  
1.  <span data-ttu-id="554a0-108">Crea una instancia de un cliente de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="554a0-108">Instantiates a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client.</span></span>  
  
2.  <span data-ttu-id="554a0-109">Llama a las operaciones de servicio desde el proxy generado.</span><span class="sxs-lookup"><span data-stu-id="554a0-109">Calls the service operations from the generated proxy.</span></span>  
  
3.  <span data-ttu-id="554a0-110">Cierra el cliente una vez completada la llamada de operación.</span><span class="sxs-lookup"><span data-stu-id="554a0-110">Closes the client once the operation call is completed.</span></span>  
  
### <a name="to-use-a-windows-communication-foundation-client"></a><span data-ttu-id="554a0-111">Uso de un cliente de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="554a0-111">To use a Windows Communication Foundation client</span></span>  
  
1.  <span data-ttu-id="554a0-112">Abra el archivo Program.cs o Program.vb del proyecto GettingStartedClient y reemplace el código existente por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="554a0-112">Open the Program.cs or Program.vb file from the GettingStartedClient project and replace the existing code with the following code:</span></span>  
  
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
  
     <span data-ttu-id="554a0-113">Observe la instrucción using o imports que importa GettingStartedClient.ServiceReference1.</span><span class="sxs-lookup"><span data-stu-id="554a0-113">Notice the using or imports statement that imports the GettingStartedClient.ServiceReference1.</span></span> <span data-ttu-id="554a0-114">Esto importa el código generado por Agregar referencia de servicio en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="554a0-114">This imports the code generated by Add Service Reference in Visual Studio.</span></span> <span data-ttu-id="554a0-115">El código crea una instancia del proxy de WCF y llama a cada una de las operaciones de servicio expuestas por el servicio de calculadora, cierra el proxy y finaliza.</span><span class="sxs-lookup"><span data-stu-id="554a0-115">The code instantiates the WCF proxy and then calls each of the service operations exposed by the calculator service, closes the proxy and terminates.</span></span>  
  
 <span data-ttu-id="554a0-116">Se ha completado el tutorial.</span><span class="sxs-lookup"><span data-stu-id="554a0-116">You have now completed the tutorial.</span></span> <span data-ttu-id="554a0-117">Ha definido un contrato de servicio, implementado el contrato de servicio, generado un proxy WCF, configurado una aplicación cliente de WCF y a continuación usado el proxy para llamar a operaciones de servicio.</span><span class="sxs-lookup"><span data-stu-id="554a0-117">You defined a service contract, implemented the service contract, generated a WCF proxy, configured a WCF client application, and then used the proxy to call service operations.</span></span> <span data-ttu-id="554a0-118">Para probar la aplicación, ejecute primero GettingStartedHost para iniciar el servicio y ejecute después GettingStartedClient.</span><span class="sxs-lookup"><span data-stu-id="554a0-118">To test out the application first run GettingStartedHost to start the service and then run GettingStartedClient.</span></span> <span data-ttu-id="554a0-119">La salida de GettingStartedHost debe ser similar a:</span><span class="sxs-lookup"><span data-stu-id="554a0-119">The output from GettingStartedHost should look like this:</span></span>  
  
```Output  
The service is ready.Press <ENTER> to terminate service.Received Add(100,15.99)Return: 115.99Received Subtract(145,76.54)Return: 68.46Received Multiply(9,81.25)Return: 731.25Received Divide(22,7)Return: 3.14285714285714  
```  
  
 <span data-ttu-id="554a0-120">La salida de GettingStartedClient debe ser similar a:</span><span class="sxs-lookup"><span data-stu-id="554a0-120">The output from GettingStartedClient should look like this:</span></span>  
  
```Output  
Add(100,15.99) = 115.99Subtract(145,76.54) = 68.46Multiply(9,81.25) = 731.25Divide(22,7) = 3.14285714285714Press <ENTER> to terminate client.  
```  
  
## <a name="see-also"></a><span data-ttu-id="554a0-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="554a0-121">See Also</span></span>  
 [<span data-ttu-id="554a0-122">Creación de clientes</span><span class="sxs-lookup"><span data-stu-id="554a0-122">Building Clients</span></span>](../../../docs/framework/wcf/building-clients.md)  
 [<span data-ttu-id="554a0-123">Cómo crear un cliente</span><span class="sxs-lookup"><span data-stu-id="554a0-123">How to: Create a Client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [<span data-ttu-id="554a0-124">Tutorial de introducción</span><span class="sxs-lookup"><span data-stu-id="554a0-124">Getting Started Tutorial</span></span>](../../../docs/framework/wcf/getting-started-tutorial.md)  
 [<span data-ttu-id="554a0-125">Programación básica de WCF</span><span class="sxs-lookup"><span data-stu-id="554a0-125">Basic WCF Programming</span></span>](../../../docs/framework/wcf/basic-wcf-programming.md)  
 [<span data-ttu-id="554a0-126">Cómo: crear un contrato dúplex</span><span class="sxs-lookup"><span data-stu-id="554a0-126">How to: Create a Duplex Contract</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)  
 [<span data-ttu-id="554a0-127">Cómo: obtener acceso a servicios con un contrato dúplex</span><span class="sxs-lookup"><span data-stu-id="554a0-127">How to: Access Services with a Duplex Contract</span></span>](../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)  
 [<span data-ttu-id="554a0-128">Introducción</span><span class="sxs-lookup"><span data-stu-id="554a0-128">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [<span data-ttu-id="554a0-129">Autohospedaje</span><span class="sxs-lookup"><span data-stu-id="554a0-129">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)
