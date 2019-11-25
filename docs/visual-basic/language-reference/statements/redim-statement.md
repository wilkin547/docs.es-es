---
title: ReDim (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.ReDim
- vb.Preserve
helpviewer_keywords:
- fixed-length strings [Visual Basic], declaring
- ReDim statement [Visual Basic], syntax
- dynamic arrays [Visual Basic], ReDim statement
- arrays [Visual Basic], reallocating
- arrays [Visual Basic], reinitializing
- arrays [Visual Basic], dimensions
- scalars, and arrays
- scalars
- declarations [Visual Basic], dynamic arrays
- variables [Visual Basic], scalar
- ReDim statement [Visual Basic]
- data types [Visual Basic], assigning
- As keyword [Visual Basic], in ReDim statement
- To keyword [Visual Basic], ReDim statement
- arrays [Visual Basic], declaring
- Preserve keyword [Visual Basic], ReDim statement
- storage [Visual Basic], allocating
- arrays [Visual Basic], and scalars
- declaration statements [Visual Basic]
- scalar variables [Visual Basic]
ms.assetid: ad1c5e07-dcd7-4ae1-a79e-ad3f2dcc2083
ms.openlocfilehash: fabfd9a45d47cc1b881b3743181a03e89158f939
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346738"
---
# <a name="redim-statement-visual-basic"></a>Instrucción ReDim (Visual Basic)
Reasigna espacio de almacenamiento a una variable de matriz.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
ReDim [ Preserve ] name(boundlist) [ ,  name(boundlist) [, ... ] ]  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|de esquema JSON|  
|----------|----------------|  
|`Preserve`|Opcional. Modificador usado para mantener los datos en la matriz existente cuando cambia el tamaño solamente de la última dimensión.|  
|`name`|Requerido. Nombre de la variable de matriz. Vea [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`boundlist`|Requerido. Lista de límites de cada dimensión de la matriz redefinida.|  
  
## <a name="remarks"></a>Comentarios  
 Puede utilizar la instrucción `ReDim` para cambiar el tamaño de una o más dimensiones de una matriz que ya se ha declarado. Si tiene una matriz grande y ya no necesita algunos de sus elementos, `ReDim` puede liberar memoria al reducir el tamaño de la matriz. Por otro lado, si la matriz necesita más elementos, `ReDim` puede agregarlos.  
  
 La instrucción `ReDim` está destinada solo a las matrices. No es válida en escalares (variables que contienen un único valor), colecciones ni estructuras. Tenga en cuenta que, si declara una variable de tipo `Array`, la instrucción `ReDim` no tiene suficiente información de tipo para crear la nueva matriz.  
  
 Solo puede usar `ReDim` en el nivel de procedimiento. Por lo tanto, el contexto de declaración de la variable debe ser un procedimiento; no puede ser un archivo de código fuente, un espacio de nombres, una interfaz, una clase, una estructura, un módulo o un bloque. Para obtener más información, vea [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).  
  
## <a name="rules"></a>Reglas  
  
- **Multiple Variables.** You can resize several array variables in the same declaration statement and specify the `name` and `boundlist` parts for each variable. Las variables se separan con comas.  
  
- **Array Bounds.** Each entry in `boundlist` can specify the lower and upper bounds of that dimension. El límite inferior es siempre 0 (cero). El límite superior es el valor de índice posible más alto para esa dimensión, no la longitud de la dimensión (que es el límite superior más uno). El índice de cada dimensión puede variar entre 0 y el valor del límite superior.  
  
     El número de dimensiones de `boundlist` debe coincidir con el número de dimensiones (rango) de la matriz original.  
  
- **Data Types.** The `ReDim` statement cannot change the data type of an array variable or its elements.  
  
- **Initialization.** The `ReDim` statement cannot provide new initialization values for the array elements.  
  
- **Rank.** The `ReDim` statement cannot change the rank (the number of dimensions) of the array.  
  
- **Resizing with Preserve.** If you use `Preserve`, you can resize only the last dimension of the array. Para cualquier otra dimensión, debe especificar el límite de la matriz existente.  
  
     Por ejemplo, si su matriz tiene solo una dimensión, puede cambiar el tamaño de esa dimensión y conservar todo el contenido de la matriz, ya que es la última y única dimensión. Sin embargo, si su matriz tiene dos o más dimensiones, puede cambiar solamente el tamaño de la última dimensión si utiliza `Preserve`.  
  
- **Properties.** You can use `ReDim` on a property that holds an array of values.  
  
## <a name="behavior"></a>Comportamiento  
  
- **Array Replacement.** `ReDim` releases the existing array and creates a new array with the same rank. La nueva matriz reemplaza la matriz liberada en la variable de matriz.  
  
- **Initialization without Preserve.** If you do not specify `Preserve`, `ReDim` initializes the elements of the new array by using the default value for their data type.  
  
- **Initialization with Preserve.** If you specify `Preserve`, Visual Basic copies the elements from the existing array to the new array.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente aumenta el tamaño de la última dimensión de una matriz dinámica sin perder los datos existentes en la matriz y, a continuación, reduce el tamaño con pérdida de datos parcial. Por último, reduce el tamaño a su valor original y reinicializa todos los elementos de la matriz.  
  
 [!code-vb[VbVbalrStatements#52](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#52)]  
  
 La instrucción `Dim` crea una nueva matriz con tres dimensiones. Cada dimensión se declara con un límite de 10, por lo que el índice de matriz para cada dimensión puede oscilar entre 0 y 10. En el siguiente análisis, las tres dimensiones se conocen como capa, fila y columna.  
  
 El primer `ReDim` crea una nueva matriz que reemplaza la matriz existente en la variable `intArray`. `ReDim` copia todos los elementos de la matriz existente en la nueva matriz. También agrega 10 columnas más al final de cada fila en cada capa e inicializa los elementos de estas nuevas columnas a 0 (el valor predeterminado de `Integer`, que es el tipo de elemento de la matriz).  
  
 El segundo `ReDim` crea otra nueva matriz y copia todos los elementos que quepan. Sin embargo, se pierden cinco columnas del final de cada fila en cada capa. No es un problema si ya ha terminado de utilizar estas columnas. Reducir el tamaño de una matriz grande puede liberar memoria que ya no necesite.  
  
 El tercer `ReDim` crea otra nueva matriz y quita otras cinco columnas del final de cada fila en cada capa. Esta vez no copia los elementos existentes. Esta instrucción revierte la matriz a su tamaño original. Dado que la instrucción no incluye el modificador `Preserve`, establece todos los elementos de matriz con sus valores predeterminados originales.  
  
 For additional examples, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.IndexOutOfRangeException>
- [Const (instrucción)](../../../visual-basic/language-reference/statements/const-statement.md)
- [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)
- [Erase (instrucción)](../../../visual-basic/language-reference/statements/erase-statement.md)
- [Nothing](../../../visual-basic/language-reference/nothing.md)
- [Matrices](../../../visual-basic/programming-guide/language-features/arrays/index.md)
