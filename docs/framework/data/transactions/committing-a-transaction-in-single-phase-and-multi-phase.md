---
title: Confirmar una transacción en fase única y múltiple
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 694ea153-e4db-41ae-96ac-9ac66dcb69a9
ms.openlocfilehash: 8d6c51249f104d35573507a9477a24d66d770693
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174438"
---
# <a name="committing-a-transaction-in-single-phase-and-multi-phase"></a><span data-ttu-id="653a0-102">Confirmar una transacción en fase única y múltiple</span><span class="sxs-lookup"><span data-stu-id="653a0-102">Committing a Transaction in Single-Phase and Multi-Phase</span></span>
<span data-ttu-id="653a0-103">Un administrador de recursos (RM) administra cada recurso utilizado, cuyas acciones coordina un administrador de transacciones (TM).</span><span class="sxs-lookup"><span data-stu-id="653a0-103">Each resource used in a transaction is managed by a resource manager (RM), whose actions are coordinated by a transaction manager (TM).</span></span> <span data-ttu-id="653a0-104">En el tema [Inscribir recursos como participantes en una transacción](enlisting-resources-as-participants-in-a-transaction.md) se describe cómo se puede dar de alta un recurso (o varios recursos) en una transacción.</span><span class="sxs-lookup"><span data-stu-id="653a0-104">The [Enlisting Resources as Participants in a Transaction](enlisting-resources-as-participants-in-a-transaction.md) topic discusses how a resource (or multiple resources) can be enlisted in a transaction.</span></span> <span data-ttu-id="653a0-105">En este tema se trata cómo la confirmación de la transacción se puede coordinar entre los recursos inscritos.</span><span class="sxs-lookup"><span data-stu-id="653a0-105">This topic discusses how transaction commitment can be coordinated among enlisted resources.</span></span>  
  
 <span data-ttu-id="653a0-106">Al final de la transacción, la aplicación solicita que se confirme o se revierta la transacción.</span><span class="sxs-lookup"><span data-stu-id="653a0-106">At the end of the transaction, the application requests the transaction to be either committed or rolled back.</span></span> <span data-ttu-id="653a0-107">El administrador de transacciones debe eliminar los riesgos como algunos administradores de recursos que votan para confirmar mientras que otros votan para deshacer la transacción.</span><span class="sxs-lookup"><span data-stu-id="653a0-107">The transaction manager must eliminate risks like some resource managers voting to commit while others voting to roll back the transaction.</span></span>  
  
 <span data-ttu-id="653a0-108">Si su transacción implica más de un recurso, debe realizar una confirmación en dos fases (2PC).</span><span class="sxs-lookup"><span data-stu-id="653a0-108">If your transaction involves more than one resource, you must perform a two-phase commit (2PC).</span></span> <span data-ttu-id="653a0-109">El protocolo de confirmación en dos fases (la fase de preparación y la de confirmación) asegura que cuando la transacción finaliza, todos los cambios a todos los recursos se confirman o se deshacen.</span><span class="sxs-lookup"><span data-stu-id="653a0-109">The two-phase commit protocol (the prepare phase and the commit phase) ensures that when the transaction ends, all changes to all resources are either totally committed or fully rolled back.</span></span> <span data-ttu-id="653a0-110">Todos los participantes se informan a continuación del resultado final.</span><span class="sxs-lookup"><span data-stu-id="653a0-110">All the participants are then informed of the final result.</span></span> <span data-ttu-id="653a0-111">Para una discusión detallada del protocolo de confirmación en dos fases, consulte el libro "Procesamiento de*transacciones: Conceptos y técnicas (Serie Morgan Kaufmann en sistemas de gestión de datos) ISBN:1558601902*" de Jim Gray.</span><span class="sxs-lookup"><span data-stu-id="653a0-111">For a detailed discussion of the two-phase commit protocol, please consult the book "*Transaction Processing : Concepts and Techniques (Morgan Kaufmann Series in Data Management Systems) ISBN:1558601902*" by Jim Gray.</span></span>  
  
 <span data-ttu-id="653a0-112">También puede optimizar el rendimiento de su transacción tomando parte en el protocolo de confirmación de fase única.</span><span class="sxs-lookup"><span data-stu-id="653a0-112">You can also optimize your transaction's performance by taking part in the Single Phase Commit protocol.</span></span> <span data-ttu-id="653a0-113">Para obtener más información, consulte [Optimización mediante confirmación](optimization-spc-and-promotable-spn.md)de fase única y Notificación de fase única promocionable .</span><span class="sxs-lookup"><span data-stu-id="653a0-113">For more information, see [Optimization using Single Phase Commit and Promotable Single Phase Notification](optimization-spc-and-promotable-spn.md).</span></span>  
  
 <span data-ttu-id="653a0-114">Si solo desea ser informado del resultado de una transacción, y no desea participar para votar, se debería registrar para el evento <xref:System.Transactions.Transaction.TransactionCompleted>.</span><span class="sxs-lookup"><span data-stu-id="653a0-114">If you just want to be informed of a transaction's outcome, and do not want to participate in voting, you should register for the <xref:System.Transactions.Transaction.TransactionCompleted> event.</span></span>  
  
