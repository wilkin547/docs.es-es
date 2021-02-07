---
description: 'Más información acerca de: flujo de transacciones WS'
title: Flujo de la transacción WS
ms.date: 03/30/2017
helpviewer_keywords:
- Transactions
ms.assetid: f8eecbcf-990a-4dbb-b29b-c3f9e3b396bd
ms.openlocfilehash: 4d0a0af77dd516bf98c5dc8318ac110a31e731e7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99668375"
---
# <a name="ws-transaction-flow"></a><span data-ttu-id="6055a-103">Flujo de la transacción WS</span><span class="sxs-lookup"><span data-stu-id="6055a-103">WS Transaction Flow</span></span>

<span data-ttu-id="6055a-104">Este ejemplo muestra el uso de una transacción coordinada por cliente y las opciones de servidor y cliente para el flujo de la transacción utilizando la Transacción atómica del WS o el protocolo OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="6055a-104">This sample demonstrates the use of a client-coordinated transaction and the client and server options for transaction flow using either the WS-Atomic Transaction or OleTransactions protocol.</span></span> <span data-ttu-id="6055a-105">Este ejemplo se basa en el [Introducción](getting-started-sample.md) que implementa un servicio de calculadora, pero las operaciones se atribuyen para mostrar el uso de `TransactionFlowAttribute` con la enumeración **TransactionFlowOption** para determinar en qué grado se habilita el flujo de transacciones.</span><span class="sxs-lookup"><span data-stu-id="6055a-105">This sample is based on the [Getting Started](getting-started-sample.md) that implements a calculator service but the operations are attributed to demonstrate the use of the `TransactionFlowAttribute` with the **TransactionFlowOption** enumeration to determine to what degree transaction flow is enabled.</span></span> <span data-ttu-id="6055a-106">Dentro del ámbito de la transacción fluida, un registro de las operaciones solicitadas se escribe a una base de datos y se conserva hasta que la transacción coordinada por el cliente se ha completado - si la transacción del cliente no se completa, la transacción del Servicio Web se asegura de que no se confirmen las actualizaciones adecuadas a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="6055a-106">Within the scope of the flowed transaction, a log of the requested operations is written to a database and persists until the client coordinated transaction has completed - if the client transaction does not complete, the Web service transaction ensures that the appropriate updates to the database are not committed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6055a-107">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="6055a-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="6055a-108">Después de iniciar una conexión al servicio y una transacción, el cliente tiene acceso a varias operaciones del servicio.</span><span class="sxs-lookup"><span data-stu-id="6055a-108">After initiating a connection to the service and a transaction, the client accesses several service operations.</span></span> <span data-ttu-id="6055a-109">El contrato para el servicio se define como sigue con cada una de las operaciones que muestran un valor diferente para `TransactionFlowOption`:</span><span class="sxs-lookup"><span data-stu-id="6055a-109">The contract for the service is defined as follows with each of the operations demonstrating a different setting for the `TransactionFlowOption`.</span></span>  

```csharp
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    [TransactionFlow(TransactionFlowOption.Mandatory)]  
    double Add(double n1, double n2);  
    [OperationContract]  
    [TransactionFlow(TransactionFlowOption.Allowed)]  
    double Subtract(double n1, double n2);  
    [OperationContract]  
    [TransactionFlow(TransactionFlowOption.NotAllowed)]  
    double Multiply(double n1, double n2);  
    [OperationContract]  
    double Divide(double n1, double n2);
}  
```

 <span data-ttu-id="6055a-110">Esto define las operaciones en el orden que serán procesadas:</span><span class="sxs-lookup"><span data-stu-id="6055a-110">This defines the operations in the order they are to be processed:</span></span>  
  
- <span data-ttu-id="6055a-111">Una solicitud de operación `Add` debe incluir una transacción fluida.</span><span class="sxs-lookup"><span data-stu-id="6055a-111">An `Add` operation request must include a flowed transaction.</span></span>  
  
- <span data-ttu-id="6055a-112">Una solicitud de operación `Subtract` puede incluir una transacción fluida.</span><span class="sxs-lookup"><span data-stu-id="6055a-112">A `Subtract` operation request may include a flowed transaction.</span></span>  
  
- <span data-ttu-id="6055a-113">Una solicitud de operación `Multiply` no debe incluir una transacción fluida a través del valor NotAllowed explícito.</span><span class="sxs-lookup"><span data-stu-id="6055a-113">A `Multiply` operation request must not include a flowed transaction through the explicit NotAllowed setting.</span></span>  
  
