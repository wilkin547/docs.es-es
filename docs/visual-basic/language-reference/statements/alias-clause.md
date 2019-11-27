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
# <a name="alias-clause-visual-basic"></a><span data-ttu-id="3915e-102">Alias (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3915e-102">Alias Clause (Visual Basic)</span></span>
<span data-ttu-id="3915e-103">Indica que un procedimiento externo tiene otro nombre en su archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="3915e-103">Indicates that an external procedure has another name in its DLL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3915e-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3915e-104">Remarks</span></span>  
 <span data-ttu-id="3915e-105">La palabra clave `Alias` se puede usar en este contexto:</span><span class="sxs-lookup"><span data-stu-id="3915e-105">The `Alias` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="3915e-106">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="3915e-106">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 <span data-ttu-id="3915e-107">En el ejemplo siguiente, se usa la palabra clave `Alias` para proporcionar el nombre de la función en advapi32. dll, `GetUserNameA`, que `getUserName` se usa en lugar de en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="3915e-107">In the following example, the `Alias` keyword is used to provide the name of the function in advapi32.dll, `GetUserNameA`, that `getUserName` is used in place of in this example.</span></span> <span data-ttu-id="3915e-108">En sub `getUser`se llama a la función `getUserName`, que muestra el nombre del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="3915e-108">Function `getUserName` is called in sub `getUser`, which displays the name of the current user.</span></span>  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="3915e-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="3915e-109">See also</span></span>

- [<span data-ttu-id="3915e-110">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="3915e-110">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