## <a name="two-phase-commit-2pc"></a><span data-ttu-id="653a0-115">Confirmación en dos fases (2PC)</span><span class="sxs-lookup"><span data-stu-id="653a0-115">Two-phase Commit (2PC)</span></span>  
 <span data-ttu-id="653a0-116">En la primera fase de la transacción, el administrador de transacciones consulta cada recurso para determinar si una transacción se debería confirmar o deshacer.</span><span class="sxs-lookup"><span data-stu-id="653a0-116">In the first transaction phase, the transaction manager queries each resource to determine whether a transaction should be committed or rolled back.</span></span> <span data-ttu-id="653a0-117">En la segunda fase de la transacción, el administrador de transacciones notifica a cada recurso el resultado de sus consultas, permitiéndole realizar cualquier limpieza necesaria.</span><span class="sxs-lookup"><span data-stu-id="653a0-117">In the second transaction phase, the transaction manager notifies each resource of the outcome of its queries, allowing it to perform any necessary cleanup.</span></span>  
  
 <span data-ttu-id="653a0-118">Para participar en este tipo de transacción, un administrador de recursos debe implementar la interfaz <xref:System.Transactions.IEnlistmentNotification>, que proporciona métodos que el TM llamará como notificaciones durante una 2PC.</span><span class="sxs-lookup"><span data-stu-id="653a0-118">To participate in this kind of transaction, a resource manager must implement the <xref:System.Transactions.IEnlistmentNotification> interface, which provides methods that are called by the TM as notifications during a 2PC.</span></span>  <span data-ttu-id="653a0-119">En el siguiente ejemplo se muestra un ejemplo de dicha implementación.</span><span class="sxs-lookup"><span data-stu-id="653a0-119">The following sample shows an example of such implementation.</span></span>  
  
 [!code-csharp[Tx_Enlist#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/tx_enlist/cs/enlist.cs#2)]
 [!code-vb[Tx_Enlist#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/tx_enlist/vb/enlist.vb#2)]  
  
### <a name="prepare-phase-phase-1"></a><span data-ttu-id="653a0-120">Preparar la fase (fase 1)</span><span class="sxs-lookup"><span data-stu-id="653a0-120">Prepare phase (Phase 1)</span></span>  
 <span data-ttu-id="653a0-121">Al recibir una solicitud <xref:System.Transactions.CommittableTransaction.Commit%2A> de la aplicación, el administrador de transacciones comienza la fase de preparación de todos los participantes alistados llamando al método <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> en cada recurso alistado para obtener el voto de cada recurso en la transacción.</span><span class="sxs-lookup"><span data-stu-id="653a0-121">Upon receiving a <xref:System.Transactions.CommittableTransaction.Commit%2A> request from the application, the transaction manager begins the Prepare phase of all the enlisted participants by calling the <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> method on each enlisted resource, in order to obtain each resource's vote on the transaction.</span></span>  
  
 <span data-ttu-id="653a0-122">Su administrador de recursos que implementa la interfaz <xref:System.Transactions.IEnlistmentNotification> debería implementar primero el método <xref:System.Transactions.IEnlistmentNotification.Prepare%28System.Transactions.PreparingEnlistment%29> como las presentaciones del ejemplo simples siguientes.</span><span class="sxs-lookup"><span data-stu-id="653a0-122">Your resource manager that implements the <xref:System.Transactions.IEnlistmentNotification> interface should first implement the <xref:System.Transactions.IEnlistmentNotification.Prepare%28System.Transactions.PreparingEnlistment%29> method as the following simple example shows.</span></span>  
  
```csharp
public void Prepare(PreparingEnlistment preparingEnlistment)  
{  
     Console.WriteLine("Prepare notification received");  
     //Perform work  
  
     Console.Write("reply with prepared? [Y|N] ");  
     c = Console.ReadKey();  
     Console.WriteLine();  
  
     //If work finished correctly, reply with prepared  
     if ((c.KeyChar == 'Y') || (c.KeyChar == 'y'))  
     {  
          preparingEnlistment.Prepared();  
          break;  
     }  
  
     // otherwise, do a ForceRollback  
     else if ((c.KeyChar == 'N') || (c.KeyChar == 'n'))  
     {  
          preparingEnlistment.ForceRollback();  
          break;  
     }  
}  
```  
  
 <span data-ttu-id="653a0-123">Cuando el administrador de recursos duradero recibe esta llamada, debería registrar la información de la recuperación (disponible recuperando la propiedad <xref:System.Transactions.PreparingEnlistment.RecoveryInformation%2A> ) de la transacción y cualquier información es necesaria para completar la transacción de confirmación.</span><span class="sxs-lookup"><span data-stu-id="653a0-123">When the durable resource manager receives this call, it should log the transaction's recovery information (available by retrieving the <xref:System.Transactions.PreparingEnlistment.RecoveryInformation%2A> property) and whatever information is necessary to complete the transaction on commit.</span></span> <span data-ttu-id="653a0-124">Esto no necesita ser realizado dentro del método <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> porque RM puede hacer esto en un subproceso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="653a0-124">This does not need to be performed within the <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> method because the RM can do this on a worker thread.</span></span>  
  
 <span data-ttu-id="653a0-125">Cuando RM ha finalizado su trabajo de preparación, debería votar para confirmar o deshacer llamando a<xref:System.Transactions.PreparingEnlistment.Prepared%2A> o al método <xref:System.Transactions.PreparingEnlistment.ForceRollback%2A>.</span><span class="sxs-lookup"><span data-stu-id="653a0-125">When the RM has finished its prepare work, it should vote to commit or roll back by calling the <xref:System.Transactions.PreparingEnlistment.Prepared%2A> or <xref:System.Transactions.PreparingEnlistment.ForceRollback%2A> method.</span></span> <span data-ttu-id="653a0-126">Observe que la clase <xref:System.Transactions.PreparingEnlistment> hereda un método <xref:System.Transactions.Enlistment.Done%2A> de la clase <xref:System.Transactions.Enlistment>.</span><span class="sxs-lookup"><span data-stu-id="653a0-126">Notice that the <xref:System.Transactions.PreparingEnlistment> class inherits a <xref:System.Transactions.Enlistment.Done%2A> method from the <xref:System.Transactions.Enlistment> class.</span></span> <span data-ttu-id="653a0-127">Si llama a este método en la devolución de llamada <xref:System.Transactions.PreparingEnlistment> durante la fase de preparación, éste informa al TM de que es una inscripción de solo lectura (es decir, administradores de recursos que pueden leer pero no pueden actualizar los datos protegidos por transacción) y el RM no recibe ninguna notificación más extensa del administrador de transacciones acerca del resultado de la transacción en fase 2.</span><span class="sxs-lookup"><span data-stu-id="653a0-127">If you call this method on the <xref:System.Transactions.PreparingEnlistment> callback during the Prepare phase, it informs the TM that it is a Read-Only enlistment (that is, resource managers that can read but cannot update transaction-protected data) and the RM receives no further notifications from the transaction manager as to the outcome of the transaction in phase 2.</span></span>  
  
 <span data-ttu-id="653a0-128">Se cuenta en la aplicación la exitosa confirmación de la transacción después de que todos los administradores de recursos voten <xref:System.Transactions.PreparingEnlistment.Prepared%2A>.</span><span class="sxs-lookup"><span data-stu-id="653a0-128">The application is told of the successful commitment of the transaction after all the resource managers vote <xref:System.Transactions.PreparingEnlistment.Prepared%2A>.</span></span>  
  
### <a name="commit-phase-phase-2"></a><span data-ttu-id="653a0-129">Confirmar la fase (fase 2)</span><span class="sxs-lookup"><span data-stu-id="653a0-129">Commit phase (Phase 2)</span></span>  
 <span data-ttu-id="653a0-130">En la segunda fase de la transacción, si el administrador de transacciones recibe correcta preparación de todos los administradores de recursos (todos los administradores de recursos han invocado <xref:System.Transactions.PreparingEnlistment.Prepared%2A> al final de fase 1), invoca el método <xref:System.Transactions.IEnlistmentNotification.Commit%2A> para cada administrador de recursos.</span><span class="sxs-lookup"><span data-stu-id="653a0-130">In the second phase of the transaction, if the transaction manager receives successful prepares from all the resource managers (all the resource managers have invoked <xref:System.Transactions.PreparingEnlistment.Prepared%2A> at the end of phase 1), it invokes the <xref:System.Transactions.IEnlistmentNotification.Commit%2A> method for each resource manager.</span></span> <span data-ttu-id="653a0-131">Los administradores de recursos pueden realizar a continuación los cambios duraderos y completar la confirmación.</span><span class="sxs-lookup"><span data-stu-id="653a0-131">The resource managers can then make the changes durable and complete the commit.</span></span>  
  
 <span data-ttu-id="653a0-132">Si cualquier administrador de recursos informa de un error para preparar en fase 1, el administrador de transacciones invoca el método <xref:System.Transactions.IEnlistmentNotification.Rollback%2A> para cada administrador de recursos e indica el error de la confirmación a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="653a0-132">If any resource manager reported a failure to prepare in phase 1, the transaction manager invokes the <xref:System.Transactions.IEnlistmentNotification.Rollback%2A> method for each resource manager and indicates the failure of the commit to the application.</span></span>  
  
 <span data-ttu-id="653a0-133">Así, su administrador de recursos debería implementar los métodos siguientes.</span><span class="sxs-lookup"><span data-stu-id="653a0-133">Thus, your resource manager should implement the following methods.</span></span>  
  
```csharp
public void Commit (Enlistment enlistment)  
{  
     // Do any work necessary when commit notification is received  
  
     // Declare done on the enlistment  
     enlistment.Done();  
}  
  
public void Rollback (Enlistment enlistment)  
{  
     // Do any work necessary when rollback notification is received  
  
     // Declare done on the enlistment
     enlistment.Done();
}  
```  
  
 <span data-ttu-id="653a0-134">El administrador de recursos realizará las operaciones necesarias para finalizar la transacción basada en el tipo de notificación y después informará al administrador de transacciones de que ha finalizado llamando al método <xref:System.Transactions.Enlistment.Done%2A> en el parámetro <xref:System.Transactions.Enlistment>.</span><span class="sxs-lookup"><span data-stu-id="653a0-134">The RM should perform any work necessary to finish the transaction based on the notification type, and inform the TM that it has finished by calling <xref:System.Transactions.Enlistment.Done%2A> method on the <xref:System.Transactions.Enlistment> parameter.</span></span> <span data-ttu-id="653a0-135">Este trabajo se puede hacer en un subproceso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="653a0-135">This work can be done on a worker thread.</span></span> <span data-ttu-id="653a0-136">Tenga en cuenta que las notificaciones de la fase 2 pueden suceder alineadas en el mismo subproceso que llamó al método <xref:System.Transactions.PreparingEnlistment.Prepared%2A> en la fase 1.</span><span class="sxs-lookup"><span data-stu-id="653a0-136">Note that the phase 2 notifications can happen inline on the same thread that called the <xref:System.Transactions.PreparingEnlistment.Prepared%2A> method in phase 1.</span></span> <span data-ttu-id="653a0-137">Como tal, no debería realizar ningún trabajo después de la llamada a <xref:System.Transactions.PreparingEnlistment.Prepared%2A> (por ejemplo, liberando bloqueos) que debería esperar que se habrían completado antes de recibir las notificaciones de la fase 2.</span><span class="sxs-lookup"><span data-stu-id="653a0-137">As such, you should not do any work after the <xref:System.Transactions.PreparingEnlistment.Prepared%2A> call (for example, releasing locks) that you would expect to have completed before receiving the phase 2 notifications.</span></span>  
  
### <a name="implementing-indoubt"></a><span data-ttu-id="653a0-138">Implementar InDoubt</span><span class="sxs-lookup"><span data-stu-id="653a0-138">Implementing InDoubt</span></span>  
 <span data-ttu-id="653a0-139">Finalmente, debería implementar el método <xref:System.Transactions.IEnlistmentNotification.InDoubt%2A> para el administrador de recursos volátil.</span><span class="sxs-lookup"><span data-stu-id="653a0-139">Finally, you should implement the <xref:System.Transactions.IEnlistmentNotification.InDoubt%2A> method for the volatile resource manager.</span></span> <span data-ttu-id="653a0-140">Se llama a este método si el administrador de transacciones pierde el contacto con uno o más participantes, por lo que su estado es desconocido.</span><span class="sxs-lookup"><span data-stu-id="653a0-140">This method is called if the transaction manager loses contact with one or more participants, so their status is unknown.</span></span> <span data-ttu-id="653a0-141">Si esto se produce, debería registrar este hecho para que se pueda investigar después si cualquiera de los participantes de la transacción ha quedado en un estado incoherente.</span><span class="sxs-lookup"><span data-stu-id="653a0-141">If this occurs, you should log this fact so that you can investigate later whether any of the transaction participants has been left in an inconsistent state.</span></span>  
  
```csharp
public void InDoubt (Enlistment enlistment)  
{  
     // log this  
     enlistment.Done();  
}  
```  
  
## <a name="single-phase-commit-optimization"></a><span data-ttu-id="653a0-142">Optimización de confirmación de fase única</span><span class="sxs-lookup"><span data-stu-id="653a0-142">Single Phase Commit Optimization</span></span>  
 <span data-ttu-id="653a0-143">La fase única el protocolo de confirmación es más eficaz en el tiempo de ejecución porque todas las actualizaciones se hacen sin ninguna coordinación explícita.</span><span class="sxs-lookup"><span data-stu-id="653a0-143">The Single Phase Commit protocol is more efficient at run time because all updates are done without any explicit coordination.</span></span> <span data-ttu-id="653a0-144">Para obtener más información sobre este protocolo, consulte [Optimización mediante confirmación](optimization-spc-and-promotable-spn.md)de fase única y Notificación de fase única promocionable .</span><span class="sxs-lookup"><span data-stu-id="653a0-144">For more information on this protocol, see [Optimization using Single Phase Commit and Promotable Single Phase Notification](optimization-spc-and-promotable-spn.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="653a0-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="653a0-145">See also</span></span>

- [<span data-ttu-id="653a0-146">Optimización mediante el uso de la confirmación de fase única y de la inscripción de fase única promovible</span><span class="sxs-lookup"><span data-stu-id="653a0-146">Optimization using Single Phase Commit and Promotable Single Phase Notification</span></span>](optimization-spc-and-promotable-spn.md)
- [<span data-ttu-id="653a0-147">Dar de alta los recursos como participantes en una transacción</span><span class="sxs-lookup"><span data-stu-id="653a0-147">Enlisting Resources as Participants in a Transaction</span></span>](enlisting-resources-as-participants-in-a-transaction.md)
