---
title: "C&#243;mo: Sobrecargar un procedimiento que toma un n&#250;mero indefinido de par&#225;metros (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "sobrecarga de procedimientos, número indefinido de parámetros"
  - "parámetros de procedimientos"
  - "procedimientos, definir"
  - "procedimientos, varias versiones"
  - "procedimientos, sobrecargar"
  - "procedimientos, parámetros"
  - "código de Visual Basic, procedimientos"
ms.assetid: c7042de2-2422-4039-94e8-ac298896af69
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Sobrecargar un procedimiento que toma un n&#250;mero indefinido de par&#225;metros (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Si un procedimiento tiene un parámetro [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md), no se puede definir una versión sobrecargada que tome una matriz unidimensional para la matriz de parámetros.  Para obtener más información, vea "Sobrecargas implícitas de un parámetro ParamArray" en [Consideraciones sobre la sobrecarga de procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md).  
  
### Para sobrecargar un procedimiento que toma un número variable de parámetros  
  
1.  Determine si para el procedimiento y el código de llamada resulta más ventajoso utilizar versiones sobrecargadas que utilizar un parámetro `ParamArray`.  Vea "Sobrecargas y matrices de parámetros" en [Consideraciones sobre la sobrecarga de procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md).  
  
2.  Determine qué número de valores proporcionados debe aceptar el procedimiento en la parte variable de la lista de parámetros.  Podría tratarse de ningún valor y de una matriz unidimensional.  
  
3.  Para cada combinación aceptable de valores proporcionados, escriba una instrucción de declaración `Sub` o `Function` que defina la lista de parámetros correspondiente.  No utilice la palabra clave `Optional` ni `ParamArray` en esta versión sobrecargada.  
  
4.  En cada declaración, anteponga la palabra clave [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) a la palabra clave `Sub` o `Function`.  
  
5.  Después de cada declaración, escriba el código del procedimiento que debería ejecutarse cuando el código de llamada proporcione los valores correspondientes a la lista de parámetros de esa declaración.  
  
6.  Finalice todos los procedimientos con la instrucción `End Sub` o `End Function`, según corresponda.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra un procedimiento definido con un parámetro [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) y a continuación se muestra una definición equivalente con procedimientos sobrecargados.  
  
 [!code-vb[VbVbcnProcedures#69](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#70](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_2.vb)]  
  
 No puede sobrecargar este tipo de procedimiento con una lista de parámetros que tome una matriz unidimensional para la matriz de parámetros.  Sin embargo, puede utilizar las firmas de las otras sobrecarga implícitas.  Las siguientes declaraciones ilustran este comportamiento:  
  
 [!code-vb[VbVbcnProcedures#71](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_3.vb)]  
  
 En las versiones sobrecargadas, el código no tiene que comprobar si el código de llamada proporciona uno o varios valores para el parámetro `ParamArray`, pero si lo hace, no tiene que comprobar cuántos valores proporciona.  [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] pasa el control a la versión que coincida con la lista de argumentos de llamada.  
  
## Compilar el código  
 Como un procedimiento con un parámetro `ParamArray` es equivalente a un conjunto de versiones sobrecargadas, no puede sobrecargar un procedimiento de este tipo con una lista de parámetros que se corresponda con alguna de estas sobrecargas implícitas.  Para obtener más información, vea [Consideraciones sobre la sobrecarga de procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md).  
  
## Seguridad de .NET Framework  
 Si se trabaja con matrices cuyo tamaño es excesivamente grande, existe el riesgo de sobrecargar alguna capacidad interna de la aplicación.  Si acepta una matriz de parámetros, debe comprobar la longitud de la matriz que transfiere el código de llamada y tomar las medidas apropiadas si es demasiado grande para la aplicación.  
  
## Vea también  
 [Procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Parámetros opcionales](../../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)   
 [Matrices de parámetros](../../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)   
 [Sobrecarga de procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Procedimientos de solución de problemas](../../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)   
 [Cómo: Definir varias versiones de un procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-multiple-versions-of-a-procedure.md)   
 [Cómo: Llamar a un procedimiento sobrecargado](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-overloaded-procedure.md)   
 [Cómo: Sobrecargar un procedimiento que toma parámetros opcionales](../../../../visual-basic/programming-guide/language-features/procedures/how-to-overload-a-procedure-that-takes-optional-parameters.md)   
 [Resolución de sobrecargas](../../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)