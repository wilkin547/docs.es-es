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
# <a name="alias-clause-visual-basic"></a><span data-ttu-id="fab78-103">Alias (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fab78-103">Alias Clause (Visual Basic)</span></span>

<span data-ttu-id="fab78-104">Indica que un procedimiento externo tiene otro nombre en su archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="fab78-104">Indicates that an external procedure has another name in its DLL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fab78-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fab78-105">Remarks</span></span>  

 <span data-ttu-id="fab78-106">La `Alias` palabra clave se puede usar en este contexto:</span><span class="sxs-lookup"><span data-stu-id="fab78-106">The `Alias` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="fab78-107">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="fab78-107">Declare Statement</span></span>](declare-statement.md)  
  
 <span data-ttu-id="fab78-108">En el ejemplo siguiente, la `Alias` palabra clave se usa para proporcionar el nombre de la función en advapi32.dll, `GetUserNameA` , que `getUserName` se usa en lugar de en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fab78-108">In the following example, the `Alias` keyword is used to provide the name of the function in advapi32.dll, `GetUserNameA`, that `getUserName` is used in place of in this example.</span></span> <span data-ttu-id="fab78-109">`getUserName`En sub `getUser` , que muestra el nombre del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="fab78-109">Function `getUserName` is called in sub `getUser`, which displays the name of the current user.</span></span>  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="fab78-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="fab78-110">See also</span></span>

- [<span data-ttu-id="fab78-111">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="fab78-111">Keywords</span></span>](../keywords/index.md)
