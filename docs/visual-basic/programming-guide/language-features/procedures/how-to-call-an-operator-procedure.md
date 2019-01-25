---
title: Procedimiento Llamar a un procedimiento de operador (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- operator procedures [Visual Basic], calling
- procedures [Visual Basic], operator
- procedure calls [Visual Basic], operator overloading
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- overloaded operators [Visual Basic], calling
- operator overloading
ms.assetid: 0dce42cc-f0b0-4c14-9f62-018b21f33497
ms.openlocfilehash: fc658dd7ef001c8d3ef7761bd2a7889f70e9e4a3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54667588"
---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a>Procedimiento Llamar a un procedimiento de operador (Visual Basic)
Llame a un procedimiento de operador mediante el símbolo de operador en una expresión. En el caso de un operador de conversión, llame a la [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) para convertir un valor de un tipo de datos a otro.  
  
 No llame explícitamente procedimientos de operador. Utilizaremos el operador, o el `CType` función en una instrucción de asignación o una expresión, la misma manera que se usa habitualmente un operador. Visual Basic realiza la llamada al procedimiento de operador.  
  
 Definir un operador en una clase o estructura también se denomina *sobrecarga* el operador.  
  
### <a name="to-call-an-operator-procedure"></a>Para llamar a un procedimiento de operador  
  
1.  Utilice el símbolo de operador en una expresión de la manera normal.  
  
2.  Asegúrese de que los tipos de datos de los operandos son adecuados para el operador y, en el orden correcto.  
  
3.  El operador contribuye al valor de la expresión, según lo previsto.  
  
### <a name="to-call-a-conversion-operator-procedure"></a>Llamar a un procedimiento de operador de conversión  
  
1.  Use `CType` dentro de una expresión.  
  
2.  Asegúrese de que los tipos de datos de los operandos son adecuados para la conversión y, en el orden correcto.  
  
3.  `CType` llama al procedimiento de operador de conversión y devuelve el valor convertido.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crean dos <xref:System.TimeSpan> estructuras, agrega juntos y almacena el resultado en una tercera <xref:System.TimeSpan> estructura. El <xref:System.TimeSpan> estructura define procedimientos de operador para sobrecargar varios operadores estándar.  
  
 [!code-vb[VbVbcnProcedures#29](./codesnippet/VisualBasic/how-to-call-an-operator-procedure_1.vb)]  
  
 Dado que <xref:System.TimeSpan> sobrecargas estándar `+` operador, en el ejemplo anterior, se llama a un procedimiento de operador cuando calcula el valor de `combinedSpan`.  
  
 Para obtener un ejemplo de una llamada a un procedimiento de operador de conversación, vea [Cómo: Usar una clase que define operadores](./how-to-use-a-class-that-defines-operators.md).  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Asegúrese de que la clase o estructura que está utilizando define el operador que desea usar.  
  
## <a name="see-also"></a>Vea también
- [Procedimientos de operadores](./operator-procedures.md)
- [Cómo: Definir un operador](./how-to-define-an-operator.md)
- [Cómo: Definir un operador de conversión](./how-to-define-a-conversion-operator.md)
- [Operator (instrucción)](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [Widening](../../../../visual-basic/language-reference/modifiers/widening.md)
- [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)
- [Structure (instrucción)](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [Cómo: Declarar una estructura](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Conversiones implícitas y explícitas](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Conversiones de ampliación y de restricción](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
