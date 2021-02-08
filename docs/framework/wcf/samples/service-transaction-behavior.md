---
description: 'Más información sobre: comportamiento de las transacciones de servicio'
title: Comportamiento de transacción de servicio
ms.date: 03/30/2017
helpviewer_keywords:
- Service Transaction Behavior Sample [Windows Communication Foundation]
ms.assetid: 1a9842a3-e84d-427c-b6ac-6999cbbc2612
ms.openlocfilehash: 1f8b76de250ef87ec5ca2d4ea4353a9a28bac248
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793069"
---
# <a name="service-transaction-behavior"></a><span data-ttu-id="7a250-103">Comportamiento de transacción de servicio</span><span class="sxs-lookup"><span data-stu-id="7a250-103">Service Transaction Behavior</span></span>

<span data-ttu-id="7a250-104">Este ejemplo muestra el uso de una transacción coordinada por el cliente y la configuración de ServiceBehaviorAttribute y OperationBehaviorAttribute para controlar el comportamiento de las transacciones de servicio.</span><span class="sxs-lookup"><span data-stu-id="7a250-104">This sample demonstrates the use of a client-coordinated transaction and the settings of ServiceBehaviorAttribute and OperationBehaviorAttribute to control service transaction behavior.</span></span> <span data-ttu-id="7a250-105">Este ejemplo se basa en el [Introducción](getting-started-sample.md) que implementa un servicio de calculadora, pero se extiende para mantener un registro de servidor de las operaciones realizadas en una tabla de base de datos y un total de ejecución con estado para las operaciones de la calculadora.</span><span class="sxs-lookup"><span data-stu-id="7a250-105">This sample is based on the [Getting Started](getting-started-sample.md) that implements a calculator service, but is extended to maintain a server log of the performed operations in a database table and a stateful running total for the calculator operations.</span></span> <span data-ttu-id="7a250-106">Las escrituras guardadas en la tabla de registro del servidor dependen del resultado de una transacción coordinada del cliente. Si la transacción del cliente no se completa, la transacción del servicio Web garantiza que las actualizaciones de la base de datos no se confirman.</span><span class="sxs-lookup"><span data-stu-id="7a250-106">Persisted writes to the server log table are dependent upon the outcome of a client coordinated transaction - if the client transaction does not complete, the Web service transaction ensures that the updates to the database are not committed.</span></span>

> [!NOTE]
> <span data-ttu-id="7a250-107">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="7a250-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="7a250-108">El contrato para el servicio define que todas las operaciones exigen que una transacción fluya con solicitudes:</span><span class="sxs-lookup"><span data-stu-id="7a250-108">The contract for the service defines that all of the operations require a transaction to be flowed with requests:</span></span>

```csharp
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples",
                    SessionMode = SessionMode.Required)]
public interface ICalculator
{
    [OperationContract]
    [TransactionFlow(TransactionFlowOption.Mandatory)]
    double Add(double n);
    [OperationContract]
    [TransactionFlow(TransactionFlowOption.Mandatory)]
    double Subtract(double n);
    [OperationContract]
    [TransactionFlow(TransactionFlowOption.Mandatory)]
    double Multiply(double n);
    [OperationContract]
    [TransactionFlow(TransactionFlowOption.Mandatory)]
    double Divide(double n);
}
```

<span data-ttu-id="7a250-109">Para habilitar el flujo de la transacción entrante, el servicio se configura con el wsHttpBinding proporcionado por el sistema con el atributo transactionFlow establecido en `true`.</span><span class="sxs-lookup"><span data-stu-id="7a250-109">To enable the incoming transaction flow, the service is configured with the system-provided wsHttpBinding with the transactionFlow attribute set to `true`.</span></span> <span data-ttu-id="7a250-110">Este enlace utiliza el protocolo WSAtomicTransactionOctober2004 interoperable:</span><span class="sxs-lookup"><span data-stu-id="7a250-110">This binding uses the interoperable WSAtomicTransactionOctober2004 protocol:</span></span>

```xml
<bindings>
  <wsHttpBinding>
    <binding name="transactionalBinding" transactionFlow="true" />
  </wsHttpBinding>
</bindings>
```