- <span data-ttu-id="6055a-114">Una solicitud de operación `Divide` no debe incluir una transacción fluida a través de la omisión de un atributo `TransactionFlow`.</span><span class="sxs-lookup"><span data-stu-id="6055a-114">A `Divide` operation request must not include a flowed transaction through the omission of a `TransactionFlow` attribute.</span></span>  
  
 <span data-ttu-id="6055a-115">Para habilitar el flujo de la transacción, se deben usar los enlaces con la [\<transactionFlow>](../../configure-apps/file-schema/wcf/transactionflow.md) propiedad habilitada además de los atributos de operación adecuados.</span><span class="sxs-lookup"><span data-stu-id="6055a-115">To enable transaction flow, bindings with the [\<transactionFlow>](../../configure-apps/file-schema/wcf/transactionflow.md) property enabled must be used in addition to the appropriate operation attributes.</span></span> <span data-ttu-id="6055a-116">En este ejemplo, la configuración del servicio expone un punto de conexión del TCP y un punto de conexión HTTP además del punto de conexión de intercambio de metadatos.</span><span class="sxs-lookup"><span data-stu-id="6055a-116">In this sample, the service's configuration exposes a TCP endpoint and an HTTP endpoint in addition to a Metadata Exchange endpoint.</span></span> <span data-ttu-id="6055a-117">El extremo TCP y el extremo HTTP usan los siguientes enlaces, y ambos tienen la [\<transactionFlow>](../../configure-apps/file-schema/wcf/transactionflow.md) propiedad habilitada.</span><span class="sxs-lookup"><span data-stu-id="6055a-117">The TCP endpoint and the HTTP endpoint use the following bindings, both of which have the [\<transactionFlow>](../../configure-apps/file-schema/wcf/transactionflow.md) property enabled.</span></span>  
  
```xml  
<bindings>  
  <netTcpBinding>  
    <binding name="transactionalOleTransactionsTcpBinding"  
             transactionFlow="true"  
             transactionProtocol="OleTransactions"/>  
  </netTcpBinding>  
  <wsHttpBinding>  
    <binding name="transactionalWsatHttpBinding"  
             transactionFlow="true" />  
  </wsHttpBinding>  
</bindings>  
```  
  
> [!NOTE]
> <span data-ttu-id="6055a-118">El netTcpBinding proporcionado por el sistema permite especificaciones de transactionProtocol, mientras que el wsHttpBinding proporcionado por el sistema utiliza solamente el protocolo más interoperable WSAtomicTransactionOctober2004.</span><span class="sxs-lookup"><span data-stu-id="6055a-118">The system-provided netTcpBinding allows specification of the transactionProtocol whereas the system-provided wsHttpBinding uses only the more interoperable WSAtomicTransactionOctober2004 protocol.</span></span> <span data-ttu-id="6055a-119">El protocolo OleTransactions solo está disponible para los clientes Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="6055a-119">The OleTransactions protocol is only available for use by Windows Communication Foundation (WCF) clients.</span></span>  
  
 <span data-ttu-id="6055a-120">Para la clase que implementa la interfaz `ICalculator`, todos los métodos se atribuyen con propiedad <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> establecida en `true`.</span><span class="sxs-lookup"><span data-stu-id="6055a-120">For the class that implements the `ICalculator` interface, all of the methods are attributed with <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> property set to `true`.</span></span> <span data-ttu-id="6055a-121">Este valor declara que todas las acciones tomadas dentro del método se producen dentro del ámbito de una transacción.</span><span class="sxs-lookup"><span data-stu-id="6055a-121">This setting declares that all actions taken within the method occur within the scope of a transaction.</span></span> <span data-ttu-id="6055a-122">En este caso, las acciones tomadas incluyen la grabación a la base de datos de registro.</span><span class="sxs-lookup"><span data-stu-id="6055a-122">In this case, the actions taken include recording to the log database.</span></span> <span data-ttu-id="6055a-123">Si la solicitud de la operación incluye a continuación una transacción fluida las acciones se producen dentro del ámbito de la transacción entrante o se genera automáticamente un nuevo ámbito de la transacción.</span><span class="sxs-lookup"><span data-stu-id="6055a-123">If the operation request includes a flowed transaction then the actions occur within the scope of the incoming transaction or a new transaction scope is automatically generated.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6055a-124">La propiedad <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> define el comportamiento local de las implementaciones de método de servicio y no define la capacidad del cliente ni el requisito para que una transacción fluya.</span><span class="sxs-lookup"><span data-stu-id="6055a-124">The <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> property defines behavior local to the service method implementations and does not define the client's ability to or requirement for flowing a transaction.</span></span>  

