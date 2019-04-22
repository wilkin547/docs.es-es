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
ms.openlocfilehash: 755443a99a1ad8b0430a76d2dba1ff27472d4c9d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58832650"
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
  
 [!code-vb[VbVbalrStatements#97](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#97)]  
  
## <a name="see-also"></a>Vea también

- [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)
- [Expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
