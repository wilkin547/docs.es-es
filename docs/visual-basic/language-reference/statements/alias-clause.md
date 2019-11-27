---
title: Cláusula Alias
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: a7f67224c5d26816bdc1974dc4aa82d796c41284
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349145"
---
# <a name="alias-clause-visual-basic"></a>Alias (Cláusula, Visual Basic)
Indica que un procedimiento externo tiene otro nombre en su archivo DLL.  
  
## <a name="remarks"></a>Comentarios  
 La palabra clave `Alias` se puede usar en este contexto:  
  
 [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 En el ejemplo siguiente, se usa la palabra clave `Alias` para proporcionar el nombre de la función en advapi32. dll, `GetUserNameA`, que `getUserName` se usa en lugar de en este ejemplo. En sub `getUser`se llama a la función `getUserName`, que muestra el nombre del usuario actual.  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="see-also"></a>Vea también

- [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)
