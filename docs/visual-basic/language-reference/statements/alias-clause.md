---
title: Alias (Cláusula, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: 3b1a66ecfd3c023a12ac62191ca3671a195b45a6
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56978233"
---
# <a name="alias-clause-visual-basic"></a>Alias (Cláusula, Visual Basic)
Indica que un procedimiento externo tiene otro nombre en su DLL.  
  
## <a name="remarks"></a>Comentarios  
 El `Alias` palabra clave se puede usar en este contexto:  
  
 [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 En el ejemplo siguiente, la `Alias` palabra clave se usa para proporcionar el nombre de la función en advapi32.dll, `GetUserNameA`, que `getUserName` en este ejemplo se utiliza en lugar de. Función `getUserName` se denomina en sub `getUser`, que muestra el nombre del usuario actual.  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="see-also"></a>Vea también
- [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)
