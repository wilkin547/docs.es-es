---
title: Compatibilidad con transacciones
ms.date: 03/30/2017
ms.assetid: 8cceb26e-8d36-4365-8967-58e2e89e0187
ms.openlocfilehash: 9c7128ef432fa609b8d628bc74caebe790058ede
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792275"
---
# <a name="transaction-support"></a>Compatibilidad con transacciones
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]admite tres modelos de transacción distintos. A continuación se enumeran estos modelos por orden de comprobaciones realizadas.  
  
## <a name="explicit-local-transaction"></a>Transacción local explícita  
 Cuando se llama a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, si la propiedad <xref:System.Data.Linq.DataContext.Transaction%2A> se establece en una transacción (`IDbTransaction`), la llamada a <xref:System.Data.Linq.DataContext.SubmitChanges%2A> se ejecuta en el contexto de la misma transacción.  
  
 Es su responsabilidad confirmar o revertir la transacción después de su correcta ejecución. La conexión que corresponde a la transacción debe coincidir con la conexión utilizada para construir <xref:System.Data.Linq.DataContext>. Si se utiliza una conexión diferente, se inicia una excepción.  
  
## <a name="explicit-distributable-transaction"></a>Transacción distribuible explícita  
 Puede llamar a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] las API (incluida, pero sin <xref:System.Data.Linq.DataContext.SubmitChanges%2A>limitarse a), en el <xref:System.Transactions.Transaction>ámbito de un activo. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]detecta que la llamada está en el ámbito de una transacción y no crea una nueva transacción. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]también evita el cierre de la conexión en este caso. Puede ejecutar consultas y el método <xref:System.Data.Linq.DataContext.SubmitChanges%2A> en el contexto de este tipo de transacción.  
  
## <a name="implicit-transaction"></a>Transacción implícita  
 Cuando se llama <xref:System.Data.Linq.DataContext.SubmitChanges%2A>a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , comprueba si la llamada está <xref:System.Transactions.Transaction> en el ámbito de o si la `Transaction` propiedad (`IDbTransaction`) está establecida en una transacción local iniciada por el usuario. Si no encuentra ninguna transacción, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] inicia una transacción local (`IDbTransaction`) y la usa para ejecutar los comandos SQL generados. Cuando todos los comandos SQL se han completado correctamente [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , confirma la transacción local y devuelve.  
  
## <a name="see-also"></a>Vea también

- [Información general](background-information.md)
- [Cómo: Envío de datos entre corchetes mediante transacciones](how-to-bracket-data-submissions-by-using-transactions.md)
