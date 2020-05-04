---
title: Parámetros
ms.date: 12/13/2019
description: Obtenga información sobre cómo usar los parámetros SQL.
ms.openlocfilehash: 1d2f818ad392a919faedd785394de28a9c6f56c3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401206"
---
# <a name="parameters"></a>Parámetros

Los parámetros se usan como protección contra ataques por inyección de código SQL. En lugar de concatenar la entrada proporcionada por el usuario con instrucciones SQL, use los parámetros para asegurarse de que la entrada solo se trate como un valor literal y no se ejecute nunca. En SQLite, los parámetros se permiten normalmente en cualquier lugar en el que se permita un literal en las instrucciones SQL.

Los parámetros pueden tener como prefijo `:`, `@` o `$`.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_Parameter)]

Vea [Tipos de datos](types.md) para obtener más información sobre cómo se asignan los valores de .NET a los de SQLite.

## <a name="truncation"></a>Truncamiento

Use la propiedad <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> para truncar los valores TEXT y BLOB.

```csharp
// Truncate name to 30 characters
command.Parameters.AddWithValue("$name", name).Length = 30;
```

## <a name="alternative-types"></a>Tipos alternativos

En ocasiones, es posible que quiera usar un tipo de SQLite alternativo. Puede hacerlo si establece la propiedad <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType>.

Se pueden usar las siguientes asignaciones de tipos alternativos. Para las asignaciones predeterminadas, vea [Tipos de datos](types.md).

| Valor          | SqliteType | Comentarios          |
| -------------- | ---------- | ---------------- |
| Char           | Integer    | UTF-16           |
| DateTime       | Real       | Valor de día juliano |
| DateTimeOffset | Real       | Valor de día juliano |
| GUID           | Blob       |                  |
| TimeSpan       | Real       | En días          |

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_SqliteType)]

## <a name="output-parameters"></a>Parámetros de salida

SQLite no admite parámetros de salida. En su lugar, devuelve los valores de los resultados de la consulta.

## <a name="see-also"></a>Vea también

* [Tipos de datos](types.md)
