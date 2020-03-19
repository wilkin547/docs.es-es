---
title: Parámetros
ms.date: 12/13/2019
description: Aprenda a usar parámetros SQL.
ms.openlocfilehash: 1d2f818ad392a919faedd785394de28a9c6f56c3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401206"
---
# <a name="parameters"></a>Parámetros

Los parámetros se utilizan para proteger contra ataques de inyección SQL. En lugar de concatenar la entrada del usuario con instrucciones SQL, utilice parámetros para asegurarse de que la entrada solo se trata como un valor literal y nunca se ejecuta. En SQLite, los parámetros normalmente se permiten en cualquier lugar donde se permite un literal en instrucciones SQL.

Los parámetros se `:`pueden `@`prefijar con , , o `$`.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/HelloWorldSample/Program.cs?name=snippet_Parameter)]

Consulte [Tipos](types.md) de datos para obtener más información sobre cómo se asignan los valores de .NET a los valores de SQLite.

## <a name="truncation"></a>Truncamiento

Utilice <xref:Microsoft.Data.Sqlite.SqliteParameter.Size> la propiedad para truncar los valores TEXT y BLOB.

```csharp
// Truncate name to 30 characters
command.Parameters.AddWithValue("$name", name).Length = 30;
```

## <a name="alternative-types"></a>Tipos alternativos

A veces, es posible que desee utilizar un tipo SQLite alternativo. Para ello, <xref:Microsoft.Data.Sqlite.SqliteParameter.SqliteType> establezca la propiedad.

Se pueden utilizar las siguientes asignaciones de tipos alternativos. Para ver las asignaciones predeterminadas, consulte [Tipos de datos](types.md).

| Value          | SqliteType | Observaciones          |
| -------------- | ---------- | ---------------- |
| Char           | Entero    | UTF-16           |
| DateTime       | Real       | Valor del día juliano |
| DateTimeOffset | Real       | Valor del día juliano |
| Guid           | Blob       |                  |
| TimeSpan       | Real       | En días          |

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_SqliteType)]

## <a name="output-parameters"></a>Parámetros de salida

SQLite no admite parámetros de salida. En su lugar, devuelve valores en los resultados de la consulta.

## <a name="see-also"></a>Consulte también

* [Tipos de datos](types.md)
