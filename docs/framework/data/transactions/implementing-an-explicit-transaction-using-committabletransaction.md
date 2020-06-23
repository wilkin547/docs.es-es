---
title: Implementar una transacción explícita mediante una transacción confirmable
description: Implemente una transacción explícita mediante la clase CommittableTransaction en .NET. Esta clase proporciona una forma explícita de que las aplicaciones usen una transacción.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 29efe5e5-897b-46c2-a35f-e599a273acc8
ms.openlocfilehash: 40001422e665a7dda3fb938c8d57860909525404
ms.sourcegitcommit: 6219b1e1feccb16d88656444210fed3297f5611e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2020
ms.locfileid: "85141996"
---
# <a name="implementing-an-explicit-transaction-using-committabletransaction"></a>Implementar una transacción explícita mediante una transacción confirmable
La clase <xref:System.Transactions.CommittableTransaction> proporciona a las aplicaciones una manera explícita de utilizar una transacción, a diferencia de utilizar implícitamente la clase <xref:System.Transactions.TransactionScope>. Es útil para las aplicaciones que desean utilizar la misma transacción por varias llamadas de función o llamadas de subproceso múltiples. A diferencia de la clase <xref:System.Transactions.TransactionScope>, el sistema de escritura de la aplicación ha de llamar específicamente a los métodos <xref:System.Transactions.CommittableTransaction.Commit%2A> y <xref:System.Transactions.Transaction.Rollback%2A> para confirmar o anular la transacción.  
  
## <a name="overview-of-the-committabletransaction-class"></a>Información general sobre la clase CommittableTransaction.  
 La clase <xref:System.Transactions.CommittableTransaction> deriva de la clase <xref:System.Transactions.Transaction>, proporcionando, por consiguiente, toda la funcionalidad del último. Específicamente útil es el método <xref:System.Transactions.Transaction.Rollback%2A> en la clase <xref:System.Transactions.Transaction> que también se puede utilizar para revertir un objeto <xref:System.Transactions.CommittableTransaction>.  
  
 La clase <xref:System.Transactions.Transaction> es similar a la clase <xref:System.Transactions.CommittableTransaction> pero no proporciona un método `Commit`. Esto le permite pasar el objeto de transacción (o clones de él) a otros métodos (potencialmente en otros subprocesos) mientras todavía se controla cuando se confirma la transacción. El código llamado puede dar de alta y votar en la transacción, pero solo el creador del objeto <xref:System.Transactions.CommittableTransaction> tiene la capacidad de confirmar la transacción.  
  
 Debe tener en cuenta lo siguiente cuando trabaje con la clase <xref:System.Transactions.CommittableTransaction>,  
  
- Al crear una transacción <xref:System.Transactions.CommittableTransaction>, no se establece la transacción ambiente. Tendrá que establecer y restablecer específicamente la transacción de ambiente con el fin de garantizar que los administradores de recursos funcionen bajo el contexto de transacción correcto cuando sea apropiado. La manera de establecer la transacción ambiente actual está estableciendo la propiedad <xref:System.Transactions.Transaction.Current%2A> estática en el objeto <xref:System.Transactions.Transaction> global.  
  
- No se puede reutilizar un objeto <xref:System.Transactions.CommittableTransaction>. Una vez confirmado o revertido un objeto <xref:System.Transactions.CommittableTransaction>, no se puede utilizar de nuevo en una transacción. Es decir, no se puede establecer como el contexto de la transacción ambiente actual.  
  
