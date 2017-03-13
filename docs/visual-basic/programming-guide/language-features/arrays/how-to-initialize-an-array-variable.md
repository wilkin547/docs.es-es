---
title: "C&#243;mo: Inicializar una variable de matriz en Visual Basic | Microsoft Docs"
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
  - "matrices [Visual Basic], declarar"
  - "matrices [Visual Basic], inicializar"
  - "matrices [Visual Basic], variables"
  - "variables [Visual Basic], inicializar"
ms.assetid: aadd7a60-7ca4-4608-b986-091f19e7fc10
caps.latest.revision: 42
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 42
---
# C&#243;mo: Inicializar una variable de matriz en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Para inicializar una variable de matriz incluya un literal de matriz en una cláusula `New` y especifique los valores iniciales de la matriz.  Puede especificar el tipo o permitir que se deduzca de los valores del literal de matriz.  Para obtener más información sobre cómo se deduce el tipo, vea "Rellenar una matriz con valores iniciales" en [Matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
### Para inicializar una variable de matriz mediante un literal de matriz  
  
-   En la cláusula `New`, o al asignar el valor de matriz, proporcione los valores de elementos entre llaves \(`{}`\).  En el ejemplo siguiente se muestran varias maneras de declarar, crear e inicializar una variable para que contenga una matriz con elementos de tipo `Char`.  
  
     [!code-vb[VbVbalrArrays#16](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_1.vb)]  
  
     Tras la ejecución de cada instrucción, la matriz creada tiene una longitud de 3, con elementos desde el índice 0 hasta el índice 2 que contienen los valores iniciales.  Si proporciona el límite superior y los valores, debe incluir un valor para cada elemento desde el índice 0 hasta el límite superior.  
  
     Observe que no tiene que especificar el límite superior del índice si proporciona valores de elementos en un literal de matriz.  Si no se especifica ningún límite superior, el tamaño de la matriz se deduce mediante el número de valores en el literal de matriz.  
  
### Para inicializar una variable de matriz multidimensional mediante literales de matriz  
  
-   Anide los valores entre llaves \(`{}`\).  Asegúrese de que todos los literales de matriz anidados se deduzcan como matrices del mismo tipo y longitud.  En el ejemplo de código siguiente se muestran varios ejemplos de inicialización de una matriz multidimensional.  
  
     [!code-vb[VbVbalrArrays#17](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_2.vb)]  
  
-   Puede especificar explícitamente los límites de la matriz, u omitirlos y dejar que el compilador los deduzca tomando como base los valores en el literal de matriz.  Si proporciona los límites superiores y los valores, debe incluir un valor para cada elemento desde el índice 0 hasta el límite superior en cada dimensión.  En el ejemplo siguiente se muestran varias maneras de declarar, crear e inicializar una variable para que contenga una matriz bidimensional con elementos de tipo `Short`.  
  
     [!code-vb[VbVbalrArrays#18](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_3.vb)]  
  
     Tras la ejecución de cada instrucción, la matriz creada contiene seis elementos inicializados que tienen los índices `(0,0)`, `(0,1)`, `(0,2)`, `(1,0)`, `(1,1)` y `(1,2)`.  Cada ubicación de matriz contiene el valor `10`.  
  
-   En el ejemplo siguiente se recorre en iteración una matriz multidimensional.  En una aplicación de consola de Windows escrita en Visual Basic, pegue el código dentro del método de `Sub Main()`.  Los últimos comentarios muestran el resultado.  
  
     [!code-vb[VbVbalrArrays#31](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_4.vb)]  
  
### Para inicializar una variable de matriz escalonada mediante literales de matriz  
  
-   Anide los valores de objetos entre llaves \(`{}`\).  Aunque también puede anidar los literales de matriz que especifican matrices de longitudes diferentes, en el caso de una matriz escalonada asegúrese de que los literales de matriz anidados se incluyan entre paréntesis \(`()`\).  Los paréntesis fuerzan la evaluación de los literales de matriz anidados y las matrices resultantes se utilizan como valores iniciales de la matriz escalonada.  En el ejemplo de código siguiente se muestran dos ejemplos de inicialización de una matriz escalonada.  
  
     [!code-vb[VbVbalrArrays#19](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_5.vb)]  
  
-   En el ejemplo siguiente se recorre en iteración una matriz escalonada.  En una aplicación de consola de Windows escrita en Visual Basic, pegue el código dentro del método de `Sub Main()`.  Los últimos comentarios en el código muestran el resultado.  
  
     [!code-vb[VbVbalrArrays#32](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_6.vb)]  
  
## Vea también  
 [Matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [Solucionar problemas de matrices](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)