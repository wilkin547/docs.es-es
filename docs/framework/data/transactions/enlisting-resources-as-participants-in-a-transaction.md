---
title: Dar de alta los recursos como participantes en una transacción
description: Dar de alta los recursos como participantes en una transacción de .NET. Un administrador de recursos administra cada recurso de una transacción, coordinada por un administrador de transacciones.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 786a12c2-d530-49f4-9c59-5c973e15a11d
ms.openlocfilehash: c3c777593750b3a4f05ae97ed6e26e19f58e4d72
ms.sourcegitcommit: 6219b1e1feccb16d88656444210fed3297f5611e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2020
ms.locfileid: "85141880"
---
# <a name="enlisting-resources-as-participants-in-a-transaction"></a>Dar de alta los recursos como participantes en una transacción

Un administrador de recursos administra cada recurso participante, cuyas acciones coordina un administrador de transacciones. La coordinación se hace a través de las notificaciones dadas a los suscriptores que han dado de alta una transacción a través del administrador de transacciones.

En este tema se trata cómo un recurso (o varios recursos) se puede dar de alta en una transacción, así como los tipos diferentes de inscripción. En el tema [confirmación de una transacción en una fase y varias fases](committing-a-transaction-in-single-phase-and-multi-phase.md) se explica cómo se puede coordinar el compromiso de la transacción entre los recursos que se han dado de alta.

## <a name="enlisting-resources-in-a-transaction"></a>Dar de alta los recursos en una transacción

Para que un administrador de recursos participe en una transacción, debe inscribirse en la transacción. La <xref:System.Transactions.Transaction> clase define un conjunto de métodos cuyos nombres comienzan por **dar de alta** que proporcionan esta funcionalidad. Los diferentes métodos de **inscripción** se corresponden con los distintos tipos de inscripción que puede tener un administrador de recursos. Específicamente, utiliza los métodos <xref:System.Transactions.Transaction.EnlistVolatile%2A> para los recursos volátiles y el método <xref:System.Transactions.Transaction.EnlistDurable%2A> para los recursos duraderos. La duración (o a la inversa la volatilidad) de un administrador de recursos hace referencia a si el administrador de recursos admite la recuperación del error. Si un administrador de recursos admite la recuperación del error, conserva los datos del almacenamiento duradero durante la fase1 (preparación) de tal manera que si el administrador de recursos baja, puede reenganchar la transacción en la recuperación y realizar las acciones apropiadas basadas en las notificaciones recibidas de la TM. En general, los administradores de recursos volátiles administran recursos volátiles como una estructura de datos en memoria (por ejemplo, una tabla hash llevada a cabo en memoria) y los administradores de recursos duraderos administran recursos que tienen una memoria auxiliar más persistente (por ejemplo, una base de datos cuyo dispositivo de copia de seguridad es el disco).

Para simplificar, después de decidir si utilizar el método<xref:System.Transactions.Transaction.EnlistDurable%2A> o <xref:System.Transactions.Transaction.EnlistVolatile%2A> basado en la compatibilidad de la duración de su recurso, debería dar de alta su recurso para participar en la confirmación en dos fases (2PC) implementando la interfaz <xref:System.Transactions.IEnlistmentNotification> para su administrador de recursos. Para obtener más información sobre 2PC, consulte [confirmar una transacción en una sola fase y varias fases](committing-a-transaction-in-single-phase-and-multi-phase.md).

Una participante única puede inscribir para más de uno de estos protocolos varias veces llamando a <xref:System.Transactions.Transaction.EnlistDurable%2A> y a <xref:System.Transactions.Transaction.EnlistVolatile%2A>.

### <a name="durable-enlistment"></a>Inscripción duradera

El método <xref:System.Transactions.Transaction.EnlistDurable%2A> se utiliza para inscribir un administrador de recursos para la participación en la transacción como un recurso duradero.  Se espera que si un administrador de recursos duradero se derrumba en el medio de una transacción, puede realizar la recuperación una vez devuelta la línea volviendo a darle de alta (utilizando el método <xref:System.Transactions.TransactionManager.Reenlist%2A>) en todas las transacciones en las que fue un participante y no completó la fase 2, y <xref:System.Transactions.TransactionManager.RecoveryComplete%2A> de la llamada cuando finaliza el procesamiento de la recuperación. Para obtener más información sobre la recuperación, vea [realizar la recuperación](performing-recovery.md).

Todos métodos <xref:System.Transactions.Transaction.EnlistDurable%2A> toman un objeto <xref:System.Guid> como su primer parámetro. El administrador de transacciones utiliza <xref:System.Guid> para asociar una inscripción duradera a un administrador de recursos determinado. Como tal, es imperativo que un administrador de recursos utilice de forma consistente el mismo <xref:System.Guid> para incluso identificarse por los administradores de recursos diferentes al reiniciar, de lo contrario se puede producir un error en la recuperación.

