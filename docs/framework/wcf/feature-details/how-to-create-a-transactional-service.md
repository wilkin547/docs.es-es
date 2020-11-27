---
title: Procedimiento para crear un servicio transaccional
ms.date: 03/30/2017
ms.assetid: 1bd2e4ed-a557-43f9-ba98-4c70cb75c154
ms.openlocfilehash: c3d094dbd5822f6025e1cc6c90aab04b61459314
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286297"
---
# <a name="how-to-create-a-transactional-service"></a><span data-ttu-id="eb762-102">Procedimiento para crear un servicio transaccional</span><span class="sxs-lookup"><span data-stu-id="eb762-102">How to: Create a Transactional Service</span></span>

<span data-ttu-id="eb762-103">Este ejemplo muestra varios aspectos sobre la creación de un servicio transaccional y el uso de una transacción iniciada por el cliente para coordinar las operaciones de servicio.</span><span class="sxs-lookup"><span data-stu-id="eb762-103">This sample demonstrates various aspects of creating a transactional service and the use of a client-initiated transaction to coordinate service operations.</span></span>  
  
### <a name="creating-a-transactional-service"></a><span data-ttu-id="eb762-104">Creación de un servicio transaccional</span><span class="sxs-lookup"><span data-stu-id="eb762-104">Creating a transactional service</span></span>  
  
1. <span data-ttu-id="eb762-105">Cree un contrato de servicios y anote las operaciones con el valor deseado de la enumeración <xref:System.ServiceModel.TransactionFlowOption> para especificar los requisitos de las transacciones entrantes.</span><span class="sxs-lookup"><span data-stu-id="eb762-105">Create a service contract and annotate the operations with the desired setting from the <xref:System.ServiceModel.TransactionFlowOption> enumeration to specify the incoming transaction requirements.</span></span> <span data-ttu-id="eb762-106">Tenga en cuenta que también puede colocar <xref:System.ServiceModel.TransactionFlowAttribute> en la clase de servicio que se va a implementar.</span><span class="sxs-lookup"><span data-stu-id="eb762-106">Note that you can also place the <xref:System.ServiceModel.TransactionFlowAttribute> on the service class being implemented.</span></span> <span data-ttu-id="eb762-107">Esto permite una implementación única de una interfaz para utilizar estos valores de transacción, en lugar de cada implementación.</span><span class="sxs-lookup"><span data-stu-id="eb762-107">This allows for a single implementation of an interface to use these transaction settings, instead of every implementation.</span></span>  
  
    ```csharp
    [ServiceContract]  
    public interface ICalculator  
    {  
        [OperationContract]  
        // Use this to require an incoming transaction  
        [TransactionFlow(TransactionFlowOption.Mandatory)]  
        double Add(double n1, double n2);  
        [OperationContract]  
        // Use this to permit an incoming transaction  
        [TransactionFlow(TransactionFlowOption.Allowed)]  
        double Subtract(double n1, double n2);  
    }  
    ```  
  
