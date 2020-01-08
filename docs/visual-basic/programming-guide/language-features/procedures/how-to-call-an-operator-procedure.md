---
title: 'Cómo: Llamar a un procedimiento de operador'
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
ms.openlocfilehash: a977b17d4b2c797bbe38d289a57f3d9d31fa64fa
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345966"
---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a>Cómo: Llamar a un procedimiento de operador (Visual Basic)
Se llama a un procedimiento de operador mediante el símbolo de operador en una expresión. En el caso de un operador de conversión, se llama a la [función ctype](../../../../visual-basic/language-reference/functions/ctype-function.md) para convertir un valor de un tipo de datos a otro.  
  
 No llame a los procedimientos de operador explícitamente. Solo se usa el operador, o la función `CType`, en una instrucción de asignación o una expresión, del mismo modo que normalmente se usa un operador. Visual Basic realiza la llamada al procedimiento de operador.  
  
 La definición de un operador en una clase o estructura también se denomina *sobrecargar* el operador.  
  
### <a name="to-call-an-operator-procedure"></a>Para llamar a un procedimiento de operador  
  
1. Use el símbolo del operador en una expresión de la manera habitual.  
  
2. Asegúrese de que los tipos de datos de los operandos son adecuados para el operador y en el orden correcto.  
  
3. El operador contribuye al valor de la expresión según lo esperado.  
  
### <a name="to-call-a-conversion-operator-procedure"></a>Para llamar a un procedimiento de operador de conversión  
  
1. Use `CType` dentro de una expresión.  
  
2. Asegúrese de que los tipos de datos de los operandos son adecuados para la conversión y en el orden correcto.  
  
3. `CType` llama al procedimiento del operador de conversión y devuelve el valor convertido.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crean dos estructuras <xref:System.TimeSpan>, se agregan juntas y se almacena el resultado en una tercera <xref:System.TimeSpan> estructura. La estructura <xref:System.TimeSpan> define los procedimientos de operador para sobrecargar varios operadores estándar.  
  
 [!code-vb[VbVbcnProcedures#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#29)]  
  
 Dado que <xref:System.TimeSpan> sobrecarga el operador de `+` estándar, en el ejemplo anterior se llama a un procedimiento de operador al calcular el valor de `combinedSpan`.  
  
 Para obtener un ejemplo de cómo llamar a un procedimiento de operador de conversación, consulte [Cómo: utilizar una clase que define operadores](./how-to-use-a-class-that-defines-operators.md).  
  
## <a name="compile-the-code"></a>Compilar el código  
 Asegúrese de que la clase o estructura que está usando define el operador que desea utilizar.  
  
## <a name="see-also"></a>Vea también

- [Procedimientos de operadores](./operator-procedures.md)
- [Definir un operador](./how-to-define-an-operator.md)
- [Definir un operador de conversión](./how-to-define-a-conversion-operator.md)
- [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [Widening](../../../../visual-basic/language-reference/modifiers/widening.md)
- [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)
- [Structure (instrucción)](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [Declarar una estructura](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Conversiones implícitas y explícitas](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Conversiones de ampliación y de restricción](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
