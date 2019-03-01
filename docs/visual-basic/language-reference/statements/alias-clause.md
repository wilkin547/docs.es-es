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
# <a name="alias-clause-visual-basic"></a><span data-ttu-id="8344f-102">Alias (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8344f-102">Alias Clause (Visual Basic)</span></span>
<span data-ttu-id="8344f-103">Indica que un procedimiento externo tiene otro nombre en su DLL.</span><span class="sxs-lookup"><span data-stu-id="8344f-103">Indicates that an external procedure has another name in its DLL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8344f-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8344f-104">Remarks</span></span>  
 <span data-ttu-id="8344f-105">El `Alias` palabra clave se puede usar en este contexto:</span><span class="sxs-lookup"><span data-stu-id="8344f-105">The `Alias` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="8344f-106">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8344f-106">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 <span data-ttu-id="8344f-107">En el ejemplo siguiente, la `Alias` palabra clave se usa para proporcionar el nombre de la función en advapi32.dll, `GetUserNameA`, que `getUserName` en este ejemplo se utiliza en lugar de.</span><span class="sxs-lookup"><span data-stu-id="8344f-107">In the following example, the `Alias` keyword is used to provide the name of the function in advapi32.dll, `GetUserNameA`, that `getUserName` is used in place of in this example.</span></span> <span data-ttu-id="8344f-108">Función `getUserName` se denomina en sub `getUser`, que muestra el nombre del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="8344f-108">Function `getUserName` is called in sub `getUser`, which displays the name of the current user.</span></span>  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="8344f-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="8344f-109">See also</span></span>
- [<span data-ttu-id="8344f-110">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8344f-110">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
