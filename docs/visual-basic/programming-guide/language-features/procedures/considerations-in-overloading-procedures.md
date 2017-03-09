---
title: "Consideraciones sobre la sobrecarga de procedimientos (Visual Basic) | Microsoft Docs"
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
  - "argumentos [Visual Basic], opcionales"
  - "argumentos [Visual Basic], matrices de parámetros"
  - "sobrecarga de funciones, sobrecargas implícitas para ParamArray"
  - "sobrecarga de funciones, restricciones"
  - "sobrecarga de funciones, programación sin tipos"
  - "Option Explicit (instrucción)"
  - "argumentos opcionales, sobrecargar"
  - "ParamArray (palabra clave), argumentos y signaturas"
  - "ParamArray (palabra clave), matrices de parámetros"
  - "ParamArray (palabra clave), signaturas"
  - "matrices de parámetros, sobrecargar argumentos"
  - "listas de parámetros"
  - "parámetros, listas"
  - "sobrecarga de procedimientos, consideraciones"
  - "procedimientos, sobrecargar"
  - "procedimientos, listas de parámetros"
  - "restricciones, sobrecargar procedimientos"
  - "signaturas, ParamArray (argumentos)"
  - "signaturas, procedimiento"
  - "programación sin tipos"
  - "código de Visual Basic, listas de parámetros"
  - "código de Visual Basic, procedimientos"
ms.assetid: a2001248-10d0-42c5-b0ce-eeedc987319f
caps.latest.revision: 26
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 26
---
# Consideraciones sobre la sobrecarga de procedimientos (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Cuando se sobrecarga un procedimiento, debe utilizarse una *firma* diferente en cada versión sobrecargada.  Normalmente esto significa que cada versión debe especificar una lista de parámetros diferente.  Para obtener más información, vea "Firmas diferentes" en [Sobrecarga de procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).  
  
 Se puede sobrecargar un procedimiento `Function` con un procedimiento `Sub`, y viceversa, a condición de que sus firmas sean diferentes.  Dos sobrecargas no pueden diferir únicamente en que una tenga un valor devuelto y la otra no.  
  
 Se puede sobrecargar una propiedad del mismo modo que se sobrecarga un procedimiento, pero también con las mismas restricciones.  Sin embargo, no se puede sobrecargar un procedimiento con una propiedad, o viceversa.  
  
