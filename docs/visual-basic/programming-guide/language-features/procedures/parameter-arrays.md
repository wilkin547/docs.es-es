---
description: 'Más información sobre: matrices de parámetros (Visual Basic)'
title: Matrices de parámetros
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
ms.openlocfilehash: e71524d9d62f0ece3a8310934eba15e9db16aaa1
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100427588"
---
# <a name="parameter-arrays-visual-basic"></a>Matrices de parámetros (Visual Basic)

Normalmente, no se puede llamar a un procedimiento con más argumentos de los especificados en la declaración de procedimiento. Si necesita un número indefinido de argumentos, puede declarar una *matriz de parámetros*, que permite que un procedimiento acepte una matriz de valores para un parámetro. No es necesario conocer el número de elementos de la matriz de parámetros al definir el procedimiento. Cada llamada al procedimiento determina el tamaño de la matriz de forma individual.  
  
## <a name="declaring-a-paramarray"></a>Declaración de ParamArray  

 La palabra clave [ParamArray](../../../language-reference/modifiers/paramarray.md) se utiliza para denotar una matriz de parámetros en la lista de parámetros. Se aplican las reglas siguientes:  
  
- Un procedimiento solo puede definir una matriz de parámetros y debe ser el último parámetro de la definición de procedimiento.  
  
- La matriz de parámetros debe pasarse por valor. Se recomienda incluir explícitamente la palabra clave [ByVal](../../../language-reference/modifiers/byval.md) en la definición de procedimiento.  
  
- La matriz de parámetros es opcional de forma automática. Su valor predeterminado es una matriz unidimensional vacía del tipo de elemento de la matriz de parámetros.  
  
- Deben ser necesarios todos los parámetros que preceden a la matriz de parámetros. La matriz de parámetros debe ser el único parámetro opcional.  
  
## <a name="calling-a-paramarray"></a>Llamar a ParamArray  

 Cuando se llama a un procedimiento que define una matriz de parámetros, se puede proporcionar el argumento de cualquiera de las maneras siguientes:  
  
- Nothing, es decir, puede omitir el argumento [ParamArray](../../../language-reference/modifiers/paramarray.md) . En este caso, se pasa una matriz vacía al procedimiento. Si se pasa explícitamente la palabra clave [Nothing](../../../language-reference/nothing.md) , se pasa una matriz null al procedimiento y se puede producir una excepción NullReferenceException si el procedimiento llamado no comprueba esta condición.
  
- Una lista de un número arbitrario de argumentos, separados por comas. El tipo de datos de cada argumento se debe poder convertir implícitamente al `ParamArray` tipo de elemento.  
  
- Matriz con el mismo tipo de elemento que el tipo de elemento de la matriz de parámetros.  
  
 En todos los casos, el código del procedimiento trata la matriz de parámetros como una matriz unidimensional con elementos del mismo tipo de datos que el `ParamArray` tipo de datos.  
  
> [!IMPORTANT]
> Siempre que se trata de una matriz que puede ser indefinidamente grande, existe el riesgo de que se produzca una gran cantidad de capacidad interna de la aplicación. Si acepta una matriz de parámetros, debe probar el tamaño de la matriz que le ha pasado el código de llamada. Siga los pasos adecuados si es demasiado grande para la aplicación. Para más información, consulte [Matrices](../arrays/index.md).  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se define y se llama a la función `calcSum` . El `ParamArray` modificador del parámetro `args` permite que la función acepte un número variable de argumentos.  
  
 [!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]  
  
 En el ejemplo siguiente se define un procedimiento con una matriz de parámetros y se generan los valores de todos los elementos de matriz pasados a la matriz de parámetros.  
  
 [!code-vb[VbVbcnProcedures#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#48)]  
  
 [!code-vb[VbVbcnProcedures#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#49)]  
  
## <a name="see-also"></a>Consulte también

- <xref:Microsoft.VisualBasic.Information.UBound%2A>
- [Procedimientos](./index.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Pasar argumentos por valor y por referencia](./passing-arguments-by-value-and-by-reference.md)
- [Paso de argumentos por posición o por nombre](./passing-arguments-by-position-and-by-name.md)
- [Parámetros opcionales](./optional-parameters.md)
- [Sobrecarga de procedimientos](./procedure-overloading.md)
- [Matrices](../arrays/index.md)
- [Opcional](../../../language-reference/modifiers/optional.md)
