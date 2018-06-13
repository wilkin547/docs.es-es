---
title: '&#39;AddressOf&#39; operando debe ser el nombre de un método (sin paréntesis)'
ms.date: 07/20/2015
f1_keywords:
- vbc30577
- bc30577
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
ms.openlocfilehash: 701d86e03d9b14236eec8436d99ec40cebbbcd44
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33583817"
---
# <a name="39addressof39-operand-must-be-the-name-of-a-method-without-parentheses"></a><span data-ttu-id="f2282-102">&#39;AddressOf&#39; operando debe ser el nombre de un método (sin paréntesis)</span><span class="sxs-lookup"><span data-stu-id="f2282-102">&#39;AddressOf&#39; operand must be the name of a method (without parentheses)</span></span>
<span data-ttu-id="f2282-103">El operador `AddressOf` crea una instancia de delegado de procedimiento que hace referencia a un procedimiento específico.</span><span class="sxs-lookup"><span data-stu-id="f2282-103">The `AddressOf` operator creates a procedure delegate instance that references a specific procedure.</span></span> <span data-ttu-id="f2282-104">La sintaxis es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="f2282-104">The syntax is as follows.</span></span>  
  
 <span data-ttu-id="f2282-105">`AddressOf` `procedurename`</span><span class="sxs-lookup"><span data-stu-id="f2282-105">`AddressOf` `procedurename`</span></span>  
  
 <span data-ttu-id="f2282-106">Inserta el siguiente argumento entre paréntesis `AddressOf`, donde se necesita ninguno.</span><span class="sxs-lookup"><span data-stu-id="f2282-106">You inserted parentheses around the argument following `AddressOf`, where none are needed.</span></span>  
  
 <span data-ttu-id="f2282-107">**Id. de error:** BC30577</span><span class="sxs-lookup"><span data-stu-id="f2282-107">**Error ID:** BC30577</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f2282-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="f2282-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="f2282-109">Quite los paréntesis que rodean el siguiente argumento `AddressOf`.</span><span class="sxs-lookup"><span data-stu-id="f2282-109">Remove the parentheses around the argument following `AddressOf`.</span></span>  
  
2.  <span data-ttu-id="f2282-110">Asegúrese de que el argumento es un nombre de método.</span><span class="sxs-lookup"><span data-stu-id="f2282-110">Make sure the argument is a method name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2282-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2282-111">See Also</span></span>  
 [<span data-ttu-id="f2282-112">AddressOf (operador)</span><span class="sxs-lookup"><span data-stu-id="f2282-112">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [<span data-ttu-id="f2282-113">Delegados</span><span class="sxs-lookup"><span data-stu-id="f2282-113">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
