---
title: "&#39; AddressOf &#39; operando debe ser el nombre de un método (sin paréntesis)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30577
- bc30577
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 02c996f1c94250526982e35395288b07db619db7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="39addressof39-operand-must-be-the-name-of-a-method-without-parentheses"></a><span data-ttu-id="63890-102">&#39; AddressOf &#39; operando debe ser el nombre de un método (sin paréntesis)</span><span class="sxs-lookup"><span data-stu-id="63890-102">&#39;AddressOf&#39; operand must be the name of a method (without parentheses)</span></span>
<span data-ttu-id="63890-103">El operador `AddressOf` crea una instancia de delegado de procedimiento que hace referencia a un procedimiento específico.</span><span class="sxs-lookup"><span data-stu-id="63890-103">The `AddressOf` operator creates a procedure delegate instance that references a specific procedure.</span></span> <span data-ttu-id="63890-104">La sintaxis es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="63890-104">The syntax is as follows.</span></span>  
  
 <span data-ttu-id="63890-105">`AddressOf` `procedurename`</span><span class="sxs-lookup"><span data-stu-id="63890-105">`AddressOf` `procedurename`</span></span>  
  
 <span data-ttu-id="63890-106">Inserta el siguiente argumento entre paréntesis `AddressOf`, donde se necesita ninguno.</span><span class="sxs-lookup"><span data-stu-id="63890-106">You inserted parentheses around the argument following `AddressOf`, where none are needed.</span></span>  
  
 <span data-ttu-id="63890-107">**Id. de error:** BC30577</span><span class="sxs-lookup"><span data-stu-id="63890-107">**Error ID:** BC30577</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="63890-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="63890-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="63890-109">Quite los paréntesis que rodean el siguiente argumento `AddressOf`.</span><span class="sxs-lookup"><span data-stu-id="63890-109">Remove the parentheses around the argument following `AddressOf`.</span></span>  
  
2.  <span data-ttu-id="63890-110">Asegúrese de que el argumento es un nombre de método.</span><span class="sxs-lookup"><span data-stu-id="63890-110">Make sure the argument is a method name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63890-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="63890-111">See Also</span></span>  
 [<span data-ttu-id="63890-112">AddressOf (operador)</span><span class="sxs-lookup"><span data-stu-id="63890-112">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [<span data-ttu-id="63890-113">Delegados</span><span class="sxs-lookup"><span data-stu-id="63890-113">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
