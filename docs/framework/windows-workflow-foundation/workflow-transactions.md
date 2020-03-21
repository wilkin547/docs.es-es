---
title: Transacciones de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: 6081fb02-c0f2-483d-97b8-f3b7dc03011d
ms.openlocfilehash: 223c18195c8ffd0b51eb5dff77aa81953f6e47a1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182669"
---
# <a name="workflow-transactions"></a><span data-ttu-id="efcff-102">Transacciones de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="efcff-102">Workflow Transactions</span></span>

[!INCLUDE[wf1](../../../includes/wf1-md.md)] <span data-ttu-id="efcff-103">proporciona el soporte técnico para participar en las transacciones del espacio de nombres <xref:System.Transactions> usando la actividad <xref:System.Activities.Statements.TransactionScope> para abarcar una unidad de trabajo con la que se haya realizado una transacción.</span><span class="sxs-lookup"><span data-stu-id="efcff-103">provides support for participating in <xref:System.Transactions> transactions by using the <xref:System.Activities.Statements.TransactionScope> activity to scope a transacted unit of work.</span></span> <span data-ttu-id="efcff-104">Aunque la clase <xref:System.Transactions.TransactionScope?displayProperty=nameWithType> debe completarse explícitamente, la actividad <xref:System.Activities.Statements.TransactionScope?displayProperty=nameWithType> realiza una llamada implícita de finalización de la transacción cuando se haya completado correctamente.</span><span class="sxs-lookup"><span data-stu-id="efcff-104">While the <xref:System.Transactions.TransactionScope?displayProperty=nameWithType> must be explicitly completed the <xref:System.Activities.Statements.TransactionScope?displayProperty=nameWithType> activity implicitly calls complete on the transaction upon successful completion.</span></span> <span data-ttu-id="efcff-105">Las actividades que se contengan en el elemento de la propiedad <xref:System.Activities.Statements.TransactionScope.Body%2A> de la actividad <xref:System.Activities.Statements.TransactionScope> participan en la transacción.</span><span class="sxs-lookup"><span data-stu-id="efcff-105">Any activities that are contained in the <xref:System.Activities.Statements.TransactionScope.Body%2A> of the <xref:System.Activities.Statements.TransactionScope> activity participate in the transaction.</span></span> <span data-ttu-id="efcff-106">WF puede fluir las transacciones en un flujo de trabajo a través del uso de la actividad <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span><span class="sxs-lookup"><span data-stu-id="efcff-106">WF can to flow transactions into a workflow through the use of the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span> <span data-ttu-id="efcff-107">Al igual que ocurre con la actividad <xref:System.Activities.Statements.TransactionScope>, cualquier actividad contenida en la propiedad <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A> participa en la transacción.</span><span class="sxs-lookup"><span data-stu-id="efcff-107">Like the <xref:System.Activities.Statements.TransactionScope> activity, any activity contained in the <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A> participates in the transaction.</span></span> <span data-ttu-id="efcff-108">WF garantiza que las actividades dependientes de <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType> funcionan con <xref:System.Activities.Statements.TransactionScope> y <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span><span class="sxs-lookup"><span data-stu-id="efcff-108">WF ensures that activities dependent on <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType> works with both <xref:System.Activities.Statements.TransactionScope> and <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span></span> <span data-ttu-id="efcff-109">Si las actividades proporcionadas por el sistema no afrontan todos los requisitos, las actividades personalizadas se pueden compilar usando <xref:System.Activities.RuntimeTransactionHandle> para habilitar los escenarios de flujo avanzado y del control de transacciones.</span><span class="sxs-lookup"><span data-stu-id="efcff-109">If the system-provided activities do not address all requirements, custom activities can be built using the <xref:System.Activities.RuntimeTransactionHandle> to enable advanced flow and transaction control scenarios.</span></span>  
  
<span data-ttu-id="efcff-110">En el ejemplo siguiente, se construye un <xref:System.Activities.Statements.Sequence> flujo de trabajo <xref:System.Activities.Statements.TransactionScope> que consta de una actividad que contiene actividades secundarias, incluida una actividad.</span><span class="sxs-lookup"><span data-stu-id="efcff-110">In the following example, a workflow is constructed consisting of a <xref:System.Activities.Statements.Sequence> activity that contains child activities including a <xref:System.Activities.Statements.TransactionScope> activity.</span></span> <span data-ttu-id="efcff-111">Las actividades <xref:System.Activities.Statements.TransactionScope.Body%2A> de <xref:System.Activities.Statements.TransactionScope> se ejecutan bajo la transacción inicializada por la actividad <xref:System.Activities.Statements.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="efcff-111">The <xref:System.Activities.Statements.TransactionScope.Body%2A> activities of the <xref:System.Activities.Statements.TransactionScope> execute under the transaction initialized by the <xref:System.Activities.Statements.TransactionScope> activity.</span></span>  
  
```csharp  
static Activity ScenarioOne()  
{  
    return new Sequence  
    {  
        Activities =  
        {  
            new WriteLine { Text = "    Begin workflow" },  
  
            new TransactionScope  
            {  
                Body = new Sequence  
                {  
                    Activities =
                    {  
                        new WriteLine { Text = "    Begin TransactionScope" },  
  
                        new PrintTransactionId(),  
  
                        new TransactionScopeTest(),  
  
                        new WriteLine { Text = "    End TransactionScope" },  
                    },  
                },  
            },  
  
            new WriteLine { Text = "    End workflow" },  
        }  
    };  
}  
```  
  
<span data-ttu-id="efcff-112">Para obtener más información, consulte using <xref:System.ServiceModel.Activities.TransactedReceiveScope>, vea Flujo de [transacciones dentro y fuera de Servicios de flujo de trabajo](../wcf/feature-details/flowing-transactions-into-and-out-of-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="efcff-112">For more information, see about using <xref:System.ServiceModel.Activities.TransactedReceiveScope>, see [Flowing Transactions into and out of Workflow Services](../wcf/feature-details/flowing-transactions-into-and-out-of-workflow-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efcff-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="efcff-113">See also</span></span>

- <xref:System.Activities.Statements.TransactionScope>
- <xref:System.Transactions.TransactionScope>
- <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType>
