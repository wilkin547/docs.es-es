---
title: let (Cláusula, Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- let_CSharpKeyword
- let
helpviewer_keywords:
- let keyword [C#]
- let clause [C#]
ms.assetid: 13c9c1a4-ce57-48ef-8e1b-4c2a59b99fb4
ms.openlocfilehash: 62294df7f0f2ebb3249dffd72ba4910fbae984c8
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45597437"
---
# <a name="let-clause-c-reference"></a>let (Cláusula, Referencia de C#)

En una expresión de consulta, a veces resulta útil almacenar el resultado de una subexpresión para usarlo en las cláusulas siguientes. Puede hacer esto con la palabra clave `let`, que crea una variable de rango y la inicializa con el resultado de la expresión que proporcione. Una vez inicializada con un valor, la variable de rango no se puede usar para almacenar otro valor. En cambio, si la variable de rango contiene un tipo consultable, se puede consultar.

## <a name="example"></a>Ejemplo

En el siguiente ejemplo, se usa `let` de dos maneras:

1. Para crear un tipo enumerable que se puede consultar.

2. Para habilitar la consulta para que llame a `ToLower` solo una vez en la variable de rango `word`. Sin usar `let`, tendría que llamar a `ToLower` en cada predicado de la cláusula `where`.

[!code-csharp[cscsrefQueryKeywords#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Let.cs#28)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../../language-reference/index.md)
- [Palabras clave para consultas (LINQ)](query-keywords.md)
- [Language-Integrated Query (LINQ)](../../linq/index.md)
- [Introducción a LINQ en C#](../../programming-guide/concepts/linq/getting-started-with-linq.md)
- [Controlar excepciones en expresiones de consulta](../../linq/handle-exceptions-in-query-expressions.md)