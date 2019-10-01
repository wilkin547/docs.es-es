---
title: IsNot (Operador) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: 32e8f9532244679d2994b0e3d98279d75f7e77b4
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701034"
---
# <a name="isnot-operator-visual-basic"></a>IsNot (Operador) (Visual Basic)

Compara dos variables de referencia de objeto.

## <a name="syntax"></a>Sintaxis

```vb
result = object1 IsNot object2
```

## <a name="parts"></a>Elementos
 `result` Obligatorio. Valor `Boolean`.

 `object1` Obligatorio. Cualquier variable o expresión `Object`.

 `object2` Obligatorio. Cualquier variable o expresión `Object`.

## <a name="remarks"></a>Comentarios
 El operador `IsNot` determina si dos referencias de objeto hacen referencia a objetos diferentes. Sin embargo, no realiza comparaciones de valores. Si `object1` y `object2` hacen referencia a la misma instancia de objeto exacta, @no__t 2 es `False`; Si no es así, `result` es `True`.

 `IsNot` es lo contrario del operador `Is`. La ventaja de `IsNot` es que puede evitar una sintaxis complicada con `Not` y `Is`, lo que puede resultar difícil de leer.

 Puede usar los operadores `Is` y `IsNot` para probar tanto los objetos enlazados en tiempo de compilación como los que se enlazan en tiempo de ejecución.

## <a name="example"></a>Ejemplo
 En el ejemplo de código siguiente se usa el operador `Is` y el operador `IsNot` para realizar la misma comparación.

 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]

## <a name="see-also"></a>Vea también

- [Is (operador)](is-operator.md)
- [TypeOf (operador)](typeof-operator.md)
- [Prioridad de operador en Visual Basic](operator-precedence.md)
- [Cómo: Prueba si dos objetos son los mismos @ no__t-0