<span data-ttu-id="7a250-111">Después de iniciar tanto una conexión con el servicio como una transacción, el cliente tiene acceso a varias operaciones de servicio dentro del ámbito de esa transacción y, a continuación, completa la transacción y cierra la conexión:</span><span class="sxs-lookup"><span data-stu-id="7a250-111">After initiating both a connection to the service and a transaction, the client accesses several service operations within the scope of that transaction and then completes the transaction and closes the connection:</span></span>

```csharp
// Create a client
CalculatorClient client = new CalculatorClient();

// Create a transaction scope with the default isolation level of Serializable
using (TransactionScope tx = new TransactionScope())
{
    Console.WriteLine("Starting transaction");

    // Call the Add service operation.
    double value = 100.00D;
    Console.WriteLine("  Adding {0}, running total={1}",
                                        value, client.Add(value));

    // Call the Subtract service operation.
    value = 45.00D;
    Console.WriteLine("  Subtracting {0}, running total={1}",
                                        value, client.Subtract(value));

    // Call the Multiply service operation.
    value = 9.00D;
    Console.WriteLine("  Multiplying by {0}, running total={1}",
                                        value, client.Multiply(value));

    // Call the Divide service operation.
    value = 15.00D;
    Console.WriteLine("  Dividing by {0}, running total={1}",
                                        value, client.Divide(value));

    Console.WriteLine("  Completing transaction");
    tx.Complete();
}

Console.WriteLine("Transaction committed");

// Closing the client gracefully closes the connection and cleans up resources
client.Close();
```

<span data-ttu-id="7a250-112">En el servicio, hay tres atributos que afectan al comportamiento de las transacciones de servicio y lo hacen de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="7a250-112">On the service, there are three attributes that affect the service transaction behavior, and they do so in the following ways:</span></span>

- <span data-ttu-id="7a250-113">En `ServiceBehaviorAttribute`:</span><span class="sxs-lookup"><span data-stu-id="7a250-113">On the `ServiceBehaviorAttribute`:</span></span>

  - <span data-ttu-id="7a250-114">La propiedad `TransactionTimeout` especifica el período dentro del cual debe completarse una transacción.</span><span class="sxs-lookup"><span data-stu-id="7a250-114">The `TransactionTimeout` property specifies the time period within which a transaction must complete.</span></span> <span data-ttu-id="7a250-115">En este ejemplo, está establecido en 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="7a250-115">In this sample it is set to 30 seconds.</span></span>

  - <span data-ttu-id="7a250-116">La propiedad `TransactionIsolationLevel` especifica el nivel de aislamiento que el servicio admite.</span><span class="sxs-lookup"><span data-stu-id="7a250-116">The `TransactionIsolationLevel` property specifies the isolation level that the service supports.</span></span> <span data-ttu-id="7a250-117">Esto es necesario para coincidir con el nivel de aislamiento del cliente.</span><span class="sxs-lookup"><span data-stu-id="7a250-117">This is required to match the client's isolation level.</span></span>

  - <span data-ttu-id="7a250-118">La propiedad `ReleaseServiceInstanceOnTransactionComplete` especifica si se recicla la instancia del servicio cuando se completa una transacción.</span><span class="sxs-lookup"><span data-stu-id="7a250-118">The `ReleaseServiceInstanceOnTransactionComplete` property specifies whether the service instance is recycled when a transaction completes.</span></span> <span data-ttu-id="7a250-119">Si se establece en `false`, el servicio mantiene la misma instancia del servicio en las solicitudes de operación.</span><span class="sxs-lookup"><span data-stu-id="7a250-119">By setting it to `false`, the service maintains the same service instance across the operation requests.</span></span> <span data-ttu-id="7a250-120">Esto es necesario para mantener el total en ejecución.</span><span class="sxs-lookup"><span data-stu-id="7a250-120">This is required to maintain the running total.</span></span> <span data-ttu-id="7a250-121">Si se establece en `true`, se genera una instancia nueva después de cada acción completada.</span><span class="sxs-lookup"><span data-stu-id="7a250-121">If set to `true`, a new instance is generated after each completed action.</span></span>

  - <span data-ttu-id="7a250-122">La propiedad `TransactionAutoCompleteOnSessionClose` especifica si se completan las transacciones pendientes cuando la sesión se cierra.</span><span class="sxs-lookup"><span data-stu-id="7a250-122">The `TransactionAutoCompleteOnSessionClose` property specifies whether outstanding transactions are completed when the session closes.</span></span> <span data-ttu-id="7a250-123">Al establecerlo en `false` , las operaciones individuales son necesarias para establecer la <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete?displayProperty=nameWithType> propiedad en `true` o para requerir explícitamente una llamada al <xref:System.ServiceModel.OperationContext.SetTransactionComplete?displayProperty=nameWithType> método para completar las transacciones.</span><span class="sxs-lookup"><span data-stu-id="7a250-123">By setting it to `false`, the individual operations are required to either set the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete?displayProperty=nameWithType> property to `true` or to explicitly require a call to the <xref:System.ServiceModel.OperationContext.SetTransactionComplete?displayProperty=nameWithType> method to complete transactions.</span></span> <span data-ttu-id="7a250-124">Este ejemplo muestra ambos enfoques.</span><span class="sxs-lookup"><span data-stu-id="7a250-124">This sample demonstrates both approaches.</span></span>

