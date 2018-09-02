---
title: Procesamiento por lotes con transacciones
ms.date: 03/30/2017
ms.assetid: ecd328ed-332e-479c-a894-489609bcddd2
ms.openlocfilehash: abada9aaf5fac8f05599467f385e708e1898832f
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43416653"
---
# <a name="transacted-batching"></a><span data-ttu-id="2a4a7-102">Procesamiento por lotes con transacciones</span><span class="sxs-lookup"><span data-stu-id="2a4a7-102">Transacted Batching</span></span>
<span data-ttu-id="2a4a7-103">Este ejemplo muestra cómo procesar por lotes transacciones leídas mediante Message Queuing (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="2a4a7-103">This sample demonstrates how to batch transacted reads by using Message Queuing (MSMQ).</span></span> <span data-ttu-id="2a4a7-104">El procesamiento por lotes con transacciones es una característica de optimización de rendimiento para las transacciones leídas en comunicación en cola.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-104">Transacted Batching is a performance optimization feature for transacted reads in queued communication.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2a4a7-105">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="2a4a7-106">En la comunicación con colas, el cliente se comunica con el servicio mediante una cola.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-106">In queued communication, the client communicates to the service using a queue.</span></span> <span data-ttu-id="2a4a7-107">Más exactamente, el cliente envía los mensajes a una cola.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-107">More precisely, the client sends messages to a queue.</span></span> <span data-ttu-id="2a4a7-108">El servicio recibe los mensajes de la cola.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-108">The service receives messages from the queue.</span></span> <span data-ttu-id="2a4a7-109">El servicio y el cliente no necesitan ejecutarse simultáneamente para comunicarse mediante una cola.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-109">The service and client therefore, do not have to be running at the same time to communicate using a queue.</span></span>  
  
 <span data-ttu-id="2a4a7-110">Este ejemplo muestra el procesamiento por lotes con transacciones.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-110">This sample demonstrates transacted batching.</span></span> <span data-ttu-id="2a4a7-111">El procesamiento por lotes con transacciones es un comportamiento que habilita el uso de una transacción única cuando se leen y se procesan muchos mensajes en la cola.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-111">Transacted batching is a behavior that enables the use of a single transaction when reading many messages in the queue and processing them.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="2a4a7-112">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="2a4a7-112">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="2a4a7-113">Asegúrese de que ha realizado la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="2a4a7-113">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="2a4a7-114">Si se ejecuta el servicio primero, comprobará que la cola esté presente.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-114">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="2a4a7-115">Si la cola no está presente, el servicio creará una.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-115">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="2a4a7-116">Puede ejecutar primero el servicio para crear la cola, o puede crear una a través del administrador de cola de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-116">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="2a4a7-117">Siga estos pasos para crear una cola en Windows 2008.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-117">Follow these steps to create a queue in Windows 2008.</span></span>  
  
    1.  <span data-ttu-id="2a4a7-118">Abra el Administrador del servidor en [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a4a7-118">Open Server Manager in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
    2.  <span data-ttu-id="2a4a7-119">Expanda el **características** ficha.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-119">Expand the **Features** tab.</span></span>  
  
    3.  <span data-ttu-id="2a4a7-120">Haga clic en **cola de mensajes privados**y seleccione **New**, **cola privada**.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-120">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>  
  
    4.  <span data-ttu-id="2a4a7-121">Compruebe el **transaccional** cuadro.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-121">Check the **Transactional** box.</span></span>  
  
    5.  <span data-ttu-id="2a4a7-122">Escriba `ServiceModelSamplesTransacted` como el nombre de la nueva cola.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-122">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2a4a7-123">En este ejemplo, el cliente envía cientos de mensajes como parte del lote.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-123">In this sample the client sends hundreds of messages as part of the batch.</span></span> <span data-ttu-id="2a4a7-124">Es normal que la aplicación del servicio tarde algún tiempo en procesarlos.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-124">It is normal for the service application to take some time to process these.</span></span>  
  
3.  <span data-ttu-id="2a4a7-125">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="2a4a7-125">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="2a4a7-126">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="2a4a7-126">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup-or-without-active-directory-integration"></a><span data-ttu-id="2a4a7-127">Para ejecutar el ejemplo en un equipo unido a un grupo de trabajo o sin integración con Active Directory</span><span class="sxs-lookup"><span data-stu-id="2a4a7-127">To run the sample on a computer joined to a workgroup or without active directory integration</span></span>  
  
1.  <span data-ttu-id="2a4a7-128">De forma predeterminada con <xref:System.ServiceModel.NetMsmqBinding>, la seguridad de transporte está habilitada.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-128">By default with the <xref:System.ServiceModel.NetMsmqBinding>, transport security is enabled.</span></span> <span data-ttu-id="2a4a7-129">Hay dos propiedades pertinentes para la seguridad de transporte MSMQ, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> y <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> `.` de forma predeterminada, el modo de autenticación se establece en `Windows` y el nivel de protección se establece en `Sign`.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-129">There are two relevant properties for MSMQ transport security, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> and <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>`.` By default, the authentication mode is set to `Windows` and the protection level is set to `Sign`.</span></span> <span data-ttu-id="2a4a7-130">Para que MSMQ proporcione la autenticación y la característica de firma, debe formar parte de un dominio y debe instalarse la opción de integración de directorio activo para MSMQ.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-130">For MSMQ to provide the authentication and signing feature, it must be part of a domain and the active directory integration option for MSMQ must be installed.</span></span> <span data-ttu-id="2a4a7-131">Si ejecuta este ejemplo en un equipo que no cumple estos criterios, recibirá un error.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-131">If you run this sample on a computer that does not satisfy these criteria you receive an error.</span></span>  
  
2.  <span data-ttu-id="2a4a7-132">Si su equipo no es parte de un dominio o no tiene la integración del directorio activo instalada, desactive la seguridad de transporte, estableciendo el modo de autenticación y el nivel de protección en `None`, tal y como se muestra en la configuración de ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2a4a7-132">If your computer is not part of a domain or does not have active directory integration installed, turn off transport security by setting the authentication mode and protection level to `None` as shown in the following sample configuration:</span></span>  
  
    ```xml  
    <system.serviceModel>  
      <behaviors>  
        <serviceBehaviors>  
          <behavior name="ThrottlingBehavior">  
            <serviceMetadata httpGetEnabled="true"/>  
            <serviceThrottling maxConcurrentCalls="5"/>  
          </behavior>  
        </serviceBehaviors>  
  
        <endpointBehaviors>  
          <behavior name="BatchingBehavior">  
            <transactedBatching maxBatchSize="100"/>  
          </behavior>  
        </endpointBehaviors>  
      </behaviors>  
      <services>  
        <service   
            behaviorConfiguration="ThrottlingBehavior"   
            name="Microsoft.ServiceModel.Samples.OrderProcessorService">  
          <host>  
            <baseAddresses>  
              <add baseAddress="http://localhost:8000/orderProcessor/transactedBatchingSample"/>  
            </baseAddresses>  
          </host>  
          <!-- Define NetMsmqEndpoint -->  
          <endpoint address="net.msmq://localhost/private/ServiceModelSamplesTransactedBatching"  
                    binding="netMsmqBinding"  
                    bindingConfiguration="Binding1"   
                    behaviorConfiguration="BatchingBehavior"   
                    contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
          <endpoint address="mex"  
                    binding="mexHttpBinding"  
                    contract="IMetadataExchange" />  
        </service>  
      </services>  
  
      <bindings>  
        <netMsmqBinding>  
          <binding name="Binding1">  
            <security mode="None" />  
          </binding>  
        </netMsmqBinding>  
      </bindings>  
  
    </system.serviceModel>  
    ```  
  
3.  <span data-ttu-id="2a4a7-133">Asegúrese de que cambia la configuración en el servidor y el cliente antes de ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-133">Ensure that you change the configuration on both the server and the client before you run the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2a4a7-134">Establecer `security``mode` en `None` es equivalente a definir la seguridad de <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> y `Message` en `None`.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-134">Setting `security``mode` to `None` is equivalent to setting <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>, and `Message` security to `None`.</span></span>  
  
4.  <span data-ttu-id="2a4a7-135">Para ejecutar la base de datos en un equipo remoto, cambie la cadena de conexión para que señale al equipo en el que reside la base de datos.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-135">To run the database on a remote computer, change the connection string to point to the computer on which the database resides.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a4a7-136">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2a4a7-136">Requirements</span></span>  
 <span data-ttu-id="2a4a7-137">Para ejecutar este ejemplo, MSMQ debe estar instalado, y se necesitan SQL o SQL Express.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-137">To run this sample, MSMQ must be installed and SQL or SQL Express is required.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="2a4a7-138">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="2a4a7-138">Demonstrates</span></span>  
 <span data-ttu-id="2a4a7-139">El ejemplo muestra el comportamiento del procesamiento por lotes con transacciones.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-139">The sample demonstrates transacted batching behavior.</span></span> <span data-ttu-id="2a4a7-140">El procesamiento por lotes con transacciones es una característica de optimización de rendimiento proporcionada con el transporte por colas de MSMQ.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-140">Transacted batching is a performance optimization feature provided with MSMQ queued transport.</span></span>  
  
 <span data-ttu-id="2a4a7-141">Cuando las transacciones se utilizan para enviar y recibir mensajes, hay en realidad 2 transacciones independientes.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-141">When transactions are used to send and receive messages there are actually 2 separate transactions.</span></span> <span data-ttu-id="2a4a7-142">Cuando el cliente envía los mensajes dentro del ámbito de una transacción, la transacción es local para el cliente y el administrador de cola del cliente.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-142">When the client sends messages within the scope of a transaction, the transaction is local to the client and the client queue manager.</span></span> <span data-ttu-id="2a4a7-143">Cuando el servicio recibe los mensajes dentro del ámbito de la transacción, la transacción es local para el servicio y el administrador de cola receptor.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-143">When the service receives messages within the scope of the transaction, the transaction is local to the service and the receiving queue manager.</span></span> <span data-ttu-id="2a4a7-144">Es muy importante recordar que el cliente y el servicio no están participando en la misma transacción; más bien, están utilizando distintas transacciones al realizar sus operaciones (como enviar y recibir) con la cola.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-144">It is very important to remember that the client and the service are not participating in the same transaction; rather they are using different transactions when performing their operations (such as send and receive) with the queue.</span></span>  
  
 <span data-ttu-id="2a4a7-145">En el ejemplo utilizamos una transacción única para la ejecución de varias operaciones del servicio.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-145">In the sample we use a single transaction for the execution of multiple service operations.</span></span> <span data-ttu-id="2a4a7-146">Esto se utiliza solo como una característica de optimización de rendimiento y no tiene afecta a la semántica de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-146">This is used only as a performance optimization feature and does not impact the semantics of the application.</span></span> <span data-ttu-id="2a4a7-147">El ejemplo se basa en [transacciones enlace MSMQ](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md).</span><span class="sxs-lookup"><span data-stu-id="2a4a7-147">The sample is based on [Transacted MSMQ Binding](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md).</span></span>  
  
## <a name="comments"></a><span data-ttu-id="2a4a7-148">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2a4a7-148">Comments</span></span>  
 <span data-ttu-id="2a4a7-149">En este ejemplo, el cliente envía un lote de mensajes al servicio desde dentro del ámbito de una transacción.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-149">In this sample, the client sends a batch of messages to the service from within the scope of a transaction.</span></span> <span data-ttu-id="2a4a7-150">Enviamos un número grande de mensajes que muestre la optimización de rendimiento; en este caso, hasta 2500 mensajes.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-150">To show the performance optimization, we send a large number of messages; in this case, up to 2500 messages.</span></span>  
  
 <span data-ttu-id="2a4a7-151">El servicio recibe a continuación los mensajes enviados a la cola dentro del ámbito de la transacción definido por el servicio.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-151">The messages sent to the queue are then received by the service within the transaction scope defined by the service.</span></span> <span data-ttu-id="2a4a7-152">Sin el procesamiento por lotes, esto produce 2500 transacciones para cada invocación de la operación del servicio.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-152">Without batching, this results in 2500 transactions for each invocation of the service operation.</span></span> <span data-ttu-id="2a4a7-153">Esto afecta el rendimiento del sistema.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-153">This impacts performance of the system.</span></span> <span data-ttu-id="2a4a7-154">Dado que dos administradores de recursos están implicados, la cola de MSMQ y la base de datos `Orders`- cada transacción de este tipo es una transacción de DTC.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-154">Because two resource managers are involved -the MSMQ queue and the `Orders` database- each such transaction is a DTC transaction.</span></span> <span data-ttu-id="2a4a7-155">Optimizamos esto utilizando un número mucho menor de transacciones asegurando que un lote de mensajes e invocaciones de operación de servicio pasan en una transacción única.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-155">We optimize this by using a much smaller number of transactions by ensuring that a batch of messages and service operation invocations happen in a single transaction.</span></span>  
  
 <span data-ttu-id="2a4a7-156">Utilizamos la característica por lotes mediante:</span><span class="sxs-lookup"><span data-stu-id="2a4a7-156">We use the batching feature by:</span></span>  
  
-   <span data-ttu-id="2a4a7-157">La especificación del comportamiento del procesamiento por lotes con transacciones en configuración.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-157">Specifying transacted batching behavior in configuration.</span></span>  
  
-   <span data-ttu-id="2a4a7-158">La especificación del tamañao de un lote en términos del número de mensajes que se leen utilizando una transacción única.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-158">Specifying a batch size in terms of number of messages to be read using a single transaction.</span></span>  
  
-   <span data-ttu-id="2a4a7-159">La especificación del número máximo de lotes simultáneos ejecutados.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-159">Specifying the maximum number of concurrent batches to run.</span></span>  
  
 <span data-ttu-id="2a4a7-160">En este ejemplo, mostramos ganancias en el rendimiento reduciendo el número de transacciones asegurando que 100 operaciones del servicio se invocan en una transacción única antes de confirmar la transacción.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-160">In this example, we show performance gains by reducing the number of transactions by ensuring that 100 service operations are invoked in a single transaction before committing the transaction.</span></span>  
  
 <span data-ttu-id="2a4a7-161">El comportamiento del servicio define un comportamiento de la operación con `TransactionScopeRequired` definido en `true`.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-161">The service behavior defines an operation behavior with `TransactionScopeRequired` set to `true`.</span></span> <span data-ttu-id="2a4a7-162">Esto garantiza que los administradores de recursos a los que el método tiene acceso utilizan el mismo ámbito de la transacción usado para recuperar el mensaje de la cola.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-162">This ensures that the same transaction scope that is used to retrieve the message from the queue is used by any resource managers accessed by the method.</span></span> <span data-ttu-id="2a4a7-163">En este ejemplo, utilizamos una base de datos básica para almacenar la información del pedido de compra contenida en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-163">In this example, we use a basic database to store the purchase order information contained in the message.</span></span> <span data-ttu-id="2a4a7-164">El ámbito de la transacción también garantiza que si el método produce una excepción, el mensaje se devuelva a la cola.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-164">The transaction scope also guarantees that if the method throws an exception, the message is returned to the queue.</span></span> <span data-ttu-id="2a4a7-165">Sin establecer este comportamiento de operación, un canal en cola crea una transacción para leer el mensaje de la cola y lo confirma automáticamente antes de la expedición de tal manera que si se produce un error en la operación, el mensaje se pierde.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-165">Without setting this operation behavior, a queued channel creates a transaction to read the message from the queue and commits it automatically before it is dispatched so that if the operation fails, the message is lost.</span></span> <span data-ttu-id="2a4a7-166">El escenario más común es que las operaciones de servicio se inscriban en la transacción que se utiliza para leer el mensaje de la cola, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-166">The most common scenario is for service operations to enlist in the transaction that is used to read the message from the queue as demonstrated in the following code.</span></span>  
  
 <span data-ttu-id="2a4a7-167">Observe que `ReleaseServiceInstanceOnTransactionComplete` está establecido en `false`.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-167">Note that `ReleaseServiceInstanceOnTransactionComplete` is set to `false`.</span></span> <span data-ttu-id="2a4a7-168">Éste es un requisito importante para el procesamiento por lotes.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-168">This is an important requirement for batching.</span></span> <span data-ttu-id="2a4a7-169">La propiedad `ReleaseServiceInstanceOnTransactionComplete` en `ServiceBehaviorAttribute` indica qué hacer con la instancia del servicio una vez la transacción se completa.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-169">The property `ReleaseServiceInstanceOnTransactionComplete` on `ServiceBehaviorAttribute` indicates what to do with the service instance once the transaction is completed.</span></span> <span data-ttu-id="2a4a7-170">De forma predeterminada, la instancia del servicio se lanza al completar la transacción.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-170">By default, the service instance is released upon completing the transaction.</span></span> <span data-ttu-id="2a4a7-171">El aspecto básico del procesamiento por lotes es el uso de una transacción única para leer y enviar muchos mensajes en la cola.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-171">The core aspect to batching is the use of a single transaction for reading and dispatching many messages in the queue.</span></span> <span data-ttu-id="2a4a7-172">Por consiguiente, al lanzar la instancia del servicio, se acaba completando la transacción prematuramente, lo que niega el mismo uso del procesamiento por lotes.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-172">Therefore releasing the service instance ends up completing the transaction prematurely negating the very use of batching.</span></span> <span data-ttu-id="2a4a7-173">Si esta propiedad está establecida en `true` y el comportamiento del procesamiento por lotes con transacciones se agrega al extremo, el comportamiento de la validación por lotes produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-173">If this property is set to `true` and transacted batching behavior is added to the endpoint, the batching validation behavior throws an exception.</span></span>  

```csharp
// Service class that implements the service contract.  
// Added code to write output to the console window.  
[ServiceBehavior(ReleaseServiceInstanceOnTransactionComplete=false,   
TransactionIsolationLevel=  
System.Transactions.IsolationLevel.Serializable, ConcurrencyMode=ConcurrencyMode.Multiple)]  
public class OrderProcessorService : IOrderProcessor  
{  
    [OperationBehavior(TransactionScopeRequired = true,  
                       TransactionAutoComplete = true)]  
    public void SubmitPurchaseOrder(PurchaseOrder po)  
    {  
        Orders.Add(po);  
        Console.WriteLine("Processing {0} ", po);  
    }  
    …  
}  
```

 <span data-ttu-id="2a4a7-174">La clase `Orders` encapsula el procesamiento de la orden.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-174">The `Orders` class encapsulates the processing of the order.</span></span> <span data-ttu-id="2a4a7-175">En el ejemplo, actualiza la base de datos con información del pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-175">In the sample, it updates the database with purchase order information.</span></span>  

```csharp
// Order Processing Logic  
public class Orders  
{  
    public static void Add(PurchaseOrder po)  
    {  
        // Insert purchase order.  
        SqlCommand insertPurchaseOrderCommand =   
        new SqlCommand(  
        "insert into PurchaseOrders(poNumber, customerId)   
                               values(@poNumber, @customerId)");  
        insertPurchaseOrderCommand.Parameters.Add("@poNumber",   
                                           SqlDbType.VarChar, 50);  
        insertPurchaseOrderCommand.Parameters.Add("@customerId",   
                                         SqlDbType.VarChar, 50);  
  
        // Insert product line item.  
        SqlCommand insertProductLineItemCommand =   
             new SqlCommand("insert into ProductLineItems(productId,   
                    unitCost, quantity, poNumber) values(@productId,   
                    @unitCost, @quantity, @poNumber)");  
        insertProductLineItemCommand.Parameters.Add("@productId",   
                                           SqlDbType.VarChar, 50);  
        insertProductLineItemCommand.Parameters.Add("@unitCost",   
                                                  SqlDbType.Float);  
        insertProductLineItemCommand.Parameters.Add("@quantity",   
                                                     SqlDbType.Int);  
        insertProductLineItemCommand.Parameters.Add("@poNumber",   
                                           SqlDbType.VarChar, 50);  
        int rowsAffected = 0;  
        using (TransactionScope scope =   
              new TransactionScope(TransactionScopeOption.Required))  
        {  
             using (SqlConnection conn = new   
                 SqlConnection(  
                 ConfigurationManager.AppSettings["connectionString"]))  
             {  
                 conn.Open();  
  
                // Insert into purchase order table.  
               insertPurchaseOrderCommand.Connection = conn;  
               insertPurchaseOrderCommand.Parameters["@poNumber"].Value   
                                                       = po.PONumber;  
             insertPurchaseOrderCommand.Parameters["@customerId"].Value   
                                                    =po.CustomerId;  
             insertPurchaseOrderCommand.ExecuteNonQuery();  
  
            // Insert into product line item table.  
            insertProductLineItemCommand.Connection = conn;  
            foreach (PurchaseOrderLineItem orderLineItem in   
                                        po.orderLineItems) {  
            insertProductLineItemCommand.Parameters["@poNumber"].Value   
                                                          =po.PONumber;  
            insertProductLineItemCommand.Parameters["@productId"].Value   
                                             = orderLineItem.ProductId;  
            insertProductLineItemCommand.Parameters["@unitCost"].Value   
                                             = orderLineItem.UnitCost;  
            insertProductLineItemCommand.Parameters["@quantity"].Value   
                                             = orderLineItem.Quantity;  
            rowsAffected +=   
            insertProductLineItemCommand.ExecuteNonQuery();  
            }  
            scope.Complete();  
        }  
     }  
     Console.WriteLine(  
     "Updated database with {0} product line items  for purchase order   
                                     {1} ", rowsAffected, po.PONumber);  
    }  
}  
```

 <span data-ttu-id="2a4a7-176">El comportamiento del procesamiento por lotes y su configuración se especifican en la configuración de la aplicación del servicio.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-176">The batching behavior and its configuration are specified in the service application configuration.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <appSettings>  
    <!-- Use appSetting to configure MSMQ queue name. -->  
    <add key="queueName"   
     value=".\private$\ServiceModelSamplesTransactedBatching" />  
    <add key="baseAddress"   
     value=  
     "http://localhost:8000/orderProcessor/transactedBatchingSample"/>  
    <add key="connectionString" value="Data Source=.\SQLEXPRESS;AttachDbFilename=|DataDirectory|orders.mdf;Integrated Security=True;User Instance=True;" />  
  </appSettings>  
  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ThrottlingBehavior">  
          <serviceThrottling maxConcurrentCalls="5"/>  
        </behavior>  
      </serviceBehaviors>  
  
      <endpointBehaviors>  
        <behavior name="BatchingBehavior">  
          <transactedBatching maxBatchSize="100"/>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <services>  
      <service   
          behaviorConfiguration="ThrottlingBehavior"   
          name="Microsoft.ServiceModel.Samples.OrderProcessorService">  
        <!-- Define NetMsmqEndpoint -->  
        <endpoint address=  
"net.msmq://localhost/private/ServiceModelSamplesTransactedBatching"  
                  binding="netMsmqBinding"  
                  behaviorConfiguration="BatchingBehavior"   
                  contract=  
                    "Microsoft.ServiceModel.Samples.IOrderProcessor" />  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
> [!NOTE]
>  <span data-ttu-id="2a4a7-177">El tamaño del lote es una pista para el sistema.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-177">The batch size is a hint to the system.</span></span> <span data-ttu-id="2a4a7-178">Por ejemplo, si especifica un tamaño del lote de 20, entonces se leerían y se enviarían 20 mensajes utilizando una transacción única y, a continuación, se confirmaría la transacción.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-178">For example, if you specify a batch size of 20, then 20 messages would be read and dispatched using a single transaction and then the transaction is committed.</span></span> <span data-ttu-id="2a4a7-179">Pero hay casos donde la transacción puede confirmar el lote antes del tamaño del lote se alcanza.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-179">But there are cases where the transaction may commit the batch before the batch size is reached.</span></span>  
>   
>  <span data-ttu-id="2a4a7-180">Se asocia a cada transacción un tiempo de espera, que se inicia una vez se crea la transacción.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-180">Associated with every transaction is a timeout that starts ticking once the transaction is created.</span></span> <span data-ttu-id="2a4a7-181">Cuando este tiempo de espera expira se anula la transacción.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-181">When this timeout expires the transaction is aborted.</span></span> <span data-ttu-id="2a4a7-182">Es posible que este tiempo de espera incluso expire antes de que se alcance el tamaño del lote.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-182">It is possible for this timeout to expire even before the batch size is reached.</span></span> <span data-ttu-id="2a4a7-183">Para evitar tener que trabajar de nuevo sobre el lote debido a la interrupción, `TransactedBatchingBehavior` comprueba para ver cuánto tiempo queda en la transacción.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-183">To avoid re-working the batch because of the abort, the `TransactedBatchingBehavior` checks to see how much time is left on the transaction.</span></span> <span data-ttu-id="2a4a7-184">Si se agota el 80% del tiempo de espera de la transacción, entonces se confirma la transacción.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-184">If 80% of the transaction timeout is used up, then the transaction is committed.</span></span>  
>   
>  <span data-ttu-id="2a4a7-185">Si no hay ningún mensaje más en la cola, en lugar de esperar a que se alcance el tamaño del lote <xref:System.ServiceModel.Description.TransactedBatchingBehavior> confirma la transacción.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-185">If there are no more messages in the queue then instead of waiting for the fulfillment of the batch size the <xref:System.ServiceModel.Description.TransactedBatchingBehavior> commits the transaction.</span></span>  
>   
>  <span data-ttu-id="2a4a7-186">La opción del tamaño del lote depende de su aplicación.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-186">The choice of the batch size is dependent on your application.</span></span> <span data-ttu-id="2a4a7-187">Si el tamaño del lote es demasiado pequeño, puede no obtener el rendimiento deseado.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-187">If the batch size is too small, you may not get the desired performance.</span></span> <span data-ttu-id="2a4a7-188">Por otro lado si el tamaño del lote es demasiado grande, puede deteriorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-188">On the other hand if the batch size is too big, it may deteriorate performance.</span></span> <span data-ttu-id="2a4a7-189">Por ejemplo, su transacción podría durar mucho más tiempo y realizar bloqueos en su base de datos o su transacción se podría bloquear, lo que podría hacer que el lote se revierta y rehacer el trabajo.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-189">For example, your transaction could live longer and hold locks on your database or your transaction could become dead locked, which could cause the batch to get rolled back and to redo the work.</span></span>  
  
 <span data-ttu-id="2a4a7-190">El cliente crea un ámbito de transacción.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-190">The client creates a transaction scope.</span></span> <span data-ttu-id="2a4a7-191">La comunicación con la cola tiene lugar dentro del ámbito de la transacción, provocando que se trate como una unidad atómica donde se envían todos los mensajes a la cola o no se envía ninguno.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-191">Communication with the queue takes place within the scope of the transaction, causing it to be treated as an atomic unit where all messages are sent to the queue or none of the messages are sent to the queue.</span></span> <span data-ttu-id="2a4a7-192">La transacción se confirma llamando a <xref:System.Transactions.TransactionScope.Complete%2A> en el ámbito de la transacción.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-192">The transaction is committed by calling <xref:System.Transactions.TransactionScope.Complete%2A> on the transaction scope.</span></span>  

```csharp
//Client implementation code.  
class Client  
{  
    static void Main()  
    {  
        Random randomGen = new Random();  
        for (int i = 0; i < 2500; i++)  
        {  
            // Create a client with given client endpoint configuration.  
            OrderProcessorClient client = new OrderProcessorClient("OrderProcessorEndpoint");  
  
            // Create the purchase order.  
            PurchaseOrder po = new PurchaseOrder();  
            po.CustomerId = "somecustomer" + i + ".com";  
            po.PONumber = Guid.NewGuid().ToString();  
  
            PurchaseOrderLineItem lineItem1 = new PurchaseOrderLineItem();  
            lineItem1.ProductId = "Blue Widget";  
            lineItem1.Quantity = randomGen.Next(1, 100);  
            lineItem1.UnitCost = (float)randomGen.NextDouble() * 10;  
  
            PurchaseOrderLineItem lineItem2 = new PurchaseOrderLineItem();  
            lineItem2.ProductId = "Red Widget";  
            lineItem2.Quantity = 890;  
            lineItem2.UnitCost = 45.89F;  
  
            po.orderLineItems = new PurchaseOrderLineItem[2];  
            po.orderLineItems[0] = lineItem1;  
            po.orderLineItems[1] = lineItem2;  
  
            //Create a transaction scope.  
            using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
            {  
                // Make a queued call to submit the purchase order.  
                client.SubmitPurchaseOrder(po);  
                // Complete the transaction.  
                scope.Complete();  
            }  
  
            client.Close();  
        }  
        Console.WriteLine();  
        Console.WriteLine("Press <ENTER> to terminate client.");  
        Console.ReadLine();  
    }  
}  
```

 <span data-ttu-id="2a4a7-193">Al ejecutar el ejemplo, las actividades del servicio y del cliente se muestran en las ventanas de la consola del cliente y del servicio.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-193">When you run the sample, the client and service activities are displayed in both the service and client console windows.</span></span> <span data-ttu-id="2a4a7-194">Puede ver los mensajes recibidos por el servicio desde el cliente.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-194">You can see the service receive messages from the client.</span></span> <span data-ttu-id="2a4a7-195">Presione Entrar en cada ventana de la consola para cerrar el servicio y el cliente.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-195">Press ENTER in each console window to shut down the service and client.</span></span> <span data-ttu-id="2a4a7-196">Observe que debido a que se está usando el proceso de poner en cola, el cliente y el servicio no tienen que estar activados y ejecutándose simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-196">Note that because queuing is in use, the client and service do not have to be up and running at the same time.</span></span> <span data-ttu-id="2a4a7-197">Puede ejecutar el cliente, cerrarlo e iniciar el servicio y seguir recibiendo mensajes.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-197">You can run the client, shut it down, and then start up the service and it still receives its messages.</span></span> <span data-ttu-id="2a4a7-198">Puede observar un gran resultado cuando los mensajes se leen en un lote y se procesan.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-198">You can see a rolling output as messages are read in a batch and processed.</span></span>  
  
```  
The service is ready.  
Press <ENTER> to terminate service.  
  
Updated database with 2 product line items for purchase order 493ac832-d216-4e94-b2a5-d7f492fb5e39  
Processing Purchase Order: 8b567f5b-0661-4662-aae2-6cef1bd6d278  
        Customer: somecustomer849.com  
        OrderDetails  
               Order LineItem: 80 of Blue Widget @unit price: $9.751623  
               Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $41622.23  
        Order status: Pending  
  
Updated database with 2 product line items for purchase order 41130b95-4ea8-40a9-91c3-2e129117fcb8  
Processing Purchase Order: 5ce2699d-9a31-4cc2-a8c5-64cda614b3c7  
        Customer: somecustomer850.com  
        OrderDetails  
               Order LineItem: 89 of Blue Widget @unit price: $6.369128  
               Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $41408.95  
        Order status: Pending  
  
Updated database with 2 product line items for purchase order 8b567f5b-0661-4662-aae2-6cef1bd6d278  
Processing Purchase Order: ea94486b-7c86-4309-a42d-2f06c00656cd  
        Customer: somecustomer851.com  
        OrderDetails  
             Order LineItem: 47 of Blue Widget @unit price: $0.9391424  
             Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $40886.24  
        Order status: Pending  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="2a4a7-199">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-199">The samples may already be installed on your computer.</span></span> <span data-ttu-id="2a4a7-200">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-200">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2a4a7-201">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-201">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2a4a7-202">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="2a4a7-202">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Batching`  
  
## <a name="see-also"></a><span data-ttu-id="2a4a7-203">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a4a7-203">See Also</span></span>
