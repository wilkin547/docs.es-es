---
title: "Alias (Cláusula, Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f61e738434ea616d751576ef21669545afc41397
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="alias-clause-visual-basic"></a>Alias (Cláusula, Visual Basic)
Indica que un procedimiento externo tiene otro nombre en su archivo DLL.  
  
## <a name="remarks"></a>Comentarios  
 El `Alias` palabra clave se puede usar en este contexto:  
  
 [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 En el ejemplo siguiente, la `Alias` palabra clave se utiliza para proporcionar el nombre de la función en advapi32.dll, `GetUserNameA`, que `getUserName` se utiliza en lugar de en este ejemplo. Función `getUserName` se denomina en sub `getUser`, que muestra el nombre del usuario actual.  
  
 [!code-vb[VbVbalrStatements#15](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/alias-clause_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)
