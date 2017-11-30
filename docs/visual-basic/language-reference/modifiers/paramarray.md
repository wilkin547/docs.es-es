---
title: ParamArray (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ParamArray
- ParamArray
helpviewer_keywords:
- ParamArray keyword [Visual Basic]
- ParamArray keyword [Visual Basic], syntax
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 06770f05aabedcf13cc9af1970a2c511a30c73b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="paramarray-visual-basic"></a>ParamArray (Visual Basic)
Especifica que un parámetro de procedimiento toma una matriz opcional de elementos del tipo especificado. `ParamArray`puede usarse solo en el último parámetro de una lista de parámetros.  
  
## <a name="remarks"></a>Comentarios  
 `ParamArray`le permite pasar un número arbitrario de argumentos al procedimiento. A `ParamArray` parámetro siempre se declara mediante [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).  
  
 Puede proporcionar uno o más argumentos para una `ParamArray` tipo de parámetro pasando una matriz de los datos apropiados, una lista separada por comas de valores, o nada en absoluto. Para obtener más información, vea "Llamar a una lista de parámetros" en [matrices de parámetros](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).  
  
> [!IMPORTANT]
>  Cuando se trabaja con una matriz que puede ser excesivamente grande, se corre el riesgo de saturar alguna capacidad interna de la aplicación. Si acepta una matriz de parámetros del código de llamada, debe comprobar su longitud y seguir los pasos adecuados si es demasiado grande para la aplicación.  
  
 El modificador `ParamArray` se puede utilizar en los contextos siguientes:  
  
 [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vea también  
 [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)  
 [Matrices de parámetros](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
