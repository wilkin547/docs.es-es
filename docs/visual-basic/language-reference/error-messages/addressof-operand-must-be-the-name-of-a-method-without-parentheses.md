---
title: El operando 'AddressOf' debe ser el nombre de un método (sin paréntesis)
ms.date: 07/20/2015
f1_keywords:
- vbc30577
- bc30577
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
ms.openlocfilehash: af1ce858108785fa4dac6352c9e80531e86fbb23
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58813969"
---
# <a name="addressof-operand-must-be-the-name-of-a-method-without-parentheses"></a><span data-ttu-id="c3604-102">El operando 'AddressOf' debe ser el nombre de un método (sin paréntesis)</span><span class="sxs-lookup"><span data-stu-id="c3604-102">'AddressOf' operand must be the name of a method (without parentheses)</span></span>
<span data-ttu-id="c3604-103">El operador `AddressOf` crea una instancia de delegado de procedimiento que hace referencia a un procedimiento específico.</span><span class="sxs-lookup"><span data-stu-id="c3604-103">The `AddressOf` operator creates a procedure delegate instance that references a specific procedure.</span></span> <span data-ttu-id="c3604-104">La sintaxis es como sigue.</span><span class="sxs-lookup"><span data-stu-id="c3604-104">The syntax is as follows.</span></span>  
  
 <span data-ttu-id="c3604-105">`AddressOf` `procedurename`</span><span class="sxs-lookup"><span data-stu-id="c3604-105">`AddressOf` `procedurename`</span></span>  
  
 <span data-ttu-id="c3604-106">Insertar paréntesis que rodean el siguiente argumento `AddressOf`, donde no son necesarias.</span><span class="sxs-lookup"><span data-stu-id="c3604-106">You inserted parentheses around the argument following `AddressOf`, where none are needed.</span></span>  
  
 <span data-ttu-id="c3604-107">**Identificador de error:** BC30577</span><span class="sxs-lookup"><span data-stu-id="c3604-107">**Error ID:** BC30577</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c3604-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="c3604-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="c3604-109">Quite los paréntesis que rodean el siguiente argumento `AddressOf`.</span><span class="sxs-lookup"><span data-stu-id="c3604-109">Remove the parentheses around the argument following `AddressOf`.</span></span>  
  
2.  <span data-ttu-id="c3604-110">Asegúrese de que el argumento es un nombre de método.</span><span class="sxs-lookup"><span data-stu-id="c3604-110">Make sure the argument is a method name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3604-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3604-111">See also</span></span>

- [<span data-ttu-id="c3604-112">AddressOf (operador)</span><span class="sxs-lookup"><span data-stu-id="c3604-112">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="c3604-113">Delegados</span><span class="sxs-lookup"><span data-stu-id="c3604-113">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