El segundo parámetro del método <xref:System.Transactions.Transaction.EnlistDurable%2A> es una referencia al objeto que el administrador de recursos implementa para recibir las notificaciones de la transacción. La sobrecarga que utiliza informa al administrador de transacciones si su administrador de recursos admite la optimización de la fase de confirmación única(SPC). La mayoría de las veces,  implementaría la interfaz <xref:System.Transactions.IEnlistmentNotification> para tomar la parte en la confirmación en dos fases (2PC). Sin embargo, si desea optimizar el proceso de confirmación, puede considerar implementar la interfaz <xref:System.Transactions.ISinglePhaseNotification> para SPC. Para obtener más información sobre SPC, consulte [confirmación de una transacción en fase única y varias fases](committing-a-transaction-in-single-phase-and-multi-phase.md) y [optimización mediante la confirmación de fase única y la notificación de fase única promocionable](optimization-spc-and-promotable-spn.md).

El tercer parámetro es una enumeración <xref:System.Transactions.EnlistmentOptions>, cuyo valor puede ser <xref:System.Transactions.EnlistmentOptions.None> o <xref:System.Transactions.EnlistmentOptions.EnlistDuringPrepareRequired>. Si el valor está establecido en <xref:System.Transactions.EnlistmentOptions.EnlistDuringPrepareRequired>, la inscripción puede dar de alta los administradores de recursos adicionales al recibir la notificación de preparación del administrador de transacciones. Sin embargo, debería ser consciente de que este tipo de inscripción no es apta para la optimización de la fase de confirmación única.

### <a name="volatile-enlistment"></a>Inscripción volátil

Los participantes que administran recursos volátiles como una caché, deberían darse de alta utilizando los métodos <xref:System.Transactions.Transaction.EnlistVolatile%2A>. Tales objetos no podrían obtener el resultado de una transacción o recuperar el estado de cualquier transacción participan después de un error del sistema.

Como dicho previamente, un administrador de recursos realizaría una inscripción volátil si administra un recurso en memoria volátil. Una de las ventajas de utilizar <xref:System.Transactions.Transaction.EnlistVolatile%2A> es que no fuerza ninguna subida innecesaria de la transacción. Para obtener más información sobre el escalado de transacciones, vea el tema sobre [escalado de administración de transacciones](transaction-management-escalation.md) . Dar de alta la volatilidad implica tanto una diferencia en el modo en que el administrador de transacciones controla la inscripción, así como lo que el administrador de transacciones espera que el administrador de recursos. Esto es porque un administrador de recursos volátil no realiza la recuperación. Los métodos <xref:System.Transactions.Transaction.EnlistVolatile%2A> no toman un parámetro <xref:System.Guid>, porque un administrador de recursos volátil no realiza la recuperación y no llama al método <xref:System.Transactions.TransactionManager.Reenlist%2A> que necesita <xref:System.Guid>.

Como con inscripciones duraderas, el método de sobrecarga que se utiliza para dar de alta indica al administrador de transacciones si su administrador de recursos admite la optimización de la fase de confirmación única. Puesto que un administrador de recursos volátil no puede realizar la recuperación, ninguna información de la recuperación se escribe para una inscripción volátil durante la fase de preparación. Por consiguiente, llamar al método <xref:System.Transactions.PreparingEnlistment.RecoveryInformation%2A> produce <xref:System.InvalidOperationException>.

El ejemplo siguiente muestra cómo dar de alta este tipo de objeto como un participante en una transacción utilizando el método <xref:System.Transactions.Transaction.EnlistVolatile%2A>.

[!code-csharp[Tx_Enlist#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/tx_enlist/cs/enlist.cs#1)]
[!code-vb[Tx_Enlist#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/tx_enlist/vb/enlist.vb#1)]

### <a name="optimizing-performance"></a>Optimizar el rendimiento

La clase <xref:System.Transactions.Transaction> también proporciona el método <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A> para dar de alta una Inscripción de fase única promocional (PSPE). Esto permite a un administrador de recursos duradero (RM) hospedar y "poseer" una transacción que puede realizar una escalada para que sea administrada por MSDTC si es necesario. Para obtener más información, consulte [optimización mediante la confirmación de fase única y la notificación de fase única promocionable](optimization-spc-and-promotable-spn.md).

## <a name="see-also"></a>Consulte también:

- [Optimización mediante el uso de la confirmación de fase única y de la inscripción de fase única promovible](optimization-spc-and-promotable-spn.md)
- [Confirmar una transacción en fase única y múltiple](committing-a-transaction-in-single-phase-and-multi-phase.md)
