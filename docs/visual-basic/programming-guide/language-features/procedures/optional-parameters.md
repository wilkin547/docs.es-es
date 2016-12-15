---
title: "Par&#225;metros opcionales (Visual Basic) | Microsoft Docs"
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
  - "argumentos [Visual Basic], opcionales"
  - "argumentos con nombre, argumentos opcionales"
  - "argumentos opcionales"
  - "argumentos opcionales, argumentos con nombre"
  - "Optional (palabra clave), argumentos opcionales"
  - "parámetros opcionales"
  - "parámetros, opcionales"
  - "procedimientos, argumentos opcionales"
  - "código de Visual Basic, procedimientos"
ms.assetid: 398d2845-1069-4e94-b934-a73b545c8b87
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Par&#225;metros opcionales (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Un parámetro de un procedimiento puede ser opcional si así se especifica y no es necesario proporcionarle argumentos al llamar al procedimiento.  Los *parámetros opcionales* se indican mediante la palabra clave `Optional` en la definición del procedimiento.  Se aplican las siguientes reglas:  
  
-   Todos los parámetros opcionales de la definición del procedimiento deben especificar un valor predeterminado.  
  
-   El valor predeterminado de un parámetro opcional debe ser una expresión constante.  
  
-   Todos los parámetros que vayan a continuación de un parámetro opcional en la definición del procedimiento también deben ser opcionales.  
  
 La siguiente sintaxis muestra una declaración de procedimiento con un parámetro opcional:  
  
```  
Sub sub name(ByVal parameter1 As datatype1, Optional ByVal parameter2 As datatype2 = defaultvalue)  
```  
  
## Llamar a procedimientos con parámetros opcionales  
 Cuando se llama a un procedimiento con un parámetro opcional, se puede elegir si se proporciona o no el argumento.  Si no se proporciona, el procedimiento utiliza el valor predeterminado declarado para dicho parámetro.  
  
 Si se omiten uno o más argumentos opcionales de la lista de argumentos, hay que utilizar comas sucesivas para delimitar sus posiciones.  En el ejemplo de llamada siguiente se suministran los argumentos primero y cuarto, pero no el segundo ni el tercero:  
  
```  
  
sub name(argument 1, , , argument 4)  
```  
  
 En el ejemplo siguiente se realizan algunas llamadas a la función `MsgBox`.  `MsgBox` tiene un parámetro obligatorio y dos parámetros opcionales.  
  
 La primera llamada a `MsgBox` proporciona los tres argumentos en el orden en que `MsgBox` los define.  La segunda llamada únicamente proporciona el argumento obligatorio.  La tercera y la cuarta llamada proporcionan el primer y el tercer argumento.  La tercera llamada lo hace por posición y la llamada cuarta, por nombre.  
  
 [!code-vb[VbVbcnProcedures#47](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/optional-parameters_1.vb)]  
  
## Determinar si un argumento opcional está presente  
 En tiempo de ejecución un procedimiento no puede detectar si un argumento determinado se ha omitido o si el código de llamada ha suministrado de forma explícita el valor predeterminado de dicho argumento.  Si fuese necesario hacer esta distinción, se podría establecer como valor predeterminado un valor improbable.  El siguiente procedimiento define el parámetro opcional  `office` y comprueba si su valor predeterminado,  `QJZ`, ha sido omitido en la llamada:  
  
 [!code-vb[VbVbcnProcedures#46](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/optional-parameters_2.vb)]  
  
 Si el parámetro opcional es un tipo de referencia, como `String`, puede utilizar `Nothing` como valor predeterminado, siempre y cuando éste no sea un valor esperado para el argumento.  
  
## Parámetros opcionales y sobrecarga  
 Otra forma de definir un procedimiento con parámetros opcionales consiste en utilizar una sobrecarga.  Si tiene un parámetro opcional, puede definir dos versiones sobrecargadas del procedimiento, una que acepte el parámetro y otra sin él.  Este planteamiento se complica a medida que aumenta el número de parámetros opcionales.  No obstante, tiene la ventaja de que permite saber con total certeza si el programa de llamada ha suministrado o no cada argumento opcional.  
  
## Vea también  
 [Procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Pasar argumentos por valor y por referencia](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Pasar argumentos por posición o por nombre](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)   
 [Matrices de parámetros](../../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)   
 [Sobrecarga de procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Optional](../../../../visual-basic/language-reference/modifiers/optional.md)   
 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)