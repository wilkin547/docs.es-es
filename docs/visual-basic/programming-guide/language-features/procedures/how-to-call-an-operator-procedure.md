---
title: "C&#243;mo: Llamar a un procedimiento de operador (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "sobrecarga de operadores"
  - "procedimientos de operadores, llamar"
  - "operadores [Visual Basic], sobrecargar"
  - "operadores sobrecargados, llamar"
  - "llamadas a procedimientos, sobrecarga de operadores"
  - "procedimientos, operador"
  - "valores devueltos, procedimientos de operadores"
  - "sintaxis, procedimientos de operadores"
ms.assetid: 0dce42cc-f0b0-4c14-9f62-018b21f33497
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# C&#243;mo: Llamar a un procedimiento de operador (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Se llama a un procedimiento de operador utilizando el símbolo de operador en una expresión.  En el caso de un operador de conversión, se llama a [CType \(Función\)](../../../../visual-basic/language-reference/functions/ctype-function.md) para convertir un valor de un tipo de datos en otro.  
  
 No se llama de forma explícita a los procedimientos de operador.  Simplemente tiene que usar el operador o la función `CType` en una instrucción de asignación o una expresión del mismo modo que usa habitualmente un operador.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] realiza la llamada al procedimiento de operador.  
  
 La definición de un operador de una clase o estructura también se denomina *sobrecarga* del operador.  
  
### Para llamar a un procedimiento de operador  
  
1.  Use el símbolo de operador en una expresión como lo haría normalmente.  
  
2.  Asegúrese de que los tipos de datos de los operandos son adecuados para el operador y están en el orden correcto.  
  
3.  El operador contribuye al valor de la expresión tal como se espera.  
  
### Para llamar a un procedimiento de operador de conversión  
  
1.  Utilice `CType` dentro de una expresión.  
  
2.  Asegúrese de que los tipos de datos de los operandos son adecuados para la conversión y están en el orden correcto.  
  
3.  `CType` llama al procedimiento de operador de conversión y devuelve el valor convertido.  
  
## Ejemplo  
 El ejemplo siguiente crea dos estructuras <xref:System.TimeSpan>, las suma y almacena el resultado en una tercera estructura <xref:System.TimeSpan>.  La estructura <xref:System.TimeSpan> define los procedimientos de operador para sobrecargar varios operadores estándar.  
  
 [!code-vb[VbVbcnProcedures#29](./codesnippet/VisualBasic/how-to-call-an-operator-procedure_1.vb)]  
  
 Como <xref:System.TimeSpan> sobrecarga el operador `+` estándar, el ejemplo anterior llama a un procedimiento de operador cuando calcula el valor de `combinedSpan`.  
  
 Para obtener un ejemplo de llamada a un procedimiento de operador de conversación, vea [Cómo: Utilizar una clase que define operadores](../../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md).  
  
## Compilar el código  
 Asegúrese de que la clase o la estructura que está utilizando define el operador que desea utilizar.  
  
## Vea también  
 [Procedimientos de operador](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Cómo: Definir un operador](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [Cómo: Definir un operador de conversión](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)   
 [Operator \(Instrucción\)](../../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Widening](../../../../visual-basic/language-reference/modifiers/widening.md)   
 [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)   
 [Structure \(Instrucción\)](../../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Cómo: Declarar una estructura](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)   
 [Conversiones implícitas y explícitas](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Conversiones de ampliación y de restricción](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)