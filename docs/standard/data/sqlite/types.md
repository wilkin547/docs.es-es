---
title: Tipos de datos
ms.date: 12/13/2019
description: Describe los tipos de datos admitidos y algunas de las limitaciones de los mismos.
ms.openlocfilehash: ae70cb91a5a6d9cfed45a5a47dda25a70362871e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450421"
---
# <a name="data-types"></a>Tipos de datos

SQLite solo tiene cuatro tipos de datos primitivos: integer, REAL, TEXT y BLOB. Las API que devuelven valores de base de datos como un `object` solo devolverán uno de estos cuatro tipos. Microsoft. Data. SQLite admite tipos de .NET adicionales, pero los valores se convierten en última instancia entre estos tipos y uno de los cuatro tipos primitivos.

| .NET           | SQLite  | Notas                                                       |
| -------------- | ------- | ------------------------------------------------------------- |
| Booleano        | INTEGER | `0` o `1`                                                    |
| Byte           | INTEGER |                                                               |
| Byte[]         | BLOB    |                                                               |
| Char           | TEXT    | UTF-8                                                         |
| DateTime       | TEXT    | AAAA-MM-DD HH: mm: SS. FFFFFFF                                   |
| DateTimeOffset | TEXT    | AAAA-MM-DD HH: mm: SS. FFFFFFFzzz                                |
| Decimal        | TEXT    | formato de `0.0###########################`. REAL sería una pérdida. |
| Doble         | REAL    |                                                               |
| GUID           | TEXT    | 00000000-0000-0000-0000-000000000000                          |
| Int16          | INTEGER |                                                               |
| Int32          | INTEGER |                                                               |
| Int64          | INTEGER |                                                               |
| SByte          | INTEGER |                                                               |
| único         | REAL    |                                                               |
| Cadena         | TEXT    | UTF-8                                                         |
| TimeSpan       | TEXT    | d. HH: mm: SS. FFFFFFF                                            |
| UInt16         | INTEGER |                                                               |
| UInt64         | INTEGER | Desbordamiento de valores grandes                                         |

## <a name="alternative-types"></a>Tipos alternativos

Algunos tipos .NET se pueden leer desde tipos de SQLite alternativos. Los parámetros también se pueden configurar para usar estos tipos alternativos. Para obtener más información, vea [Parámetros](parameters.md#alternative-types).

| .NET           | SQLite  | Notas          |
| -------------- | ------- | ---------------- |
| Char           | INTEGER | UTF-16           |
| DateTime       | REAL    | Valor de día juliano |
| DateTimeOffset | REAL    | Valor de día juliano |
| GUID           | BLOB    |                  |
| TimeSpan       | REAL    | En días          |

Por ejemplo, la siguiente consulta Lee un valor TimeSpan de una columna REAL del conjunto de resultados.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DateAndTimeSample/Program.cs?name=snippet_AlternativeType)]

## <a name="column-types"></a>Tipos de columna

SQLite usa un sistema de tipos dinámico en el que el tipo de un valor está asociado al propio valor y no a la columna en la que se almacena. Puede usar cualquier nombre de tipo de columna que desee. Microsoft. Data. SQLite no aplicará ninguna semántica adicional a estos nombres.

El nombre del tipo de columna tiene un impacto en la [afinidad de tipo](https://www.sqlite.org/datatype3.html#type_affinity). Un problema común es que el uso de un tipo de columna STRING intentará convertir valores en integer o REAL, lo que puede dar lugar a resultados inesperados. Se recomienda usar solo los cuatro nombres de tipo de SQLite primitivos: integer, REAL, TEXT y BLOB.

SQLite le permite especificar aspectos como la longitud, la precisión y la escala, pero el motor de base de datos no los exige. La aplicación es responsable de aplicarlos.

## <a name="see-also"></a>Vea también

- [Tipos de texto en SQLite](https://www.sqlite.org/datatype3.html)
