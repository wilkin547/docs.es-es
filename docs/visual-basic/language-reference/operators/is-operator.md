---
title: Operador is
ms.date: 07/20/2015
f1_keywords:
- vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
ms.openlocfilehash: 1c2d87ef0a8202332c87af552f488d652c400213
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812268"
---
# <a name="is-operator-visual-basic"></a>Operador is (Visual Basic)

Compara dos variables de referencia de objeto.

## <a name="syntax"></a>Syntax

```vb
result = object1 Is object2
```

## <a name="parts"></a>Partes

 `result`  
 Necesario. Cualquier `Boolean` valor.  
  
 `object1`  
 Necesario. Cualquier `Object` nombre.  
  
 `object2`  
 Necesario. Cualquier `Object` nombre.  
  
## <a name="remarks"></a>Comentarios

El `Is` operador determina si dos referencias de objeto hacen referencia al mismo objeto. Sin embargo, no realiza comparaciones de valores. Si `object1` y `object2` ambos hacen referencia a la misma instancia de objeto exacta, `result` es `True` ; si no es así, `result` es `False` .

> [!NOTE]
> La `Is` palabra clave también se usa en la [selección... Instrucción Case](../statements/select-case-statement.md).
  
## <a name="example"></a>Ejemplo

En el ejemplo siguiente se usa el `Is` operador para comparar pares de referencias de objeto. Los resultados se asignan a un `Boolean` valor que representa si los dos objetos son idénticos.

[!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]

Como se muestra en el ejemplo anterior, puede utilizar el `Is` operador para probar los objetos enlazados en tiempo de compilación y en tiempo de ejecución.

## <a name="use-typeof-operator-with-is-operator"></a>Usar el operador typeof con is

`Is` el operador también se puede usar con la `TypeOf` palabra clave para crear una `TypeOf` expresión... `Is` , que comprueba si una variable de objeto es compatible con un tipo de datos. Por ejemplo:

```vb
If TypeOf sender Is Button Then
```

## <a name="see-also"></a>Consulte también

- [Typeof (operador)](typeof-operator.md)
- [Operador IsNot](isnot-operator.md)
- [Comparison Operators in Visual Basic](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Prioridad de operador en Visual Basic](operator-precedence.md)
- [Lista de operadores según funcionalidad](operators-listed-by-functionality.md)
- [Operadores y expresiones](../../programming-guide/language-features/operators-and-expressions/index.md)
