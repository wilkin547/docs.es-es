---
title: Integración de los componentes transaccionales de Enterprise Services
ms.date: 03/30/2017
ms.assetid: 05dab277-b8b2-48cf-b40c-826be128b175
ms.openlocfilehash: 33e09eab1d7ad24dc234cfff21e352611e0b2ef9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59202045"
---
# <a name="integrating-enterprise-services-transactional-components"></a><span data-ttu-id="dcac2-102">Integración de los componentes transaccionales de Enterprise Services</span><span class="sxs-lookup"><span data-stu-id="dcac2-102">Integrating Enterprise Services Transactional Components</span></span>
<span data-ttu-id="dcac2-103">Windows Communication Foundation (WCF) proporciona un mecanismo automático para integrar con Enterprise Services (consulte [la integración con aplicaciones COM +](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)).</span><span class="sxs-lookup"><span data-stu-id="dcac2-103">Windows Communication Foundation (WCF) provides an automatic mechanism for integrating with Enterprise Services (see [Integrating with COM+ Applications](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)).</span></span> <span data-ttu-id="dcac2-104">Sin embargo, puede querer flexibilidad para desarrollar servicios que utilicen internamente componentes transaccionales hospedados en Enterprise Services.</span><span class="sxs-lookup"><span data-stu-id="dcac2-104">However, you may want the flexibility to develop services that internally use transactional components hosted within Enterprise Services.</span></span> <span data-ttu-id="dcac2-105">Dado que la característica de transacciones de WCF se basa el <xref:System.Transactions> infraestructura, el proceso de integración de Enterprise Services con WCF es idéntico a la especificación de interoperabilidad entre <xref:System.Transactions> y Enterprise Services, tal como se describe en [Interoperabilidad con Enterprise Services y transacciones de COM +](https://go.microsoft.com/fwlink/?LinkId=94949).</span><span class="sxs-lookup"><span data-stu-id="dcac2-105">Because the WCF Transactions feature is built on the <xref:System.Transactions> infrastructure, the process for integrating Enterprise Services with WCF is identical to that for specifying interoperability between <xref:System.Transactions> and Enterprise Services, as outlined in [Interoperability with Enterprise Services and COM+ Transactions](https://go.microsoft.com/fwlink/?LinkId=94949).</span></span>  
  
 <span data-ttu-id="dcac2-106">Para proporcionar el nivel deseado de interoperabilidad entre la transacción fluida entrante y la transacción de contexto de COM+, la implementación del servicio debe crear una instancia <xref:System.Transactions.TransactionScope> y utilizar el valor adecuado de la enumeración <xref:System.Transactions.EnterpriseServicesInteropOption>.</span><span class="sxs-lookup"><span data-stu-id="dcac2-106">To provide the desired level of interoperability between the incoming flowed transaction and the COM+ context transaction, the service implementation must create a <xref:System.Transactions.TransactionScope> instance and use the appropriate value from the <xref:System.Transactions.EnterpriseServicesInteropOption> enumeration.</span></span>  
  
## <a name="integrating-enterprise-services-with-a-service-operation"></a><span data-ttu-id="dcac2-107">Integración de Enterprise Services con una operación de servicio</span><span class="sxs-lookup"><span data-stu-id="dcac2-107">Integrating Enterprise Services with a Service Operation</span></span>  
 <span data-ttu-id="dcac2-108">El código siguiente muestra una operación, con flujo de transacción permitido, que crea un <xref:System.Transactions.TransactionScope> con la opción <xref:System.Transactions.EnterpriseServicesInteropOption.Full>.</span><span class="sxs-lookup"><span data-stu-id="dcac2-108">The following code demonstrates an operation, with Allowed transaction flow, that creates a <xref:System.Transactions.TransactionScope> with the <xref:System.Transactions.EnterpriseServicesInteropOption.Full> option.</span></span> <span data-ttu-id="dcac2-109">Las condiciones siguientes se aplican en este escenario:</span><span class="sxs-lookup"><span data-stu-id="dcac2-109">The following conditions apply in this scenario:</span></span>  
  
-   <span data-ttu-id="dcac2-110">Si el cliente fluye una transacción, la operación, incluida la llamada al componente Enterprise Services, se ejecuta dentro del ámbito de esa transacción.</span><span class="sxs-lookup"><span data-stu-id="dcac2-110">If the client flows a transaction, the operation, including the call to the Enterprise Services component, is executed within the scope of that transaction.</span></span> <span data-ttu-id="dcac2-111">El uso de <xref:System.Transactions.EnterpriseServicesInteropOption.Full> asegura que la transacción se sincroniza con el contexto <xref:System.EnterpriseServices>, lo que significa que la transacción ambiente para <xref:System.Transactions> y <xref:System.EnterpriseServices> es la misma.</span><span class="sxs-lookup"><span data-stu-id="dcac2-111">Using <xref:System.Transactions.EnterpriseServicesInteropOption.Full> ensures that the transaction is synchronized with the <xref:System.EnterpriseServices> context, which means that the ambient transaction for <xref:System.Transactions> and the <xref:System.EnterpriseServices> is the same.</span></span>  
  
-   <span data-ttu-id="dcac2-112">Si el cliente no fluye una transacción, al establecer <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> en `true` se crea un nuevo ámbito de transacción para la operación.</span><span class="sxs-lookup"><span data-stu-id="dcac2-112">If the client does not flow a transaction, setting <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> to `true` creates a new transaction scope for the operation.</span></span> <span data-ttu-id="dcac2-113">De igual forma, utilizar <xref:System.Transactions.EnterpriseServicesInteropOption.Full> garantiza que la transacción de la operación es igual que la transacción utilizada dentro del contexto del componente <xref:System.EnterpriseServices>.</span><span class="sxs-lookup"><span data-stu-id="dcac2-113">Similarly, using <xref:System.Transactions.EnterpriseServicesInteropOption.Full> ensures that the operation’s transaction is the same as the transaction used inside the <xref:System.EnterpriseServices> component's context.</span></span>  
  
 <span data-ttu-id="dcac2-114">Cualquier llamada adicional al método también se produce dentro del ámbito de la transacción de la misma operación.</span><span class="sxs-lookup"><span data-stu-id="dcac2-114">Any additional method calls also occur within the scope of the same operation’s transaction.</span></span>  
  
```  
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
  
 <span data-ttu-id="dcac2-115">Si no se necesita ninguna sincronización entre la transacción actual de la operación y las llamadas a los componentes transaccionales de Enterprise Services, después utilice la opción <xref:System.Transactions.EnterpriseServicesInteropOption.None> cuando cree instancias de la instancia <xref:System.Transactions.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="dcac2-115">If no synchronization is required between an operation’s current transaction and calls to transactional Enterprise Services components, then use the <xref:System.Transactions.EnterpriseServicesInteropOption.None> option when instantiating the <xref:System.Transactions.TransactionScope> instance.</span></span>  
  
## <a name="integrating-enterprise-services-with-a-client"></a><span data-ttu-id="dcac2-116">Integración de Enterprise Services con un cliente</span><span class="sxs-lookup"><span data-stu-id="dcac2-116">Integrating Enterprise Services with a Client</span></span>  
 <span data-ttu-id="dcac2-117">El código siguiente muestra código de cliente utilizando una instancia <xref:System.Transactions.TransactionScope> con el valor <xref:System.Transactions.EnterpriseServicesInteropOption.Full>.</span><span class="sxs-lookup"><span data-stu-id="dcac2-117">The following code demonstrates client code using a <xref:System.Transactions.TransactionScope> instance with the <xref:System.Transactions.EnterpriseServicesInteropOption.Full> setting.</span></span> <span data-ttu-id="dcac2-118">En este escenario, las llamadas a las operaciones de servicio que admiten el flujo de la transacción se producen dentro del ámbito de la misma transacción como las llamadas a los componentes de Enterprise Services.</span><span class="sxs-lookup"><span data-stu-id="dcac2-118">In this scenario, calls to service operations that support transaction flow occur within the scope of the same transaction as the calls to Enterprise Services components.</span></span>  
  
```  
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
  
## <a name="see-also"></a><span data-ttu-id="dcac2-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="dcac2-119">See also</span></span>

- [<span data-ttu-id="dcac2-120">Integración en aplicaciones COM+</span><span class="sxs-lookup"><span data-stu-id="dcac2-120">Integrating with COM+ Applications</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="dcac2-121">Integración en aplicaciones COM</span><span class="sxs-lookup"><span data-stu-id="dcac2-121">Integrating with COM Applications</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications.md)
