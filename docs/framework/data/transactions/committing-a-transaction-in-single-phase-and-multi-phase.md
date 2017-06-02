---
title: "Confirmar una transacci&#243;n en fase &#250;nica y fase m&#250;ltiple  | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 694ea153-e4db-41ae-96ac-9ac66dcb69a9
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Confirmar una transacci&#243;n en fase &#250;nica y fase m&#250;ltiple 
Un administrador de recursos \(RM\) administra cada recurso utilizado, cuyas acciones coordina un administrador de transacciones \(TM\). En este tema  [Dar de alta recursos como participantes en una transacción ](../../../../docs/framework/data/transactions/enlisting-resources-as-participants-in-a-transaction.md) se trata cómo un recurso \(o múltiples recursos\) pueden inscribirse en una transacción.En este tema se trata cómo la confirmación de la transacción se puede coordinar entre los recursos inscritos.  
  
 Al final de la transacción, la aplicación pide confirmar la transacción o revertirlaEl administrador de transacciones debe eliminar los riesgos como algunos administradores de recursos que votan para confirmar mientras que otros votan para deshacer la transacción.  
  
 Si su transacción implica más de un recurso, debe realizar una confirmación en dos fases \(2PC\).El protocolo de confirmación en dos fases \(la fase de preparación y la de confirmación\) asegura que cuando la transacción finaliza, todos los cambios a todos los recursos se confirman o se deshacen.Todos los participantes se informan a continuación del resultado final.Para obtener una discusión detallada del protocolo de confirmación en dos fases, consulte el libro "*Procesamiento de transacciones: Conceptos y Técnicas \(Serie de Morgan Kaufmann en Sistemas de administración de datos\) ISBN:1558601902*" por Jim Gray.  
  
 También puede optimizar el rendimiento de su transacción tomando parte en el protocolo de confirmación de fase única.Para obtener más información, consulte [Optimización mediante el uso de la confirmación de fase única y de la confirmación de fase única promocionable ](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md).  
  
 Si solo desea ser informado del resultado de una transacción, y no desea participar para votar, se debería registrar para el evento <xref:System.Transactions.Transaction.TransactionCompleted>.  
  
