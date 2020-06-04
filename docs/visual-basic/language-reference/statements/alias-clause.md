---
title: Cláusula Alias
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: c28e931a376b20b2058a7187551405cd9523d4fe
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408476"
---
# <a name="alias-clause-visual-basic"></a><span data-ttu-id="a0941-102">Alias (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a0941-102">Alias Clause (Visual Basic)</span></span>
<span data-ttu-id="a0941-103">Indica que un procedimiento externo tiene otro nombre en su archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="a0941-103">Indicates that an external procedure has another name in its DLL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0941-104">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a0941-104">Remarks</span></span>  
 <span data-ttu-id="a0941-105">La `Alias` palabra clave se puede usar en este contexto:</span><span class="sxs-lookup"><span data-stu-id="a0941-105">The `Alias` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="a0941-106">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="a0941-106">Declare Statement</span></span>](declare-statement.md)  
  
 <span data-ttu-id="a0941-107">En el ejemplo siguiente, la `Alias` palabra clave se usa para proporcionar el nombre de la función en advapi32. dll, `GetUserNameA` , que `getUserName` se usa en lugar de en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a0941-107">In the following example, the `Alias` keyword is used to provide the name of the function in advapi32.dll, `GetUserNameA`, that `getUserName` is used in place of in this example.</span></span> <span data-ttu-id="a0941-108">`getUserName`En sub `getUser` , que muestra el nombre del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="a0941-108">Function `getUserName` is called in sub `getUser`, which displays the name of the current user.</span></span>  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="a0941-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a0941-109">See also</span></span>

- [<span data-ttu-id="a0941-110">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a0941-110">Keywords</span></span>](../keywords/index.md)
