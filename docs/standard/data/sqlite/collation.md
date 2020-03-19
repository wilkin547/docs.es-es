---
title: Intercalación
ms.date: 12/13/2019
description: Aprenda a crear una secuencia de intercalación personalizada.
ms.openlocfilehash: b93c82a4ace154b8293b05effa8f9e9294fa7708
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "79506546"
---
# <a name="collation"></a>Intercalación

SQLite utiliza secuencias de intercalación al comparar valores DE TEXTO para determinar el orden y la igualdad. Puede especificar qué intercalación se va a utilizar al crear columnas o por operación en consultas SQL. SQLite incluye tres secuencias de intercalación de forma predeterminada.

| Intercalación | Descripción                               |
| --------- | ----------------------------------------- |
| RTRIM     | Ignora el espacio en blanco final               |
| NOCASE    | Sin distinción entre mayúsculas y minúsculas para caracteres ASCII A-Z |
| BINARY    | Sensible a mayúsculas y minúsculas. Compara bytes directamente   |

## <a name="custom-collation"></a>Intercalación personalizada

También puede definir sus propias secuencias de intercalación o <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>invalidar las integradas mediante . En el ejemplo siguiente se muestra cómo reemplazar la intercalación NOCASE para admitir caracteres Unicode. El [código de ejemplo completo](https://github.com/dotnet/samples/blob/master/snippets/standard/data/sqlite/CollationSample/Program.cs) está disponible en GitHub.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/CollationSample/Program.cs?name=snippet_Collation)]

## <a name="like-operator"></a>Like (operador)

El operador LIKE de SQLite no respeta las intercalaciones. La implementación predeterminada tiene la misma semántica que la intercalación NOCASE. Solo distingue mayúsculas de minúsculas para los caracteres ASCII de la A a la Z.

Puede hacer que el operador LIKE distinta entre mayúsculas y minúsculas mediante la siguiente instrucción pragma:

```sql
PRAGMA case_sensitive_like = 1
```

Consulte [Funciones definidas por el usuario](user-defined-functions.md) para obtener más información sobre cómo reemplazar la implementación del operador LIKE.

## <a name="see-also"></a>Consulte también

* [Funciones definidas por el usuario](user-defined-functions.md)
* [Sintaxis SQL](https://www.sqlite.org/lang.html)
