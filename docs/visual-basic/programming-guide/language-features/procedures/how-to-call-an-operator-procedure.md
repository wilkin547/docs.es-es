---
title: "Cómo: llamar a un procedimiento de operador (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- operator procedures, calling
- procedures, operator
- procedure calls, operator overloading
- syntax, Operator procedures
- operators [Visual Basic], overloading
- return values, Operator procedures
- overloaded operators, calling
- operator overloading
ms.assetid: 0dce42cc-f0b0-4c14-9f62-018b21f33497
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2403e7a8270c17a8db5417cd8394fd47c373d493
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a>Cómo: Llamar a un procedimiento de operador (Visual Basic)
Puede llamar a un procedimiento de operador utilizando el símbolo de operador en una expresión. En el caso de un operador de conversión, se llama a la [CType (función)](../../../../visual-basic/language-reference/functions/ctype-function.md) para convertir un valor de un tipo de datos a otro.  
  
 No se llama explícitamente procedimientos de operador. Simplemente utiliza el operador o la `CType` función, en una instrucción de asignación o una expresión, del mismo modo que se usa habitualmente un operador. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]realiza la llamada al procedimiento de operador.  
  
 Definir un operador en una clase o estructura también se denomina *sobrecarga* el operador.  
  
### <a name="to-call-an-operator-procedure"></a>Para llamar a un procedimiento de operador  
  
1.  Utilice el símbolo de operador en una expresión de la manera normal.  
  
2.  Asegúrese de que los tipos de datos de los operandos son adecuados para el operador y en el orden correcto.  
  
3.  El operador contribuye al valor de la expresión como se esperaba.  
  
### <a name="to-call-a-conversion-operator-procedure"></a>Llamar a un procedimiento de operador de conversión  
  
1.  Use `CType` dentro de una expresión.  
  
2.  Asegúrese de que los tipos de datos de los operandos son adecuados para la conversión y, en el orden correcto.  
  
3.  `CType`llama al procedimiento de operador de conversión y devuelve el valor convertido.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crean dos <xref:System.TimeSpan>estructuras, suma y almacena el resultado en una tercera <xref:System.TimeSpan>estructura.</xref:System.TimeSpan> </xref:System.TimeSpan> El <xref:System.TimeSpan>estructura define los procedimientos de operador para sobrecargar varios operadores estándar.</xref:System.TimeSpan>  
  
 [!code-vb[VbVbcnProcedures&#29;](./codesnippet/VisualBasic/how-to-call-an-operator-procedure_1.vb)]  
  
 Porque <xref:System.TimeSpan>sobrecargas estándar `+` operador, en el ejemplo anterior, se llama a un procedimiento de operador cuando calcula el valor de `combinedSpan`.</xref:System.TimeSpan>  
  
 Para obtener un ejemplo de una llamada a un procedimiento de operador de conversación, vea [Cómo: utilizar una clase que define los operadores](./how-to-use-a-class-that-defines-operators.md).  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Asegúrese de que la clase o estructura que está utilizando define el operador que desea utilizar.  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos de operadores](./operator-procedures.md)   
 [Cómo: definir un operador](./how-to-define-an-operator.md)   
 [Cómo: definir un operador de conversión](./how-to-define-a-conversion-operator.md)   
 [Operator (instrucción)](../../../../visual-basic/language-reference/statements/operator-statement.md)   
 [De ampliación](../../../../visual-basic/language-reference/modifiers/widening.md)   
 [De restricción](../../../../visual-basic/language-reference/modifiers/narrowing.md)   
 [Structure (instrucción)](../../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Cómo: declarar una estructura](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)   
 [Conversiones implícitas y explícitas](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Conversiones de ampliación y de restricción](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
