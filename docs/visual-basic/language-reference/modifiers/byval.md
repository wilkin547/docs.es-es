---
title: ByVal (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ByVal
- ByVal
helpviewer_keywords:
- ByVal keyword [Visual Basic], contexts
- ByVal keyword [Visual Basic]
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c192cdb4ac43ad614fbfb663079c03ddc6c358c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="byval-visual-basic"></a>ByVal (Visual Basic)
Especifica que un argumento se pasa de tal manera que el procedimiento que se llama o la propiedad no se puede cambiar el valor de una variable subyacente del argumento en el código de llamada.  
  
## <a name="remarks"></a>Comentarios  
 El modificador `ByVal` se puede utilizar en los contextos siguientes:  
  
 [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Operator (instrucción)](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra el uso de la `ByVal` mecanismo con un argumento de tipo de referencia que pasa el parámetro. En el ejemplo, el argumento es `c1`, una instancia de clase `Class1`. `ByVal`impide que el código en los procedimientos cambie el valor subyacente del argumento de referencia, `c1`, pero no protege los campos accesibles y las propiedades de `c1`.  
  
 [!code-vb[VbVbalrKeywords#10](../../../visual-basic/language-reference/codesnippet/VisualBasic/byval_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)  
 [Paso de argumentos por valor y por referencia](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