## <a name="creating-a-committabletransaction"></a>Crear un CommittableTransaction  
 En el ejemplo siguiente se crea una nueva instancia de <xref:System.Transactions.CommittableTransaction> y se confirma.  
  
 [!code-csharp[Tx_CommittableTx#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/tx_committabletx/cs/committabletxwithsql.cs#1)]
 [!code-vb[Tx_CommittableTx#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/tx_committabletx/vb/committabletxwithsql.vb#1)]  
  
 Al crear una instancia de <xref:System.Transactions.CommittableTransaction>, no se establece automáticamente el contexto de la transacción ambiente. Por consiguiente, cualquier operación en un administrador de recursos no forma parte de esa transacción. La propiedad <xref:System.Transactions.Transaction.Current%2A> estática en el objeto <xref:System.Transactions.Transaction> global se utiliza para establecer o recuperar la transacción ambiente y la aplicación debe establecerlo manualmente para asegurarse de que los administradores de recursos pueden participar en la transacción. También es una práctica buena guardar la transacción ambiente anterior y restaurarla al terminar de utilizar el objeto <xref:System.Transactions.CommittableTransaction>.  
  
 Para confirmar la transacción se necesita llamar explícitamente al método <xref:System.Transactions.CommittableTransaction.Commit%2A> . Para deshacer una transacción, debería llamar al método <xref:System.Transactions.Transaction.Rollback%2A>. Es importante tener en cuenta que hasta que <xref:System.Transactions.CommittableTransaction> se haya confirmado o revertido, se bloquean todos los recursos implicados todavía en esa transacción.  
  
 Un objeto <xref:System.Transactions.CommittableTransaction> se puede utilizar por las llamadas de función y subprocesos. Sin embargo, es tarea del desarrollador de aplicaciones administrar las excepciones y específicamente llamar al método <xref:System.Transactions.Transaction.Rollback%28System.Exception%29> en caso de error.  
  
## <a name="asynchronous-commit"></a>Confirmación asincrónica  
 La clase <xref:System.Transactions.CommittableTransaction> también proporciona un mecanismo para confirmar de forma asincrónica una transacción. Una confirmación de la transacción puede tardar un tiempo sustancial, al igual que podría implicar varios accesos a bases de datos y una posible latencia de red. Al desear evitar los interbloqueos en aplicaciones de alto rendimiento, puede utilizar la confirmación asincrónica para finalizar lo antes posible el trabajo transaccional y ejecutar la operación de la confirmación como una tarea en segundo plano. <xref:System.Transactions.CommittableTransaction.BeginCommit%2A> y los métodos <xref:System.Transactions.CommittableTransaction.EndCommit%2A> de la clase <xref:System.Transactions.CommittableTransaction> le permiten esto.  
  
 Puede llamar <xref:System.Transactions.CommittableTransaction.BeginCommit%2A> para enviar el retraso de la confirmación a un subproceso del grupo de subprocesos. También puede llamar <xref:System.Transactions.CommittableTransaction.EndCommit%2A> para determinar si se ha confirmado la transacción realmente. Si la transacción no se confirma por cualquier razón, <xref:System.Transactions.CommittableTransaction.EndCommit%2A> se producirá una excepción de transacción. Si no se confirma la transacción todavía cuando se llama <xref:System.Transactions.CommittableTransaction.EndCommit%2A>, se bloquea el llamador hasta que la transacción se confirme o anule.  
  
 La manera más fácil de hacer una confirmación asincrónica es proporcionando un método de devolución de llamada, para ser llamado cuando la confirmación esté terminada. Sin embargo, debe llamar al método <xref:System.Transactions.CommittableTransaction.EndCommit%2A> en el objeto <xref:System.Transactions.CommittableTransaction> original utilizado para invocar la llamada. Para obtener ese objeto, puede convertir en un nivel inferior el parámetro *IAsyncResult* del método de devolución de llamada, ya que la <xref:System.Transactions.CommittableTransaction> clase implementa la <xref:System.IAsyncResult> clase.  
  
 El ejemplo siguiente muestra cómo se puede hacer una confirmación asincrónica.  
  
```csharp  
public void DoTransactionalWork()  
{  
     Transaction oldAmbient = Transaction.Current;  
     CommittableTransaction committableTransaction = new CommittableTransaction();  
     Transaction.Current = committableTransaction;  
  
     try  
     {  
          /* Perform transactional work here */  
          // No errors - commit transaction asynchronously  
          committableTransaction.BeginCommit(OnCommitted,null);  
     }  
     finally  
     {  
          //Restore the ambient transaction
          Transaction.Current = oldAmbient;  
     }  
}  
void OnCommitted(IAsyncResult asyncResult)  
{  
     CommittableTransaction committableTransaction;  
     committableTransaction = asyncResult as CommittableTransaction;
     Debug.Assert(committableTransaction != null);  
     try  
     {  
          using(committableTransaction)  
          {  
               committableTransaction.EndCommit(asyncResult);  
          }  
     }  
     catch(TransactionException e)  
     {  
          //Handle the failure to commit  
     }  
}  
```  
  
## <a name="see-also"></a>Consulte también:

- [Implementar una transacción implícita mediante el ámbito de la transacción](implementing-an-implicit-transaction-using-transaction-scope.md)
- [Procesar transacciones](index.md)
