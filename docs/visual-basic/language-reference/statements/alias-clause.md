---
description: 'Más información acerca de: cláusula alias (Visual Basic)'
title: Cláusula Alias
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: bf0ee1c22105b29aedb99ce45a99ba866f4b93c1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99674082"
---
# <a name="alias-clause-visual-basic"></a>Alias (Cláusula, Visual Basic)

Indica que un procedimiento externo tiene otro nombre en su archivo DLL.  
  
## <a name="remarks"></a>Observaciones  

 La `Alias` palabra clave se puede usar en este contexto:  
  
 [Declare Statement](declare-statement.md)  
  
 En el ejemplo siguiente, la `Alias` palabra clave se usa para proporcionar el nombre de la función en advapi32.dll, `GetUserNameA` , que `getUserName` se usa en lugar de en este ejemplo. `getUserName`En sub `getUser` , que muestra el nombre del usuario actual.  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="see-also"></a>Vea también

- [Palabras clave](../keywords/index.md)
