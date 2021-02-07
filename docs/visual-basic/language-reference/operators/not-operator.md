---
description: 'Más información acerca de: operador not (Visual Basic)'
title: Operador Not
ms.date: 07/20/2015
f1_keywords:
- vb.Not
helpviewer_keywords:
- Boolean expressions, negating
- operators [Visual Basic], bitwise
- negation operator [Visual Basic]
- inverse bit values in variables [Visual Basic]
- bitwise operators [Visual Basic], NOT operator
- bitwise comparison [Visual Basic]
- Not operator [Visual Basic]
- logical negation
- operators [Visual Basic], negation
ms.assetid: 8f2ea83c-d2ed-480a-a474-3042a1cad9b5
ms.openlocfilehash: 91f3525b52d6f38081b8e5ba208c193f714a4045
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665359"
---
# <a name="not-operator-visual-basic"></a>Not (Operador, Visual Basic)

Realiza una negación lógica de una `Boolean` expresión o una negación bit a bit en una expresión numérica.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
result = Not expression  
```  
  
## <a name="parts"></a>Partes  

 `result`  
 Obligatorio. Cualquier expresión numérica o de tipo `Boolean`.  
  
 `expression`  
 Obligatorio. Cualquier expresión numérica o de tipo `Boolean`.  
  
## <a name="remarks"></a>Observaciones  

 En `Boolean` el caso de las expresiones, en la tabla siguiente se muestra cómo `result` se determina.  
  
|Si `expression` es |El valor de `result` es|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 En el caso de las expresiones numéricas, el `Not` operador invierte los valores de bit de cualquier expresión numérica y establece el bit correspondiente en de `result` acuerdo con la tabla siguiente.  
  
|Si el bit de `expression` es|El bit de `result` es|  
|-------------------------------|----------------------------|  
|1|0|  
|0|1|  
  
> [!NOTE]
> Puesto que los operadores lógicos y bit a bit tienen una prioridad más baja que otros operadores aritméticos y relacionales, las operaciones bit a bit deben ir entre paréntesis para garantizar una ejecución precisa.  
  
## <a name="data-types"></a>Tipo de datos  

 En el caso de una negación booleana, el tipo de datos del resultado es `Boolean` . En el caso de una negación bit a bit, el tipo de datos del resultado es el mismo que el de `expression` . Sin embargo, si Expression es `Decimal` , el resultado es `Long` .  
  
## <a name="overloading"></a>Sobrecarga  

 El `Not` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando su operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se usa el `Not` operador para realizar la negación lógica de una `Boolean` expresión. El resultado es un `Boolean` valor que representa el inverso del valor de la expresión.  
  
 [!code-vb[VbVbalrOperators#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#33)]  
  
 En el ejemplo anterior se generan los resultados de `False` y `True` , respectivamente.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se usa el `Not` operador para realizar la negación lógica de los bits individuales de una expresión numérica. El bit en el patrón del resultado se establece en la inversa del bit correspondiente en el patrón de operando, incluido el bit de signo.  
  
 [!code-vb[VbVbalrOperators#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#34)]  
  
 En el ejemplo anterior se generan los resultados de – 11, – 9 y – 7, respectivamente.  
  
## <a name="see-also"></a>Vea también

- [Operadores lógicos y bit a bit (Visual Basic)](logical-bitwise-operators.md)
- [Prioridad de operador en Visual Basic](operator-precedence.md)
- [Lista de operadores según funcionalidad](operators-listed-by-functionality.md)
- [Operadores lógicos y bit a bit en Visual Basic](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
