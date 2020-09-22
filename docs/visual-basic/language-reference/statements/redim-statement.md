---
title: Instrucción ReDim
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
ms.openlocfilehash: 17bc806f2e92c61f1dd7425de40b1a68f926a583
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872031"
---
# <a name="redim-statement-visual-basic"></a>Instrucción ReDim (Visual Basic)

Reasigna espacio de almacenamiento a una variable de matriz.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
ReDim [ Preserve ] name(boundlist) [ ,  name(boundlist) [, ... ] ]  
```  
  
## <a name="parts"></a>Partes  
  
|Término|Definición|  
|----------|----------------|  
|`Preserve`|Opcional. Modificador usado para mantener los datos en la matriz existente cuando cambia el tamaño solamente de la última dimensión.|  
|`name`|Obligatorio. Nombre de la variable de matriz. Vea [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`boundlist`|Obligatorio. Lista de límites de cada dimensión de la matriz redefinida.|  
  
## <a name="remarks"></a>Comentarios  

 Puede utilizar la instrucción `ReDim` para cambiar el tamaño de una o más dimensiones de una matriz que ya se ha declarado. Si tiene una matriz grande y ya no necesita algunos de sus elementos, `ReDim` puede liberar memoria al reducir el tamaño de la matriz. Por otro lado, si la matriz necesita más elementos, `ReDim` puede agregarlos.  
  
 La instrucción `ReDim` está destinada solo a las matrices. No es válida en escalares (variables que contienen un único valor), colecciones ni estructuras. Tenga en cuenta que, si declara una variable de tipo `Array`, la instrucción `ReDim` no tiene suficiente información de tipo para crear la nueva matriz.  
  
 Solo puede usar `ReDim` en el nivel de procedimiento. Por lo tanto, el contexto de declaración de la variable debe ser un procedimiento; no puede ser un archivo de código fuente, un espacio de nombres, una interfaz, una clase, una estructura, un módulo o un bloque. Para obtener más información, vea [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).  
  
## <a name="rules"></a>Reglas  
  
- **Varias variables.** Puede cambiar el tamaño de varias variables de matriz en la misma instrucción de declaración y especificar las `name` `boundlist` partes y para cada variable. Las variables se separan con comas.  
  
- **Límites de matriz.** Cada entrada en `boundlist` puede especificar los límites inferior y superior de esa dimensión. El límite inferior es siempre 0 (cero). El límite superior es el valor de índice posible más alto para esa dimensión, no la longitud de la dimensión (que es el límite superior más uno). El índice de cada dimensión puede variar entre 0 y el valor del límite superior.  
  
     El número de dimensiones de `boundlist` debe coincidir con el número de dimensiones (rango) de la matriz original.  
  
- **Tipos de datos.** La `ReDim` instrucción no puede cambiar el tipo de datos de una variable de matriz o sus elementos.  
  
- **Inicial.** La `ReDim` instrucción no puede proporcionar nuevos valores de inicialización para los elementos de la matriz.  
  
- **Criterios.** La `ReDim` instrucción no puede cambiar el rango (número de dimensiones) de la matriz.  
  
- **Cambiar el tamaño con Preserve.** Si usa `Preserve` , solo puede cambiar el tamaño de la última dimensión de la matriz. Para cualquier otra dimensión, debe especificar el límite de la matriz existente.  
  
     Por ejemplo, si su matriz tiene solo una dimensión, puede cambiar el tamaño de esa dimensión y conservar todo el contenido de la matriz, ya que es la última y única dimensión. Sin embargo, si su matriz tiene dos o más dimensiones, puede cambiar solamente el tamaño de la última dimensión si utiliza `Preserve`.  
  
- **Propiedades.** Puede usar `ReDim` en una propiedad que contiene una matriz de valores.  
  
## <a name="behavior"></a>Comportamiento  
  
- **Reemplazo de matriz.** `ReDim` libera la matriz existente y crea una nueva matriz con el mismo rango. La nueva matriz reemplaza la matriz liberada en la variable de matriz.  
  
- **Inicialización sin Preserve.** Si no especifica `Preserve` , `ReDim` inicializa los elementos de la nueva matriz utilizando el valor predeterminado para su tipo de datos.  
  
- **Inicialización con Preserve.** Si especifica `Preserve` , Visual Basic copia los elementos de la matriz existente en la nueva matriz.  
  
## <a name="example"></a>Ejemplo  

 El ejemplo siguiente aumenta el tamaño de la última dimensión de una matriz dinámica sin perder los datos existentes en la matriz y, a continuación, reduce el tamaño con pérdida de datos parcial. Por último, reduce el tamaño a su valor original y reinicializa todos los elementos de la matriz.  
  
 [!code-vb[VbVbalrStatements#52](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#52)]  
  
 La instrucción `Dim` crea una nueva matriz con tres dimensiones. Cada dimensión se declara con un límite de 10, por lo que el índice de matriz para cada dimensión puede oscilar entre 0 y 10. En el siguiente análisis, las tres dimensiones se conocen como capa, fila y columna.  
  
 El primer `ReDim` crea una nueva matriz que reemplaza la matriz existente en la variable `intArray`. `ReDim` copia todos los elementos de la matriz existente en la nueva matriz. También agrega 10 columnas más al final de cada fila en cada capa e inicializa los elementos de estas nuevas columnas a 0 (el valor predeterminado de `Integer`, que es el tipo de elemento de la matriz).  
  
 El segundo `ReDim` crea otra nueva matriz y copia todos los elementos que quepan. Sin embargo, se pierden cinco columnas del final de cada fila en cada capa. No es un problema si ya ha terminado de utilizar estas columnas. Reducir el tamaño de una matriz grande puede liberar memoria que ya no necesite.  
  
 El tercer `ReDim` crea otra nueva matriz y quita otras cinco columnas del final de cada fila en cada capa. Esta vez no copia los elementos existentes. Esta instrucción revierte la matriz a su tamaño original. Dado que la instrucción no incluye el modificador `Preserve`, establece todos los elementos de matriz con sus valores predeterminados originales.  
  
 Para obtener más ejemplos, consulte [matrices](../../programming-guide/language-features/arrays/index.md).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.IndexOutOfRangeException>
- [Instrucción Const](const-statement.md)
- [Instrucción Dim](dim-statement.md)
- [Instrucción Erase](erase-statement.md)
- [Nothing](../nothing.md)
- [Matrices](../../programming-guide/language-features/arrays/index.md)
