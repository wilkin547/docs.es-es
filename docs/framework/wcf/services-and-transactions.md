---
title: Servicios y transacciones
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: service contracts [WCF], designing services and transactions
ms.assetid: 864813ff-2709-4376-912d-f5c8d318c460
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 680a86d453dd8ca7c78d0ca6ba60cbaa691e44f3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="services-and-transactions"></a>Servicios y transacciones
Las aplicaciones [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] pueden iniciar una transacción desde dentro de un cliente y coordinar la transacción dentro de la operación del servicio. Los clientes pueden iniciar una transacción e invocación varias operaciones del servicio y garantizar que las operaciones del servicio se confirmen o reviertan como una unidad única.  
  
 Puede habilitar el comportamiento de la transacción en el contrato de servicios especificando <xref:System.ServiceModel.ServiceBehaviorAttribute> y estableciendo su <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> y las propiedades <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> para las operaciones del servicio que requieren las transacciones del cliente. El parámetro <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> especifica si se completa automáticamente la transacción en la que se ejecuta el método si no se produce ninguna excepción no controlada. [!INCLUDE[crabout](../../../includes/crabout-md.md)]Estos atributos, vea [atributos de transacción de ServiceModel](../../../docs/framework/wcf/feature-details/servicemodel-transaction-attributes.md).  
  
 El trabajo que se realiza en las operaciones del servicio y que es administrado por un administrador de recursos, como registrar las actualizaciones de base de datos, forma parte de la transacción del cliente.  
  
 El ejemplo siguiente muestra el uso de los atributos <xref:System.ServiceModel.ServiceBehaviorAttribute> y <xref:System.ServiceModel.OperationBehaviorAttribute> para controlar el comportamiento de la transacción del lado del servicio.  
  
```  
[ServiceBehavior(TransactionIsolationLevel = System.Transactions.IsolationLevel.Serializable)]  
public class CalculatorService: ICalculatorLog  
{  
    [OperationBehavior(TransactionScopeRequired = true,  
                           TransactionAutoComplete = true)]  
    public double Add(double n1, double n2)  
    {  
        recordToLog(String.Format("Added {0} to {1}", n1, n2));  
        return n1 + n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,   
                               TransactionAutoComplete = true)]  
    public double Subtract(double n1, double n2)  
    {  
        recordToLog(String.Format("Subtracted {0} from {1}", n1, n2));  
        return n1 - n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,   
                                       TransactionAutoComplete = true)]  
    public double Multiply(double n1, double n2)  
    {  
        recordToLog(String.Format("Multiplied {0} by {1}", n1, n2));  
        return n1 * n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,   
                                       TransactionAutoComplete = true)]  
    public double Divide(double n1, double n2)  
    {  
        recordToLog(String.Format("Divided {0} by {1}", n1, n2));  
        return n1 / n2;  
    }  
  
}  
```  
  
 Puede habilitar las transacciones y transacciones de flujo de la configuración del cliente y servicio enlaces para utilizar el protocolo WS-AtomicTransaction y configuración de la [ \<transactionFlow >](../../../docs/framework/configure-apps/file-schema/wcf/transactionflow.md) elemento `true`, como se muestra en el siguiente ejemplo de configuración.  
  
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
  
```  
using (TransactionScope ts = new TransactionScope(TransactionScopeOption.RequiresNew))  
{  
    //Do work here  
    ts.Complete();  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Compatibilidad transaccional en System.ServiceModel](../../../docs/framework/wcf/feature-details/transactional-support-in-system-servicemodel.md)  
 [Modelos de transacción](../../../docs/framework/wcf/feature-details/transaction-models.md)  
 [Flujo de transacciones de WS](../../../docs/framework/wcf/samples/ws-transaction-flow.md)
