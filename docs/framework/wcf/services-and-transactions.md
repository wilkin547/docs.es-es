---
title: Servicios y transacciones
ms.date: 03/30/2017
helpviewer_keywords:
- service contracts [WCF], designing services and transactions
ms.assetid: 864813ff-2709-4376-912d-f5c8d318c460
ms.openlocfilehash: e60f84aafe6c62a657cd3f27c9ccdb6b65186c35
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96235914"
---
# <a name="services-and-transactions"></a>Servicios y transacciones

Las aplicaciones de Windows Communication Foundation (WCF) pueden iniciar una transacción desde dentro de un cliente y coordinar la transacción dentro de la operación de servicio. Los clientes pueden iniciar una transacción e invocación varias operaciones del servicio y garantizar que las operaciones del servicio se confirmen o reviertan como una unidad única.  
  
 Puede habilitar el comportamiento de la transacción en el contrato de servicios especificando <xref:System.ServiceModel.ServiceBehaviorAttribute> y estableciendo su <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> y las propiedades <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> para las operaciones del servicio que requieren las transacciones del cliente. El parámetro <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> especifica si se completa automáticamente la transacción en la que se ejecuta el método si no se produce ninguna excepción no controlada. Para obtener más información sobre estos atributos, consulte [atributos de transacción de ServiceModel](./feature-details/servicemodel-transaction-attributes.md).  
  
 El trabajo que se realiza en las operaciones del servicio y que es administrado por un administrador de recursos, como registrar las actualizaciones de base de datos, forma parte de la transacción del cliente.  
  
 El ejemplo siguiente muestra el uso de los atributos <xref:System.ServiceModel.ServiceBehaviorAttribute> y <xref:System.ServiceModel.OperationBehaviorAttribute> para controlar el comportamiento de la transacción del lado del servicio.  
  
```csharp
[ServiceBehavior(TransactionIsolationLevel = System.Transactions.IsolationLevel.Serializable)]  
public class CalculatorService: ICalculatorLog  
{  
    [OperationBehavior(TransactionScopeRequired = true,  
                           TransactionAutoComplete = true)]  
    public double Add(double n1, double n2)  
    {  
        recordToLog($"Added {n1} to {n2}");
        return n1 + n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,
                               TransactionAutoComplete = true)]  
    public double Subtract(double n1, double n2)  
    {  
        recordToLog($"Subtracted {n1} from {n2}");
        return n1 - n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,
                                       TransactionAutoComplete = true)]  
    public double Multiply(double n1, double n2)  
    {  
        recordToLog($"Multiplied {n1} by {n2}");
        return n1 * n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,
                                       TransactionAutoComplete = true)]  
    public double Divide(double n1, double n2)  
    {  
        recordToLog($"Divided {n1} by {n2}", n1, n2);
        return n1 / n2;  
    }  
  
}  
```  
  
 Puede habilitar transacciones y el flujo de transacciones mediante la configuración de los enlaces del cliente y del servicio para utilizar el protocolo de WS-AtomicTransaction y el establecimiento del [\<transactionFlow>](../configure-apps/file-schema/wcf/transactionflow.md) elemento en `true` , como se muestra en la configuración del ejemplo siguiente.  
  
```xml  
<client>  
    <endpoint address="net.tcp://localhost/ServiceModelSamples/service"
          binding="netTcpBinding"
          bindingConfiguration="netTcpBindingWSAT"
          contract="Microsoft.ServiceModel.Samples.ICalculatorLog" />  
</client>  
  
<bindings>  
    <netTcpBinding>  
        <binding name="netTcpBindingWSAT"  
                transactionFlow="true"  
                transactionProtocol="WSAtomicTransactionOctober2004" />  
     </netTcpBinding>  
</bindings>  
```  
  
 Los clientes pueden comenzar una transacción creando <xref:System.Transactions.TransactionScope> e invocando las operaciones del servicio dentro del ámbito de la transacción.  
  
```csharp
using (TransactionScope ts = new TransactionScope(TransactionScopeOption.RequiresNew))  
{  
    //Do work here  
    ts.Complete();  
}  
```  
  
## <a name="see-also"></a>Vea también

- [Compatibilidad transaccional en System.ServiceModel](./feature-details/transactional-support-in-system-servicemodel.md)
- [Modelos de transacción](./feature-details/transaction-models.md)
- [Flujo de la transacción WS](./samples/ws-transaction-flow.md)
