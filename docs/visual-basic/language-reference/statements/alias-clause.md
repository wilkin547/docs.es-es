---
title: Alias (Cláusula, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: 9cf97402d0b0a6cd16dd75a970c1d29a2fcc30a7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498575"
---
# <a name="alias-clause-visual-basic"></a>Alias (Cláusula, Visual Basic)
Indica que un procedimiento externo tiene otro nombre en su DLL.  
  
## <a name="remarks"></a>Comentarios  
 El `Alias` palabra clave se puede usar en este contexto:  
  
 [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 En el ejemplo siguiente, la `Alias` palabra clave se usa para proporcionar el nombre de la función en advapi32.dll, `GetUserNameA`, que `getUserName` en este ejemplo se utiliza en lugar de. Función `getUserName` se denomina en sub `getUser`, que muestra el nombre del usuario actual.  
  
 [!code-vb[VbVbalrStatements#15](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/alias-clause_1.vb)]  
  
## <a name="see-also"></a>Vea también
- [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)
