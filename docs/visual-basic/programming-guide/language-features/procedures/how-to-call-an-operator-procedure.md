---
title: 'Cómo: Llamar a un procedimiento de operador (Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 21545f2488bfabd0abc9c6e316d21bbc4d5aeb91
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a>Cómo: Llamar a un procedimiento de operador (Visual Basic)
Llame a un procedimiento de operador mediante el símbolo del operador en una expresión. En el caso de un operador de conversión, se llama a la [CType (función)](../../../../visual-basic/language-reference/functions/ctype-function.md) para convertir un valor de un tipo de datos a otro.  
  
 No se llama explícitamente procedimientos de operadores. Solo se usa el operador, o la `CType` función, en una instrucción de asignación o una expresión, del mismo modo que se usa habitualmente un operador. Visual Basic realiza la llamada al procedimiento de operador.  
  
 Definir un operador en una clase o estructura también se denomina *sobrecarga* el operador.  
  
### <a name="to-call-an-operator-procedure"></a>Para llamar a un procedimiento de operador  
  
1.  Utilice el símbolo del operador en una expresión de la forma normal.  
  
2.  Asegúrese de que los tipos de datos de los operandos son adecuados para el operador y en el orden correcto.  
  
3.  El operador contribuye al valor de la expresión tal y como se esperaba.  
  
### <a name="to-call-a-conversion-operator-procedure"></a>Llamar a un procedimiento de operador de conversión  
  
1.  Use `CType` dentro de una expresión.  
  
2.  Asegúrese de que los tipos de datos de los operandos son adecuados para la conversión y, en el orden correcto.  
  
3.  `CType` llama al procedimiento de operador de conversión y devuelve el valor convertido.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea dos <xref:System.TimeSpan> las estructuras y los agrega juntos y almacena el resultado en una tercera <xref:System.TimeSpan> estructura. El <xref:System.TimeSpan> estructura define los procedimientos de operador para sobrecargar varios operadores estándares.  
  
 [!code-vb[VbVbcnProcedures#29](./codesnippet/VisualBasic/how-to-call-an-operator-procedure_1.vb)]  
  
 Dado que <xref:System.TimeSpan> sobrecargas el estándar `+` (operador), en el ejemplo anterior, se llama a un procedimiento de operador cuando calcula el valor de `combinedSpan`.  
  
 Para obtener un ejemplo de una llamada a un procedimiento de operador de conversación, vea [Cómo: utilizar una clase que define operadores](./how-to-use-a-class-that-defines-operators.md).  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Asegúrese de que la clase o estructura que está utilizando define el operador que desea utilizar.  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos de operadores](./operator-procedures.md)  
 [Definir un operador](./how-to-define-an-operator.md)  
 [Definir un operador de conversión](./how-to-define-a-conversion-operator.md)  
 [Operator (instrucción)](../../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Widening](../../../../visual-basic/language-reference/modifiers/widening.md)  
 [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [Structure (instrucción)](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Declarar una estructura](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [Conversiones implícitas y explícitas](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Conversiones de ampliación y de restricción](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
