---
title: "Compatibilidad con transacciones | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8cceb26e-8d36-4365-8967-58e2e89e0187
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Compatibilidad con transacciones
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] admite tres modelos de transacción distintos.  A continuación se enumeran estos modelos por orden de comprobaciones realizadas.  
  
## Transacción local explícita  
 Cuando se llama a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, si la propiedad <xref:System.Data.Linq.DataContext.Transaction%2A> se establece en una transacción \(`IDbTransaction`\), la llamada a <xref:System.Data.Linq.DataContext.SubmitChanges%2A> se ejecuta en el contexto de la misma transacción.  
  
 Es su responsabilidad confirmar o revertir la transacción después de su correcta ejecución.  La conexión que corresponde a la transacción debe coincidir con la conexión utilizada para construir <xref:System.Data.Linq.DataContext>.  Si se utiliza una conexión diferente, se inicia una excepción.  
  
## Transacción distribuible explícita  
 Puede llamar a las API de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] \(incluidas, entre otras, <xref:System.Data.Linq.DataContext.SubmitChanges%2A>\) en el ámbito de un objeto <xref:System.Transactions.Transaction> activo.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]detecta que la llamada está en el ámbito de una transacción y no crea una nueva transacción.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]también impide el cierre de la conexión en ese caso.  Puede ejecutar consultas y el método <xref:System.Data.Linq.DataContext.SubmitChanges%2A> en el contexto de este tipo de transacción.  
  
## Transacción implícita  
 Al llamar a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] comprueba si la llamada se encuentra en el ámbito de una <xref:System.Transactions.Transaction> o si la propiedad `Transaction` \(`IDbTransaction`\) está establecida en una transacción local iniciada por el usuario.  Si no encuentra ninguna de estas transacciones, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] inicia una transacción local \(`IDbTransaction`\) y la usa para ejecutar los comandos SQL generados.  Cuando se han completado todos los comandos SQL correctamente, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] confirma la transacción local y devuelve un valor.  
  
## Vea también  
 [Información general](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)   
 [Cómo: Catalogar envíos de datos mediante transacciones](../../../../../../docs/framework/data/adonet/sql/linq/how-to-bracket-data-submissions-by-using-transactions.md)