---
title: El operando 'AddressOf' debe ser el nombre de un método (sin paréntesis)
ms.date: 07/20/2015
f1_keywords:
- vbc30577
- bc30577
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
ms.openlocfilehash: 37b02ab76730458b757835fda37b8cb145ed93ad
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55262119"
---
# <a name="addressof-operand-must-be-the-name-of-a-method-without-parentheses"></a><span data-ttu-id="1ced9-102">El operando 'AddressOf' debe ser el nombre de un método (sin paréntesis)</span><span class="sxs-lookup"><span data-stu-id="1ced9-102">'AddressOf' operand must be the name of a method (without parentheses)</span></span>
<span data-ttu-id="1ced9-103">El operador `AddressOf` crea una instancia de delegado de procedimiento que hace referencia a un procedimiento específico.</span><span class="sxs-lookup"><span data-stu-id="1ced9-103">The `AddressOf` operator creates a procedure delegate instance that references a specific procedure.</span></span> <span data-ttu-id="1ced9-104">La sintaxis es como sigue.</span><span class="sxs-lookup"><span data-stu-id="1ced9-104">The syntax is as follows.</span></span>  
  
 <span data-ttu-id="1ced9-105">`AddressOf` `procedurename`</span><span class="sxs-lookup"><span data-stu-id="1ced9-105">`AddressOf` `procedurename`</span></span>  
  
 <span data-ttu-id="1ced9-106">Insertar paréntesis que rodean el siguiente argumento `AddressOf`, donde no son necesarias.</span><span class="sxs-lookup"><span data-stu-id="1ced9-106">You inserted parentheses around the argument following `AddressOf`, where none are needed.</span></span>  
  
 <span data-ttu-id="1ced9-107">**Identificador de error:** BC30577</span><span class="sxs-lookup"><span data-stu-id="1ced9-107">**Error ID:** BC30577</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1ced9-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="1ced9-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="1ced9-109">Quite los paréntesis que rodean el siguiente argumento `AddressOf`.</span><span class="sxs-lookup"><span data-stu-id="1ced9-109">Remove the parentheses around the argument following `AddressOf`.</span></span>  
  
2.  <span data-ttu-id="1ced9-110">Asegúrese de que el argumento es un nombre de método.</span><span class="sxs-lookup"><span data-stu-id="1ced9-110">Make sure the argument is a method name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ced9-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ced9-111">See also</span></span>
- [<span data-ttu-id="1ced9-112">AddressOf (operador)</span><span class="sxs-lookup"><span data-stu-id="1ced9-112">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="1ced9-113">Delegados</span><span class="sxs-lookup"><span data-stu-id="1ced9-113">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
