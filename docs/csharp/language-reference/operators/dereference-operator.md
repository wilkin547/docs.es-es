---
title: Operador -&gt; (Referencia de C#)
ms.date: 11/26/2018
f1_keywords:
- ->_CSharpKeyword
helpviewer_keywords:
- member access operator (->) [C#]
- -> operator [C#]
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
ms.openlocfilehash: 178724ede105d809bd812461121a38d5a0e90517
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53144135"
---
# <a name="-gt-operator-c-reference"></a>Operador -&gt; (Referencia de C#)

El operador de acceso de miembro de puntero `->` combina el direccionamiento indirecto del puntero y el acceso del miembro.

Si `x` es un puntero de tipo `T*` y `y` es un miembro accesible de `T`, una expresión de formato

```csharp
x->y
```

es equivalente a

```csharp
(*x).y
```

El operador `->` requiere un contexto [unsafe](../keywords/unsafe.md).

Para obtener más información, vea [Cómo: Acceder a un miembro con un puntero (Guía de programación de C#)](../../programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md).

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

El operador `->` no se puede sobrecargar.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, vea la sección [Acceso a miembros de puntero](~/_csharplang/spec/unsafe-code.md#pointer-member-access) de la [Especificación del lenguaje C#](../language-specification/index.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Operadores de C#](index.md)
- [Tipos de puntero](../../programming-guide/unsafe-code-pointers/pointer-types.md)