```csharp
// Service class that implements the service contract.  
[ServiceBehavior(TransactionIsolationLevel = System.Transactions.IsolationLevel.Serializable)]  
public class CalculatorService : ICalculator  
{  
    [OperationBehavior(TransactionScopeRequired = true)]  
    public double Add(double n1, double n2)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Adding {0} to {1}", n1, n2));  
        return n1 + n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true)]  
    public double Subtract(double n1, double n2)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Subtracting {0} from {1}", n2, n1));  
        return n1 - n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true)]  
    public double Multiply(double n1, double n2)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Multiplying {0} by {1}", n1, n2));  
        return n1 * n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true)]  
    public double Divide(double n1, double n2)  
    {  
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Dividing {0} by {1}", n1, n2));  
        return n1 / n2;  
    }  
  
    // Logging method omitted for brevity  
}  
```

 <span data-ttu-id="6055a-125">En el cliente, la configuración de `TransactionFlowOption` del servicio en las operaciones se refleja en la definición generada del cliente de la interfaz `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="6055a-125">On the client, the service's `TransactionFlowOption` settings on the operations are reflected in the client's generated definition of the `ICalculator` interface.</span></span> <span data-ttu-id="6055a-126">Asimismo, la configuración de propiedades del servicio `transactionFlow` se refleja en la configuración de la aplicación del cliente.</span><span class="sxs-lookup"><span data-stu-id="6055a-126">Also, the service's `transactionFlow` property settings are reflected in the client's application configuration.</span></span> <span data-ttu-id="6055a-127">El cliente puede seleccionar el transporte y el protocolo seleccionando el `endpointConfigurationName` adecuado:</span><span class="sxs-lookup"><span data-stu-id="6055a-127">The client can select the transport and protocol by selecting the appropriate `endpointConfigurationName`.</span></span>  

```csharp
// Create a client using either wsat or oletx endpoint configurations  
CalculatorClient client = new CalculatorClient("WSAtomicTransaction_endpoint");  
// CalculatorClient client = new CalculatorClient("OleTransactions_endpoint");  
```

> [!NOTE]
> <span data-ttu-id="6055a-128">El comportamiento observado de este ejemplo es el mismo, independientemente de qué protocolo o transporte se elige.</span><span class="sxs-lookup"><span data-stu-id="6055a-128">The observed behavior of this sample is the same no matter which protocol or transport is chosen.</span></span>  
  
 <span data-ttu-id="6055a-129">Habiendo iniciado la conexión al servicio, el cliente crea un nuevo `TransactionScope` alrededor de las llamadas a las operaciones del servicio.</span><span class="sxs-lookup"><span data-stu-id="6055a-129">Having initiated the connection to the service, the client creates a new `TransactionScope` around the calls to the service operations.</span></span>  

```csharp
// Start a transaction scope  
using (TransactionScope tx =  
            new TransactionScope(TransactionScopeOption.RequiresNew))  
{  
    Console.WriteLine("Starting transaction");  
  
    // Call the Add service operation  
    //  - generatedClient will flow the required active transaction  
    double value1 = 100.00D;  
    double value2 = 15.99D;  
    double result = client.Add(value1, value2);  
    Console.WriteLine("  Add({0},{1}) = {2}", value1, value2, result);  
  
    // Call the Subtract service operation  
    //  - generatedClient will flow the allowed active transaction  
    value1 = 145.00D;  
    value2 = 76.54D;  
    result = client.Subtract(value1, value2);  
    Console.WriteLine("  Subtract({0},{1}) = {2}", value1, value2, result);  
  
    // Start a transaction scope that suppresses the current transaction  
    using (TransactionScope txSuppress =  
                new TransactionScope(TransactionScopeOption.Suppress))  
    {  
        // Call the Subtract service operation  
        //  - the active transaction is suppressed from the generatedClient  
        //    and no transaction will flow  
        value1 = 21.05D;  
        value2 = 42.16D;  
        result = client.Subtract(value1, value2);  
        Console.WriteLine("  Subtract({0},{1}) = {2}", value1, value2, result);  
  
        // Complete the suppressed scope  
        txSuppress.Complete();  
    }  
  
    // Call the Multiply service operation  
    // - generatedClient will not flow the active transaction  
    value1 = 9.00D;  
    value2 = 81.25D;  
    result = client.Multiply(value1, value2);  
    Console.WriteLine("  Multiply({0},{1}) = {2}", value1, value2, result);  
  
    // Call the Divide service operation.  
    // - generatedClient will not flow the active transaction  
    value1 = 22.00D;  
    value2 = 7.00D;  
    result = client.Divide(value1, value2);  
    Console.WriteLine("  Divide({0},{1}) = {2}", value1, value2, result);  
  
    // Complete the transaction scope  
    Console.WriteLine("  Completing transaction");  
    tx.Complete();  
}  
  
