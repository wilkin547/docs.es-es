---
title: Procedimiento para inicializar una variable de matriz
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], initializing
- arrays [Visual Basic], variables
- arrays [Visual Basic], initializing
- arrays [Visual Basic], declaring
ms.assetid: aadd7a60-7ca4-4608-b986-091f19e7fc10
ms.openlocfilehash: 1add054a6cb6468f4581f92ca3a258c5b0cdc77d
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058864"
---
# <a name="how-to-initialize-an-array-variable-in-visual-basic"></a>Cómo: Inicializar una variable de matriz en Visual Basic

Para inicializar una variable de matriz, incluya un literal de matriz en una `New` cláusula y especifique los valores iniciales de la matriz. Puede especificar el tipo o permitir que se infiera de los valores del literal de matriz. Para obtener más información sobre cómo se deduce el tipo, vea "rellenar una matriz con valores iniciales" en [matrices](index.md).  
  
### <a name="to-initialize-an-array-variable-by-using-an-array-literal"></a>Para inicializar una variable de matriz mediante un literal de matriz  
  
- En la `New` cláusula o al asignar el valor de matriz, proporcione los valores de elemento entre llaves ( `{}` ). En el ejemplo siguiente se muestran varias maneras de declarar, crear e inicializar una variable que contenga una matriz con elementos de tipo `Char` .  
  
     [!code-vb[VbVbalrArrays#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#16)]  
  
     Una vez ejecutada cada instrucción, la matriz que se crea tiene una longitud de 3, con elementos en el índice 0 hasta el índice 2 que contiene los valores iniciales. Si proporciona el límite superior y los valores, debe incluir un valor para cada elemento desde el índice 0 hasta el límite superior.  
  
     Tenga en cuenta que no es necesario especificar el límite superior del índice si se proporcionan valores de elemento en un literal de matriz. Si no se especifica ningún límite superior, el tamaño de la matriz se deduce en función del número de valores del literal de matriz.  
  
### <a name="to-initialize-a-multidimensional-array-variable-by-using-array-literals"></a>Para inicializar una variable de matriz multidimensional utilizando literales de matriz  
  
- Anide los valores entre llaves ( `{}` ) entre llaves. Asegúrese de que todos los literales de matriz anidados se deducen como matrices del mismo tipo y longitud. En el ejemplo de código siguiente se muestran varios ejemplos de inicialización de la matriz multidimensional.  
  
     [!code-vb[VbVbalrArrays#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#17)]  
  
- Puede especificar explícitamente los límites de la matriz o dejarlos fuera y hacer que el compilador deduzca los límites de la matriz basándose en los valores del literal de matriz. Si proporciona los límites superiores y los valores, debe incluir un valor para cada elemento desde el índice 0 hasta el límite superior de cada dimensión. En el ejemplo siguiente se muestran varias maneras de declarar, crear e inicializar una variable para que contenga una matriz bidimensional que tiene elementos de tipo `Short`  
  
     [!code-vb[VbVbalrArrays#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#18)]  
  
     Una vez ejecutada cada instrucción, la matriz creada contiene seis elementos inicializados que tienen índices `(0,0)` , `(0,1)` , `(0,2)` , `(1,0)` , `(1,1)` y `(1,2)` . Cada ubicación de la matriz contiene el valor `10` .  
  
- En el ejemplo siguiente se recorre en iteración una matriz multidimensional. En una aplicación de consola de Windows escrita en Visual Basic, pegue el código dentro del `Sub Main()` método. Los últimos Comentarios muestran el resultado.  
  
     [!code-vb[VbVbalrArrays#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#31)]  
  
### <a name="to-initialize-a-jagged-array-variable-by-using-array-literals"></a>Para inicializar una variable de matriz escalonada mediante literales de matriz  
  
- Anide los valores de objeto entre llaves ( `{}` ). Aunque también puede anidar literales de matriz que especifican matrices de longitudes diferentes, en el caso de una matriz escalonada, asegúrese de que los literales de matriz anidados se incluyen entre paréntesis ( `()` ). Los paréntesis fuerzan la evaluación de los literales de matriz anidados y las matrices resultantes se utilizan como valores iniciales de la matriz escalonada. En el ejemplo de código siguiente se muestran dos ejemplos de inicialización de matriz escalonada.  
  
     [!code-vb[VbVbalrArrays#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#19)]  
  
- En el ejemplo siguiente se recorre en iteración una matriz escalonada. En una aplicación de consola de Windows escrita en Visual Basic, pegue el código dentro del `Sub Main()` método.  Los últimos Comentarios del código muestran la salida.  
  
     [!code-vb[VbVbalrArrays#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#32)]  
  
## <a name="see-also"></a>Vea también

- [Matrices](index.md)
- [Solución de problemas de matrices](troubleshooting-arrays.md)
