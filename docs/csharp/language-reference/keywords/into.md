---
title: 'into: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- into_CSharpKeyword
- into
helpviewer_keywords:
- into keyword [C#]
ms.assetid: 81ec62c1-f0b1-4755-8a31-959876e77f65
ms.openlocfilehash: f0f5ff1e56a65e83385f814df2fadd957f53561e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713626"
---
# <a name="into-c-reference"></a>into (Referencia de C#)

La palabra clave contextual `into` puede usarse para crear un identificador temporal para almacenar los resultados de una cláusula [group](group-clause.md), [join](join-clause.md) o [select](select-clause.md) en un nuevo identificador. Este identificador puede ser un generador de comandos de consulta adicionales. Cuando se usa en una cláusula `group` o `select`, el uso del nuevo identificador se denomina a veces una *continuación*.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente, se muestra el uso de la palabra clave `into` para habilitar un identificador temporal `fruitGroup` que tiene un tipo deducido de `IGrouping`. Mediante el identificador, puede invocar el método <xref:System.Linq.Enumerable.Count%2A> en cada grupo y seleccionar solo los grupos que contienen dos o más palabras.

[!code-csharp[cscsrefQueryKeywords#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Into.cs#18)]

El uso de `into` en una cláusula `group` solo es necesario cuando quiere realizar operaciones de consulta adicionales en cada grupo. Para obtener más información, vea [group (Cláusula)](group-clause.md).

Para obtener un ejemplo del uso de `into` en una cláusula `join`, vea [join (Cláusula)](join-clause.md).

## <a name="see-also"></a>Vea también

- [Palabras clave para consultas (LINQ)](query-keywords.md)
- [LINQ en C#](../../linq/index.md)
- [group (cláusula)](group-clause.md)
