---
title: Objeto Transaction y operaciones de copia masiva
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f6f0cbc9-f7bf-4d6e-875f-ad1ba0b4aa62
ms.openlocfilehash: 27fafc0ef45b80eddd993229f52d119b40b4956f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155449"
---
# <a name="transaction-and-bulk-copy-operations"></a>Objeto Transaction y operaciones de copia masiva

Las operaciones de copia masiva se pueden realizar como operaciones aisladas o como parte de una transacción en varios pasos. Esta última opción permite realizar más de una operación de copia masiva en la misma transacción, así como realizar otras operaciones de base de datos (como inserciones, actualizaciones y eliminaciones) mientras todavía se puede confirmar o revertir la transacción entera.  
  
 De forma predeterminada, una operación de copia masiva se realiza como una operación aislada. La operación de copia masiva tiene lugar sin transacciones y sin la oportunidad de revertirla. Si necesita revertir toda o parte de la copia masiva cuando se produce un error, puede usar una <xref:System.Data.SqlClient.SqlBulkCopy> transacción administrada por, realizar la operación de copia masiva en una transacción existente o inscribirse en un **System. Transactions** <xref:System.Transactions.Transaction> .  
  
## <a name="performing-a-non-transacted-bulk-copy-operation"></a>Realización de una operación de copia masiva sin transacción  

 La aplicación de consola siguiente muestra lo que sucede cuando una operación de copia masiva sin transacciones detecta un error en medio de la operación.  
  
 En el ejemplo, las tablas de origen y de destino incluyen cada una una columna `Identity` denominada **ProductID**. En primer lugar, el código prepara la tabla de destino mediante la eliminación de todas las filas y luego inserta una sola fila cuyo **ProductID** se sabe que existe en la tabla de origen. De forma predeterminada, se genera un nuevo valor para la columna `Identity` en la tabla de destino para cada fila agregada. En este ejemplo, cuando se abre la conexión, se establece una opción que obliga al proceso de carga masiva a usar los valores `Identity` de la tabla de origen en su lugar.  
  
 La operación de copia masiva se ejecuta con la propiedad <xref:System.Data.SqlClient.SqlBulkCopy.BatchSize%2A> establecida en 10. Cuando la operación encuentra la fila no válida, se produce una excepción. En este primer ejemplo, la operación de copia masiva es sin transacciones. Se confirman todos los lotes copiados hasta el punto del error; el lote que contiene la clave duplicada se revierte y la operación de copia masiva se detiene antes de procesar el resto de los lotes.  
  
