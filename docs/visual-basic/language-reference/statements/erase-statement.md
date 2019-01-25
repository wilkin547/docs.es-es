---
title: Erase (Instrucción, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: cab3da4465b4671d203036c2d9bcd40662dc234a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54522445"
---
# <a name="erase-statement-visual-basic"></a><span data-ttu-id="4d09e-102">Erase (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4d09e-102">Erase Statement (Visual Basic)</span></span>
<span data-ttu-id="4d09e-103">Se utiliza para liberar variables de matriz y desasignar la memoria utilizada para sus elementos.</span><span class="sxs-lookup"><span data-stu-id="4d09e-103">Used to release array variables and deallocate the memory used for their elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d09e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d09e-104">Syntax</span></span>  
  
```  
Erase arraylist  
```  
  
## <a name="parts"></a><span data-ttu-id="4d09e-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="4d09e-105">Parts</span></span>  
 `arraylist`  
 <span data-ttu-id="4d09e-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="4d09e-106">Required.</span></span> <span data-ttu-id="4d09e-107">Lista de variables de matriz debe borrarse.</span><span class="sxs-lookup"><span data-stu-id="4d09e-107">List of array variables to be erased.</span></span> <span data-ttu-id="4d09e-108">Las variables se separan con comas.</span><span class="sxs-lookup"><span data-stu-id="4d09e-108">Multiple variables are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d09e-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4d09e-109">Remarks</span></span>  
 <span data-ttu-id="4d09e-110">El `Erase` instrucción sólo puede aparecer en el nivel de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="4d09e-110">The `Erase` statement can appear only at procedure level.</span></span> <span data-ttu-id="4d09e-111">Esto significa que puede publicar matrices dentro de un procedimiento, pero no en el nivel de clase o módulo.</span><span class="sxs-lookup"><span data-stu-id="4d09e-111">This means you can release arrays inside a procedure but not at class or module level.</span></span>  
  
 <span data-ttu-id="4d09e-112">El `Erase` instrucción es equivalente a asignar `Nothing` a cada variable de matriz.</span><span class="sxs-lookup"><span data-stu-id="4d09e-112">The `Erase` statement is equivalent to assigning `Nothing` to each array variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d09e-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4d09e-113">Example</span></span>  
 <span data-ttu-id="4d09e-114">En el ejemplo siguiente se usa el `Erase` instrucción borrar dos matrices y liberar su memoria (1000 y 100 elementos de almacenamiento, respectivamente).</span><span class="sxs-lookup"><span data-stu-id="4d09e-114">The following example uses the `Erase` statement to clear two arrays and free their memory (1000 and 100 storage elements, respectively).</span></span> <span data-ttu-id="4d09e-115">El `ReDim` instrucción, a continuación, asigna una nueva instancia de matriz a la matriz tridimensional.</span><span class="sxs-lookup"><span data-stu-id="4d09e-115">The `ReDim` statement then assigns a new array instance to the three-dimensional array.</span></span>  
  
 [!code-vb[VbVbalrStatements#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/erase-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="4d09e-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d09e-116">See also</span></span>
- [<span data-ttu-id="4d09e-117">Nothing</span><span class="sxs-lookup"><span data-stu-id="4d09e-117">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)
- [<span data-ttu-id="4d09e-118">ReDim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="4d09e-118">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
