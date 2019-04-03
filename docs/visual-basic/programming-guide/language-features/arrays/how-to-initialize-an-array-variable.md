---
title: Filtrar Inicializar una Variable de matriz en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], initializing
- arrays [Visual Basic], variables
- arrays [Visual Basic], initializing
- arrays [Visual Basic], declaring
ms.assetid: aadd7a60-7ca4-4608-b986-091f19e7fc10
ms.openlocfilehash: 4aa783d6179c72760a12d0259d587b5b38bb9140
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832247"
---
# <a name="how-to-initialize-an-array-variable-in-visual-basic"></a>Filtrar Inicializar una Variable de matriz en Visual Basic
Inicializar una variable de matriz mediante la inclusión de un literal de matriz en un `New` cláusula y especifique los valores iniciales de la matriz. Puede especificar el tipo o permitir que se deduzca de los valores del literal de matriz. Para obtener más información acerca de cómo se deduce el tipo, vea "Rellenar una matriz con valores iniciales" en [matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
### <a name="to-initialize-an-array-variable-by-using-an-array-literal"></a>Para inicializar una variable de matriz mediante un literal de matriz  
  
-   En el `New` cláusula, o cuando se asigna el valor de matriz, proporcione los valores de elementos entre llaves (`{}`). El ejemplo siguiente muestra varias maneras de declarar, crear e inicializar una variable para que contenga una matriz que contiene elementos de tipo `Char`.  
  
     [!code-vb[VbVbalrArrays#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#16)]  
  
     Tras la ejecución de cada instrucción, la matriz creada tiene una longitud de 3, con elementos en el índice 0 hasta el índice 2 que contiene los valores iniciales. Si proporciona el límite superior y los valores, debe incluir un valor para cada elemento desde el índice 0 hasta el límite superior.  
  
     Tenga en cuenta que no es necesario especificar el límite superior del índice si proporciona valores de elemento de un literal de matriz. Si no se especifica ningún límite superior, el tamaño de la matriz se deduce en función del número de valores del literal de matriz.  
  
### <a name="to-initialize-a-multidimensional-array-variable-by-using-array-literals"></a>Para inicializar una variable de matriz multidimensional mediante literales de matriz  
  
-   Anide los valores entre llaves (`{}`) dentro de llaves. Asegúrese de que los literales de matriz anidados que todos deduzcan como matrices del mismo tipo y longitud. El ejemplo de código siguiente muestra varios ejemplos de inicialización de matriz multidimensional.  
  
     [!code-vb[VbVbalrArrays#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#17)]  
  
-   Explícitamente puede especificar los límites de matriz, o dejarlos fuera y hacer que el compilador deduzca los límites de matriz basándose en los valores del literal de matriz. Si proporciona los límites superiores y los valores, debe incluir un valor para cada elemento desde el índice 0 hasta el límite superior de cada dimensión. El ejemplo siguiente muestra varias maneras de declarar, crear e inicializar una variable para que contenga una matriz bidimensional con elementos de tipo `Short`  
  
     [!code-vb[VbVbalrArrays#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#18)]  
  
     Tras la ejecución de cada instrucción, la matriz creada contiene seis elementos inicializados que tienen índices `(0,0)`, `(0,1)`, `(0,2)`, `(1,0)`, `(1,1)`, y `(1,2)`. Cada ubicación de la matriz contiene el valor `10`.  
  
-   El ejemplo siguiente se recorre en iteración una matriz multidimensional. En una aplicación de consola de Windows que se escribe en Visual Basic, pegue el código dentro de la `Sub Main()` método. Los últimos comentarios muestran el resultado.  
  
     [!code-vb[VbVbalrArrays#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#31)]  
  
### <a name="to-initialize-a-jagged-array-variable-by-using-array-literals"></a>Para inicializar una variable de matriz escalonada mediante literales de matriz  
  
-   Anide los valores de objeto dentro de llaves (`{}`). Aunque también puede anidar los literales de matriz que especifican matrices de longitudes diferentes, en el caso de una matriz escalonada, asegúrese de que los literales de matriz anidados se incluyan entre paréntesis (`()`). Los paréntesis fuerzan la evaluación de los literales de matriz anidados y las matrices resultantes se utilizan como los valores iniciales de la matriz escalonada. El ejemplo de código siguiente muestra dos ejemplos de inicialización de matriz escalonada.  
  
     [!code-vb[VbVbalrArrays#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#19)]  
  
-   El ejemplo siguiente se recorre en iteración una matriz escalonada. En una aplicación de consola de Windows que se escribe en Visual Basic, pegue el código dentro de la `Sub Main()` método.  Los últimos comentarios en el código muestran la salida.  
  
     [!code-vb[VbVbalrArrays#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#32)]  
  
## <a name="see-also"></a>Vea también

- [Matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Solución de problemas de matrices](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
