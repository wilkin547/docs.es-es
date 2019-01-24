---
title: Matrices de parámetros (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- parameter arrays [Visual Basic], about parameter arrays
- ParamArray keyword [Visual Basic], parameter arrays
- Visual Basic code, procedures
- parameters [Visual Basic], parameter arrays
- arguments [Visual Basic], parameter arrays
- procedures [Visual Basic], indefinite number of argument values
- arrays [Visual Basic], parameter arrays
ms.assetid: c43edfae-9114-4096-9ebc-8c5c957a1067
ms.openlocfilehash: eac637c0fcaaded25a54332b2f1188876ef5f29a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54711887"
---
# <a name="parameter-arrays-visual-basic"></a>Matrices de parámetros (Visual Basic)
Por lo general, no se puede llamar a un procedimiento con más argumentos de la declaración de procedimiento especifica. Cuando se necesita un número indefinido de argumentos, se puede declarar un *matriz de parámetros*, lo que permite que un procedimiento aceptar una matriz de valores para un parámetro. No es necesario saber el número de elementos de la matriz de parámetros cuando se define el procedimiento. El tamaño de la matriz se determina individualmente por cada llamada al procedimiento.  
  
## <a name="declaring-a-paramarray"></a>Declarar una matriz de parámetros  
 Usa el [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) palabra clave para denotar una matriz de parámetros en la lista de parámetros. Se aplican las siguientes reglas:  
  
-   Un procedimiento puede definir solo una matriz de parámetros y debe ser el último parámetro en la definición del procedimiento.  
  
-   La matriz de parámetros debe pasarse por valor. Lo programación es recomendable incluir explícitamente el [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) palabra clave en la definición del procedimiento.  
  
-   La matriz de parámetros es opcional de forma automática. Su valor predeterminado es una matriz unidimensional vacía del tipo de elemento de la matriz de parámetros.  
  
-   Todos los parámetros que precede a la matriz de parámetros deben ser obligatorios. La matriz de parámetros debe ser el único parámetro opcional.  
  
## <a name="calling-a-paramarray"></a>Una llamada a una matriz de parámetros  
 Cuando se llama a un procedimiento que se define una matriz de parámetros, puede proporcionar el argumento en cualquiera de las maneras siguientes:  
  
-   Nada, es decir, puede omitir el [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) argumento. En este caso, se pasa una matriz vacía para el procedimiento. También puede pasar la [nada](../../../../visual-basic/language-reference/nothing.md) palabra clave, con el mismo efecto.  
  
-   Una lista de un número arbitrario de argumentos, separados por comas. El tipo de datos de cada argumento debe ser implícitamente convertible a la `ParamArray` tipo de elemento.  
  
-   Una matriz con el mismo tipo de elemento como tipo de elemento de la matriz de parámetros.  
  
 En todos los casos, el código dentro del procedimiento considera la matriz de parámetros como una matriz unidimensional con elementos del mismo tipo de datos como el `ParamArray` tipo de datos.  
  
> [!IMPORTANT]
>  Si se trabaja con una matriz que puede ser excesivamente grande, hay un riesgo de sobrecargar alguna capacidad interna de la aplicación. Si acepta una matriz de parámetros, se debe comprobar el tamaño de la matriz que el código que realiza la llamada pasa a él. Si es demasiado grande para su aplicación, tome medidas oportunas. Para obtener más información, consulte [matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente se define y llama a la función `calcSum`. El `ParamArray` modificador para el parámetro `args` permite que la función que acepte un número variable de argumentos.  
  
 [!code-vb[VbVbalrStatements#26](../../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/parameter-arrays_1.vb)]  
  
 El ejemplo siguiente define un procedimiento con una matriz de parámetros y genera los valores de todos los elementos de matriz que se pasa a la matriz de parámetros.  
  
 [!code-vb[VbVbcnProcedures#48](./codesnippet/VisualBasic/parameter-arrays_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#49](./codesnippet/VisualBasic/parameter-arrays_3.vb)]  
  
## <a name="see-also"></a>Vea también
- <xref:Microsoft.VisualBasic.Information.UBound%2A>
- [Procedimientos](./index.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Paso de argumentos por valor y por referencia](./passing-arguments-by-value-and-by-reference.md)
- [Paso de argumentos por posición o por nombre](./passing-arguments-by-position-and-by-name.md)
- [Parámetros opcionales](./optional-parameters.md)
- [Sobrecarga de procedimientos](./procedure-overloading.md)
- [Matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Opcional](../../../../visual-basic/language-reference/modifiers/optional.md)
