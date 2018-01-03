---
title: Transacciones y simultaneidad
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f46570de-9e50-4fe6-8710-a8c31fa8569b
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 4301a232e2b38d44ecb288e76439742f7fe4d58f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="transactions-and-concurrency"></a>Transacciones y simultaneidad
Una transacción consiste en un comando único o en un grupo de comandos que se ejecutan como un paquete. Las transacciones permiten combinar varias operaciones en una sola unidad de trabajo. Si en un punto de la transacción se produjera un error, todas las actualizaciones podrían revertirse y devolverse al estado que tenían antes de la transacción.  
  
 Una transacción debe ajustarse a las propiedades ACID (atomicidad, coherencia, aislamiento y durabilidad) para poder garantizar la coherencia de datos. La mayoría de los sistemas de bases de datos relacionales, como Microsoft SQL Server, admiten transacciones, al proporcionar funciones de bloqueo, registro y administración de transacciones cada vez que una aplicación cliente realiza una operación de actualización, inserción o eliminación.  
  
> [!NOTE]
>  Las transacciones que requieren varios recursos pueden reducir la simultaneidad si la duración del bloqueo es demasiado larga. Por ello, haga la transacción lo más corta posible.  
  
 Las transacciones explícitas en procedimientos almacenados suelen dar mejores resultados cuando una transacción implica el uso de varias tablas en la misma base de datos o servidor. Se pueden crear transacciones en procedimientos almacenados de SQL Server mediante las instrucciones `BEGIN TRANSACTION`, `COMMIT TRANSACTION` o `ROLLBACK TRANSACTION` de Transact-SQL. Para obtener más información, vea los Libros en pantalla de SQL Server.  
  
 Las transacciones que implican varios administradores de recursos, como un a transacción entre [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] y Oracle, requieren una transacción distribuida.  
  
## <a name="in-this-section"></a>En esta sección  
 [Transacciones locales](../../../../docs/framework/data/adonet/local-transactions.md)  
 Muestra cómo realizar transacciones en una base de datos.  
  
 [Transacciones distribuidas](../../../../docs/framework/data/adonet/distributed-transactions.md)  
 Describe cómo realizar transacciones distribuidas en ADO.NET.  
  
 [Integración de System.Transactions con SQL Server](../../../../docs/framework/data/adonet/system-transactions-integration-with-sql-server.md)  
 Describe la integración de <xref:System.Transactions> con [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] para trabajar con transacciones distribuidas.  
  
 [Simultaneidad optimista](../../../../docs/framework/data/adonet/optimistic-concurrency.md)  
 Describe la simultaneidad optimista y pesimista, y cómo puede probar las infracciones de simultaneidad.  
  
## <a name="see-also"></a>Vea también  
 [Principios de la transacción](../../../../docs/framework/data/transactions/transaction-fundamentals.md)  
 [Conexión a un origen de datos](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [Comandos y parámetros](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [Objetos DataAdapter y DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [Objetos DbProviderFactory](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
