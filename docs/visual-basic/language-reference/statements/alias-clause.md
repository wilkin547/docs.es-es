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
# <a name="alias-clause-visual-basic"></a><span data-ttu-id="d8c82-102">Alias (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d8c82-102">Alias Clause (Visual Basic)</span></span>

<span data-ttu-id="d8c82-103">Indica que un procedimiento externo tiene otro nombre en su archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="d8c82-103">Indicates that an external procedure has another name in its DLL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8c82-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d8c82-104">Remarks</span></span>  

 <span data-ttu-id="d8c82-105">La `Alias` palabra clave se puede usar en este contexto:</span><span class="sxs-lookup"><span data-stu-id="d8c82-105">The `Alias` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="d8c82-106">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="d8c82-106">Declare Statement</span></span>](declare-statement.md)  
  
 <span data-ttu-id="d8c82-107">En el ejemplo siguiente, la `Alias` palabra clave se usa para proporcionar el nombre de la función en advapi32.dll, `GetUserNameA` , que `getUserName` se usa en lugar de en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d8c82-107">In the following example, the `Alias` keyword is used to provide the name of the function in advapi32.dll, `GetUserNameA`, that `getUserName` is used in place of in this example.</span></span> <span data-ttu-id="d8c82-108">`getUserName`En sub `getUser` , que muestra el nombre del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="d8c82-108">Function `getUserName` is called in sub `getUser`, which displays the name of the current user.</span></span>  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="d8c82-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d8c82-109">See also</span></span>

- [<span data-ttu-id="d8c82-110">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="d8c82-110">Keywords</span></span>](../keywords/index.md)
