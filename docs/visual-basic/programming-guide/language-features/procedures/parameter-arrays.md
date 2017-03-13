---
title: "Matrices de par&#225;metros (Visual Basic) | Microsoft Docs"
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
  - "argumentos [Visual Basic], matrices de parámetros"
  - "matrices [Visual Basic], matrices de parámetros"
  - "ParamArray (palabra clave), matrices de parámetros"
  - "matrices de parámetros, acerca de las matrices de parámetros"
  - "parámetros, matrices de parámetros"
  - "procedimientos, número indefinido de valores de argumentos"
  - "código de Visual Basic, procedimientos"
ms.assetid: c43edfae-9114-4096-9ebc-8c5c957a1067
caps.latest.revision: 26
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 26
---
# Matrices de par&#225;metros (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Normalmente no es posible llamar a un procedimiento con un número de argumentos superior al especificado en la declaración del procedimiento.  Si se necesita un número indeterminado de argumentos, puede declararse una *matriz de parámetros*, que permite que un procedimiento acepte una matriz de valores en un parámetro.  No es necesario conocer el número de elementos de la matriz de parámetros en el momento de definir el procedimiento.  El tamaño de la matriz se determina individualmente en cada llamada al procedimiento.  
  
## Declarar una matriz de parámetros  
 Utilice la palabra clave [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) para denotar una matriz de parámetros en la lista de parámetros.  Se aplican las siguientes reglas:  
  
-   Un procedimiento puede definir únicamente una matriz de parámetros, que debe ser el último parámetro en la definición del procedimiento.  
  
-   La matriz de parámetros debe pasarse por valor.  Es un hábito de programación recomendado incluir de manera explícita la palabra clave [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) en la definición del procedimiento.  
  
-   La matriz de parámetros es opcional de forma automática.  Su valor predeterminado es una matriz unidimensional vacía del tipo de elemento de la matriz de parámetros.  
  
-   Todos los parámetros que preceden a la matriz de parámetros deben ser obligatorios.  La matriz de parámetros debe ser el único parámetro opcional.  
  
## Llamar a un lista de parámetros  
 Cuando se llama a un procedimiento que define una matriz de parámetros, se puede proporcionar el argumento de los siguientes modos:  
  
-   Ninguno, es decir, puede omitirse el argumento [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md).  En este caso, se pasará una matriz vacía al procedimiento.  También puede pasarse la palabra clave [Nothing](../../../../visual-basic/language-reference/nothing.md), obteniéndose el mismo efecto.  
  
-   Una lista con un número arbitrario de argumentos, separados por comas.  El tipo de los datos de cada argumento debe poder convertirse implícitamente al tipo de elemento `ParamArray`.  
  
-   Una matriz con el mismo tipo de elemento que la matriz de parámetros.  
  
 En todas las clases, el código del procedimiento debe considerar la matriz de parámetros una matriz unidimensional, cuyos elementos deben tener el mismo tipo de datos que `ParamArray`.  
  
> [!IMPORTANT]
>  Si se trabaja con matrices cuyo tamaño es excesivamente grande, existe el riesgo de sobrecargar alguna capacidad interna de la aplicación.  Si acepta una matriz de parámetros, debe comprobar el tamaño de la matriz que el código de llamada ha transferido.  Tome las medidas necesarias si la matriz es demasiado grande para la aplicación.  Para obtener más información, vea [Matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## Ejemplo  
 El ejemplo siguiente se define y se llama a la función `calcSum`.  El modificador de `ParamArray` para el parámetro `args` permite que la función acepte un número variable de argumentos.  
  
 [!code-vb[VbVbalrStatements#26](../../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/parameter-arrays_1.vb)]  
  
 En el ejemplo siguiente se define un procedimiento con una matriz de parámetros y se generan los valores de todos los elementos de matriz pasados a la matriz de parámetros.  
  
 [!code-vb[VbVbcnProcedures#48](./codesnippet/VisualBasic/parameter-arrays_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#49](./codesnippet/VisualBasic/parameter-arrays_3.vb)]  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Information.UBound%2A>   
 [Procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Pasar argumentos por valor y por referencia](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Pasar argumentos por posición o por nombre](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)   
 [Parámetros opcionales](../../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)   
 [Sobrecarga de procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [Optional](../../../../visual-basic/language-reference/modifiers/optional.md)