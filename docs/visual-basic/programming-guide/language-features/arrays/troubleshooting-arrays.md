---
title: Solucionar problemas de matrices
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting arrays
- arrays [Visual Basic], initialization errors
- troubleshooting Visual Basic, arrays
- arrays [Visual Basic], compilation errors
- arrays [Visual Basic], declaration errors
- arrays [Visual Basic], troubleshooting
ms.assetid: f4e971c7-c0a4-4ed7-a77a-8d71039f266f
ms.openlocfilehash: 3c50c68c2a39aa04cff2dd43b5dfde709aec290f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349064"
---
# <a name="troubleshooting-arrays-visual-basic"></a>Solucionar problemas de matrices (Visual Basic)
En esta página se enumeran algunos problemas comunes que pueden producirse al trabajar con matrices.  
  
## <a name="compilation-errors-declaring-and-initializing-an-array"></a>Errores de compilación que declaran e inicializan una matriz  
 Pueden surgir errores de compilación debido a la incomprensión de las reglas para declarar, crear e inicializar matrices. Las causas más comunes de los errores son las siguientes:  
  
- Proporcionar una [nueva cláusula Operator](../../../../visual-basic/language-reference/operators/new-operator.md) después de especificar la longitud de la dimensión en la declaración de la variable de matriz. En las líneas de código siguientes se muestran declaraciones no válidas de este tipo.  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
- Especificar longitudes de dimensión para más que la matriz de nivel superior de una matriz escalonada. En la línea de código siguiente se muestra una declaración no válida de este tipo.  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
- Omitir la palabra clave `New` al especificar los valores de los elementos. En la línea de código siguiente se muestra una declaración no válida de este tipo.  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
- Proporcionar una cláusula `New` sin llaves (`{}`). En las líneas de código siguientes se muestran declaraciones no válidas de este tipo.  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## <a name="accessing-an-array-out-of-bounds"></a>Acceder a una matriz fuera de los límites  
 El proceso de inicialización de una matriz asigna un límite superior y un límite inferior a cada dimensión. Cada acceso a un elemento de la matriz debe especificar un índice válido, o subíndice, para cada dimensión. Si un índice está por debajo de su límite inferior o por encima de su límite superior, se produce una excepción <xref:System.IndexOutOfRangeException>. El compilador no puede detectar este tipo de error, por lo que se produce un error en tiempo de ejecución.  
  
### <a name="determining-bounds"></a>Determinar los límites  
 Si otro componente pasa una matriz al código (por ejemplo, como un argumento de procedimiento), no se conoce el tamaño de la matriz o las longitudes de sus dimensiones. Siempre debe determinar el límite superior de cada dimensión de una matriz antes de intentar tener acceso a los elementos. Si la matriz se ha creado por algunos medios distintos de una Visual Basic `New` cláusula, el límite inferior podría ser distinto de 0 y es más seguro determinar también ese límite inferior.  
  
### <a name="specifying-the-dimension"></a>Especificar la dimensión  
 Al determinar los límites de una matriz multidimensional, tenga cuidado al especificar la dimensión. Los `dimension` parámetros de los métodos <xref:System.Array.GetLowerBound%2A> y <xref:System.Array.GetUpperBound%2A> se basan en 0, mientras que los parámetros `Rank` de las funciones Visual Basic <xref:Microsoft.VisualBasic.Information.LBound%2A> y <xref:Microsoft.VisualBasic.Information.UBound%2A> se basan en 1.  
  
## <a name="see-also"></a>Vea también

- [Matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Cómo: Inicializar una variable de matriz en Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)