- <span data-ttu-id="7a250-125">En `ServiceContractAttribute`:</span><span class="sxs-lookup"><span data-stu-id="7a250-125">On the `ServiceContractAttribute`:</span></span>

  - <span data-ttu-id="7a250-126">La propiedad `SessionMode` especifica si el servicio pone en correlación las solicitudes adecuadas en una sesión lógica.</span><span class="sxs-lookup"><span data-stu-id="7a250-126">The `SessionMode` property specifies whether the service correlates the appropriate requests into a logical session.</span></span> <span data-ttu-id="7a250-127">Dado que este servicio incluye las operaciones en las que la propiedad OperationBehaviorAttribute TransactionAutoComplete está establecida en `false` (multiplicar y dividir), debe especificarse `SessionMode.Required`.</span><span class="sxs-lookup"><span data-stu-id="7a250-127">Because this service includes operations where the OperationBehaviorAttribute TransactionAutoComplete property is set to `false` (Multiply and Divide), `SessionMode.Required` must be specified.</span></span> <span data-ttu-id="7a250-128">Por ejemplo, la operación de multiplicación no completa su transacción sino que confía en una llamada posterior para que se complete la operación de división usando el método `SetTransactionComplete`; el servicio debe poder determinar que estas operaciones se están produciendo dentro de la misma sesión.</span><span class="sxs-lookup"><span data-stu-id="7a250-128">For example, the Multiply operation does not complete its transaction and instead relies upon a later call to Divide to complete using the `SetTransactionComplete` method; the service must be able to determine that these operations are occurring within the same session.</span></span>

- <span data-ttu-id="7a250-129">En `OperationBehaviorAttribute`:</span><span class="sxs-lookup"><span data-stu-id="7a250-129">On the `OperationBehaviorAttribute`:</span></span>

  - <span data-ttu-id="7a250-130">La propiedad `TransactionScopeRequired` especifica si las acciones de la operación se deberían ejecutar dentro del ámbito de una transacción.</span><span class="sxs-lookup"><span data-stu-id="7a250-130">The `TransactionScopeRequired` property specifies whether the operation's actions should be executed within a transaction scope.</span></span> <span data-ttu-id="7a250-131">Se establece en `true` para todas las operaciones de este ejemplo y, dado que el cliente fluye su transacción a todas las operaciones, las acciones se producen dentro del ámbito de la transacción de ese cliente.</span><span class="sxs-lookup"><span data-stu-id="7a250-131">This is set to `true` for all operations in this sample and, because the client flows its transaction to all operations, the actions occur within the scope of that client transaction.</span></span>

  - <span data-ttu-id="7a250-132">La propiedad `TransactionAutoComplete` especifica si se completa automáticamente la transacción en la que se ejecuta el método si no se producen excepciones no controladas.</span><span class="sxs-lookup"><span data-stu-id="7a250-132">The `TransactionAutoComplete` property specifies whether the transaction in which the method executes is automatically completed if no unhandled exceptions occur.</span></span> <span data-ttu-id="7a250-133">Tal y como se ha descrito previamente, se establece en `true` para las operaciones de suma y resta, y en `false` para las de multiplicación y división.</span><span class="sxs-lookup"><span data-stu-id="7a250-133">As previously described, this is set to `true` for the Add and Subtract operations but `false` for the Multiply and Divide operations.</span></span> <span data-ttu-id="7a250-134">Las operaciones de suma y resta completan sus acciones automáticamente, la de división completa sus acciones mediante una llamada explícita al método `SetTransactionComplete` y la de multiplicación no completa sus acciones, sino que en realidad confía y necesita una llamada posterior, por ejemplo a la operación de dividir, para completar las acciones.</span><span class="sxs-lookup"><span data-stu-id="7a250-134">The Add and Subtract operations complete their actions automatically, the Divide completes its actions through an explicit call to the `SetTransactionComplete` method, and the Multiply does not complete its actions but instead relies upon and requires a later call, such as to Divide, to complete the actions.</span></span>

