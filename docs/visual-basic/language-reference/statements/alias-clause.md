---
title: Cláusula Alias
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: 77d4685f242864842e5a84b3a3de3ba1793e9aa4
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866687"
---
# <a name="alias-clause-visual-basic"></a>Alias (Cláusula, Visual Basic)

Indica que un procedimiento externo tiene otro nombre en su archivo DLL.  
  
## <a name="remarks"></a>Comentarios  

 La `Alias` palabra clave se puede usar en este contexto:  
  
 [Declare Statement](declare-statement.md)  
  
 En el ejemplo siguiente, la `Alias` palabra clave se usa para proporcionar el nombre de la función en advapi32.dll, `GetUserNameA` , que `getUserName` se usa en lugar de en este ejemplo. `getUserName`En sub `getUser` , que muestra el nombre del usuario actual.  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="see-also"></a>Consulte también

- [Palabras clave](../keywords/index.md)
