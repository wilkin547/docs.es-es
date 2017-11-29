---
title: "Cómo: Inicializar una variable de matriz en Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], initializing
- arrays [Visual Basic], variables
- arrays [Visual Basic], initializing
- arrays [Visual Basic], declaring
ms.assetid: aadd7a60-7ca4-4608-b986-091f19e7fc10
caps.latest.revision: "42"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3ccdbed601d3fa87acb0833bc153c199b17a4eba
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-initialize-an-array-variable-in-visual-basic"></a>Cómo: Inicializar una variable de matriz en Visual Basic
Inicializar una variable de matriz mediante la inclusión de una matriz literal en una `New` cláusula y especificar los valores iniciales de la matriz. Puede especificar el tipo o permitir que se pueden inferir de los valores del literal de matriz. Para obtener más información acerca de cómo se deduce el tipo, vea "Rellenar una matriz con valores iniciales" en [matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
### <a name="to-initialize-an-array-variable-by-using-an-array-literal"></a>Para inicializar una variable de matriz mediante un literal de matriz  
  
-   En el `New` cláusula, o cuando se asigna el valor de matriz, proporcione los valores de elementos entre llaves (`{}`). En el ejemplo siguiente se muestra varias maneras de declarar, crear e inicializar una variable para contener una matriz que contiene elementos de tipo `Char`.  
  
     [!code-vb[VbVbalrArrays#16](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_1.vb)]  
  
     Después de que se ejecuta cada instrucción, la matriz que se crea tiene una longitud de 3, con elementos en el índice 0 hasta el índice 2 que contiene los valores iniciales. Si proporciona el límite superior y los valores, debe incluir un valor para cada elemento desde el índice 0 hasta el límite superior.  
  
     Tenga en cuenta que no es necesario especificar el límite superior del índice si proporciona valores de elemento en un literal de matriz. Si no se especifica ningún límite superior, el tamaño de la matriz se deduce en función del número de valores en el literal de matriz.  
  
### <a name="to-initialize-a-multidimensional-array-variable-by-using-array-literals"></a>Para inicializar una variable de matriz multidimensional con literales de matriz  
  
-   Anide los valores entre llaves (`{}`) dentro de llaves. Asegúrese de que los literales de matriz anidados que todos deducir como matrices del mismo tipo y longitud. El ejemplo de código siguiente muestra varios ejemplos de inicialización de matriz multidimensional.  
  
     [!code-vb[VbVbalrArrays#17](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_2.vb)]  
  
-   Explícitamente puede especificar los límites de matriz, o dejarlos fuera y hacer que el compilador deduzca los límites de matriz basados en los valores del literal de matriz. Si proporciona los límites superiores y los valores, debe incluir un valor para cada elemento desde el índice 0 hasta el límite superior de cada dimensión. En el ejemplo siguiente se muestra varias maneras de declarar, crear e inicializar una variable para contener una matriz bidimensional con elementos de tipo`Short`  
  
     [!code-vb[VbVbalrArrays#18](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_3.vb)]  
  
     Después de que se ejecuta cada instrucción, la matriz creada contiene seis elementos inicializados que tienen índices `(0,0)`, `(0,1)`, `(0,2)`, `(1,0)`, `(1,1)`, y `(1,2)`. Cada ubicación de la matriz contiene el valor `10`.  
  
-   En el ejemplo siguiente se recorre en iteración una matriz multidimensional. En una aplicación de consola de Windows que se escribe en Visual Basic, pegue el código dentro de la `Sub Main()` método. Los comentarios de la última muestran la salida.  
  
     [!code-vb[VbVbalrArrays#31](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_4.vb)]  
  
### <a name="to-initialize-a-jagged-array-variable-by-using-array-literals"></a>Para inicializar una variable de matriz escalonada mediante literales de matriz  
  
-   Anidar los valores de objeto dentro de llaves (`{}`). Aunque también puede anidar los literales de matriz que especifican matrices de longitudes diferentes, en el caso de una matriz escalonada, asegúrese que los literales de matriz anidados se encierran entre paréntesis (`()`). Los paréntesis fuerzan la evaluación de los literales de matriz anidados y las matrices resultantes se utilizan como los valores iniciales de la matriz escalonada. En el ejemplo de código siguiente se muestra dos ejemplos de inicialización de matriz escalonada.  
  
     [!code-vb[VbVbalrArrays#19](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_5.vb)]  
  
-   En el ejemplo siguiente se recorre en iteración una matriz escalonada. En una aplicación de consola de Windows que se escribe en Visual Basic, pegue el código dentro de la `Sub Main()` método.  El último comentarios en el código muestran la salida.  
  
     [!code-vb[VbVbalrArrays#32](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_6.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [Solución de problemas de matrices](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