Console.WriteLine("Transaction committed");  
```

 <span data-ttu-id="6055a-130">Las llamadas a las operaciones son como sigue:</span><span class="sxs-lookup"><span data-stu-id="6055a-130">The calls to the operations are as follows:</span></span>  
  
- <span data-ttu-id="6055a-131">La solicitud `Add` provoca que la transacción necesaria fluya hasta al servicio y las acciones del servicio se producen dentro del ámbito de la transacción del cliente.</span><span class="sxs-lookup"><span data-stu-id="6055a-131">The `Add` request flows the required transaction to the service and the service's actions occur within the scope of the client's transaction.</span></span>  
  
- <span data-ttu-id="6055a-132">La primera solicitud `Subtract` también fluye la transacción permitida hacia el servicio y de nuevo las acciones del servicio se producen dentro del ámbito de la transacción del cliente.</span><span class="sxs-lookup"><span data-stu-id="6055a-132">The first `Subtract` request also flows the allowed transaction to the service and again the service's actions occur within the scope of the client's transaction.</span></span>  
  
- <span data-ttu-id="6055a-133">La segunda solicitud `Subtract` se realiza dentro de un nuevo ámbito de la transacción declarado con la opción `TransactionScopeOption.Suppress`.</span><span class="sxs-lookup"><span data-stu-id="6055a-133">The second `Subtract` request is performed within a new transaction scope declared with the `TransactionScopeOption.Suppress` option.</span></span> <span data-ttu-id="6055a-134">Esto suprime la transacción exterior inicial del cliente y la solicitud no fluye hasta una transacción al servicio.</span><span class="sxs-lookup"><span data-stu-id="6055a-134">This suppresses the client's initial outer transaction and the request does not flow a transaction to the service.</span></span> <span data-ttu-id="6055a-135">Este enfoque permite a un cliente cancelar explícitamente una suscripción y protegerse contra el fluir de una transacción a un servicio cuando no es necesario.</span><span class="sxs-lookup"><span data-stu-id="6055a-135">This approach allows a client to explicitly opt-out of and protect against flowing a transaction to a service when that is not required.</span></span> <span data-ttu-id="6055a-136">Las acciones del servicio se producen dentro del ámbito de una transacción nueva y no conectada.</span><span class="sxs-lookup"><span data-stu-id="6055a-136">The service's actions occur within the scope of a new and unconnected transaction.</span></span>  
  
- <span data-ttu-id="6055a-137">La solicitud `Multiply` no fluye una transacción al servicio porque la definición generada del cliente de la interfaz `ICalculator` incluye un conjunto <xref:System.ServiceModel.TransactionFlowAttribute> establecido como <xref:System.ServiceModel.TransactionFlowOption>`NotAllowed`.</span><span class="sxs-lookup"><span data-stu-id="6055a-137">The `Multiply` request does not flow a transaction to the service because the client's generated definition of the `ICalculator` interface includes a <xref:System.ServiceModel.TransactionFlowAttribute> set to <xref:System.ServiceModel.TransactionFlowOption>`NotAllowed`.</span></span>  
  
- <span data-ttu-id="6055a-138">La solicitud `Divide` no fluye una transacción al servicio porque, de nuevo, la definición de la interfaz `ICalculator` generada del cliente, no incluye un `TransactionFlowAttribute`.</span><span class="sxs-lookup"><span data-stu-id="6055a-138">The `Divide` request does not flow a transaction to the service because again the client's generated definition of the `ICalculator` interface does not include a `TransactionFlowAttribute`.</span></span> <span data-ttu-id="6055a-139">Las acciones del servicio se producen de nuevo dentro del ámbito de otra transacción nueva y no conectada.</span><span class="sxs-lookup"><span data-stu-id="6055a-139">The service's actions again occur within the scope of another new and unconnected transaction.</span></span>  
  
 <span data-ttu-id="6055a-140">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="6055a-140">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="6055a-141">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="6055a-141">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Starting transaction  
  Add(100,15.99) = 115.99  
  Subtract(145,76.54) = 68.46  
  Subtract(21.05,42.16) = -21.11  
  Multiply(9,81.25) = 731.25  
  Divide(22,7) = 3.14285714285714  
  Completing transaction  
Transaction committed  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="6055a-142">El registro de las solicitudes de operación de servicio se muestra en la ventana de la consola del servicio.</span><span class="sxs-lookup"><span data-stu-id="6055a-142">The logging of the service operation requests are displayed in the service's console window.</span></span> <span data-ttu-id="6055a-143">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="6055a-143">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Press <ENTER> to terminate the service.  
  Writing row to database: Adding 100 to 15.99  
  Writing row to database: Subtracting 76.54 from 145  
  Writing row to database: Subtracting 42.16 from 21.05  
  Writing row to database: Multiplying 9 by 81.25  
  Writing row to database: Dividing 22 by 7  
```  
  
 <span data-ttu-id="6055a-144">Después de una ejecución correcta, el ámbito de la transacción del cliente se completa y se confirman todas las acciones tomadas dentro de ese ámbito.</span><span class="sxs-lookup"><span data-stu-id="6055a-144">After a successful execution, the client's transaction scope completes and all actions taken within that scope are committed.</span></span> <span data-ttu-id="6055a-145">Específicamente, los 5 registros nombrados se conservan en la base de datos del servicio.</span><span class="sxs-lookup"><span data-stu-id="6055a-145">Specifically, the noted 5 records are persisted in the service's database.</span></span> <span data-ttu-id="6055a-146">Los 2 primeros de éstos se han producido dentro del ámbito de la transacción del cliente.</span><span class="sxs-lookup"><span data-stu-id="6055a-146">The first 2 of these have occurred within the scope of the client's transaction.</span></span>  
  
 <span data-ttu-id="6055a-147">Si se produce una excepción en cualquier parte dentro del `TransactionScope` del cliente, la transacción no puede completarse.</span><span class="sxs-lookup"><span data-stu-id="6055a-147">If an exception occurred anywhere within the client's `TransactionScope` then the transaction cannot complete.</span></span> <span data-ttu-id="6055a-148">Esto produce que los registros registrados dentro de ese ámbito no se confirmen en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="6055a-148">This causes the records logged within that scope to not be committed to the database.</span></span> <span data-ttu-id="6055a-149">Este efecto se puede observar repitiendo el ejemplo ejecutado después de marcar como comentario la llamada para completar el `TransactionScope` exterior.</span><span class="sxs-lookup"><span data-stu-id="6055a-149">This effect can be observed by repeating the sample run after commenting out the call to complete the outer `TransactionScope`.</span></span> <span data-ttu-id="6055a-150">En este tipo de procesos, solo se registran las tres últimas acciones (desde la segunda solicitud `Subtract`, `Multiply` y `Divide`) porque la transacción del cliente no fluyó hacia ellas.</span><span class="sxs-lookup"><span data-stu-id="6055a-150">On such a run, only the last 3 actions (from the second `Subtract`, the `Multiply` and the `Divide` requests) are logged because the client transaction did not flow to those.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="6055a-151">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="6055a-151">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="6055a-152">Para compilar la versión de C# o Visual Basic .NET de la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md)</span><span class="sxs-lookup"><span data-stu-id="6055a-152">To build the C# or Visual Basic .NET version of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md)</span></span>  
  
