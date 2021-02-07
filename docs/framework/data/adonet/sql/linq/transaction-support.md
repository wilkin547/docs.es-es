---
description: 'Más información acerca de: compatibilidad con transacciones'
title: Compatibilidad con transacciones
ms.date: 03/30/2017
ms.assetid: 8cceb26e-8d36-4365-8967-58e2e89e0187
ms.openlocfilehash: 97c076fadacde01c7d14e5d51b000839b3d014a2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99681180"
---
# <a name="transaction-support"></a>Compatibilidad con transacciones

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] admite tres modelos de transacción distintos. A continuación se enumeran estos modelos por orden de comprobaciones realizadas.  
  
## <a name="explicit-local-transaction"></a>Transacción local explícita  

 Cuando se llama a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, si la propiedad <xref:System.Data.Linq.DataContext.Transaction%2A> se establece en una transacción (`IDbTransaction`), la llamada a <xref:System.Data.Linq.DataContext.SubmitChanges%2A> se ejecuta en el contexto de la misma transacción.  
  
 Es su responsabilidad confirmar o revertir la transacción después de su correcta ejecución. La conexión que corresponde a la transacción debe coincidir con la conexión utilizada para construir <xref:System.Data.Linq.DataContext>. Si se utiliza una conexión diferente, se inicia una excepción.  
  
## <a name="explicit-distributable-transaction"></a>Transacción distribuible explícita  

 Puede llamar a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] las API (incluida, pero sin limitarse a <xref:System.Data.Linq.DataContext.SubmitChanges%2A> ), en el ámbito de un activo <xref:System.Transactions.Transaction> . [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] detecta que la llamada está en el ámbito de una transacción y no crea una nueva transacción. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] también evita el cierre de la conexión en este caso. Puede ejecutar consultas y el método <xref:System.Data.Linq.DataContext.SubmitChanges%2A> en el contexto de este tipo de transacción.  
  
## <a name="implicit-transaction"></a>Transacción implícita  

 Cuando se llama <xref:System.Data.Linq.DataContext.SubmitChanges%2A> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] a, comprueba si la llamada está en el ámbito de <xref:System.Transactions.Transaction> o si la `Transaction` propiedad ( `IDbTransaction` ) está establecida en una transacción local iniciada por el usuario. Si no encuentra ninguna transacción, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] inicia una transacción local ( `IDbTransaction` ) y la usa para ejecutar los comandos SQL generados. Cuando todos los comandos SQL se han completado correctamente, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] confirma la transacción local y devuelve.  
  
## <a name="see-also"></a>Vea también

- [Información general](background-information.md)
- [Procedimiento para poner entre corchetes envíos de datos mediante el uso de transacciones](how-to-bracket-data-submissions-by-using-transactions.md)