> [!NOTE]
> Este ejemplo no se ejecutará a menos que haya creado las tablas de trabajo como se describe en el ejemplo de configuración de la [copia masiva](bulk-copy-example-setup.md). Este código se proporciona para mostrar la sintaxis para usar **SqlBulkCopy**. Si las tablas de origen y destino se encuentran en la misma instancia de SQL Server, es más fácil y rápido usar una instrucción `INSERT … SELECT` de Transact-SQL para copiar los datos.  
  
 [!code-csharp[DataWorks SqlBulkCopy.DefaultTransaction#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.DefaultTransaction/CS/source.cs#1)]
 [!code-vb[DataWorks SqlBulkCopy.DefaultTransaction#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.DefaultTransaction/VB/source.vb#1)]  
  
## <a name="performing-a-dedicated-bulk-copy-operation-in-a-transaction"></a>Realización de una operación de copia masiva dedicada en una transacción  

 De forma predeterminada, una operación de copia masiva es su propia transacción. Si desea realizar una operación de copia masiva dedicada, cree una nueva instancia de <xref:System.Data.SqlClient.SqlBulkCopy> con una cadena de conexión o use un objeto <xref:System.Data.SqlClient.SqlConnection> existente sin una transacción activa. En cada escenario, la operación de copia masiva crea y confirma o revierte la transacción.  
  
 Puede especificar explícitamente la opción <xref:System.Data.SqlClient.SqlBulkCopyOptions.UseInternalTransaction> en el constructor de la clase <xref:System.Data.SqlClient.SqlBulkCopy> para provocar de forma explícita una operación de copia masiva que se ejecute en su propia transacción, lo que da lugar a que cada lote de la operación de copia masiva se ejecute en una transacción independiente.  
  
> [!NOTE]
> Dado que diferentes lotes se ejecutan en diferentes transacciones, si se produce un error durante la operación de copia masiva, se revertirán todas las filas del lote actual, pero las filas de los lotes anteriores permanecerán en la base de datos.  
  
 La aplicación de consola siguiente es similar al ejemplo anterior, con una excepción: en este caso, la operación de copia masiva administra sus propias transacciones. Se confirman todos los lotes copiados hasta el punto del error; el lote que contiene la clave duplicada se revierte y la operación de copia masiva se detiene antes de procesar el resto de los lotes.  
  
> [!IMPORTANT]
> Este ejemplo no se ejecutará a menos que haya creado las tablas de trabajo como se describe en el ejemplo de configuración de la [copia masiva](bulk-copy-example-setup.md). Este código se proporciona para mostrar la sintaxis para usar **SqlBulkCopy**. Si las tablas de origen y destino se encuentran en la misma instancia de SQL Server, es más fácil y rápido usar una instrucción `INSERT … SELECT` de Transact-SQL para copiar los datos.  
  
 [!code-csharp[DataWorks SqlBulkCopy.InternalTransaction#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.InternalTransaction/CS/source.cs#1)]
 [!code-vb[DataWorks SqlBulkCopy.InternalTransaction#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.InternalTransaction/VB/source.vb#1)]  
  
## <a name="using-existing-transactions"></a>Uso de transacciones existentes  

 Puede especificar un objeto <xref:System.Data.SqlClient.SqlTransaction> existente como un parámetro en un constructor de <xref:System.Data.SqlClient.SqlBulkCopy>. En esta situación, la operación de copia masiva se realiza en una transacción existente y el estado de la transacción no sufre ningún cambio (es decir, no se confirma ni se anula). Esto permite que una aplicación incluya la operación de copia masiva en una transacción con otras operaciones de base de datos. Sin embargo, si no se especifica un objeto <xref:System.Data.SqlClient.SqlTransaction> y se pasa una referencia nula, y la conexión tiene una transacción activa, se produce una excepción.  
  
 Si se produce un error y necesita revertir toda la operación de copia masiva, o si la copia masiva debe ejecutarse como parte de un proceso más grande que se pueda revertir, puede proporcionar un objeto <xref:System.Data.SqlClient.SqlTransaction> al constructor de <xref:System.Data.SqlClient.SqlBulkCopy>.  
  
 La siguiente aplicación de consola es similar al primer ejemplo (sin transacciones), con una excepción: en este ejemplo, la operación de copia masiva se incluye en una transacción externa más grande. Cuando se produce la infracción de la clave principal, toda la transacción se revierte y no se agrega ninguna fila a la tabla de destino.  
  
> [!IMPORTANT]
> Este ejemplo no se ejecutará a menos que haya creado las tablas de trabajo como se describe en el ejemplo de configuración de la [copia masiva](bulk-copy-example-setup.md). Este código se proporciona para mostrar la sintaxis para usar **SqlBulkCopy**. Si las tablas de origen y destino se encuentran en la misma instancia de SQL Server, es más fácil y rápido usar una instrucción `INSERT … SELECT` de Transact-SQL para copiar los datos.  
  
 [!code-csharp[DataWorks SqlBulkCopy.SqlTransaction#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.SqlTransaction/CS/source.cs#1)]
 [!code-vb[DataWorks SqlBulkCopy.SqlTransaction#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.SqlTransaction/VB/source.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [Operaciones de copia masiva en SQL Server](bulk-copy-operations-in-sql-server.md)
- [Información general de ADO.NET](../ado-net-overview.md)
