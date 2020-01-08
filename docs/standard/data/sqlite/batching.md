---
title: Procesamiento por lotes
ms.date: 12/13/2019
description: Obtenga información sobre cómo ejecutar un lote de instrucciones SQL en un solo comando.
ms.openlocfilehash: 0799784471520bb279db6a4b5879ad30945bdebb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450313"
---
# <a name="batching"></a>Procesamiento por lotes

SQLite no admite de forma nativa instrucciones SQL por lotes juntas en un solo comando. Sin embargo, dado que no hay ninguna red implicada, no sería realmente útil el rendimiento. Sin embargo, Microsoft. Data. SQLite no implementa el procesamiento por lotes de instrucciones para que se comporte de forma más similar a otros proveedores de ADO.NET.

Al llamar a <xref:System.Data.Common.DbCommand.ExecuteReader%2A?displayProperty=nameWithType>, las instrucciones se ejecutan hasta la primera que devuelve los resultados. La llamada a <xref:System.Data.Common.DbDataReader.NextResult%2A?displayProperty=nameWithType> continúa ejecutando instrucciones hasta el siguiente que devuelve los resultados o hasta que llega al final del lote. La llamada a <xref:System.Data.Common.DbDataReader.Dispose%2A?displayProperty=nameWithType> o <xref:System.Data.Common.DbDataReader.Close%2A> ejecuta cualquier instrucción restante que no haya consumido `NextResult()`. Si no desecha un lector de datos, el finalizador intenta ejecutar las instrucciones restantes, pero se omiten los errores que encuentre. Por este motivo, es importante desechar `DbDataReader` objetos al usar lotes.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BatchingSample/Program.cs?name=snippet_Batching)]

## <a name="see-also"></a>Vea también

* [Bulk Insert](bulk-insert.md)
