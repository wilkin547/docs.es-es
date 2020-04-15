---
title: Tipos de datos
ms.date: 12/13/2019
description: Describe los tipos de datos admitidos y algunas de las limitaciones que los rodean.
ms.openlocfilehash: a11ff382f80cd979506d6195c299c8234c3eb8ea
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389039"
---
# <a name="data-types"></a>Tipos de datos

SQLite solo tiene cuatro tipos de datos primitivos: INTEGER, REAL, TEXT y BLOB. Las API que devuelven `object` valores de base de datos como un solo devolverán uno de estos cuatro tipos. Microsoft.Data.Sqlite admite tipos .NET adicionales, pero los valores se coaccionan en última instancia entre estos tipos y uno de los cuatro tipos primitivos.

| .NET           | SQLite  | Observaciones                                                       |
| -------------- | ------- | ------------------------------------------------------------- |
| Boolean        | INTEGER | `0` o `1`                                                    |
| Byte           | INTEGER |                                                               |
| Byte[]         | BLOB    |                                                               |
| Char           | TEXT    | UTF-8                                                         |
| DateTime       | TEXT    | aaaa-MM-dd HH:mm:ss. FFFFFFF                                   |
| DateTimeOffset | TEXT    | aaaa-MM-dd HH:mm:ss. FFFFFFFzzz                                |
| Decimal        | TEXT    | `0.0###########################`Formato. REAL sería pérdida. |
| Double         | real    |                                                               |
| Guid           | TEXT    | 00000000-0000-0000-0000-000000000000                          |
| Int16          | INTEGER |                                                               |
| Int32          | INTEGER |                                                               |
| Int64          | INTEGER |                                                               |
| SByte          | INTEGER |                                                               |
| Single         | real    |                                                               |
| String         | TEXT    | UTF-8                                                         |
| TimeSpan       | TEXT    | d.hh:mm:ss.fffffff                                            |
| UInt16         | INTEGER |                                                               |
| UInt32         | INTEGER |                                                               |
| UInt64         | INTEGER | Desbordamiento de valores grandes                                         |

## <a name="alternative-types"></a>Tipos alternativos

Algunos tipos de .NET se pueden leer de tipos SQLite alternativos. Los parámetros también se pueden configurar para utilizar estos tipos alternativos. Para obtener más información, vea [Parámetros](parameters.md#alternative-types).

| .NET           | SQLite  | Observaciones          |
| -------------- | ------- | ---------------- |
| Char           | INTEGER | UTF-16           |
| DateTime       | real    | Valor del día juliano |
| DateTimeOffset | real    | Valor del día juliano |
| Guid           | BLOB    |                  |
| TimeSpan       | real    | En días          |

Por ejemplo, la siguiente consulta lee un valor TimeSpan de una columna REAL del conjunto de resultados.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_AlternativeType)]

## <a name="column-types"></a>Tipos de columna

SQLite utiliza un sistema de tipos dinámicos donde el tipo de un valor está asociado con el propio valor y no con la columna donde se almacena. Puedes usar cualquier nombre de tipo de columna que quieras. Microsoft.Data.Sqlite no aplicará ninguna semántica adicional a estos nombres.

El nombre de tipo de columna tiene un impacto en la afinidad de [tipo](https://www.sqlite.org/datatype3.html#type_affinity). Un gotcha común es que el uso de un tipo de columna de STRING intentará convertir valores a INTEGER o REAL, lo que puede dar lugar a resultados inesperados. Se recomienda utilizar solo los cuatro nombres de tipo SQLite primitivos: INTEGER, REAL, TEXT y BLOB.

SQLite le permite especificar facetas de tipo como longitud, precisión y escala, pero el motor de base de datos no las aplica. La aplicación es responsable de aplicarlas.

## <a name="see-also"></a>Consulte también

- [Tipos de datos en SQLite](https://www.sqlite.org/datatype3.html)
