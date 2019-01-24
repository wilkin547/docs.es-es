---
title: Call (Instrucción, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Call
helpviewer_keywords:
- procedures [Visual Basic], Call statement
- Call statement [Visual Basic]
- procedures [Visual Basic], calling
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
ms.openlocfilehash: e706650ac6da84d9b4e77fc549811e731be61b92
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54594166"
---
# <a name="call-statement-visual-basic"></a>Call (Instrucción, Visual Basic)
Transfiere el control a un `Function`, `Sub`, o el procedimiento de la biblioteca de vínculos dinámicos (DLL).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a>Elementos  
|||
|---|---|
|`procedureName`|Obligatorio. Nombre del procedimiento para llamar a.|
|`argumentList`|Opcional. Lista de variables o expresiones que representan los argumentos que se pasan al procedimiento cuando se llama. Varios argumentos están separados por comas. Si incluye `argumentList`, debe encerrarlo entre paréntesis.|
|||
  
## <a name="remarks"></a>Comentarios  
 Puede usar el `Call` palabra clave cuando se llama a un procedimiento. Para la mayoría de las llamadas de procedimiento, no es necesario usar esta palabra clave.  
  
 Normalmente, se utiliza el `Call` palabra clave cuando la expresión llamada no se inicia con un identificador. El uso de la `Call` no se recomienda la palabra clave para otros usos.  
  
 Si el procedimiento devuelve un valor, el `Call` instrucción lo descarta.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente muestra dos ejemplos donde el `Call` palabra clave es necesario llamar a un procedimiento. En ambos ejemplos, la expresión llamada no se inicia con un identificador.  
  
 [!code-vb[VbVbalrStatements#97](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/call-statement_1.vb)]  
  
## <a name="see-also"></a>Vea también
- [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)
- [Expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
