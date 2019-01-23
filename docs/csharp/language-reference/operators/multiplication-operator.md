---
title: '* operador: Referencia de C#'
ms.custom: seodec18
ms.date: 04/04/2018
f1_keywords:
- '*_CSharpKeyword'
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
ms.openlocfilehash: f4490c4632d9344eb879ea55c20787b838781d91
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333738"
---
# <a name="-operator-c-reference"></a>Operador * (Referencia de C#)

El operador de multiplicación (`*`) calcula el producto de sus operandos. Todos los tipos numéricos tienen operadores de multiplicación predefinidos.

`*` también ejerce de operador de desreferencia, que permite leer y escribir en un puntero.

## <a name="remarks"></a>Comentarios

El operador `*` también se usa para declarar tipos de puntero y desreferenciar punteros. Este operador solo puede usarse en contextos no seguros, que son en los que se usa la palabra clave [unsafe](../keywords/unsafe.md) y que requieren la opción de compilador [/ unsafe](../compiler-options/unsafe-compiler-option.md).  El operador de desreferencia también se conoce como el operador de direccionamiento indirecto.

Los tipos definidos por el usuario pueden sobrecargar el operador binario `*` (consulte [operator](../keywords/operator.md)). Cuando se sobrecarga un operador binario, el operador de asignación correspondiente, si lo hay, también se sobrecarga de modo implícito.

## <a name="example"></a>Ejemplo

[!code-csharp-interactive[csRefOperators#50](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#50)]

## <a name="example"></a>Ejemplo

[!code-csharp[csRefOperators#51](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#51)]

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Código no seguro y punteros](../../programming-guide/unsafe-code-pointers/index.md)
- [Operadores de C#](index.md)