<span data-ttu-id="7a250-135">La implementación del servicio con atributos es como sigue:</span><span class="sxs-lookup"><span data-stu-id="7a250-135">The attributed service implementation is as follows:</span></span>

```csharp
[ServiceBehavior(
    TransactionIsolationLevel = System.Transactions.IsolationLevel.Serializable,
    TransactionTimeout = "00:00:30",
    ReleaseServiceInstanceOnTransactionComplete = false,
    TransactionAutoCompleteOnSessionClose = false)]
public class CalculatorService : ICalculator
{
    double runningTotal;

    public CalculatorService()
    {
        Console.WriteLine("Creating new service instance...");
    }

    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    public double Add(double n)
    {
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Adding {0} to {1}", n, runningTotal));
        runningTotal = runningTotal + n;
        return runningTotal;
    }

    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    public double Subtract(double n)
    {
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Subtracting {0} from {1}", n, runningTotal));
        runningTotal = runningTotal - n;
        return runningTotal;
    }

    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = false)]
    public double Multiply(double n)
    {
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Multiplying {0} by {1}", runningTotal, n));
        runningTotal = runningTotal * n;
        return runningTotal;
    }

    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = false)]
    public double Divide(double n)
    {
        RecordToLog(String.Format(CultureInfo.CurrentCulture, "Dividing {0} by {1}", runningTotal, n));
        runningTotal = runningTotal / n;
        OperationContext.Current.SetTransactionComplete();
        return runningTotal;
    }

    // Logging method omitted for brevity
}
```

<span data-ttu-id="7a250-136">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="7a250-136">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="7a250-137">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="7a250-137">Press ENTER in the client window to shut down the client.</span></span>

```console
Starting transaction
Performing calculations...
  Adding 100, running total=100
  Subtracting 45, running total=55
  Multiplying by 9, running total=495
  Dividing by 15, running total=33
  Completing transaction
Transaction committed
Press <ENTER> to terminate client.
```

<span data-ttu-id="7a250-138">El registro de las solicitudes de operación de servicio se muestra en la ventana de la consola del servicio.</span><span class="sxs-lookup"><span data-stu-id="7a250-138">The logging of the service operation requests are displayed in the service's console window.</span></span> <span data-ttu-id="7a250-139">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="7a250-139">Press ENTER in the client window to shut down the client.</span></span>

```console
Press <ENTER> to terminate service.
Creating new service instance...
  Writing row 1 to database: Adding 100 to 0
  Writing row 2 to database: Subtracting 45 from 100
  Writing row 3 to database: Multiplying 55 by 9
  Writing row 4 to database: Dividing 495 by 15
```

<span data-ttu-id="7a250-140">Tenga en cuenta que además de mantener el total en ejecución de los cálculos, el servicio informa sobre la creación de instancias (una instancia en este ejemplo) y registra las solicitudes de operación en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="7a250-140">Note that in addition to keeping the running total of the calculations, the service reports the creation of instances (one instance for this sample) and logs the operation requests to a database.</span></span> <span data-ttu-id="7a250-141">Como todas las solicitudes fluyen en la transacción del cliente, cualquier error para completar esa transacción da como resultado que se reviertan todas las operaciones de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7a250-141">Because all of the requests flow the client's transaction, any failure to complete that transaction results in all of the database operations being rolled back.</span></span> <span data-ttu-id="7a250-142">Esto se puede demostrar de varias maneras:</span><span class="sxs-lookup"><span data-stu-id="7a250-142">This can be demonstrated in a number of ways:</span></span>

- <span data-ttu-id="7a250-143">Marcar como comentario la llamada del cliente en `tx.Complete`() y volver a ejecutar. Esto ocasiona que el cliente salga del ámbito de la transacción sin completar su transacción.</span><span class="sxs-lookup"><span data-stu-id="7a250-143">Comment out the client's call to `tx.Complete`() and rerun - this results in the client exiting the transaction scope without completing its transaction.</span></span>