2. <span data-ttu-id="eb762-108">Cree una clase de implementación y utilice <xref:System.ServiceModel.ServiceBehaviorAttribute> para especificar opcionalmente <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> y <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A>.</span><span class="sxs-lookup"><span data-stu-id="eb762-108">Create an implementation class, and use the <xref:System.ServiceModel.ServiceBehaviorAttribute> to optionally specify a <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> and a <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A>.</span></span> <span data-ttu-id="eb762-109">Debería tener en cuenta que, en muchos casos, el valor predeterminado de <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A> de 60 segundos y el de <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> de `Unspecified` son adecuados.</span><span class="sxs-lookup"><span data-stu-id="eb762-109">You should note that in many cases, the default <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A> of 60 seconds and the default <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> of `Unspecified` are appropriate.</span></span> <span data-ttu-id="eb762-110">Para cada operación, puede utilizar el atributo <xref:System.ServiceModel.OperationBehaviorAttribute> para especificar si el trabajo realizado dentro del método debería producirse dentro del ámbito de la transacción según el valor del atributo <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>.</span><span class="sxs-lookup"><span data-stu-id="eb762-110">For each operation, you can use the <xref:System.ServiceModel.OperationBehaviorAttribute> attribute to specify whether work performed within the method should occur within the scope of a transaction scope according to the value of the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> attribute.</span></span> <span data-ttu-id="eb762-111">En este caso, la transacción utilizada para el método `Add` es igual que la transacción entrante obligatoria que fluye desde el cliente y la transacción utilizada para el método `Subtract` es igual que la transacción entrante si una fluye desde el cliente, o una transacción nueva creada implícitamente y localmente.</span><span class="sxs-lookup"><span data-stu-id="eb762-111">In this case, the transaction used for the `Add` method is the same as the mandatory incoming transaction that is flowed from the client, and the transaction used for the `Subtract` method is either the same as the incoming transaction if one was flowed from the client, or a new implicitly and locally created transaction.</span></span>  
  
    ```csharp
    [ServiceBehavior(  
        TransactionIsolationLevel = System.Transactions.IsolationLevel.Serializable,  
        TransactionTimeout = "00:00:45")]  
    public class CalculatorService : ICalculator  
    {  
        [OperationBehavior(TransactionScopeRequired = true)]  
        public double Add(double n1, double n2)  
        {  
            // Perform transactional operation  
            RecordToLog($"Adding {n1} to {n2}");
            return n1 + n2;  
        }  
  
        [OperationBehavior(TransactionScopeRequired = true)]  
        public double Subtract(double n1, double n2)  
        {  
            // Perform transactional operation  
            RecordToLog($"Subtracting {n2} from {n1}");
            return n1 - n2;  
        }  
  
        private static void RecordToLog(string recordText)  
        {  
            // Database operations omitted for brevity  
            // This is where the transaction provides specific benefit  
            // - changes to the database will be committed only when  
            // the transaction completes.  
        }  
    }  
    ```  
  