2. <span data-ttu-id="6055a-153">Asegúrese de que se ha instalado SQL Server Express Edition o SQL Server, y que la cadena de conexión se ha establecido correctamente en el archivo de configuración de la aplicación del servicio.</span><span class="sxs-lookup"><span data-stu-id="6055a-153">Ensure that you have installed SQL Server Express Edition or SQL Server, and that the connection string has been correctly set in the service’s application configuration file.</span></span> <span data-ttu-id="6055a-154">Para ejecutar el ejemplo sin utilizar una base de datos, establezca el valor `usingSql` en el archivo de configuración de la aplicación del servicio en `false`</span><span class="sxs-lookup"><span data-stu-id="6055a-154">To run the sample without using a database, set the `usingSql` value in the service’s application configuration file to `false`</span></span>  
  
3. <span data-ttu-id="6055a-155">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6055a-155">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="6055a-156">Para una configuración de varios equipos, habilite el Coordinador de transacciones distribuidas mediante las instrucciones siguientes, y utilice la herramienta WsatConfig.exe de Windows SDK con el fin de habilitar la compatibilidad para red de las transacciones WCF.</span><span class="sxs-lookup"><span data-stu-id="6055a-156">For cross-machine configuration, enable the Distributed Transaction Coordinator using the instructions below, and use the WsatConfig.exe tool from the Windows SDK to enable WCF Transactions network support.</span></span> <span data-ttu-id="6055a-157">Para obtener información sobre la configuración de WsatConfig.exe, consulte Configuración de la [compatibilidad con transacciones de WS-Atomic](../feature-details/configuring-ws-atomic-transaction-support.md).</span><span class="sxs-lookup"><span data-stu-id="6055a-157">For information on setting up WsatConfig.exe, see [Configuring WS-Atomic Transaction Support](../feature-details/configuring-ws-atomic-transaction-support.md).</span></span>  
  
 <span data-ttu-id="6055a-158">Tanto si ejecuta el ejemplo en el mismo equipo como en equipos diferentes, debe configurar Microsoft Coordinador de transacciones distribuidas (MSDTC) para habilitar el flujo de transacciones de red y utilizar la herramienta de WsatConfig.exe para habilitar la compatibilidad de red de las transacciones de WCF.</span><span class="sxs-lookup"><span data-stu-id="6055a-158">Whether you run the sample on the same computer or on different computers, you must configure the Microsoft Distributed Transaction Coordinator (MSDTC) to enable network transaction flow and use the WsatConfig.exe tool to enable WCF transactions network support.</span></span>  
  
