---
title: Procesamiento por lotes
ms.date: 12/13/2019
description: Obtenga información sobre cómo ejecutar un lote de instrucciones SQL en un mismo comando.
ms.openlocfilehash: 0799784471520bb279db6a4b5879ad30945bdebb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450313"
---
# <a name="batching"></a>Procesamiento por lotes

SQLite no admite de forma nativa la ejecución de instrucciones SQL por lotes en un mismo comando, pero, al no haber ninguna red implicada, hacerlo no supondría una mejora del rendimiento de todas formas. Con todo, Microsoft.Data.Sqlite sí que implementa el procesamiento de instrucciones por lotes para hacer que se comporte de forma más parecida a otros proveedores de ADO.NET.

Al llamar a <xref:System.Data.Common.DbCommand.ExecuteReader%2A?displayProperty=nameWithType>, las instrucciones se van ejecutando hasta la primera que devuelva resultados. La llamada a <xref:System.Data.Common.DbDataReader.NextResult%2A?displayProperty=nameWithType> sigue ejecutando instrucciones hasta llegar a la siguiente que devuelva resultados o hasta alcanzar el final del lote. Cuando se llama a <xref:System.Data.Common.DbDataReader.Dispose%2A?displayProperty=nameWithType> o <xref:System.Data.Common.DbDataReader.Close%2A>, se ejecuta cualquier instrucción restante que `NextResult()` no haya usado. Si no se dispone de un lector de datos, el finalizador intenta ejecutar las instrucciones restantes, pero los errores que encuentre se omitirán, de ahí que sea importante disponer de objetos `DbDataReader` al usar lotes.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BatchingSample/Program.cs?name=snippet_Batching)]

## <a name="see-also"></a>Vea también

* [Inserción masiva](bulk-insert.md)
