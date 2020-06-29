---
title: Parámetros
ms.date: 12/13/2019
description: Obtenga información sobre cómo usar los parámetros SQL.
ms.openlocfilehash: b24610a5cb65e2b24171452acef9bf55b4995431
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768955"
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
command.Parameters.AddWithValue("$name", name).Size = 30;
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