### <a name="to-configure-the-microsoft-distributed-transaction-coordinator-msdtc-to-support-running-the-sample"></a><span data-ttu-id="6055a-159">Para configurar el Coordinador de transacciones distribuidas (MSDTC) con el fin de permitir la ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="6055a-159">To configure the Microsoft Distributed Transaction Coordinator (MSDTC) to support running the sample</span></span>  
  
1. <span data-ttu-id="6055a-160">En un equipo de servicio que ejecute Windows Server 2003 o Windows XP, configure MSDTC para permitir las transacciones de red de entrada según estas instrucciones.</span><span class="sxs-lookup"><span data-stu-id="6055a-160">On a service machine running Windows Server 2003 or Windows XP, configure MSDTC to allow incoming network transactions by following these instructions.</span></span>  
  
    1. <span data-ttu-id="6055a-161">En el menú **Inicio** , vaya a **Panel de control**, **herramientas administrativas** y servicios de **componentes**.</span><span class="sxs-lookup"><span data-stu-id="6055a-161">From the **Start** menu, navigate to **Control Panel**, then **Administrative Tools**, and then **Component Services**.</span></span>  
  
    2. <span data-ttu-id="6055a-162">Expanda **servicios de componentes**.</span><span class="sxs-lookup"><span data-stu-id="6055a-162">Expand **Component Services**.</span></span> <span data-ttu-id="6055a-163">Abra la carpeta **equipos** .</span><span class="sxs-lookup"><span data-stu-id="6055a-163">Open the **Computers** folder.</span></span>  
  
    3. <span data-ttu-id="6055a-164">Haga clic con el botón derecho en **mi PC** y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6055a-164">Right-click **My Computer** and select **Properties**.</span></span>  
  
    4. <span data-ttu-id="6055a-165">En la pestaña **MSDTC** , haga clic en **configuración de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="6055a-165">On the **MSDTC** tab, click **Security Configuration**.</span></span>  
  
    5. <span data-ttu-id="6055a-166">Compruebe el **acceso a DTC desde la red** y **permita la entrada**.</span><span class="sxs-lookup"><span data-stu-id="6055a-166">Check **Network DTC Access** and **Allow Inbound**.</span></span>  
  
    6. <span data-ttu-id="6055a-167">Haga clic en **Aceptar** y, a continuación, en **sí** para reiniciar el servicio MSDTC.</span><span class="sxs-lookup"><span data-stu-id="6055a-167">Click **OK**, then click **Yes** to restart the MSDTC service.</span></span>  
  
    7. <span data-ttu-id="6055a-168">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="6055a-168">Click **OK** to close the dialog box.</span></span>  
  
