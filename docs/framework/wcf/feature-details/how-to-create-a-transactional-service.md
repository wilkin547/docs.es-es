---
title: "Cómo: Crear un servicio transaccional"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1bd2e4ed-a557-43f9-ba98-4c70cb75c154
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4a61c1c4aeba63baee3c5e2ba5110710ed9f45f2
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-create-a-transactional-service"></a>Cómo: Crear un servicio transaccional
Este ejemplo muestra varios aspectos sobre la creación de un servicio transaccional y el uso de una transacción iniciada por el cliente para coordinar las operaciones de servicio.  
  
### <a name="creating-a-transactional-service"></a>Creación de un servicio transaccional  
  
1.  Cree un contrato de servicios y anote las operaciones con el valor deseado de la enumeración <xref:System.ServiceModel.TransactionFlowOption> para especificar los requisitos de las transacciones entrantes. Tenga en cuenta que también puede colocar <xref:System.ServiceModel.TransactionFlowAttribute> en la clase de servicio que se va a implementar. Esto permite una implementación única de una interfaz para utilizar estos valores de transacción, en lugar de cada implementación.  
  
    ```  
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
  
2.  Cree una clase de implementación y utilice <xref:System.ServiceModel.ServiceBehaviorAttribute> para especificar opcionalmente <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> y <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A>. Debería tener en cuenta que, en muchos casos, el valor predeterminado de <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A> de 60 segundos y el de <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> de `Unspecified` son adecuados. Para cada operación, puede utilizar el atributo <xref:System.ServiceModel.OperationBehaviorAttribute> para especificar si el trabajo realizado dentro del método debería producirse dentro del ámbito de la transacción según el valor del atributo <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>. En este caso, la transacción utilizada para el método `Add` es igual que la transacción entrante obligatoria que fluye desde el cliente y la transacción utilizada para el método `Subtract` es igual que la transacción entrante si una fluye desde el cliente, o una transacción nueva creada implícitamente y localmente.  
  
    ```  
    [ServiceBehavior(  
        TransactionIsolationLevel = System.Transactions.IsolationLevel.Serializable,  
        TransactionTimeout = "00:00:45")]  
    public class CalculatorService : ICalculator  
    {  
        [OperationBehavior(TransactionScopeRequired = true)]  
        public double Add(double n1, double n2)  
        {  
            // Perform transactional operation  
            RecordToLog(String.Format("Adding {0} to {1}", n1, n2));  
            return n1 + n2;  
        }  
  
        [OperationBehavior(TransactionScopeRequired = true)]  
        public double Subtract(double n1, double n2)  
        {  
            // Perform transactional operation  
            RecordToLog(String.Format("Subtracting {0} from {1}", n2, n1));  
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
  
3.  Configure los enlaces en el archivo de configuración, especificando que debería fluir el contexto de la transacción, y los protocolos que se van a utilizar para ello. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Configuración de transacción de ServiceModel](../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md). Concretamente, se especifica el tipo de enlace en el atributo `binding` del elemento del extremo. El [ \<extremo >](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) elemento contiene un `bindingConfiguration` atributo que hace referencia a una configuración de enlace denominada `transactionalOleTransactionsTcpBinding`, tal y como se muestra en el siguiente ejemplo de configuración.  
  
    ```xml  
    <service name="CalculatorService">  
      <endpoint address="net.tcp://localhost:8008/CalcService"  
        binding="netTcpBinding"  
        bindingConfiguration="transactionalOleTransactionsTcpBinding"  
        contract="ICalculator"  
        name="OleTransactions_endpoint" />  
    </service>  
    ```  
  
     El flujo de la transacción está habilitado en el nivel de configuración mediante el atributo `transactionFlow` y el protocolo de transacción se especifica mediante el atributo `transactionProtocol`, tal y como se muestra en la configuración siguiente.  
  
    ```xml  
    <bindings>  
      <netTcpBinding>  
        <binding name="transactionalOleTransactionsTcpBinding"  
          transactionFlow="true"  
          transactionProtocol="OleTransactions"/>  
      </netTcpBinding>  
    </bindings>  
    ```  
  
### <a name="supporting-multiple-transaction-protocols"></a>Compatibilidad de varios protocolos de transacción  
  
1.  Para un rendimiento óptimo, debería utilizar el protocolo OleTransactions para los escenarios que implican un cliente y servicio escritos con [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]. Sin embargo, el protocolo WS-AtomicTransaction (WS-AT) es útil para los escenarios cuando se requiere la interoperabilidad con pilas de protocolo de otro fabricante. Puede configurar los servicios [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para aceptar ambos protocolos al proporcionar varios extremos con los enlaces adecuados específicos del protocolo, tal y como se muestra en la configuración de muestra siguiente.  
  
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
  
     El protocolo de transacción se especifica utilizando el atributo `transactionProtocol`. Sin embargo, este atributo está ausente del `wsHttpBinding` proporcionado por sistema, ya que este enlace solo puede utilizar el protocolo WS-AT.  
  
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
  
### <a name="controlling-the-completion-of-a-transaction"></a>Control de la realización de una transacción  
  
1.  De forma predeterminada, las operaciones [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] completan automáticamente las transacciones si no se produce ninguna excepción no controlada. Puede modificar este comportamiento mediante la propiedad <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> y el método <xref:System.ServiceModel.OperationContext.SetTransactionComplete%2A>. Cuando es necesario que se produzca una operación dentro de la misma transacción como otra operación (por ejemplo, una operación de débito y crédito), puede deshabilitar el comportamiento de autocompletar definiendo la propiedad <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> en `false` tal y como se muestra en el ejemplo de operación `Debit` siguiente. La transacción que la operación `Debit` utiliza no se completa hasta que se llama a un método con la propiedad <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> definida en `true`, tal y como se muestra en la operación `Credit1` o cuando se llama al método <xref:System.ServiceModel.OperationContext.SetTransactionComplete%2A> para marcar explícitamente la transacción como completada, tal y como se muestra en la operación `Credit2`. Tenga en cuenta que las dos operaciones de crédito se muestran para fines informativos, y que una operación de crédito única sería más típica.  
  
    ```  
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
  
2.  Para la correlación de transacción, establecer la propiedad <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> en `false` requiere el uso de un enlace con sesión. Este requisito se especifica con la propiedad `SessionMode` en <xref:System.ServiceModel.ServiceContractAttribute>.  
  
    ```  
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
  
### <a name="controlling-the-lifetime-of-a-transactional-service-instance"></a>Control de la duración de una instancia de servicio transaccional  
  
1.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A> para especificar si se libera la instancia del servicio subyacente cuando se completa una transacción. Puesto que el valor predeterminado es `true`, a menos que se configure lo contrario, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] muestra un comportamiento de activación "Just-In-Time" eficaz y predecible. Las llamadas a un servicio en una transacción subsiguiente aseguran una nueva instancia del servicio sin restos del estado de la transacción anterior. Aunque esto resulta a menudo útil, a veces puede querer mantener el estado dentro de la instancia del servicio más allá de la realización de la transacción. Algunos ejemplos de ello serían cuándo resulta costoso recuperar o volver a constituir el estado necesario o los controladores a los recursos. Puede hacer esto al definir la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A> en `false`. Con ese valor, la instancia y cualquier estado asociado estarán disponibles en llamadas subsiguientes. Al utilizar esto, proporcione la consideración adecuada a cuándo y cómo se borrarán y completarán las transacciones y el estado. El ejemplo siguiente muestra cómo hacer esto manteniendo la instancia con la variable `runningTotal`.  
  
    ```  
    [ServiceBehavior(TransactionIsolationLevel = [ServiceBehavior(  
        ReleaseServiceInstanceOnTransactionComplete = false)]  
    public class CalculatorService : ICalculator  
    {  
        double runningTotal = 0;  
  
        [OperationBehavior(TransactionScopeRequired = true)]  
        public double Add(double n)  
        {  
            // Perform transactional operation  
            RecordToLog(String.Format("Adding {0} to {1}", n, runningTotal));  
            runningTotal = runningTotal + n;  
            return runningTotal;  
        }  
  
        [OperationBehavior(TransactionScopeRequired = true)]  
        public double Subtract(double n)  
        {  
            // Perform transactional operation  
            RecordToLog(String.Format("Subtracting {0} from {1}", n, runningTotal));  
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
    >  Desde que la duración de la instancia es un comportamiento que es interno al servicio y controlado a través de la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute>, no se requiere ninguna modificación en la configuración de servicio ni en el contrato de servicio para establecer el comportamiento de la instancia. Además, la conexión no contendrá ninguna representación de esto.
