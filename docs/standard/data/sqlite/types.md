---
title: Tipos de datos
ms.date: 12/13/2019
description: Se describen los tipos de datos admitidos y algunas de sus limitaciones.
ms.openlocfilehash: a11ff382f80cd979506d6195c299c8234c3eb8ea
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389039"
---
# <a name="data-types"></a>Tipos de datos

SQLite solo tiene cuatro tipos de datos primitivos: INTEGER, REAL, TEXT y BLOB. Las API que devuelven valores de base de datos como `object` solo devolverán uno de estos cuatro tipos. Microsoft.Data.SQLite admite tipos de .NET adicionales, pero los valores se convierten en última instancia entre estos tipos y uno de los cuatro tipos primitivos.

| .NET           | SQLite  | Comentarios                                                       |
| -------------- | ------- | ------------------------------------------------------------- |
| Booleano        | INTEGER | `0` o `1`                                                    |
| Byte           | INTEGER |                                                               |
| Byte[]         | BLOB    |                                                               |
| Char           | TEXT    | UTF-8                                                         |
| DateTime       | TEXT    | aaaa-MM-dd HH:mm:ss.FFFFFFF                                   |
| DateTimeOffset | TEXT    | aaaa-MM-dd HH:mm:ss.FFFFFFFzzz                                |
| Decimal        | TEXT    | Formato `0.0###########################`. REAL tendría pérdidas. |
| Doble         | real    |                                                               |
| GUID           | TEXT    | 00000000-0000-0000-0000-000000000000                          |
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

Algunos tipos de .NET se pueden leer desde tipos de SQLite alternativos. Los parámetros también se pueden configurar para usar estos tipos alternativos. Para obtener más información, vea [Parámetros](parameters.md#alternative-types).

| .NET           | SQLite  | Comentarios          |
| -------------- | ------- | ---------------- |
| Char           | INTEGER | UTF-16           |
| DateTime       | real    | Valor de día juliano |
| DateTimeOffset | real    | Valor de día juliano |
| GUID           | BLOB    |                  |
| TimeSpan       | real    | En días          |

Por ejemplo, en la consulta siguiente se lee un valor TimeSpan de una columna REAL del conjunto de resultados.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_AlternativeType)]

## <a name="column-types"></a>Tipos de columna

SQLite usa un sistema de tipos dinámicos en el que el tipo de un valor está asociado al propio valor y no a la columna en la que se almacena. Puede usar cualquier nombre de tipo de columna que quiera. Microsoft.Data.SQLite no aplicará ninguna semántica adicional a estos nombres.

El nombre del tipo de columna afecta a la [afinidad de tipos](https://www.sqlite.org/datatype3.html#type_affinity). Un problema común es que el uso de un tipo de columna STRING intentará convertir valores en INTEGER o REAL, lo que puede dar lugar a resultados inesperados. Se recomienda usar solo los cuatro nombres de tipo de SQLite primitivos: INTEGER, REAL, TEXT y BLOB.

SQLite permite especificar facetas como la longitud, la precisión y la escala, pero el motor de base de datos no las exige. La aplicación es responsable de aplicarlas.

## <a name="see-also"></a>Vea también

- [Tipos de datos In SQLite](https://www.sqlite.org/datatype3.html)