- <span data-ttu-id="7a250-144">Marcar como comentario la llamada a la operación de servicio de dividir. Así se impide que la acción iniciada por la operación de multiplicación se complete y, por tanto, la transacción del cliente tampoco podrá completarse.</span><span class="sxs-lookup"><span data-stu-id="7a250-144">Comment out the call to the Divide service operation - this results prevent the action initiated by the Multiply operation from completing and thus the client's transaction ultimately also fails to complete.</span></span>

- <span data-ttu-id="7a250-145">Iniciar una excepción no controlada en cualquier parte del ámbito de la transacción del cliente. Del mismo modo, esto impide que el cliente complete su transacción.</span><span class="sxs-lookup"><span data-stu-id="7a250-145">Throw an unhandled exception anywhere in the client's transaction scope - this similarly prevents the client from completing its transaction.</span></span>

<span data-ttu-id="7a250-146">El resultado en cualquiera de estos casos es que no se confirma ninguna de las operaciones realizadas dentro del ámbito y no se incrementa el recuento de filas conservadas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7a250-146">The result of any of these is that none of the operations performed within that scope are committed and the count of rows persisted to the database do not increment.</span></span>

> [!NOTE]
> <span data-ttu-id="7a250-147">Como parte del proceso de compilación, el archivo de base de datos se copia en la carpeta de la bandeja.</span><span class="sxs-lookup"><span data-stu-id="7a250-147">As part of the build process the database file is copied to the bin folder.</span></span> <span data-ttu-id="7a250-148">Debe examinar esa copia del archivo de base de datos para observar las filas que se conservan en el registro en lugar del archivo que está incluido en el proyecto de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7a250-148">You must look at that copy of the database file to observe the rows that are persisted to the log rather than the file that is included in the Visual Studio project.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="7a250-149">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="7a250-149">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="7a250-150">Asegúrese de que ha instalado SQL Server 2005 Express Edition o SQL Server 2005.</span><span class="sxs-lookup"><span data-stu-id="7a250-150">Ensure that you have installed SQL Server 2005 Express Edition or SQL Server 2005.</span></span> <span data-ttu-id="7a250-151">En el archivo App.config del servicio, puede establecerse la base de datos`connectionString` o las interacciones de la base de datos pueden deshabilitarse estableciendo el valor `usingSql` de appSettings en `false`.</span><span class="sxs-lookup"><span data-stu-id="7a250-151">In the service's App.config file, the database `connectionString` may be set or the database interactions may be disabled by setting the appSettings `usingSql` value to `false`.</span></span>

2. <span data-ttu-id="7a250-152">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="7a250-152">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="7a250-153">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="7a250-153">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

<span data-ttu-id="7a250-154">Si ejecuta el ejemplo en los equipos, debe configurar Microsoft Coordinador de transacciones distribuidas (MSDTC) para habilitar el flujo de transacciones de red y utilizar la herramienta de WsatConfig.exe para habilitar la compatibilidad de red de las transacciones de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="7a250-154">If you run the sample across machines, you must configure the Microsoft Distributed Transaction Coordinator (MSDTC) to enable network transaction flow and use the WsatConfig.exe tool to enable Windows Communication Foundation (WCF) transactions network support.</span></span>

### <a name="to-configure-the-microsoft-distributed-transaction-coordinator-msdtc-to-support-running-the-sample-across-machines"></a><span data-ttu-id="7a250-155">Para configurar MSDTC de forma que admita la ejecución del ejemplo en varios equipos</span><span class="sxs-lookup"><span data-stu-id="7a250-155">To configure the Microsoft Distributed Transaction Coordinator (MSDTC) to support running the sample across machines</span></span>

