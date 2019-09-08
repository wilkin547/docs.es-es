---
title: Transacciones y simultaneidad
ms.date: 03/30/2017
ms.assetid: f46570de-9e50-4fe6-8710-a8c31fa8569b
ms.openlocfilehash: 837fe6c42d64f7416dbd895e56a38d1a409e567a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70791317"
---
# <a name="transactions-and-concurrency"></a>Transacciones y simultaneidad
Una transacción consiste en un comando único o en un grupo de comandos que se ejecutan como un paquete. Las transacciones permiten combinar varias operaciones en una sola unidad de trabajo. Si en un punto de la transacción se produjera un error, todas las actualizaciones podrían revertirse y devolverse al estado que tenían antes de la transacción.  
  
 Una transacción debe ajustarse a las propiedades ACID (atomicidad, coherencia, aislamiento y durabilidad) para poder garantizar la coherencia de datos. La mayoría de los sistemas de bases de datos relacionales, como Microsoft SQL Server, admiten transacciones, al proporcionar funciones de bloqueo, registro y administración de transacciones cada vez que una aplicación cliente realiza una operación de actualización, inserción o eliminación.  
  
> [!NOTE]
> Las transacciones que requieren varios recursos pueden reducir la simultaneidad si la duración del bloqueo es demasiado larga. Por ello, haga la transacción lo más corta posible.  
  
 Las transacciones explícitas en procedimientos almacenados suelen dar mejores resultados cuando una transacción implica el uso de varias tablas en la misma base de datos o servidor. Se pueden crear transacciones en procedimientos almacenados de SQL Server mediante las instrucciones `BEGIN TRANSACTION`, `COMMIT TRANSACTION` o `ROLLBACK TRANSACTION` de Transact-SQL. Para obtener más información, vea los Libros en pantalla de SQL Server.  
  
 Las transacciones que implican diferentes administradores de recursos, como una transacción entre SQL Server y Oracle, requieren una transacción distribuida.  
  
## <a name="in-this-section"></a>En esta sección  
 [Transacciones locales](local-transactions.md)  
 Muestra cómo realizar transacciones en una base de datos.  
  
 [Transacciones distribuidas](distributed-transactions.md)  
 Describe cómo realizar transacciones distribuidas en ADO.NET.  
  
 [Integración de System.Transactions con SQL Server](system-transactions-integration-with-sql-server.md)  
 Describe <xref:System.Transactions> la integración con SQL Server para trabajar con transacciones distribuidas.  
  
 [Simultaneidad optimista](optimistic-concurrency.md)  
 Describe la simultaneidad optimista y pesimista, y cómo puede probar las infracciones de simultaneidad.  
  
## <a name="see-also"></a>Vea también

- [Principios de la transacción](../transactions/transaction-fundamentals.md)
- [Conexión a un origen de datos](connecting-to-a-data-source.md)
- [Comandos y parámetros](commands-and-parameters.md)
- [Objetos DataAdapter y DataReader](dataadapters-and-datareaders.md)
- [Objetos DbProviderFactory](dbproviderfactories.md)
- [Información general sobre ADO.NET](ado-net-overview.md)