## Alternativas a las versiones sobrecargadas  
 A veces existen alternativas a las versiones sobrecargadas, es especial cuando la presencia de argumentos es opcional o su número es variable.  
  
 Tenga presente que los argumentos opcionales no se admiten necesariamente en todos los lenguajes y que las matrices de parámetros están limitadas a [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  Si se está escribiendo un procedimiento y es probable que un código escrito en diferentes lenguajes llame a este procedimiento, las versiones sobrecargadas ofrecen la mayor flexibilidad.  
  
### Sobrecargas y argumentos opcionales  
 Cuando el código de llamada puede proporcionar u omitir uno o varios argumentos, se pueden definir varias versiones sobrecargadas o utilizar parámetros opcionales.  
  
#### Cuándo utilizar versiones sobrecargadas  
 Puede considerar la posibilidad de definir una serie de versiones sobrecargadas en los casos siguientes:  
  
-   La lógica del código del procedimiento difiere significativamente en función de si el código de llamada proporciona o no un argumento opcional.  
  
-   El código del procedimiento no puede probar con seguridad si el código de llamada ha proporcionado un argumento opcional.  Esto ocurre, por ejemplo, si no se puede esperar que el código de llamada proporcione un candidato posible a un valor predeterminado.  
  
#### Cuándo utilizar parámetros opcionales  
 Es posible que prefiera utilizar uno o varios parámetros opcionales en los siguientes casos:  
  
-   La única acción necesaria cuando el código de llamada no proporciona un argumento opcional es establecer el parámetro en un valor predeterminado.  En una situación como esta, el código del procedimiento puede resultar menos complicado si se define una única versión con uno o varios parámetros `Optional`.  
  
 Para obtener más información, vea [Parámetros opcionales](../../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).  
  
### Sobrecargas y ParamArrays  
 Cuando el código de llamada puede pasar un número variable de argumentos, puede definir varias versiones sobrecargadas o utilizar una matriz de parámetros.  
  
#### Cuándo utilizar versiones sobrecargadas  
 Puede considerar la posibilidad de definir una serie de versiones sobrecargadas en los casos siguientes:  
  
-   Sabe que el código de llamada nunca pasa más que un pequeño número de valores a la matriz de parámetros.  
  
-   La lógica del código del procedimiento difiere significativamente en función de la cantidad de valores que transfiere el código de llamada.  
  
-   El código de llamada puede pasar valores de tipos de datos diferentes.  
  
#### Cuándo utilizar una matriz de parámetros  
 Conviene utilizar un parámetro `ParamArray` en los casos siguientes:  
  
-   No se puede predecir cuántos valores puede pasar el código de llamada a la matriz de parámetros, y puede tratarse de un número elevado.  
  
-   La lógica del procedimiento se presta a recorrer en iteración todos los valores que transfiere el código de llamada, efectuando fundamentalmente las mismas operaciones en cada valor.  
  
 Para obtener más información, vea [Matrices de parámetros](../../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).  
  
## Sobrecargas implícitas de parámetros opcionales  
 Un procedimiento con un parámetro [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) equivale a dos procedimientos sobrecargados, uno con el parámetro opcional y otro sin él.  No puede sobrecargar este tipo de procedimiento con una lista de parámetros que se corresponda con cualquiera de ellos.  Las siguientes declaraciones ilustran este comportamiento:  
  
 [!code-vb[VbVbcnProcedures#58](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/considerations-in-overlo_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#60](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/considerations-in-overlo_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#61](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/considerations-in-overlo_3.vb)]  
  
 Existe un conjunto de sobrecargas implícitas para un procedimiento con varios argumentos opcionales, a las que se llega por una lógica similar a la del ejemplo anterior.  
  
## Sobrecargas implícitas de un parámetro ParamArray  
 El compilador considera que un procedimiento con un parámetro [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) tiene un número infinito de sobrecargas, que se diferencian entre sí por la información que el código de llamada pasa a la matriz de parámetros, como se muestra a continuación:  
  
-   Una sobrecarga cuando el código de llamada no proporciona ningún argumento a `ParamArray`  
  
-   Una sobrecarga cuando el código de llamada proporciona una matriz unidimensional del tipo de elemento `ParamArray`  
  
-   Para cada entero positivo, una sobrecarga cuando el código de llamada pasa ese número de argumentos, todos del tipo de elemento `ParamArray`  
  
 Las siguientes declaraciones ilustran estas sobrecargas implícitas:  
  
 [!code-vb[VbVbcnProcedures#68](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/considerations-in-overlo_4.vb)]  
  
 [!code-vb[VbVbcnProcedures#70](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/considerations-in-overlo_5.vb)]  
  
 No puede sobrecargar este tipo de procedimiento con una lista de parámetros que tome una matriz unidimensional para la matriz de parámetros.  Sin embargo, puede utilizar las firmas de las otras sobrecarga implícitas.  Las siguientes declaraciones ilustran este comportamiento:  
  
 [!code-vb[VbVbcnProcedures#71](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/considerations-in-overlo_6.vb)]  
  
## Programación sin tipos como alternativa a la sobrecarga  
 Si desea permitir que el código de llamada pasar tipos de datos diferentes a un parámetro, un enfoque alternativo es programación sin tipos.  Puede establecer el modificador de comprobación de tipo en `Off` con la opción del compilador [Option Strict \(Instrucción\)](../../../../visual-basic/language-reference/statements/option-strict-statement.md) u [\/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md).  No tiene que declarar después el tipo de datos del parámetro.  No obstante, este planteamiento presenta estas desventajas en comparación con la sobrecarga:  
  
-   La programación sin tipos hace que la ejecución del código sea menos eficiente.  
  
-   El procedimiento debe comprobar todos los tipos de datos que anticipe que se le van a pasar.  
  
-   El compilador no puede indicar que se ha producido un error si el código de llamada pasa un tipo de datos que el procedimiento no admite.  
  
## Vea también  
 [Procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Procedimientos de solución de problemas](../../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)   
 [Cómo: Definir varias versiones de un procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-multiple-versions-of-a-procedure.md)   
 [Cómo: Llamar a un procedimiento sobrecargado](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-overloaded-procedure.md)   
 [Cómo: Sobrecargar un procedimiento que toma parámetros opcionales](../../../../visual-basic/programming-guide/language-features/procedures/how-to-overload-a-procedure-that-takes-optional-parameters.md)   
 [Cómo: Sobrecargar un procedimiento que toma un número indefinido de parámetros](../../../../visual-basic/programming-guide/language-features/procedures/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)   
 [Resolución de sobrecargas](../../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)   
 [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)