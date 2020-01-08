---
title: Limitaciones de Dapper
ms.date: 12/13/2019
description: Describe algunas de las limitaciones que encontrará al usar Dapper.
ms.openlocfilehash: 90c7fb24f068d663081390bdba9b1b222b4be56e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450499"
---
# <a name="dapper-limitations"></a>Limitaciones de Dapper

Hay algunas limitaciones que debe tener en cuenta al usar Microsoft. Data. SQLite con [Dapper](https://stackexchange.github.io/Dapper/).

## <a name="parameters"></a>Parameters

Los nombres de los parámetros de SQLite distinguen mayúsculas de minúsculas. Asegúrese de que los nombres de parámetro utilizados en SQL coinciden con las propiedades del objeto anónimo. Problema [#18861](https://github.com/aspnet/EntityFrameworkCore/issues/18861) mejoraría esta experiencia.

Dapper también espera parámetros para usar el prefijo `@`. Otros prefijos no funcionarán.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_Parameter)]

## <a name="data-types"></a>Tipos de datos

Dapper Lee los valores mediante el indizador SqliteDataReader. El tipo de valor devuelto de este indexador es Object, lo que significa que solo devolverá los valores Long, Double, String o Byte []. Para obtener más información, vea [tipos de datos](types.md). Dapper controla la mayoría de las conversiones entre estos y otros tipos primitivos. Desafortunadamente, no controla `DateTimeOffset`, `Guid`o `TimeSpan`. Cree controladores de tipos si desea utilizar estos tipos en los resultados.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_TypeHandlers)]

No olvide agregar los controladores de tipo antes de realizar la consulta.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_AddTypeHandlers)]

## <a name="see-also"></a>Vea también

* [Tipos de datos](types.md)
* [Limitaciones de Async](async.md)
