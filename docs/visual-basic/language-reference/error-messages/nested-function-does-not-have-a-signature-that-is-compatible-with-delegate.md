---
title: "Función anidada no tiene una firma que es compatible con el delegado &#39; &lt;nombredelegado&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 60cf15343023110561da3e3fcf202bd00394127a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-39ltdelegatenamegt39"></a>Función anidada no tiene una firma que es compatible con el delegado &#39; &lt;nombredelegado&gt;&#39;
Se ha asignado una expresión lambda a un delegado que tiene una firma compatible. Por ejemplo, en el código siguiente, el delegado `Del` tiene dos parámetros de entero.  
  
```vb  
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer  
```  
  
 El error se produce si una expresión lambda con un argumento se declara como tipo `Del`:  
  
```vb  
' Neither of these is valid.   
' Dim lambda1 As Del = Function(n As Integer) n + 1  
' Dim lambda2 As Del = Function(n) n + 1  
```  
  
 **Id. de error:** BC36532  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Ajuste la definición de delegado o la expresión lambda asignada para que las firmas son compatibles.  
  
## <a name="see-also"></a>Vea también  
 [Conversión de delegado flexible](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)  
 [Expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
