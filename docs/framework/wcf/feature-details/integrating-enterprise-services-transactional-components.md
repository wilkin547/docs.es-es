---
title: "Integración de los componentes transaccionales de Enterprise Services"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 05dab277-b8b2-48cf-b40c-826be128b175
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a236a34dd20661d62d59a3712a1800ff1f9a11ad
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="integrating-enterprise-services-transactional-components"></a><span data-ttu-id="687a3-102">Integración de los componentes transaccionales de Enterprise Services</span><span class="sxs-lookup"><span data-stu-id="687a3-102">Integrating Enterprise Services Transactional Components</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="687a3-103">Proporciona un mecanismo automático para la integración con Enterprise Services (vea [integración con aplicaciones COM +](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)).</span><span class="sxs-lookup"><span data-stu-id="687a3-103"> provides an automatic mechanism for integrating with Enterprise Services (see [Integrating with COM+ Applications](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)).</span></span> <span data-ttu-id="687a3-104">Sin embargo, puede querer flexibilidad para desarrollar servicios que utilicen internamente componentes transaccionales hospedados en Enterprise Services.</span><span class="sxs-lookup"><span data-stu-id="687a3-104">However, you may want the flexibility to develop services that internally use transactional components hosted within Enterprise Services.</span></span> <span data-ttu-id="687a3-105">Dado que la [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] característica de transacciones se basa en el <xref:System.Transactions> infraestructura, el proceso de integración de Enterprise Services con [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] es idéntico de la especificación de interoperabilidad entre <xref:System.Transactions> y Enterprise Servicios, como se describe en [interoperabilidad con servicios empresariales y las transacciones COM +](http://go.microsoft.com/fwlink/?LinkId=94949).</span><span class="sxs-lookup"><span data-stu-id="687a3-105">Because the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Transactions feature is built on the <xref:System.Transactions> infrastructure, the process for integrating Enterprise Services with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is identical to that for specifying interoperability between <xref:System.Transactions> and Enterprise Services, as outlined in [Interoperability with Enterprise Services and COM+ Transactions](http://go.microsoft.com/fwlink/?LinkId=94949).</span></span>  
  
 <span data-ttu-id="687a3-106">Para proporcionar el nivel deseado de interoperabilidad entre la transacción fluida entrante y la transacción de contexto de COM+, la implementación del servicio debe crear una instancia <xref:System.Transactions.TransactionScope> y utilizar el valor adecuado de la enumeración <xref:System.Transactions.EnterpriseServicesInteropOption>.</span><span class="sxs-lookup"><span data-stu-id="687a3-106">To provide the desired level of interoperability between the incoming flowed transaction and the COM+ context transaction, the service implementation must create a <xref:System.Transactions.TransactionScope> instance and use the appropriate value from the <xref:System.Transactions.EnterpriseServicesInteropOption> enumeration.</span></span>  
  
## <a name="integrating-enterprise-services-with-a-service-operation"></a><span data-ttu-id="687a3-107">Integración de Enterprise Services con una operación de servicio</span><span class="sxs-lookup"><span data-stu-id="687a3-107">Integrating Enterprise Services with a Service Operation</span></span>  
 <span data-ttu-id="687a3-108">El código siguiente muestra una operación, con flujo de transacción permitido, que crea un <xref:System.Transactions.TransactionScope> con la opción <xref:System.Transactions.EnterpriseServicesInteropOption.Full>.</span><span class="sxs-lookup"><span data-stu-id="687a3-108">The following code demonstrates an operation, with Allowed transaction flow, that creates a <xref:System.Transactions.TransactionScope> with the <xref:System.Transactions.EnterpriseServicesInteropOption.Full> option.</span></span> <span data-ttu-id="687a3-109">Las condiciones siguientes se aplican en este escenario:</span><span class="sxs-lookup"><span data-stu-id="687a3-109">The following conditions apply in this scenario:</span></span>  
  
-   <span data-ttu-id="687a3-110">Si el cliente fluye una transacción, la operación, incluida la llamada al componente Enterprise Services, se ejecuta dentro del ámbito de esa transacción.</span><span class="sxs-lookup"><span data-stu-id="687a3-110">If the client flows a transaction, the operation, including the call to the Enterprise Services component, is executed within the scope of that transaction.</span></span> <span data-ttu-id="687a3-111">El uso de <xref:System.Transactions.EnterpriseServicesInteropOption.Full> asegura que la transacción se sincroniza con el contexto <xref:System.EnterpriseServices>, lo que significa que la transacción ambiente para <xref:System.Transactions> y <xref:System.EnterpriseServices> es la misma.</span><span class="sxs-lookup"><span data-stu-id="687a3-111">Using <xref:System.Transactions.EnterpriseServicesInteropOption.Full> ensures that the transaction is synchronized with the <xref:System.EnterpriseServices> context, which means that the ambient transaction for <xref:System.Transactions> and the <xref:System.EnterpriseServices> is the same.</span></span>  
  
-   <span data-ttu-id="687a3-112">Si el cliente no fluye una transacción, al establecer <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> en `true` se crea un nuevo ámbito de transacción para la operación.</span><span class="sxs-lookup"><span data-stu-id="687a3-112">If the client does not flow a transaction, setting <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> to `true` creates a new transaction scope for the operation.</span></span> <span data-ttu-id="687a3-113">De igual forma, utilizar <xref:System.Transactions.EnterpriseServicesInteropOption.Full> garantiza que la transacción de la operación es igual que la transacción utilizada dentro del contexto del componente <xref:System.EnterpriseServices>.</span><span class="sxs-lookup"><span data-stu-id="687a3-113">Similarly, using <xref:System.Transactions.EnterpriseServicesInteropOption.Full> ensures that the operation’s transaction is the same as the transaction used inside the <xref:System.EnterpriseServices> component's context.</span></span>  
  
 <span data-ttu-id="687a3-114">Cualquier llamada adicional al método también se produce dentro del ámbito de la transacción de la misma operación.</span><span class="sxs-lookup"><span data-stu-id="687a3-114">Any additional method calls also occur within the scope of the same operation’s transaction.</span></span>  
  
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
  
 <span data-ttu-id="687a3-115">Si no se necesita ninguna sincronización entre la transacción actual de la operación y las llamadas a los componentes transaccionales de Enterprise Services, después utilice la opción <xref:System.Transactions.EnterpriseServicesInteropOption.None> cuando cree instancias de la instancia <xref:System.Transactions.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="687a3-115">If no synchronization is required between an operation’s current transaction and calls to transactional Enterprise Services components, then use the <xref:System.Transactions.EnterpriseServicesInteropOption.None> option when instantiating the <xref:System.Transactions.TransactionScope> instance.</span></span>  
  
## <a name="integrating-enterprise-services-with-a-client"></a><span data-ttu-id="687a3-116">Integración de Enterprise Services con un cliente</span><span class="sxs-lookup"><span data-stu-id="687a3-116">Integrating Enterprise Services with a Client</span></span>  
 <span data-ttu-id="687a3-117">El código siguiente muestra código de cliente utilizando una instancia <xref:System.Transactions.TransactionScope> con el valor <xref:System.Transactions.EnterpriseServicesInteropOption.Full>.</span><span class="sxs-lookup"><span data-stu-id="687a3-117">The following code demonstrates client code using a <xref:System.Transactions.TransactionScope> instance with the <xref:System.Transactions.EnterpriseServicesInteropOption.Full> setting.</span></span> <span data-ttu-id="687a3-118">En este escenario, las llamadas a las operaciones de servicio que admiten el flujo de la transacción se producen dentro del ámbito de la misma transacción como las llamadas a los componentes de Enterprise Services.</span><span class="sxs-lookup"><span data-stu-id="687a3-118">In this scenario, calls to service operations that support transaction flow occur within the scope of the same transaction as the calls to Enterprise Services components.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="687a3-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="687a3-119">See Also</span></span>  
 [<span data-ttu-id="687a3-120">Integración con aplicaciones COM +</span><span class="sxs-lookup"><span data-stu-id="687a3-120">Integrating with COM+ Applications</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [<span data-ttu-id="687a3-121">Integración con las aplicaciones COM</span><span class="sxs-lookup"><span data-stu-id="687a3-121">Integrating with COM Applications</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications.md)