3. <span data-ttu-id="eb762-112">Configure los enlaces en el archivo de configuración, especificando que debería fluir el contexto de la transacción, y los protocolos que se van a utilizar para ello.</span><span class="sxs-lookup"><span data-stu-id="eb762-112">Configure the bindings in the configuration file, specifying that the transaction context should be flowed, and the protocols to be used to do so.</span></span> <span data-ttu-id="eb762-113">Para obtener más información, vea [configuración de transacciones de ServiceModel](servicemodel-transaction-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="eb762-113">For more information, see [ServiceModel Transaction Configuration](servicemodel-transaction-configuration.md).</span></span> <span data-ttu-id="eb762-114">Concretamente, se especifica el tipo de enlace en el atributo `binding` del elemento del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="eb762-114">Specifically, the binding type is specified in the endpoint element’s `binding` attribute.</span></span> <span data-ttu-id="eb762-115">El [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) elemento contiene un `bindingConfiguration` atributo que hace referencia a una configuración de enlace denominada `transactionalOleTransactionsTcpBinding` , como se muestra en la configuración del ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="eb762-115">The [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) element contains a `bindingConfiguration` attribute that references a binding configuration named `transactionalOleTransactionsTcpBinding`, as shown in the following sample configuration.</span></span>  
  
    ```xml  
    <service name="CalculatorService">  
      <endpoint address="net.tcp://localhost:8008/CalcService"  
        binding="netTcpBinding"  
        bindingConfiguration="transactionalOleTransactionsTcpBinding"  
        contract="ICalculator"  
        name="OleTransactions_endpoint" />  
    </service>  
    ```  
  
     <span data-ttu-id="eb762-116">El flujo de la transacción está habilitado en el nivel de configuración mediante el atributo `transactionFlow` y el protocolo de transacción se especifica mediante el atributo `transactionProtocol`, tal y como se muestra en la configuración siguiente.</span><span class="sxs-lookup"><span data-stu-id="eb762-116">Transaction flow is enabled at the configuration level by using the `transactionFlow` attribute, and the transaction protocol is specified using the `transactionProtocol` attribute, as shown in the following configuration.</span></span>  
  
    ```xml  
    <bindings>  
      <netTcpBinding>  
        <binding name="transactionalOleTransactionsTcpBinding"  
          transactionFlow="true"  
          transactionProtocol="OleTransactions"/>  
      </netTcpBinding>  
    </bindings>  
    ```  
  
### <a name="supporting-multiple-transaction-protocols"></a><span data-ttu-id="eb762-117">Compatibilidad de varios protocolos de transacción</span><span class="sxs-lookup"><span data-stu-id="eb762-117">Supporting multiple transaction protocols</span></span>  
  
1. <span data-ttu-id="eb762-118">Para obtener un rendimiento óptimo, debe usar el protocolo OleTransactions en escenarios que impliquen un cliente y un servicio escritos mediante Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="eb762-118">For optimal performance, you should use the OleTransactions protocol for scenarios involving a client and service written using Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="eb762-119">Sin embargo, el protocolo WS-AtomicTransaction (WS-AT) es útil para los escenarios cuando se requiere la interoperabilidad con pilas de protocolo de otro fabricante.</span><span class="sxs-lookup"><span data-stu-id="eb762-119">However, the WS-AtomicTransaction (WS-AT) protocol is useful for scenarios when interoperability with third-party protocol stacks is required.</span></span> <span data-ttu-id="eb762-120">Puede configurar los servicios WCF para que acepten ambos protocolos al proporcionar varios puntos de conexión con los enlaces específicos del protocolo adecuados, tal como se muestra en la configuración del ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="eb762-120">You can configure WCF services to accept both protocols by providing multiple endpoints with appropriate protocol-specific bindings, as shown in the following sample configuration.</span></span>  
  
    ```xml  
    <service name="CalculatorService">  
      <endpoint address="http://localhost:8000/CalcService"  
        binding="wsHttpBinding"  
        bindingConfiguration="transactionalWsatHttpBinding"  
        contract="ICalculator"  
        name="WSAtomicTransaction_endpoint" />  
      <endpoint address="net.tcp://localhost:8008/CalcService"  
        binding="netTcpBinding"  
        bindingConfiguration="transactionalOleTransactionsTcpBinding"  
        contract="ICalculator"  
        name="OleTransactions_endpoint" />  
    </service>  
    ```  
  
     <span data-ttu-id="eb762-121">El protocolo de transacción se especifica utilizando el atributo `transactionProtocol`.</span><span class="sxs-lookup"><span data-stu-id="eb762-121">The transaction protocol is specified using the `transactionProtocol` attribute.</span></span> <span data-ttu-id="eb762-122">Sin embargo, este atributo está ausente del `wsHttpBinding` proporcionado por sistema, ya que este enlace solo puede utilizar el protocolo WS-AT.</span><span class="sxs-lookup"><span data-stu-id="eb762-122">However, this attribute is absent from the system-provided `wsHttpBinding`, because this binding can only use the WS-AT protocol.</span></span>  
  
    ```xml  
    <bindings>  
      <wsHttpBinding>  
        <binding name="transactionalWsatHttpBinding"  
          transactionFlow="true" />  
      </wsHttpBinding>  
      <netTcpBinding>  
        <binding name="transactionalOleTransactionsTcpBinding"  
          transactionFlow="true"  
          transactionProtocol="OleTransactions"/>  
      </netTcpBinding>  
    </bindings>  
    ```  
  
### <a name="controlling-the-completion-of-a-transaction"></a><span data-ttu-id="eb762-123">Control de la realización de una transacción</span><span class="sxs-lookup"><span data-stu-id="eb762-123">Controlling the completion of a transaction</span></span>  
  
1. <span data-ttu-id="eb762-124">De forma predeterminada, las operaciones de WCF completan automáticamente las transacciones si no se produce ninguna excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="eb762-124">By default, WCF operations automatically complete transactions if no unhandled exceptions are thrown.</span></span> <span data-ttu-id="eb762-125">Puede modificar este comportamiento mediante la propiedad <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> y el método <xref:System.ServiceModel.OperationContext.SetTransactionComplete%2A>.</span><span class="sxs-lookup"><span data-stu-id="eb762-125">You can modify this behavior by using the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> property and the <xref:System.ServiceModel.OperationContext.SetTransactionComplete%2A> method.</span></span> <span data-ttu-id="eb762-126">Cuando es necesario que se produzca una operación dentro de la misma transacción como otra operación (por ejemplo, una operación de débito y crédito), puede deshabilitar el comportamiento de autocompletar definiendo la propiedad <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> en `false` tal y como se muestra en el ejemplo de operación `Debit` siguiente.</span><span class="sxs-lookup"><span data-stu-id="eb762-126">When an operation is required to occur within the same transaction as another operation (for example, a debit and credit operation), you can disable the autocomplete behavior by setting the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> property to `false` as shown in the following `Debit` operation example.</span></span> <span data-ttu-id="eb762-127">La transacción que la operación `Debit` utiliza no se completa hasta que se llama a un método con la propiedad <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> definida en `true`, tal y como se muestra en la operación `Credit1` o cuando se llama al método <xref:System.ServiceModel.OperationContext.SetTransactionComplete%2A> para marcar explícitamente la transacción como completada, tal y como se muestra en la operación `Credit2`.</span><span class="sxs-lookup"><span data-stu-id="eb762-127">The transaction the `Debit` operation uses is not completed until a method with the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> property set to `true` is called, as shown in the operation `Credit1`, or when the <xref:System.ServiceModel.OperationContext.SetTransactionComplete%2A> method is called to explicitly mark the transaction as complete, as shown in the operation `Credit2`.</span></span> <span data-ttu-id="eb762-128">Tenga en cuenta que las dos operaciones de crédito se muestran para fines informativos, y que una operación de crédito única sería más típica.</span><span class="sxs-lookup"><span data-stu-id="eb762-128">Note that the two credit operations are shown for illustration purposes, and that a single credit operation would be more typical.</span></span>  
  
    ```csharp
    [ServiceBehavior]  
    public class CalculatorService : IAccount  
    {  
        [OperationBehavior(  
            TransactionScopeRequired = true, TransactionAutoComplete = false)]  
        public void Debit(double n)  
        {  
            // Perform debit operation  
  
            return;  
        }  
  
        [OperationBehavior(  
            TransactionScopeRequired = true, TransactionAutoComplete = true)]  
        public void Credit1(double n)  
        {  
            // Perform credit operation  
  
            return;  
        }  
  
        [OperationBehavior(  
            TransactionScopeRequired = true, TransactionAutoComplete = false)]  
        public void Credit2(double n)  
        {  
            // Perform alternate credit operation  
  
            OperationContext.Current.SetTransactionComplete();  
            return;  
        }  
    }  
    ```  
  
2. <span data-ttu-id="eb762-129">Para la correlación de transacción, establecer la propiedad <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> en `false` requiere el uso de un enlace con sesión.</span><span class="sxs-lookup"><span data-stu-id="eb762-129">For the purposes of transaction correlation, setting the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> property to `false` requires the use of a sessionful binding.</span></span> <span data-ttu-id="eb762-130">Este requisito se especifica con la propiedad `SessionMode` en <xref:System.ServiceModel.ServiceContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="eb762-130">This requirement is specified with the `SessionMode` property on the <xref:System.ServiceModel.ServiceContractAttribute>.</span></span>  
  
    ```csharp
    [ServiceContract(SessionMode = SessionMode.Required)]  
    public interface IAccount  
    {  
        [OperationContract]  
        [TransactionFlow(TransactionFlowOption.Allowed)]  
        void Debit(double n);  
        [OperationContract]  
        [TransactionFlow(TransactionFlowOption.Allowed)]  
        void Credit1(double n);  
        [OperationContract]  
        [TransactionFlow(TransactionFlowOption.Allowed)]  
        void Credit2(double n);  
    }  
    ```  
  
### <a name="controlling-the-lifetime-of-a-transactional-service-instance"></a><span data-ttu-id="eb762-131">Control de la duración de una instancia de servicio transaccional</span><span class="sxs-lookup"><span data-stu-id="eb762-131">Controlling the lifetime of a transactional service instance</span></span>  
  
1. <span data-ttu-id="eb762-132">WCF usa la <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A> propiedad para especificar si se libera la instancia del servicio subyacente cuando se completa una transacción.</span><span class="sxs-lookup"><span data-stu-id="eb762-132">WCF uses the <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A> property to specify whether the underlying service instance is released when a transaction completes.</span></span> <span data-ttu-id="eb762-133">Dado que el valor predeterminado es `true` , a menos que se configure de otra forma, WCF exhibe un comportamiento de activación "Just-in-Time" eficaz y predecible.</span><span class="sxs-lookup"><span data-stu-id="eb762-133">Since this defaults to `true`, unless configured otherwise, WCF exhibits an efficient and predictable "just-in-time" activation behavior.</span></span> <span data-ttu-id="eb762-134">Las llamadas a un servicio en una transacción subsiguiente aseguran una nueva instancia del servicio sin restos del estado de la transacción anterior.</span><span class="sxs-lookup"><span data-stu-id="eb762-134">Calls to a service on a subsequent transaction are assured a new service instance with no remnants of the previous transaction's state.</span></span> <span data-ttu-id="eb762-135">Aunque esto resulta a menudo útil, a veces puede querer mantener el estado dentro de la instancia del servicio más allá de la realización de la transacción.</span><span class="sxs-lookup"><span data-stu-id="eb762-135">While this is often useful, sometimes you may want to maintain state within the service instance beyond the transaction completion.</span></span> <span data-ttu-id="eb762-136">Algunos ejemplos de ello serían cuándo resulta costoso recuperar o volver a constituir el estado necesario o los controladores a los recursos.</span><span class="sxs-lookup"><span data-stu-id="eb762-136">Examples of this would be when required state or handles to resources are expensive to retrieve or reconstitute.</span></span> <span data-ttu-id="eb762-137">Puede hacer esto al definir la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A> en `false`.</span><span class="sxs-lookup"><span data-stu-id="eb762-137">You can do this by setting the <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A> property to `false`.</span></span> <span data-ttu-id="eb762-138">Con ese valor, la instancia y cualquier estado asociado estarán disponibles en llamadas subsiguientes.</span><span class="sxs-lookup"><span data-stu-id="eb762-138">With that setting, the instance and any associated state will be available on subsequent calls.</span></span> <span data-ttu-id="eb762-139">Al utilizar esto, proporcione la consideración adecuada a cuándo y cómo se borrarán y completarán las transacciones y el estado.</span><span class="sxs-lookup"><span data-stu-id="eb762-139">When using this, give careful consideration to when and how state and transactions will be cleared and completed.</span></span> <span data-ttu-id="eb762-140">El ejemplo siguiente muestra cómo hacer esto manteniendo la instancia con la variable `runningTotal`.</span><span class="sxs-lookup"><span data-stu-id="eb762-140">The following sample demonstrates how to do this by maintaining the instance with the `runningTotal` variable.</span></span>  
  
    ```csharp
    [ServiceBehavior(TransactionIsolationLevel = [ServiceBehavior(  
        ReleaseServiceInstanceOnTransactionComplete = false)]  
    public class CalculatorService : ICalculator  
    {  
        double runningTotal = 0;  
  
        [OperationBehavior(TransactionScopeRequired = true)]  
        public double Add(double n)  
        {  
            // Perform transactional operation  
            RecordToLog($"Adding {n} to {runningTotal}");
            runningTotal = runningTotal + n;  
            return runningTotal;  
        }  
  
        [OperationBehavior(TransactionScopeRequired = true)]  
        public double Subtract(double n)  
        {  
            // Perform transactional operation  
            RecordToLog($"Subtracting {n} from {runningTotal}");
            runningTotal = runningTotal - n;  
            return runningTotal;  
        }  
  
        private static void RecordToLog(string recordText)  
        {  
            // Database operations omitted for brevity  
        }  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="eb762-141">Desde que la duración de la instancia es un comportamiento que es interno al servicio y controlado a través de la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute>, no se requiere ninguna modificación en la configuración de servicio ni en el contrato de servicio para establecer el comportamiento de la instancia.</span><span class="sxs-lookup"><span data-stu-id="eb762-141">Since the instance lifetime is a behavior that is internal to the service, and controlled through the <xref:System.ServiceModel.ServiceBehaviorAttribute> property, no modification to the service configuration or service contract is required to set the instance behavior.</span></span> <span data-ttu-id="eb762-142">Además, la conexión no contendrá ninguna representación de esto.</span><span class="sxs-lookup"><span data-stu-id="eb762-142">In addition, the wire will contain no representation of this.</span></span>
