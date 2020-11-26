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
# <a name="services-and-transactions"></a><span data-ttu-id="3d3cc-102">Servicios y transacciones</span><span class="sxs-lookup"><span data-stu-id="3d3cc-102">Services and Transactions</span></span>

<span data-ttu-id="3d3cc-103">Las aplicaciones de Windows Communication Foundation (WCF) pueden iniciar una transacción desde dentro de un cliente y coordinar la transacción dentro de la operación de servicio.</span><span class="sxs-lookup"><span data-stu-id="3d3cc-103">Windows Communication Foundation (WCF) applications can initiate a transaction from within a client and coordinate the transaction within the service operation.</span></span> <span data-ttu-id="3d3cc-104">Los clientes pueden iniciar una transacción e invocación varias operaciones del servicio y garantizar que las operaciones del servicio se confirmen o reviertan como una unidad única.</span><span class="sxs-lookup"><span data-stu-id="3d3cc-104">Clients can initiate a transaction and invoke several service operations and ensure that the service operations are either committed or rolled back as a single unit.</span></span>  
  
 <span data-ttu-id="3d3cc-105">Puede habilitar el comportamiento de la transacción en el contrato de servicios especificando <xref:System.ServiceModel.ServiceBehaviorAttribute> y estableciendo su <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> y las propiedades <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> para las operaciones del servicio que requieren las transacciones del cliente.</span><span class="sxs-lookup"><span data-stu-id="3d3cc-105">You can enable the transaction behavior in the service contract by specifying a <xref:System.ServiceModel.ServiceBehaviorAttribute> and setting its <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> and <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> properties for service operations that require client transactions.</span></span> <span data-ttu-id="3d3cc-106">El parámetro <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> especifica si se completa automáticamente la transacción en la que se ejecuta el método si no se produce ninguna excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="3d3cc-106">The <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> parameter specifies whether the transaction in which the method executes is automatically completed if no unhandled exceptions are thrown.</span></span> <span data-ttu-id="3d3cc-107">Para obtener más información sobre estos atributos, consulte [atributos de transacción de ServiceModel](./feature-details/servicemodel-transaction-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="3d3cc-107">For more information about these attributes, see [ServiceModel Transaction Attributes](./feature-details/servicemodel-transaction-attributes.md).</span></span>  
  
 <span data-ttu-id="3d3cc-108">El trabajo que se realiza en las operaciones del servicio y que es administrado por un administrador de recursos, como registrar las actualizaciones de base de datos, forma parte de la transacción del cliente.</span><span class="sxs-lookup"><span data-stu-id="3d3cc-108">The work that is performed in the service operations and managed by a resource manager, such as logging database updates, is part of the client’s transaction.</span></span>  
  
 <span data-ttu-id="3d3cc-109">El ejemplo siguiente muestra el uso de los atributos <xref:System.ServiceModel.ServiceBehaviorAttribute> y <xref:System.ServiceModel.OperationBehaviorAttribute> para controlar el comportamiento de la transacción del lado del servicio.</span><span class="sxs-lookup"><span data-stu-id="3d3cc-109">The following sample demonstrates usage of the <xref:System.ServiceModel.ServiceBehaviorAttribute> and <xref:System.ServiceModel.OperationBehaviorAttribute> attributes to control service-side transaction behavior.</span></span>  
  
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
  
 <span data-ttu-id="3d3cc-110">Puede habilitar transacciones y el flujo de transacciones mediante la configuración de los enlaces del cliente y del servicio para utilizar el protocolo de WS-AtomicTransaction y el establecimiento del [\<transactionFlow>](../configure-apps/file-schema/wcf/transactionflow.md) elemento en `true` , como se muestra en la configuración del ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="3d3cc-110">You can enable transactions and transaction flow by configuring the client and service bindings to use the WS-AtomicTransaction protocol, and setting the [\<transactionFlow>](../configure-apps/file-schema/wcf/transactionflow.md) element to `true`, as shown in the following sample configuration.</span></span>  
  
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
  
 <span data-ttu-id="3d3cc-111">Los clientes pueden comenzar una transacción creando <xref:System.Transactions.TransactionScope> e invocando las operaciones del servicio dentro del ámbito de la transacción.</span><span class="sxs-lookup"><span data-stu-id="3d3cc-111">Clients can begin a transaction by creating a <xref:System.Transactions.TransactionScope> and invoking service operations within the scope of the transaction.</span></span>  
  
```csharp
using (TransactionScope ts = new TransactionScope(TransactionScopeOption.RequiresNew))  
{  
    //Do work here  
    ts.Complete();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="3d3cc-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d3cc-112">See also</span></span>

- [<span data-ttu-id="3d3cc-113">Compatibilidad transaccional en System.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="3d3cc-113">Transactional Support in System.ServiceModel</span></span>](./feature-details/transactional-support-in-system-servicemodel.md)
- [<span data-ttu-id="3d3cc-114">Modelos de transacción</span><span class="sxs-lookup"><span data-stu-id="3d3cc-114">Transaction Models</span></span>](./feature-details/transaction-models.md)
- [<span data-ttu-id="3d3cc-115">Flujo de la transacción WS</span><span class="sxs-lookup"><span data-stu-id="3d3cc-115">WS Transaction Flow</span></span>](./samples/ws-transaction-flow.md)
