---
title: "Resoluci&#243;n de sobrecarga (Visual Basic) | Microsoft Docs"
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
  - "resolución de sobrecargas"
  - "sobrecargas, resolución"
  - "sobrecarga de procedimientos, resolución de sobrecargas"
  - "procedimientos, llamar"
  - "procedimientos, sobrecargar"
  - "signaturas, procedimiento"
  - "código de Visual Basic, procedimientos"
ms.assetid: 766115d1-4352-45fb-859f-6063e0de0ec0
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# Resoluci&#243;n de sobrecarga (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Cuando el compilador de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] encuentra una llamada a un procedimiento que está definido en varias versiones sobrecargadas, debe decidir a qué sobrecarga tiene que llamar.  Para ello, sigue estos pasos:  
  
1.  **Accesibilidad.** Elimina cualquier sobrecarga con un nivel de acceso que impida que el código de llamada pueda invocarla.  
  
2.  **Número de parámetros.** Elimina cualquier sobrecarga que defina un número de parámetros que no coincida con los que se suministran en la llamada.  
  
3.  **Tipos de datos de parámetros.** El compilador da prioridad a los métodos de instancia sobre los métodos de extensión.  Si se encuentra un método de instancia que exige sólo conversiones de ampliación que coincidan con la llamada al procedimiento, se descartan todos los métodos de extensión y el compilador sigue sólo con los candidatos del método de instancia.  Si no se encuentra ningún método de instancia de este tipo, sigue con ambos métodos de instancia y de extensión.  
  
     En esta fase, elimina cualquier sobrecarga para la que los tipos de datos de los argumentos de llamada no se pueden convertir a los tipos definidos en la sobrecarga.  
  
4.  **Conversiones de restricción.** Elimina cualquier sobrecarga que requiera una conversión de restricción de los tipos de argumentos de llamada a los tipos de parámetros definidos.  Esto se aplica si el modificador de comprobación de tipo \([Option Strict \(Instrucción\)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)\) es `On` u `Off`.  
  
5.  **Ampliación mínima.** El compilador considera las sobrecargas restantes en parejas.  En cada pareja, compara los tipos de datos de los parámetros definidos.  Si los tipos de una de las sobrecargas se amplían a los tipos correspondientes de la otra, el compilador elimina la última.  Es decir, conserva la sobrecarga que necesite la menor cantidad de ampliación.  
  
6.  **Candidata única.** Continúa considerando las sobrecargas por partes hasta que sólo quede una y resuelve la llamada en esa sobrecarga.  Si el compilador no puede reducir las sobrecargas a una sola candidata, genera un error.  
  
 La ilustración siguiente muestra el proceso que determina a qué conjunto de versiones sobrecargadas se va a llamar.  
  
 ![Diagrama de flujo de proceso de resolución de sobrecarga](../../../../visual-basic/programming-guide/language-features/procedures/media/overloadres.gif "OverloadRes")  
Resolver entre versiones sobrecargadas  
  
 Este proceso de resolución de las sobrecargas se ilustra en el siguiente ejemplo:  
  
 [!code-vb[VbVbcnProcedures#62](./codesnippet/VisualBasic/overload-resolution_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#63](./codesnippet/VisualBasic/overload-resolution_2.vb)]  
  
 En la primera llamada, el compilador elimina la primera sobrecarga porque el tipo del primer argumento \(`Short`\) se restringe al tipo del parámetro correspondiente \(`Byte`\).  A continuación, elimina la tercera sobrecarga porque cada tipo de argumento de la segunda sobrecarga \(`Short` y `Single`\) se amplía al tipo correspondiente a la tercera sobrecarga \(`Integer` y `Single`\).  La segunda sobrecarga requiere una ampliación menor, y por eso el compilador la utiliza en la llamada.  
  
 En la segunda llamada, el compilador no puede eliminar ninguna sobrecarga teniendo en cuenta la restricción.  Elimina la tercera sobrecarga por el mismo motivo por el que la eliminó en la primera llamada, porque puede llamar a la segunda sobrecarga con una ampliación menor de los tipos de argumentos.  Sin embargo, el compilador no puede decidirse entre la primera y la segunda sobrecarga.  Cada una de ellas tiene un tipo de parámetro definido que se amplía al tipo correspondiente de la otra \(`Byte` a `Short`, pero `Single` a `Double`\).  Por lo tanto, el compilador genera un error de resolución de sobrecarga.  
  
## Argumentos opcionales sobrecargados y ParamArray  
 Si dos sobrecargas de un procedimiento tienen firmas idénticas excepto en que el último argumento se declara [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) en una sobrecarga y [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) en la otra, el compilador resuelve la llamada a dicho procedimiento de la manera siguiente:  
  
|||  
|-|-|  
|Si la llamada suministra el último argumento como|El compilador resuelve la llamada a la sobrecarga declarando el último argumento como|  
|Ningún valor \(argumento omitido\)|`Optional`|  
|Un valor único|`Optional`|  
|Dos o más valores en una lista separada por comas|`ParamArray`|  
|Una matriz de cualquier longitud \(incluida una matriz vacía\)|`ParamArray`|  
  
## Vea también  
 [Parámetros opcionales](../../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)   
 [Matrices de parámetros](../../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)   
 [Sobrecarga de procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Procedimientos de solución de problemas](../../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)   
 [Cómo: Definir varias versiones de un procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-multiple-versions-of-a-procedure.md)   
 [Cómo: Llamar a un procedimiento sobrecargado](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-overloaded-procedure.md)   
 [Cómo: Sobrecargar un procedimiento que toma parámetros opcionales](../../../../visual-basic/programming-guide/language-features/procedures/how-to-overload-a-procedure-that-takes-optional-parameters.md)   
 [Cómo: Sobrecargar un procedimiento que toma un número indefinido de parámetros](../../../../visual-basic/programming-guide/language-features/procedures/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)   
 [Consideraciones sobre la sobrecarga de procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)   
 [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)   
 [métodos de extensión.](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)