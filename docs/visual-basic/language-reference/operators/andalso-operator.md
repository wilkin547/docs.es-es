---
description: 'Más información sobre: operador AndAlso (Visual Basic)'
title: Operador AndAlso
ms.date: 07/20/2015
f1_keywords:
- vb.AndAlso
- AndAlso
helpviewer_keywords:
- short-circuiting
- AndAlso operator [Visual Basic]
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], conjunction
- short-circuit evaluation
ms.assetid: bbc15191-b374-495b-9b8f-7b8c2f4388eb
ms.openlocfilehash: dcf6c2685bf8f9ffee27b00543786cd3b315b327
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99774270"
---
# <a name="andalso-operator-visual-basic"></a>AndAlso (Operador, Visual Basic)

Realiza una conjunción lógica de cortocircuito en dos expresiones.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a>Partes  
  
|Término|Definición|  
|---|---|  
|`result`|Obligatorio. Cualquier expresión `Boolean` . El resultado es el `Boolean` resultado de la comparación de las dos expresiones.|  
|`expression1`|Obligatorio. Cualquier expresión `Boolean` .|  
|`expression2`|Obligatorio. Cualquier expresión `Boolean` .|  
  
## <a name="remarks"></a>Observaciones  

 Se dice que una operación lógica es *cortocircuitada* si el código compilado puede omitir la evaluación de una expresión en función del resultado de otra expresión. Si el resultado de la primera expresión evaluada determina el resultado final de la operación, no es necesario evaluar la segunda expresión, porque no puede cambiar el resultado final. El cortocircuito puede mejorar el rendimiento si la expresión omitida es compleja o si implica llamadas a procedimientos.  
  
 Si ambas expresiones se evalúan como `True` , `result` es `True` . En la tabla siguiente se muestra cómo `result` se determina.  
  
|Si `expression1` es |Y `expression2` es|El valor de `result` es|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|(no evaluado)|`False`|  
  
## <a name="data-types"></a>Tipo de datos  

 El `AndAlso` operador solo se define para el [tipo de datos Boolean](../data-types/boolean-data-type.md). Visual Basic convierte cada operando según sea necesario en `Boolean` antes de evaluar la expresión. Si asigna el resultado a un tipo numérico, Visual Basic lo convierte de `Boolean` a ese tipo tal que `False` se convierte en `0` y `True` se convierte en `-1` .
Para obtener más información, vea [conversiones de tipo booleano](../data-types/boolean-data-type.md#type-conversions).
  
## <a name="overloading"></a>Sobrecarga  

 El [operador and](and-operator.md) y el [operador IsFalse](isfalse-operator.md) se pueden *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. La sobrecarga de los `And` `IsFalse` operadores y afecta al comportamiento del `AndAlso` operador. Si el código utiliza `AndAlso` en una clase o estructura que sobrecarga `And` y `IsFalse` , asegúrese de que entiende su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se usa el `AndAlso` operador para realizar una conjunción lógica entre dos expresiones. El resultado es un `Boolean` valor que indica si toda la expresión conunida es true. Si la primera expresión es `False` , el segundo no se evalúa.  
  
 [!code-vb[VbVbalrOperators#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#24)]  
  
 En el ejemplo anterior se generan los resultados de `True` , `False` y `False` , respectivamente. En el cálculo de `secondCheck` , la segunda expresión no se evalúa porque la primera ya está `False` . Sin embargo, la segunda expresión se evalúa en el cálculo de `thirdCheck` .  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra un `Function` procedimiento que busca un valor determinado entre los elementos de una matriz. Si la matriz está vacía, o si se ha superado la longitud de la matriz, la `While` instrucción no probará el elemento de la matriz con el valor de búsqueda.  
  
 [!code-vb[VbVbalrOperators#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#25)]  
  
## <a name="see-also"></a>Vea también

- [Operadores lógicos y bit a bit (Visual Basic)](logical-bitwise-operators.md)
- [Prioridad de operador en Visual Basic](operator-precedence.md)
- [Lista de operadores según funcionalidad](operators-listed-by-functionality.md)
- [Operador And](and-operator.md)
- [Operador IsFalse](isfalse-operator.md)
- [Operadores lógicos y bit a bit en Visual Basic](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
