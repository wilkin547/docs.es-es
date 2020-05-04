---
title: Limitaciones de Dapper
ms.date: 12/13/2019
description: Se describen algunas de las limitaciones que encontrará al usar Dapper.
ms.openlocfilehash: 396507f25f591a9ab5c3bb07c0af6fd8d175e4ea
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901207"
---
# <a name="dapper-limitations"></a>Limitaciones de Dapper

Hay algunas limitaciones que debe tener en cuenta al usar Microsoft.Data.SQLite con [Dapper](https://stackexchange.github.io/Dapper/).

## <a name="parameters"></a>Parámetros

Los nombres de parámetros de SQLite distinguen mayúsculas de minúsculas. Asegúrese de que los nombres de parámetro utilizados en SQL coinciden con las propiedades del objeto anónimo. La incidencia [#18861](https://github.com/dotnet/efcore/issues/18861) mejorará esta experiencia.

Dapper también espera que los parámetros usen el prefijo `@`. Otros prefijos no funcionarán.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_Parameter)]

## <a name="data-types"></a>Tipos de datos

Dapper lee los valores mediante el indizador SqliteDataReader. El tipo de valor devuelto de este indexador es Object, lo que significa que solo devolverá valores Long, Double, String o Byte[]. Para obtener más información, vea [Tipos de datos](types.md). Dapper controla la mayoría de las conversiones entre estos y otros tipos primitivos. Desafortunadamente, no controla `DateTimeOffset`, `Guid` o `TimeSpan`. Cree controladores de tipos si quiere usar estos tipos en los resultados.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_TypeHandlers)]

No olvide agregar los controladores de tipo antes de realizar la consulta.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_AddTypeHandlers)]

## <a name="see-also"></a>Vea también

* [Tipos de datos](types.md)
* [Limitaciones de Async](async.md)
