---
title: Administrar la simultaneidad con DependentTransaction
ms.date: 03/30/2017
ms.assetid: b85a97d8-8e02-4555-95df-34c8af095148
ms.openlocfilehash: a8ddcab4b065c3400f9f9f7ec9ce04befdd0f29b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174386"
---
# <a name="managing-concurrency-with-dependenttransaction"></a>Administrar la simultaneidad con DependentTransaction
Se crea un objeto <xref:System.Transactions.Transaction> utilizando el método <xref:System.Transactions.Transaction.DependentClone%2A>. Su solo propósito es garantizar que la transacción no pueda confirmar mientras algunas otras partes de código (por ejemplo, un subproceso de trabajo) todavía están realizando el trabajo en la transacción. Cuando finalmente se completa el proceso de la transacción clonada y está preparada para confirmarse, se puede notificar al creador de la transacción con el método <xref:System.Transactions.DependentTransaction.Complete%2A>. Así se puede conservar la coherencia y exactitud de los datos.  
  
 La clase <xref:System.Transactions.DependentTransaction> también se puede utilizar para administrar la simultaneidad entre las tareas asincrónicas. En este escenario, el elemento primario puede continuar ejecutando cualquier código mientras el clon dependiente funciona en sus propias tareas. En otras palabras, no se bloquea la ejecución del elemento primario hasta que el dependiente complete.  
  
## <a name="creating-a-dependent-clone"></a>Crear un clon dependiente  
 Para crear una transacción dependiente, llame al método <xref:System.Transactions.Transaction.DependentClone%2A> y pase la enumeración <xref:System.Transactions.DependentCloneOption> como un parámetro. Este parámetro define el comportamiento de la transacción si se llama `Commit` en la transacción primaria antes de que el clon dependiente indique que está listo para que la transacción se confirme (llamando al método <xref:System.Transactions.DependentTransaction.Complete%2A> ). Los valores siguientes son válidos para este parámetro:  
  
- <xref:System.Transactions.DependentCloneOption.BlockCommitUntilComplete>crea una transacción dependiente que bloquea el proceso de confirmación <xref:System.Transactions.DependentTransaction.Complete%2A> de la transacción primaria hasta que se agota el tiempo de espera de la transacción principal o hasta que se llama a todos los dependientes que indican su finalización. Esto es útil cuando el cliente no desea que la transacción primaria se confirme hasta que las transacciones dependientes se hayan completado. Si la primaria finaliza su trabajo antes que la transacción dependiente y llama <xref:System.Transactions.CommittableTransaction.Commit%2A> en la transacción, el proceso de la confirmación se bloquea en un estado donde el trabajo adicional se puede hacer en la transacción y se pueden crear nuevas inscripciones, hasta que todos los dependientes llamen <xref:System.Transactions.DependentTransaction.Complete%2A>. En cuanto todos ellos hayan finalizado su trabajo y llamen a <xref:System.Transactions.DependentTransaction.Complete%2A>, el proceso de la confirmación para la transacción comienza.  
  
- <xref:System.Transactions.DependentCloneOption.RollbackIfNotComplete>, por otro lado, crea una transacción dependiente que automáticamente se anula en caso de que se llame a <xref:System.Transactions.CommittableTransaction.Commit%2A> en la transacción primaria antes de que <xref:System.Transactions.DependentTransaction.Complete%2A> se haya llamado. En este caso, todo el trabajo hecho en la transacción dependiente está intacto dentro de una duración de la transacción y nadie tiene una oportunidad para simplemente confirmar una parte de él.  
  
 Se debe llamar al método <xref:System.Transactions.DependentTransaction.Complete%2A> solo una vez cuando su aplicación finaliza su trabajo en la transacción dependiente; de lo contrario, se inicia <xref:System.InvalidOperationException>. Después de que se invoca esta llamada, no debería intentar realizar ningún trabajo adicional en la transacción o se producirá una excepción.  
  
 El ejemplo de código siguiente muestra cómo crear una transacción dependiente para administrar dos tareas simultáneas clonando una transacción dependiente y pasándola a un subproceso de trabajo.  
  
```csharp  
public class WorkerThread  
{  
    public void DoWork(DependentTransaction dependentTransaction)  
    {  
        Thread thread = new Thread(ThreadMethod);  
        thread.Start(dependentTransaction);
    }  
  
    public void ThreadMethod(object transaction)
    {
        DependentTransaction dependentTransaction = transaction as DependentTransaction;  
        Debug.Assert(dependentTransaction != null);
        try  
        {  
            using(TransactionScope ts = new TransactionScope(dependentTransaction))  
            {  
                /* Perform transactional work here */
                ts.Complete();  
            }  
        }  
        finally  
        {  
            dependentTransaction.Complete();
             dependentTransaction.Dispose();
        }  
    }  
  
//Client code
using(TransactionScope scope = new TransactionScope())  
{  
    Transaction currentTransaction = Transaction.Current;  
    DependentTransaction dependentTransaction;
    dependentTransaction = currentTransaction.DependentClone(DependentCloneOption.BlockCommitUntilComplete);  
    WorkerThread workerThread = new WorkerThread();  
    workerThread.DoWork(dependentTransaction);  
    /* Do some transactional work here, then: */  
    scope.Complete();  
}  
```  
  
 El código de cliente crea un ámbito transaccional que también establece la transacción ambiente. No debería pasar la transacción ambiente al subproceso de trabajo. En su lugar, debería clonar la transacción actual (ambiente) llamando al método <xref:System.Transactions.Transaction.DependentClone%2A> en la transacción actual y pasar el dependiente al subproceso de trabajo.  
  
 El método `ThreadMethod` se ejecuta en el nuevo subproceso. El cliente inicia un nuevo subproceso, pasando la transacción dependiente como el parámetro `ThreadMethod`.  
  
 Dado que la transacción dependiente se crea con <xref:System.Transactions.DependentCloneOption.BlockCommitUntilComplete>, se garantiza que no se puede confirmar la transacción hasta que todo el trabajo transaccional hecho en el segundo subproceso esté finalizado y se llame a <xref:System.Transactions.DependentTransaction.Complete%2A> en la transacción dependiente. Esto significa que si el ámbito del cliente finaliza (cuando intenta eliminar `using` el objeto de transacción al final de la instrucción) antes de que el nuevo subproceso llame <xref:System.Transactions.DependentTransaction.Complete%2A> a la transacción dependiente, el código de cliente se bloquea hasta que <xref:System.Transactions.DependentTransaction.Complete%2A> se llama en el dependiente. A continuación, la transacción puede terminar de confirmarse o anularse.  
  
## <a name="concurrency-issues"></a>Problemas de simultaneidad  
 Existen problemas de simultaneidad adicionales de los que necesita ser consciente al utilizar la clase <xref:System.Transactions.DependentTransaction>:  
  
- Si el subproceso de trabajo deshace la transacción pero el elemento primario intenta confirmarlo, se inicia <xref:System.Transactions.TransactionAbortedException>.  
  
- Debería crear un nuevo clon dependiente para cada subproceso de trabajo en la transacción. No pase el mismo clon dependiente a varios subprocesos, porque solo uno de ellos puede llamar <xref:System.Transactions.DependentTransaction.Complete%2A> en él.  
  
- Si el subproceso de trabajo genera un nuevo subproceso de trabajo, asegúrese de crear un clon dependiente a partir del clon dependiente y pasarlo al nuevo subproceso.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Transactions.DependentTransaction>