## Confirmación en dos fases \(2PC\)  
 En la primera fase de la transacción, el administrador de transacciones consulta cada recurso para determinar si una transacción se debería confirmar o deshacer.En la segunda fase de la transacción, el administrador de transacciones notifica a cada recurso el resultado de sus consultas, permitiéndole realizar cualquier limpieza necesaria.  
  
 Para participar en este tipo de transacción, un administrador de recursos debe implementar la interfaz <xref:System.Transactions.IEnlistmentNotification>, que proporciona métodos que el TM llamará como notificaciones durante una 2PC.En el siguiente ejemplo se muestra un ejemplo de dicha implementación.  
  
 [!code-csharp[Tx_Enlist#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/tx_enlist/cs/enlist.cs#2)]
 [!code-vb[Tx_Enlist#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/tx_enlist/vb/enlist.vb#2)]  
  
### Preparar la fase \(fase 1\)  
 Al recibir una solicitud <xref:System.Transactions.CommittableTransaction.Commit%2A> de la aplicación, el administrador de transacciones comienza la fase de preparación de todos los participantes alistados llamando al método <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> en cada recurso alistado para obtener el voto de cada recurso en la transacción.  
  
 Su administrador de recursos que implementa la interfaz <xref:System.Transactions.IEnlistmentNotification> debería implementar primero el método <xref:System.Transactions.IEnlistmentNotification.Prepare%28System.Transactions.PreparingEnlistment%29> como las presentaciones del ejemplo simples siguientes.  
  
```  
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
  
 Cuando el administrador de recursos duradero recibe esta llamada, debería registrar la información de la recuperación \(disponible recuperando la propiedad <xref:System.Transactions.PreparingEnlistment.RecoveryInformation%2A> \) de la transacción y cualquier información es necesaria para completar la transacción de confirmación.Esto no necesita ser realizado dentro del método <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> porque RM puede hacer esto en un subproceso de trabajo.  
  
 Cuando RM ha finalizado su trabajo de preparación, debería votar para confirmar o deshacer llamando a<xref:System.Transactions.PreparingEnlistment.Prepared%2A> o al método <xref:System.Transactions.PreparingEnlistment.ForceRollback%2A>.Observe que la clase <xref:System.Transactions.PreparingEnlistment> hereda un método <xref:System.Transactions.Enlistment.Done%2A> de la clase <xref:System.Transactions.Enlistment>.Si llama a este método en la devolución de llamada <xref:System.Transactions.PreparingEnlistment> durante la fase de preparación, éste informa al TM de que es una inscripción de solo lectura \(es decir, administradores de recursos que pueden leer pero no pueden actualizar los datos protegidos por transacción\) y el RM no recibe ninguna notificación más extensa del administrador de transacciones acerca del resultado de la transacción en fase 2.  
  
 Se cuenta en la aplicación la exitosa confirmación de la transacción después de que todos los administradores de recursos voten <xref:System.Transactions.PreparingEnlistment.Prepared%2A>.  
  
### Confirmar la fase \(fase 2\)  
 En la segunda fase de la transacción, si el administrador de transacciones recibe correcta preparación de todos los administradores de recursos \(todos los administradores de recursos han invocado <xref:System.Transactions.PreparingEnlistment.Prepared%2A> al final de fase 1\), invoca el método <xref:System.Transactions.IEnlistmentNotification.Commit%2A> para cada administrador de recursos.Los administradores de recursos pueden realizar a continuación los cambios duraderos y completar la confirmación.  
  
 Si cualquier administrador de recursos informa de un error para preparar en fase 1, el administrador de transacciones invoca el método <xref:System.Transactions.IEnlistmentNotification.Rollback%2A> para cada administrador de recursos e indica el error de la confirmación a la aplicación.  
  
 Así, su administrador de recursos debería implementar los métodos siguientes.  
  
```  
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
  
 El administrador de recursos realizará las operaciones necesarias para finalizar la transacción basada en el tipo de notificación y después informará al administrador de transacciones de que ha finalizado llamando al método <xref:System.Transactions.Enlistment.Done%2A> en el parámetro <xref:System.Transactions.Enlistment>.Este trabajo se puede hacer en un subproceso de trabajo.Tenga en cuenta que las notificaciones de la fase 2 pueden suceder alineadas en el mismo subproceso que llamó al método <xref:System.Transactions.PreparingEnlistment.Prepared%2A> en la fase 1.Como tal, no debería realizar ningún trabajo después de la llamada a <xref:System.Transactions.PreparingEnlistment.Prepared%2A> \(por ejemplo, liberando bloqueos\) que debería esperar que se habrían completado antes de recibir las notificaciones de la fase 2.  
  
### Implementar InDoubt  
 Finalmente, debería implementar el método <xref:System.Transactions.IEnlistmentNotification.InDoubt%2A> para el administrador de recursos volátil.Se llama a este método si el administrador de transacciones pierde el contacto con uno o más participantes, por lo que su estado es desconocido.Si esto se produce, debería registrar este hecho para que se pueda investigar después si cualquiera de los participantes de la transacción ha quedado en un estado incoherente.  
  
```  
public void InDoubt (Enlistment enlistment)  
{  
     // log this  
     enlistment.Done();  
}  
```  
  
## Optimización de confirmación de fase única  
 La fase única el protocolo de confirmación es más eficaz en el tiempo de ejecución porque todas las actualizaciones se hacen sin ninguna coordinación explícita.Para obtener más información sobre este protocolo vea [Optimización mediante el uso de la confirmación de fase única y de la confirmación de fase única promocionable ](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md).  
  
## Vea también  
 [Optimización mediante el uso de la confirmación de fase única y de la confirmación de fase única promocionable ](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md)   
 [Dar de alta recursos como participantes en una transacción ](../../../../docs/framework/data/transactions/enlisting-resources-as-participants-in-a-transaction.md)