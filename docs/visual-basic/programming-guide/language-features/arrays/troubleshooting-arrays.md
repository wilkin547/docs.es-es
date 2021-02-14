---
description: Más información acerca de cómo solucionar problemas de matrices (Visual Basic)
title: Solución de problemas de matrices
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting arrays
- arrays [Visual Basic], initialization errors
- troubleshooting Visual Basic, arrays
- arrays [Visual Basic], compilation errors
- arrays [Visual Basic], declaration errors
- arrays [Visual Basic], troubleshooting
ms.assetid: f4e971c7-c0a4-4ed7-a77a-8d71039f266f
ms.openlocfilehash: 2aca3c1819ed6482e132ba432e5e70fbdf9a5b3a
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100454500"
---
# <a name="troubleshooting-arrays-visual-basic"></a>Solucionar problemas de matrices (Visual Basic)

En esta página se enumeran algunos problemas comunes que pueden producirse al trabajar con matrices.  
  
## <a name="compilation-errors-declaring-and-initializing-an-array"></a>Errores de compilación que declaran e inicializan una matriz  

 Pueden surgir errores de compilación debido a la incomprensión de las reglas para declarar, crear e inicializar matrices. Las causas más comunes de los errores son las siguientes:  
  
- Proporcionar una [nueva cláusula Operator](../../../language-reference/operators/new-operator.md) después de especificar la longitud de la dimensión en la declaración de la variable de matriz. En las líneas de código siguientes se muestran declaraciones no válidas de este tipo.  
  
     `Dim INVALIDsingleDimByteArray(2) As Byte = New Byte()`  
  
     `Dim INVALIDtwoDimShortArray(1, 1) As Short = New Short(,)`  
  
     `Dim INVALIDjaggedByteArray(1)() As Byte = New Byte()()`  
  
- Especificar longitudes de dimensión para más que la matriz de nivel superior de una matriz escalonada. En la línea de código siguiente se muestra una declaración no válida de este tipo.  
  
     `Dim INVALIDjaggedByteArray(1)(1) As Byte`  
  
- Omitiendo la `New` palabra clave al especificar los valores de elemento. En la línea de código siguiente se muestra una declaración no válida de este tipo.  
  
     `Dim INVALIDoneDimShortArray() As Short = Short() {0, 1, 2, 3}`  
  
- Proporcionar una `New` cláusula sin llaves ( `{}` ). En las líneas de código siguientes se muestran declaraciones no válidas de este tipo.  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte()`  
  
     `Dim INVALIDsingleDimByteArray() As Byte = New Byte(2)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(,)`  
  
     `Dim INVALIDtwoDimShortArray(,) As Short = New Short(1, 1)`  
  
## <a name="accessing-an-array-out-of-bounds"></a>Acceder a una matriz fuera de los límites  

 El proceso de inicialización de una matriz asigna un límite superior y un límite inferior a cada dimensión. Cada acceso a un elemento de la matriz debe especificar un índice válido, o subíndice, para cada dimensión. Si un índice está por debajo de su límite inferior o por encima de su límite superior, se <xref:System.IndexOutOfRangeException> produce una excepción. El compilador no puede detectar este tipo de error, por lo que se produce un error en tiempo de ejecución.  
  
### <a name="determining-bounds"></a>Determinar los límites  

 Si otro componente pasa una matriz al código (por ejemplo, como un argumento de procedimiento), no se conoce el tamaño de la matriz o las longitudes de sus dimensiones. Siempre debe determinar el límite superior de cada dimensión de una matriz antes de intentar tener acceso a los elementos. Si la matriz se ha creado por algunos medios distintos de una `New` cláusula Visual Basic, el límite inferior podría ser distinto de 0 y es más seguro determinar ese límite inferior también.  
  
### <a name="specifying-the-dimension"></a>Especificar la dimensión  

 Al determinar los límites de una matriz multidimensional, tenga cuidado al especificar la dimensión. Los `dimension` parámetros de los <xref:System.Array.GetLowerBound%2A> <xref:System.Array.GetUpperBound%2A> métodos y se basan en 0, mientras que los `Rank` parámetros de las <xref:Microsoft.VisualBasic.Information.LBound%2A> funciones Visual Basic y <xref:Microsoft.VisualBasic.Information.UBound%2A> se basan en 1.  
  
## <a name="see-also"></a>Vea también

- [Matrices](index.md)
- [Cómo: Inicializar una variable de matriz en Visual Basic](how-to-initialize-an-array-variable.md)
