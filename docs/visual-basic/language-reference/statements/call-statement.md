---
title: "Call (Instrucción, Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Call
helpviewer_keywords:
- procedures [Visual Basic], Call statement
- Call statement [Visual Basic]
- procedures [Visual Basic], calling
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c72450fd6f931f36f640d3e384a6fd38d57a7a23
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="call-statement-visual-basic"></a>Call (Instrucción, Visual Basic)
Transfiere el control a un `Function`, `Sub`, o un procedimiento de biblioteca de vínculos dinámicos (DLL).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a>Elementos  
 `procedureName`  
 Obligatorio. Nombre del procedimiento al que llamar.  
  
 `argumentList`  
 Opcional. Lista de variables o expresiones que representan los argumentos que se pasan al procedimiento cuando se llama. Varios argumentos están separados por comas. Si incluye `argumentList`, debe encerrarlo entre paréntesis.  
  
## <a name="remarks"></a>Comentarios  
 Puede usar el `Call` palabra clave cuando se llama a un procedimiento. Para la mayoría de las llamadas de procedimiento, no es necesario que utilice esta palabra clave.  
  
 Normalmente, se utiliza el `Call` palabra clave cuando la expresión llamada no se inicia con un identificador. El uso de la `Call` no se recomienda la palabra clave para otros usos.  
  
 Si el procedimiento devuelve un valor, el `Call` instrucción lo descarta.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente muestra dos ejemplos donde el `Call` palabra clave es necesario llamar a un procedimiento. En ambos ejemplos, la expresión llamada no se inicia con un identificador.  
  
 [!code-vb[VbVbalrStatements#97](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/call-statement_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [Expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
