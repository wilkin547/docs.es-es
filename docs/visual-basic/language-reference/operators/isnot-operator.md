---
description: 'Más información acerca de: Operador IsNot (Visual Basic)'
title: IsNot (operador)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- comparison operators [Visual Basic]
- TypeOf...IsNot expression
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: ac3e127676dfa57d14e07838152022de62fc336b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665671"
---
# <a name="isnot-operator-visual-basic"></a>IsNot (Operador) (Visual Basic)

Compara dos variables de referencia de objeto.

## <a name="syntax"></a>Sintaxis

```vb
result = object1 IsNot object2
```

## <a name="parts"></a>Partes

- `result`

  Necesario. Valor `Boolean`.

- `object1`

  Necesario. Cualquier `Object` variable o expresión.

- `object2`

  Necesario. Cualquier `Object` variable o expresión.

## <a name="remarks"></a>Observaciones

El `IsNot` operador determina si dos referencias de objeto hacen referencia a objetos diferentes. Sin embargo, no realiza comparaciones de valores. Si `object1` y `object2` ambos hacen referencia a la misma instancia de objeto exacta, `result` es `False` ; si no, `result` es `True` .

`IsNot` es lo contrario del `Is` operador. La ventaja de `IsNot` es que puede evitar una sintaxis complicada con `Not` y `Is` , que puede ser difícil de leer.

 Puede usar los `Is` operadores y `IsNot` para probar los objetos enlazados en tiempo de compilación y en tiempo de ejecución.

## <a name="example"></a>Ejemplo

En el ejemplo de código siguiente se usa el `Is` operador y el `IsNot` operador para realizar la misma comparación.

[!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]

## <a name="use-typeof-operator-with-isnot-operator"></a>Usar el operador typeof con el Operador IsNot

A partir de Visual Basic 14, puede usar el `TypeOf` operador con el `IsNot` operador para comprobar si un objeto *no* es compatible con un tipo de datos. Por ejemplo:

```vb
If TypeOf sender IsNot Button Then
```

## <a name="see-also"></a>Vea también

- [Operador Is](is-operator.md)
- [Operador TypeOf](typeof-operator.md)
- [Prioridad de operador en Visual Basic](operator-precedence.md)
- [Procedimiento para comprobar si dos objetos son iguales](../../programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
