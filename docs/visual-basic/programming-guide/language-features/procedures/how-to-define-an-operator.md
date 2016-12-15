---
title: "C&#243;mo: Definir un operador (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "sobrecarga de operadores"
  - "procedimientos de operadores, acerca de los procedimientos de operadores"
  - "operadores [Visual Basic], definir"
  - "operadores [Visual Basic], sobrecargar"
  - "procedimientos, definir"
  - "procedimientos, operador"
  - "valores devueltos, procedimientos de operadores"
  - "sintaxis, procedimientos de operadores"
  - "código de Visual Basic, operadores"
  - "código de Visual Basic, procedimientos"
ms.assetid: d4b0e253-092a-4e6e-9fe2-01f562140a29
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Definir un operador (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Si ha definido una clase o estructura, puede definir el comportamiento de un operador estándar \(como `*`, `<>` o `And`\) cuando uno o los dos operandos pertenecen al tipo de datos de la clase o estructura.  
  
 Defina al operador estándar como un procedimiento de operador dentro de la clase o estructura.  Todos los procedimientos de operador deben ser `Public` `Shared`.  
  
 La definición de un operador de una clase o estructura también se denomina *sobrecarga* del operador.  
  
## Ejemplo  
 En el ejemplo siguiente se define el operador `+` en una estructura denominada  `height`.  La estructura utiliza altos que se miden en pies y pulgadas.  Una *pulgada* equivale a 2,54 centímetros y un *pie* a 12 pulgadas.  Para garantizar que los valores están normalizados \(pulgadas \< 12,0\), el constructor lleva a cabo una aritmética *módulo* 12.  El operador `+` utiliza el constructor para generar valores normalizados.  
  
 [!code-vb[VbVbcnProcedures#25](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-define-an-operator_1.vb)]  
  
 Puede probar la estructura  `height`  con el código siguiente.  
  
 [!code-vb[VbVbcnProcedures#26](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-define-an-operator_2.vb)]  
  
 Para obtener más información y ejemplos, vea [Sobrecarga en Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703)  
  
## Vea también  
 [Procedimientos de operador](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Cómo: Definir un operador de conversión](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)   
 [Cómo: Llamar a un procedimiento de operador](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)   
 [Cómo: Utilizar una clase que define operadores](../../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)   
 [Operator \(Instrucción\)](../../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Structure \(Instrucción\)](../../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Cómo: Declarar una estructura](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)   
 [Mod \(Operador\)](../../../../visual-basic/language-reference/operators/mod-operator.md)