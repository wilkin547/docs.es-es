---
title: IsNot (Operador)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: 616506f64d20e1f150b443433f1b69040136a5ba
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74336072"
---
# <a name="isnot-operator-visual-basic"></a>IsNot (Operador) (Visual Basic)

Compara dos variables de referencia de objeto.

## <a name="syntax"></a>Sintaxis

```vb
result = object1 IsNot object2
```

## <a name="parts"></a>Elementos
 `result` Obligatorio. Valor `Boolean`.

 `object1` Obligatorio. Cualquier `Object` variable o expresión.

 `object2` Obligatorio. Cualquier `Object` variable o expresión.

## <a name="remarks"></a>Comentarios
 El operador `IsNot` determina si dos referencias de objeto hacen referencia a objetos diferentes. Sin embargo, no realiza comparaciones de valores. Si `object1` y `object2` hacen referencia a la misma instancia de objeto exacta, se `False``result`. Si no es así, `result` se `True`.

 `IsNot` es lo contrario del operador de `Is`. La ventaja de `IsNot` es que puede evitar una sintaxis poco complicada con `Not` y `Is`, lo que puede resultar difícil de leer.

 Puede usar los operadores `Is` y `IsNot` para probar los objetos enlazados en tiempo de compilación y en tiempo de ejecución.

## <a name="example"></a>Ejemplo
 En el ejemplo de código siguiente se usa el operador `Is` y el operador `IsNot` para realizar la misma comparación.

 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]

## <a name="see-also"></a>Vea también

- [Is (operador)](is-operator.md)
- [TypeOf (operador)](typeof-operator.md)
- [Prioridad de operador en Visual Basic](operator-precedence.md)
- [Comprobar si dos objetos son iguales](../../programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
