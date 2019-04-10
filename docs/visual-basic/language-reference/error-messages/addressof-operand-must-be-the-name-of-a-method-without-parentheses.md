---
title: El operando 'AddressOf' debe ser el nombre de un método (sin paréntesis)
ms.date: 07/20/2015
f1_keywords:
- vbc30577
- bc30577
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
ms.openlocfilehash: b8c67c2390df91c6a4af66e020365544e6bf369b
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59323829"
---
# <a name="addressof-operand-must-be-the-name-of-a-method-without-parentheses"></a><span data-ttu-id="a853e-102">El operando 'AddressOf' debe ser el nombre de un método (sin paréntesis)</span><span class="sxs-lookup"><span data-stu-id="a853e-102">'AddressOf' operand must be the name of a method (without parentheses)</span></span>
<span data-ttu-id="a853e-103">El operador `AddressOf` crea una instancia de delegado de procedimiento que hace referencia a un procedimiento específico.</span><span class="sxs-lookup"><span data-stu-id="a853e-103">The `AddressOf` operator creates a procedure delegate instance that references a specific procedure.</span></span> <span data-ttu-id="a853e-104">La sintaxis es como sigue.</span><span class="sxs-lookup"><span data-stu-id="a853e-104">The syntax is as follows.</span></span>  
  
 `AddressOf` `procedurename`  
  
 <span data-ttu-id="a853e-105">Insertar paréntesis que rodean el siguiente argumento `AddressOf`, donde no son necesarias.</span><span class="sxs-lookup"><span data-stu-id="a853e-105">You inserted parentheses around the argument following `AddressOf`, where none are needed.</span></span>  
  
 <span data-ttu-id="a853e-106">**Identificador de error:** BC30577</span><span class="sxs-lookup"><span data-stu-id="a853e-106">**Error ID:** BC30577</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a853e-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="a853e-107">To correct this error</span></span>  
  
1. <span data-ttu-id="a853e-108">Quite los paréntesis que rodean el siguiente argumento `AddressOf`.</span><span class="sxs-lookup"><span data-stu-id="a853e-108">Remove the parentheses around the argument following `AddressOf`.</span></span>  
  
2. <span data-ttu-id="a853e-109">Asegúrese de que el argumento es un nombre de método.</span><span class="sxs-lookup"><span data-stu-id="a853e-109">Make sure the argument is a method name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a853e-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="a853e-110">See also</span></span>

- [<span data-ttu-id="a853e-111">AddressOf (Operador)</span><span class="sxs-lookup"><span data-stu-id="a853e-111">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="a853e-112">Delegados</span><span class="sxs-lookup"><span data-stu-id="a853e-112">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
