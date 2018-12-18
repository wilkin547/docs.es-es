---
title: 'Operador %=: Referencia de C#'
ms.custom: seodec18
ms.date: 09/04/2018
f1_keywords:
- '%=_CSharpKeyword'
helpviewer_keywords:
- remainder assignment operator (%=) [C#]
- '%= assignment operator (remainder assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
ms.openlocfilehash: d0732f9578b64c894ecc1d3bb15cee11a8d5b6a3
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245566"
---
# <a name="-operator-c-reference"></a>%= (operador) (Referencia de C#)

El operador de asignación y resto.

Una expresión que usa el operador `%=`, como  

```csharp
x %= y
```  

es equivalente a  

```csharp
x = x % y
```  

salvo que `x` solo se evalúa una vez.
  
El [operador de resto](remainder-operator.md) `%` calcula el resto después de la división de sus operandos. Es compatible con todos los tipos numéricos.

Si un tipo definido por el usuario [sobrecarga](../keywords/operator.md) el [operador de resto](remainder-operator.md) `%`, el operador de asignación de resto `%=` se sobrecarga implícitamente.
  
En el siguiente ejemplo se muestra el uso del operador `%=`:

[!code-csharp-interactive[%= example](~/samples/snippets/csharp/language-reference/operators/RemainderExamples.cs#3)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Operadores de C#](index.md)
