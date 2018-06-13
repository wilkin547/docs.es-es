---
title: Solucionar problemas de matrices (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting arrays
- arrays [Visual Basic], initialization errors
- troubleshooting Visual Basic, arrays
- arrays [Visual Basic], compilation errors
- arrays [Visual Basic], declaration errors
- arrays [Visual Basic], troubleshooting
ms.assetid: f4e971c7-c0a4-4ed7-a77a-8d71039f266f
ms.openlocfilehash: 4ab6d376ad8652e460e33c4f2c3285e8c80286fe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654273"
---
# <a name="troubleshooting-arrays-visual-basic"></a>Solucionar problemas de matrices (Visual Basic)
Esta página enumera algunos problemas comunes que pueden producirse al trabajar con matrices.  
  
## <a name="compilation-errors-declaring-and-initializing-an-array"></a>Errores de compilación declarar e inicializar una matriz  
 Pueden surgir errores de compilación de falta de comprensión de las reglas para declarar, crear e inicializar matrices. Las causas más comunes de errores son los siguientes:  
  
-   Proporcionar un [New (operador)](../../../../visual-basic/language-reference/operators/new-operator.md) cláusula después de especificar longitudes de dimensión en la declaración de variable de matriz. Las líneas de código siguientes muestran declaraciones no válidas de este tipo.  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
-   Especificar longitudes de dimensión más de la matriz de nivel superior de una matriz escalonada. La siguiente línea de código muestra una declaración no válida de este tipo.  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
-   Si se omite la `New` palabra clave al especificar los valores del elemento. La siguiente línea de código muestra una declaración no válida de este tipo.  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
-   Proporcionar un `New` cláusula sin llaves (`{}`). Las líneas de código siguientes muestran declaraciones no válidas de este tipo.  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## <a name="accessing-an-array-out-of-bounds"></a>Obtener acceso a una matriz fuera de límites  
 El proceso de inicialización de una matriz asigna un límite superior y un límite inferior a cada dimensión. Cada acceso a un elemento de la matriz debe especificar un índice válido, o subíndice, para cada dimensión. Si un índice está por debajo de su límite inferior o por encima de su límite superior, un <xref:System.IndexOutOfRangeException> resultados de la excepción. El compilador no puede detectar este tipo de error, por lo que se produce un error en tiempo de ejecución.  
  
### <a name="determining-bounds"></a>Determinar los límites  
 Si otro componente pasa una matriz en el código, por ejemplo como un argumento de procedimiento, se desconoce el tamaño de la matriz o la longitud de sus dimensiones. Siempre debe determinar el límite superior para cada dimensión de una matriz antes de intentar tener acceso a los elementos. Si la matriz se ha creado por otros medios distintos a un de Visual Basic `New` cláusula, el límite inferior podría ser algo distinto de 0, y es más seguro determinar también ese límite inferior.  
  
### <a name="specifying-the-dimension"></a>Especificar la dimensión  
 Al determinar los límites de una matriz multidimensional, tenga cuidado de cómo especificar la dimensión. El `dimension` parámetros de la <xref:System.Array.GetLowerBound%2A> y <xref:System.Array.GetUpperBound%2A> métodos están basadas en 0, mientras el `Rank` parámetros de Visual Basic <xref:Microsoft.VisualBasic.Information.LBound%2A> y <xref:Microsoft.VisualBasic.Information.UBound%2A> funciones están basados en 1.  
  
## <a name="see-also"></a>Vea también  
 [Matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [Cómo: Inicializar una variable de matriz en Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)
