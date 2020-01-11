---
title: Limitaciones de ADO.NET
ms.date: 12/13/2019
description: Describe algunas de las limitaciones de ADO.NET que puede encontrar.
ms.openlocfilehash: 8664b73071fc859ed30080f549b05e7d6ed020f4
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901259"
---
# <a name="adonet-limitations"></a>Limitaciones de ADO.NET

Microsoft. Data. SQLite proporciona implementaciones de muchas de las abstracciones de ADO.NET, pero hay algunas limitaciones.

## <a name="database-schema-information"></a>Información de esquema de base de datos

Los metadatos acerca de los resultados de la consulta están disponibles mediante el método <xref:Microsoft.Data.Sqlite.SqliteDataReader.GetSchemaTable%2A>.

`DbConnection.GetSchema()` no está implementado. Esta API no está bien definida, por lo que se recomienda recuperar los metadatos de la base de datos directamente mediante las API de SQLite estándar, como la tabla [sqlite_master](https://www.sqlite.org/fileformat.html#storage_of_the_sql_database_schema) y la pragma [table_info](https://www.sqlite.org/pragma.html#pragma_table_info) .

Para obtener más información, vea [metadatos](metadata.md).

## <a name="systemtransactions"></a>System.Transactions

Microsoft. Data. SQLite todavía no admite System. Transactions. En su lugar, use las transacciones ADO.NET. Para obtener más información, vea [transacciones](transactions.md).

Proporcione comentarios sobre la falta de compatibilidad con System. Transactions en el [#13825](https://github.com/dotnet/efcore/issues/13825)de problemas.

## <a name="data-adapters"></a>Adaptadores de datos

Microsoft. Data. SQLite todavía no ha implementado `DbDataAdapter`. Esto significa que solo puede usar `DataSet` ADO.NET y `DataTable` para cargar datos y no actualizarlos.

Use el [#13838](https://github.com/dotnet/efcore/issues/13838) de problemas para proporcionar comentarios sobre la implementación de `DbDataAdapter`.

## <a name="output-parameters"></a>Parámetros de salida

SQLite no admite parámetros de salida.

## <a name="positional-parameters"></a>Parámetros posicionales

Microsoft. Data. SQLite solo admite [parámetros](parameters.md)con nombre. No se admiten los parámetros posicionales.

## <a name="stored-procedures"></a>Procedimientos almacenados

SQLite no admite procedimientos almacenados.

## <a name="isolation-levels"></a>Niveles de aislamiento

Los niveles de aislamiento `Chaos` y `Snapshot` no se admiten en las transacciones de SQLite.

## <a name="see-also"></a>Vea también

* [Limitaciones de Async](async.md)
* [Tipos de datos](types.md)
* [Transacciones](transactions.md)
