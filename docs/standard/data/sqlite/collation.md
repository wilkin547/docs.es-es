---
title: Collation
ms.date: 12/13/2019
description: Obtenga información sobre cómo crear una secuencia de intercalación personalizada.
ms.openlocfilehash: 9879846cc191a62c4cb47a0fbaa47c59153ba61c
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242977"
---
# <a name="collation"></a>Collation

SQLite usa las secuencias de intercalación al comparar valores de texto para determinar el orden y la igualdad. Puede especificar la intercalación que se va a usar al crear columnas o por operación en consultas SQL. SQLite incluye tres secuencias de intercalación de forma predeterminada.

| Collation | Descripción                               |
| --------- | ----------------------------------------- |
| RTRIM     | Ignora los espacios en blanco finales               |
| NOCASE    | No distingue mayúsculas de minúsculas para los caracteres ASCII A-Z |
| BINARY    | Distingue mayúsculas de minúsculas. Compara los bytes directamente   |

## <a name="custom-collation"></a>Intercalación personalizada

También puede definir secuencias de intercalación propias o invalidar las creadas mediante <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>. En el ejemplo siguiente se muestra cómo invalidar la intercalación NOCASE para admitir caracteres Unicode. El [ejemplo de código completo](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/CollationSample/Program.cs) está disponible en GitHub.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/CollationSample/Program.cs?name=snippet_Collation)]

## <a name="like-operator"></a>Like (operador)

El operador LIKE de SQLite no respeta las intercalaciones. La implementación predeterminada tiene la misma semántica que la intercalación NOCASE. No distingue mayúsculas de minúsculas para los caracteres ASCII de la A a la Z.

Puede hacer que el operador LIKE distinga mayúsculas de minúsculas con la siguiente instrucción pragma:

```sql
PRAGMA case_sensitive_like = 1
```

Vea [Funciones definidas por el usuario](user-defined-functions.md) para obtener más información sobre cómo invalidar la implementación del operador LIKE.

## <a name="see-also"></a>Vea también

* [Funciones definidas por el usuario](user-defined-functions.md)
* [Sintaxis de SQL](https://www.sqlite.org/lang.html)