2. <span data-ttu-id="6055a-169">En un equipo de servicio que ejecute Windows Server 2008 o Windows Vista, configure MSDTC para permitir las transacciones de red de entrada según estas instrucciones.</span><span class="sxs-lookup"><span data-stu-id="6055a-169">On a service machine running Windows Server 2008 or Windows Vista, configure MSDTC to allow incoming network transactions by following these instructions.</span></span>  
  
    1. <span data-ttu-id="6055a-170">En el menú **Inicio** , vaya a **Panel de control**, **herramientas administrativas** y servicios de **componentes**.</span><span class="sxs-lookup"><span data-stu-id="6055a-170">From the **Start** menu, navigate to **Control Panel**, then **Administrative Tools**, and then **Component Services**.</span></span>  
  
    2. <span data-ttu-id="6055a-171">Expanda **servicios de componentes**.</span><span class="sxs-lookup"><span data-stu-id="6055a-171">Expand **Component Services**.</span></span> <span data-ttu-id="6055a-172">Abra la carpeta **equipos** .</span><span class="sxs-lookup"><span data-stu-id="6055a-172">Open the **Computers** folder.</span></span> <span data-ttu-id="6055a-173">Seleccione **Coordinador de transacciones distribuidas**.</span><span class="sxs-lookup"><span data-stu-id="6055a-173">Select **Distributed Transaction Coordinator**.</span></span>  
  
    3. <span data-ttu-id="6055a-174">Haga clic con el botón secundario en **Coordinador de DTC** y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6055a-174">Right-click **DTC Coordinator** and select **Properties**.</span></span>  
  
    4. <span data-ttu-id="6055a-175">En la pestaña **seguridad** , Active **acceso a DTC desde la red** y **permitir entrantes**.</span><span class="sxs-lookup"><span data-stu-id="6055a-175">On the **Security** tab, check **Network DTC Access** and **Allow Inbound**.</span></span>  
  
    5. <span data-ttu-id="6055a-176">Haga clic en **Aceptar** y, a continuación, en **sí** para reiniciar el servicio MSDTC.</span><span class="sxs-lookup"><span data-stu-id="6055a-176">Click **OK**, then click **Yes** to restart the MSDTC service.</span></span>  
  
    6. <span data-ttu-id="6055a-177">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="6055a-177">Click **OK** to close the dialog box.</span></span>  
  
3. <span data-ttu-id="6055a-178">En el equipo cliente, configure MSDTC para permitir las transacciones de red salientes:</span><span class="sxs-lookup"><span data-stu-id="6055a-178">On the client machine, configure MSDTC to allow outgoing network transactions:</span></span>  
  
    1. <span data-ttu-id="6055a-179">En el menú **Inicio** , vaya a `Control Panel` , a continuación **herramientas administrativas** y a **servicios de componentes**.</span><span class="sxs-lookup"><span data-stu-id="6055a-179">From the **Start** menu, navigate to `Control Panel`, then **Administrative Tools**, and then **Component Services**.</span></span>  
  
    2. <span data-ttu-id="6055a-180">Haga clic con el botón derecho en **mi PC** y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6055a-180">Right-click **My Computer** and select **Properties**.</span></span>  
  
    3. <span data-ttu-id="6055a-181">En la pestaña **MSDTC** , haga clic en **configuración de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="6055a-181">On the **MSDTC** tab, click **Security Configuration**.</span></span>  
  
    4. <span data-ttu-id="6055a-182">Compruebe el **acceso a DTC desde la red** y **permita el tráfico saliente**.</span><span class="sxs-lookup"><span data-stu-id="6055a-182">Check **Network DTC Access** and **Allow Outbound**.</span></span>  
  
    5. <span data-ttu-id="6055a-183">Haga clic en **Aceptar** y, a continuación, en **sí** para reiniciar el servicio MSDTC.</span><span class="sxs-lookup"><span data-stu-id="6055a-183">Click **OK**, then click **Yes** to restart the MSDTC service.</span></span>  
  
    6. <span data-ttu-id="6055a-184">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="6055a-184">Click **OK** to close the dialog box.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6055a-185">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="6055a-185">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6055a-186">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="6055a-186">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="6055a-187">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="6055a-187">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6055a-188">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="6055a-188">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\TransactionFlow`
