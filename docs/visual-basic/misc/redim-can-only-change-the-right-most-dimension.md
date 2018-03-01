---
title: "&#39; ReDim &#39; solo se puede cambiar la dimensión más a la derecha"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrArray_TypeMismatch
ms.assetid: d53cf41b-7a7a-466c-a29a-920d99698fa9
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 752e0e54c48b3b348a477787e5e911f1b1777667
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="39redim39-can-only-change-the-right-most-dimension"></a>&#39; ReDim &#39; solo se puede cambiar la dimensión más a la derecha
Una instrucción `ReDim` intentó usar la palabra clave `Preserve` para cambiar una dimensión de una matriz que no es la última dimensión. Si usa `Preserve`, solo puede cambiar el tamaño de la última dimensión de la matriz. Para todas las demás dimensiones, debe especificar el mismo tamaño que la matriz existente.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Quite la palabra clave `Preserve` .  
  
## <a name="see-also"></a>Vea también  
 [Matrices en Visual Basic](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)  
 [Dimensiones de la matriz en Visual Basic](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)  
 [ReDim (instrucción)](../../visual-basic/language-reference/statements/redim-statement.md)  
 [Dim (instrucción)](../../visual-basic/language-reference/statements/dim-statement.md)  
 [Conservar: eliminar](http://msdn.microsoft.com/library/91badeab-b4e0-48b6-92c9-9f0c8f995d81)
