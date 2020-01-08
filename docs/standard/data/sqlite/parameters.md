---
title: Parameters
ms.date: 12/13/2019
description: Obtenga información sobre cómo usar los parámetros SQL.
ms.openlocfilehash: 1d2f818ad392a919faedd785394de28a9c6f56c3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450427"
---
# <a name="parameters"></a>Parameters

Los parámetros se usan para protegerse frente a ataques de inyección de SQL. En lugar de concatenar los datos proporcionados por el usuario con instrucciones SQL, use los parámetros para asegurarse de que la entrada solo se trate como un valor literal y no se ejecute nunca. En SQLite, los parámetros se permiten normalmente en cualquier lugar en el que se permita un literal en las instrucciones SQL.

Los parámetros pueden tener como prefijo `:`, `@`o `$`.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_Parameter)]

Vea [tipos de datos](types.md) para obtener más información sobre cómo se asignan los valores de .net a los valores de SQLite.

## <a name="truncation"></a>Truncamiento

Use la propiedad <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> para truncar los valores de texto y BLOB.

```csharp
// Truncate name to 30 characters
command.Parameters.AddWithValue("$name", name).Length = 30;
```

## <a name="alternative-types"></a>Tipos alternativos

En ocasiones, es posible que desee usar un tipo de SQLite alternativo. Para ello, establezca la propiedad <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType>.

Se pueden usar las siguientes asignaciones de tipos alternativos. Para las asignaciones predeterminadas, vea [tipos de datos](types.md).

| {2&gt;Value&lt;2}          | SqliteType | Notas          |
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