1. <span data-ttu-id="7a250-156">En el equipo de servicio, configure MSDTC para permitir las transacciones de red entrantes.</span><span class="sxs-lookup"><span data-stu-id="7a250-156">On the service machine, configure MSDTC to allow incoming network transactions.</span></span>

    1. <span data-ttu-id="7a250-157">En el menú **Inicio** , vaya a **Panel de control**, **herramientas administrativas** y servicios de **componentes**.</span><span class="sxs-lookup"><span data-stu-id="7a250-157">From the **Start** menu, navigate to **Control Panel**, then **Administrative Tools**, and then **Component Services**.</span></span>

    2. <span data-ttu-id="7a250-158">Haga clic con el botón derecho en **mi PC** y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7a250-158">Right-click **My Computer** and select **Properties**.</span></span>

    3. <span data-ttu-id="7a250-159">En la pestaña **MSDTC** , haga clic en **configuración de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="7a250-159">On the **MSDTC** tab, click **Security Configuration**.</span></span>

    4. <span data-ttu-id="7a250-160">Compruebe el **acceso a DTC desde la red** y **permita la entrada**.</span><span class="sxs-lookup"><span data-stu-id="7a250-160">Check **Network DTC Access** and **Allow Inbound**.</span></span>

    5. <span data-ttu-id="7a250-161">Haga clic en **sí** para reiniciar el servicio MS DTC y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7a250-161">Click **Yes** to restart the MS DTC service and then click **OK**.</span></span>

    6. <span data-ttu-id="7a250-162">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="7a250-162">Click **OK** to close the dialog box.</span></span>

2. <span data-ttu-id="7a250-163">En el equipo de servicio y el equipo cliente, configure el Firewall de Windows para incluir Microsoft DTC (MSDTC, Coordinador de transacciones distribuidas) en la lista de aplicaciones exceptuadas:</span><span class="sxs-lookup"><span data-stu-id="7a250-163">On the service machine and the client machine, configure the Windows Firewall to include the Microsoft Distributed Transaction Coordinator (MSDTC) to the list of excepted applications:</span></span>

    1. <span data-ttu-id="7a250-164">Ejecute la aplicación Firewall de Windows desde el Panel de control.</span><span class="sxs-lookup"><span data-stu-id="7a250-164">Run the Windows Firewall application from Control Panel.</span></span>

    2. <span data-ttu-id="7a250-165">En la pestaña **excepciones** , haga clic en **Agregar programa**.</span><span class="sxs-lookup"><span data-stu-id="7a250-165">From the **Exceptions** tab, click **Add Program**.</span></span>

    3. <span data-ttu-id="7a250-166">Desplácese a la carpeta C:\WINDOWS\System32.</span><span class="sxs-lookup"><span data-stu-id="7a250-166">Browse to the folder C:\WINDOWS\System32.</span></span>

    4. <span data-ttu-id="7a250-167">Seleccione Msdtc.exe y haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="7a250-167">Select Msdtc.exe and click **Open**.</span></span>

    5. <span data-ttu-id="7a250-168">Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Agregar programa** y haga clic en **Aceptar** de nuevo para cerrar el applet Firewall de Windows.</span><span class="sxs-lookup"><span data-stu-id="7a250-168">Click **OK** to close the **Add Program** dialog box, and click **OK** again to close the Windows Firewall applet.</span></span>

3. <span data-ttu-id="7a250-169">En el equipo cliente, configure MSDTC para permitir las transacciones de red salientes:</span><span class="sxs-lookup"><span data-stu-id="7a250-169">On the client machine, configure MSDTC to allow outgoing network transactions:</span></span>

    1. <span data-ttu-id="7a250-170">En el menú **Inicio** , vaya a **Panel de control**, **herramientas administrativas** y servicios de **componentes**.</span><span class="sxs-lookup"><span data-stu-id="7a250-170">From the **Start** menu, navigate to **Control Panel**, then **Administrative Tools**, and then **Component Services**.</span></span>

    2. <span data-ttu-id="7a250-171">Haga clic con el botón derecho en **mi PC** y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7a250-171">Right-click **My Computer** and select **Properties**.</span></span>

    3. <span data-ttu-id="7a250-172">En la pestaña **MSDTC** , haga clic en **configuración de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="7a250-172">On the **MSDTC** tab, click **Security Configuration**.</span></span>

    4. <span data-ttu-id="7a250-173">Compruebe el **acceso a DTC desde la red** y **permita el tráfico saliente**.</span><span class="sxs-lookup"><span data-stu-id="7a250-173">Check **Network DTC Access** and **Allow Outbound**.</span></span>

    5. <span data-ttu-id="7a250-174">Haga clic en **sí** para reiniciar el servicio MS DTC y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7a250-174">Click **Yes** to restart the MS DTC service and then click **OK**.</span></span>

    6. <span data-ttu-id="7a250-175">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="7a250-175">Click **OK** to close the dialog box.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7a250-176">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="7a250-176">The samples may already be installed on your machine.</span></span> <span data-ttu-id="7a250-177">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="7a250-177">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="7a250-178">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="7a250-178">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7a250-179">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="7a250-179">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Transactions`
