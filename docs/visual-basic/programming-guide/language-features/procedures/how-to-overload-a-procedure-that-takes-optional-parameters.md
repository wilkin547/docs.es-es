---
title: "C&#243;mo: Sobrecargar un procedimiento que toma par&#225;metros opcionales (Visual Basic) | Microsoft Docs"
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
  - "sobrecarga de procedimientos, parámetros opcionales"
  - "parámetros de procedimientos"
  - "procedimientos, definir"
  - "procedimientos, varias versiones"
  - "procedimientos, sobrecargar"
  - "procedimientos, parámetros"
  - "código de Visual Basic, procedimientos"
ms.assetid: 825f9d56-4cde-43fd-993a-b9171717e2eb
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Sobrecargar un procedimiento que toma par&#225;metros opcionales (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Si un procedimiento tiene uno o varios parámetros [Optional](../../../../visual-basic/language-reference/modifiers/optional.md), no se puede definir ninguna versión sobrecargada que se corresponda con alguna de sus sobrecargas implícitas.  Para obtener más información, vea "Sobrecargas implícitas para parámetros opcionales" en [Consideraciones sobre la sobrecarga de procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md).  
  
## Un parámetro opcional  
  
#### Para sobrecargar un procedimiento que toma un parámetro opcional  
  
1.  Escriba una instrucción de declaración `Sub` o `Function` que incluya el parámetro opcional en la lista de parámetros.  No utilice la palabra clave `Optional` en esta versión sobrecargada.  
  
2.  Anteponga la palabra clave [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) a la palabra clave `Sub` o `Function`.  
  
3.  Escriba el código de procedimiento que debería ejecutarse cuando el código de llamada proporcione el argumento opcional.  
  
4.  Finalice el procedimiento con la instrucción `End Sub` o `End Function`, según corresponda.  
  
5.  Escriba una segunda instrucción de declaración que sea idéntica a la primera salvo porque no debe incluir el parámetro opcional en la lista de parámetros.  
  
6.  Escriba el código de procedimiento que debería ejecutarse cuando el código de llamada no proporcione el argumento opcional.  Finalice el procedimiento con la instrucción `End Sub` o `End Function`, según corresponda.  
  
     En el ejemplo siguiente se muestra un procedimiento definido con un parámetro opcional, un conjunto equivalente de dos procedimientos sobrecargados y, por último, ejemplos de versiones sobrecargadas válidas y no válidas.  
  
     [!code-vb[VbVbcnProcedures#59](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-optional-parameters_1.vb)]  
  
     [!code-vb[VbVbcnProcedures#60](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-optional-parameters_2.vb)]  
  
     [!code-vb[VbVbcnProcedures#61](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-optional-parameters_3.vb)]  
  
## Varios parámetros opcionales  
 En un procedimiento con varios parámetros opcionales, normalmente son necesarias más de dos versiones sobrecargadas.  Por ejemplo, si hay dos parámetros opcionales y el código de llamada puede proporcionar u omitir cada uno de ellos con independencia del otro, serán necesarias cuatro versiones sobrecargadas, una por cada combinación posible de los argumentos proporcionados.  
  
 Como el número de parámetros opcionales aumenta, también se incrementa la complejidad de la sobrecarga.  A menos que algunas combinaciones de los argumentos proporcionados no sean aceptables, para N parámetros opcionales necesitará 2 ^ N versiones sobrecargadas.  Dependiendo de la naturaleza del procedimiento, quizás considere que la claridad de la lógica podría justificar el esfuerzo adicional que supone definir todas las versiones sobrecargadas.  
  
#### Para sobrecargar un procedimiento que toma varios parámetros opcionales  
  
1.  Determine qué combinaciones de los argumentos opcionales proporcionados son aceptables en la lógica del procedimiento.  Podría generarse una combinación inaceptable si un parámetro opcional dependiera de otro.  Por ejemplo, si un parámetro acepta el nombre del cónyuge y otro acepta la edad del cónyuge, una combinación de argumentos que proporcione la edad pero omita el nombre sería inaceptable.  
  
2.  Para cada combinación aceptable de los argumentos opcionales proporcionados, escriba una instrucción de declaración `Sub` o `Function` que defina la lista de parámetros correspondiente.  No utilice la palabra clave `Optional`.  
  
3.  En cada declaración, anteponga la palabra clave [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) a la palabra clave `Sub` o `Function`.  
  
4.  Después de cada declaración, escriba el código del procedimiento que debería ejecutarse cuando el código de llamada proporcione una lista de argumentos que se corresponda con la lista de parámetros de esa declaración.  
  
5.  Finalice todos los procedimientos con la instrucción `End Sub` o `End Function`, según corresponda.  
  
## Vea también  
 [Procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Parámetros opcionales](../../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)   
 [Matrices de parámetros](../../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)   
 [Sobrecarga de procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Procedimientos de solución de problemas](../../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)   
 [Cómo: Definir varias versiones de un procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-multiple-versions-of-a-procedure.md)   
 [Cómo: Llamar a un procedimiento sobrecargado](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-overloaded-procedure.md)   
 [Cómo: Sobrecargar un procedimiento que toma un número indefinido de parámetros](../../../../visual-basic/programming-guide/language-features/procedures/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)   
 [Resolución de sobrecargas](../../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)