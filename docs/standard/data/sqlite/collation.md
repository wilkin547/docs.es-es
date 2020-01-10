---
title: Collation
ms.date: 12/13/2019
description: Obtenga información sobre cómo crear una secuencia de intercalación personalizada.
ms.openlocfilehash: 9cc574a75c8f5347dd9bb44e36af72e50afa57b4
ms.sourcegitcommit: cbdc0f4fd39172b5191a35200c33d5030774463c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "75777384"
---
# <a name="collation"></a>Collation

SQLite usa las secuencias de intercalación cuando se comparan valores de texto para determinar el orden y la igualdad. Puede especificar la intercalación que se va a usar al crear columnas o por operación en consultas SQL. SQLite incluye tres secuencias de intercalación de forma predeterminada.

| Collation | Descripción                               |
| --------- | ----------------------------------------- |
| RTRIM     | Omite el espacio en blanco final               |
| Nocase    | No distingue entre mayúsculas y minúsculas para los caracteres ASCII A-Z |
| BINARY    | Distingue mayúsculas de minúsculas. Compara los bytes directamente   |

## <a name="custom-collation"></a>Intercalación personalizada

También puede definir sus propias secuencias de intercalación o invalidar las creadas mediante <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>. En el ejemplo siguiente se muestra cómo invalidar la intercalación nocase para admitir caracteres Unicode. El [código de ejemplo completo](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/CollationSample/Program.cs) está disponible en github.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/CollationSample/Program.cs?name=snippet_Collation)]

## <a name="like-operator"></a>Like (operador)

El operador LIKE de SQLite no respeta las intercalaciones. La implementación predeterminada tiene la misma semántica que la intercalación nocase. No distingue entre mayúsculas y minúsculas para los caracteres ASCII de la a a la Z.

Puede hacer que el operador LIKE distinga entre mayúsculas y minúsculas con la siguiente instrucción pragma:

```sql
PRAGMA case_sensitive_like = 0
```

Vea [funciones definidas por el usuario](user-defined-functions.md) para obtener más información sobre cómo invalidar la implementación del operador like.

## <a name="see-also"></a>Vea también

* [Funciones definidas por el usuario](user-defined-functions.md)
* [Sintaxis de SQL](https://www.sqlite.org/lang.html)
