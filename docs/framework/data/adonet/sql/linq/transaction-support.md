---
title: Compatibilidad con transacciones
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8cceb26e-8d36-4365-8967-58e2e89e0187
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 543ea3d1a0f767a10b36e040155e7e9304aca5a9
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="transaction-support"></a>Compatibilidad con transacciones
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]admite tres modelos de transacción distintos. A continuación se enumeran estos modelos por orden de comprobaciones realizadas.  
  
## <a name="explicit-local-transaction"></a>Transacción local explícita  
 Cuando se llama a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, si la propiedad <xref:System.Data.Linq.DataContext.Transaction%2A> se establece en una transacción (`IDbTransaction`), la llamada a <xref:System.Data.Linq.DataContext.SubmitChanges%2A> se ejecuta en el contexto de la misma transacción.  
  
 Es su responsabilidad confirmar o revertir la transacción después de su correcta ejecución. La conexión que corresponde a la transacción debe coincidir con la conexión utilizada para construir <xref:System.Data.Linq.DataContext>. Si se utiliza una conexión diferente, se inicia una excepción.  
  
## <a name="explicit-distributable-transaction"></a>Transacción distribuible explícita  
 Puede llamar a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] API (incluidos pero no limitados a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>) en el ámbito de un activo <xref:System.Transactions.Transaction>. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]detecta que la llamada está en el ámbito de una transacción y no crea una nueva transacción. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]También impide el cierre la conexión en este caso. Puede ejecutar consultas y el método <xref:System.Data.Linq.DataContext.SubmitChanges%2A> en el contexto de este tipo de transacción.  
  
## <a name="implicit-transaction"></a>Transacción implícita  
 Cuando se llama a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] comprueba si la llamada se encuentra en el ámbito de un <xref:System.Transactions.Transaction> o si la `Transaction` propiedad (`IDbTransaction`) está establecida en una transacción local iniciada por el usuario. Si no encuentra ninguna de estas transacciones, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] inicia una transacción local (`IDbTransaction`) y lo utiliza para ejecutar los comandos SQL generados. Cuando se han completado correctamente todos los comandos SQL, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] confirma la transacción local y devuelve.  
  
## <a name="see-also"></a>Vea también  
 [Información general](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [Colocación entre corchetes de envíos de datos utilizando transacciones](../../../../../../docs/framework/data/adonet/sql/linq/how-to-bracket-data-submissions-by-using-transactions.md)
