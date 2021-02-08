---
description: Más información acerca de la integración de componentes transaccionales de Enterprise Services
title: Integración de los componentes transaccionales de Enterprise Services
ms.date: 03/30/2017
ms.assetid: 05dab277-b8b2-48cf-b40c-826be128b175
ms.openlocfilehash: 67b3a58900d2842c304d76ff6dd1325e961d8394
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802832"
---
# <a name="integrating-enterprise-services-transactional-components"></a><span data-ttu-id="68ddd-103">Integración de los componentes transaccionales de Enterprise Services</span><span class="sxs-lookup"><span data-stu-id="68ddd-103">Integrating Enterprise Services Transactional Components</span></span>

<span data-ttu-id="68ddd-104">Windows Communication Foundation (WCF) proporciona un mecanismo automático para la integración con Enterprise Services (consulte [integración con aplicaciones com+](integrating-with-com-plus-applications.md)).</span><span class="sxs-lookup"><span data-stu-id="68ddd-104">Windows Communication Foundation (WCF) provides an automatic mechanism for integrating with Enterprise Services (see [Integrating with COM+ Applications](integrating-with-com-plus-applications.md)).</span></span> <span data-ttu-id="68ddd-105">Sin embargo, puede querer flexibilidad para desarrollar servicios que utilicen internamente componentes transaccionales hospedados en Enterprise Services.</span><span class="sxs-lookup"><span data-stu-id="68ddd-105">However, you may want the flexibility to develop services that internally use transactional components hosted within Enterprise Services.</span></span> <span data-ttu-id="68ddd-106">Dado que la característica de transacciones de WCF se basa en la <xref:System.Transactions> infraestructura de, el proceso de integración de Enterprise Services con WCF es idéntico al que indica la interoperabilidad entre <xref:System.Transactions> y Enterprise Services, tal y como se describe en [interoperabilidad con las transacciones de Enterprise Services y com+](/previous-versions/dotnet/netframework-3.0/ms229974(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="68ddd-106">Because the WCF Transactions feature is built on the <xref:System.Transactions> infrastructure, the process for integrating Enterprise Services with WCF is identical to that for specifying interoperability between <xref:System.Transactions> and Enterprise Services, as outlined in [Interoperability with Enterprise Services and COM+ Transactions](/previous-versions/dotnet/netframework-3.0/ms229974(v=vs.85)).</span></span>  
  
 <span data-ttu-id="68ddd-107">Para proporcionar el nivel deseado de interoperabilidad entre la transacción fluida entrante y la transacción de contexto de COM+, la implementación del servicio debe crear una instancia <xref:System.Transactions.TransactionScope> y utilizar el valor adecuado de la enumeración <xref:System.Transactions.EnterpriseServicesInteropOption>.</span><span class="sxs-lookup"><span data-stu-id="68ddd-107">To provide the desired level of interoperability between the incoming flowed transaction and the COM+ context transaction, the service implementation must create a <xref:System.Transactions.TransactionScope> instance and use the appropriate value from the <xref:System.Transactions.EnterpriseServicesInteropOption> enumeration.</span></span>  
  
## <a name="integrating-enterprise-services-with-a-service-operation"></a><span data-ttu-id="68ddd-108">Integración de Enterprise Services con una operación de servicio</span><span class="sxs-lookup"><span data-stu-id="68ddd-108">Integrating Enterprise Services with a Service Operation</span></span>  

 <span data-ttu-id="68ddd-109">El código siguiente muestra una operación, con flujo de transacción permitido, que crea un <xref:System.Transactions.TransactionScope> con la opción <xref:System.Transactions.EnterpriseServicesInteropOption.Full>.</span><span class="sxs-lookup"><span data-stu-id="68ddd-109">The following code demonstrates an operation, with Allowed transaction flow, that creates a <xref:System.Transactions.TransactionScope> with the <xref:System.Transactions.EnterpriseServicesInteropOption.Full> option.</span></span> <span data-ttu-id="68ddd-110">Las condiciones siguientes se aplican en este escenario:</span><span class="sxs-lookup"><span data-stu-id="68ddd-110">The following conditions apply in this scenario:</span></span>  
  
- <span data-ttu-id="68ddd-111">Si el cliente fluye una transacción, la operación, incluida la llamada al componente Enterprise Services, se ejecuta dentro del ámbito de esa transacción.</span><span class="sxs-lookup"><span data-stu-id="68ddd-111">If the client flows a transaction, the operation, including the call to the Enterprise Services component, is executed within the scope of that transaction.</span></span> <span data-ttu-id="68ddd-112">El uso de <xref:System.Transactions.EnterpriseServicesInteropOption.Full> asegura que la transacción se sincroniza con el contexto <xref:System.EnterpriseServices>, lo que significa que la transacción ambiente para <xref:System.Transactions> y <xref:System.EnterpriseServices> es la misma.</span><span class="sxs-lookup"><span data-stu-id="68ddd-112">Using <xref:System.Transactions.EnterpriseServicesInteropOption.Full> ensures that the transaction is synchronized with the <xref:System.EnterpriseServices> context, which means that the ambient transaction for <xref:System.Transactions> and the <xref:System.EnterpriseServices> is the same.</span></span>  
  
- <span data-ttu-id="68ddd-113">Si el cliente no fluye una transacción, al establecer <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> en `true` se crea un nuevo ámbito de transacción para la operación.</span><span class="sxs-lookup"><span data-stu-id="68ddd-113">If the client does not flow a transaction, setting <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> to `true` creates a new transaction scope for the operation.</span></span> <span data-ttu-id="68ddd-114">De igual forma, utilizar <xref:System.Transactions.EnterpriseServicesInteropOption.Full> garantiza que la transacción de la operación es igual que la transacción utilizada dentro del contexto del componente <xref:System.EnterpriseServices>.</span><span class="sxs-lookup"><span data-stu-id="68ddd-114">Similarly, using <xref:System.Transactions.EnterpriseServicesInteropOption.Full> ensures that the operation’s transaction is the same as the transaction used inside the <xref:System.EnterpriseServices> component's context.</span></span>  
  
 <span data-ttu-id="68ddd-115">Cualquier llamada adicional al método también se produce dentro del ámbito de la transacción de la misma operación.</span><span class="sxs-lookup"><span data-stu-id="68ddd-115">Any additional method calls also occur within the scope of the same operation’s transaction.</span></span>  
  
```csharp
[ServiceContract()]  
public interface ICustomerServiceContract  
{  
   [OperationContract]  
   [TransactionFlow(TransactionFlowOption.Allowed)]  
   void UpdateCustomerNameOperation(int customerID, string newCustomerName);  
}  
  
[ServiceBehavior(TransactionIsolationLevel = System.Transactions.IsolationLevel.Serializable)]  
public class CustomerService : ICustomerServiceContract  
{  
   [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
   public void UpdateCustomerNameOperation(int customerID, string newCustomerName)  
   {  
   // Create a transaction scope with full ES interop  
      using (TransactionScope ts = new TransactionScope(  
                     TransactionScopeOption.Required,  
                     new TransactionOptions(),  
                     EnterpriseServicesInteropOption.Full))  
      {  
         // Create an Enterprise Services component  
         // Call UpdateCustomer method on an Enterprise Services
         // component
  
         // Call UpdateOtherCustomerData method on an Enterprise
         // Services component
         ts.Complete();  
      }  
  
      // Do UpdateAdditionalData on an non-Enterprise Services  
      // component  
   }  
}  
```  
  
 <span data-ttu-id="68ddd-116">Si no se necesita ninguna sincronización entre la transacción actual de la operación y las llamadas a los componentes transaccionales de Enterprise Services, después utilice la opción <xref:System.Transactions.EnterpriseServicesInteropOption.None> cuando cree instancias de la instancia <xref:System.Transactions.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="68ddd-116">If no synchronization is required between an operation’s current transaction and calls to transactional Enterprise Services components, then use the <xref:System.Transactions.EnterpriseServicesInteropOption.None> option when instantiating the <xref:System.Transactions.TransactionScope> instance.</span></span>  
  
## <a name="integrating-enterprise-services-with-a-client"></a><span data-ttu-id="68ddd-117">Integración de Enterprise Services con un cliente</span><span class="sxs-lookup"><span data-stu-id="68ddd-117">Integrating Enterprise Services with a Client</span></span>  

 <span data-ttu-id="68ddd-118">El código siguiente muestra código de cliente utilizando una instancia <xref:System.Transactions.TransactionScope> con el valor <xref:System.Transactions.EnterpriseServicesInteropOption.Full>.</span><span class="sxs-lookup"><span data-stu-id="68ddd-118">The following code demonstrates client code using a <xref:System.Transactions.TransactionScope> instance with the <xref:System.Transactions.EnterpriseServicesInteropOption.Full> setting.</span></span> <span data-ttu-id="68ddd-119">En este escenario, las llamadas a las operaciones de servicio que admiten el flujo de la transacción se producen dentro del ámbito de la misma transacción como las llamadas a los componentes de Enterprise Services.</span><span class="sxs-lookup"><span data-stu-id="68ddd-119">In this scenario, calls to service operations that support transaction flow occur within the scope of the same transaction as the calls to Enterprise Services components.</span></span>  
  
```csharp
static void Main()  
{  
    // Create a client  
    CalculatorClient client = new CalculatorClient();  
  
    // Create a transaction scope with full ES interop  
    using (TransactionScope ts = new TransactionScope(  
          TransactionScopeOption.Required,  
          new TransactionOptions(),  
          EnterpriseServicesInteropOption.Full))  
    {  
        // Call Add calculator service operation  
  
        // Create an Enterprise Services component  
  
        // Call UpdateCustomer method on an Enterprise Services
        // component
  
        ts.Complete();  
    }  
  
    // Closing the client gracefully closes the connection and
    // cleans up resources  
    client.Close();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="68ddd-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="68ddd-120">See also</span></span>

- [<span data-ttu-id="68ddd-121">Integración con aplicaciones COM+</span><span class="sxs-lookup"><span data-stu-id="68ddd-121">Integrating with COM+ Applications</span></span>](integrating-with-com-plus-applications.md)
- [<span data-ttu-id="68ddd-122">Integración en aplicaciones COM</span><span class="sxs-lookup"><span data-stu-id="68ddd-122">Integrating with COM Applications</span></span>](integrating-with-com-applications.md)
