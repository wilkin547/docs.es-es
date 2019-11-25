---
title: Erase (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: 6d2052ceccbecd772c4e4bb18052aed74223a36e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343697"
---
# <a name="erase-statement-visual-basic"></a><span data-ttu-id="17ab1-102">Erase (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="17ab1-102">Erase Statement (Visual Basic)</span></span>
<span data-ttu-id="17ab1-103">Used to release array variables and deallocate the memory used for their elements.</span><span class="sxs-lookup"><span data-stu-id="17ab1-103">Used to release array variables and deallocate the memory used for their elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17ab1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="17ab1-104">Syntax</span></span>  
  
```vb  
Erase arraylist  
```  
  
## <a name="parts"></a><span data-ttu-id="17ab1-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="17ab1-105">Parts</span></span>  
 `arraylist`  
 <span data-ttu-id="17ab1-106">Requerido.</span><span class="sxs-lookup"><span data-stu-id="17ab1-106">Required.</span></span> <span data-ttu-id="17ab1-107">List of array variables to be erased.</span><span class="sxs-lookup"><span data-stu-id="17ab1-107">List of array variables to be erased.</span></span> <span data-ttu-id="17ab1-108">Las variables se separan con comas.</span><span class="sxs-lookup"><span data-stu-id="17ab1-108">Multiple variables are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="17ab1-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="17ab1-109">Remarks</span></span>  
 <span data-ttu-id="17ab1-110">The `Erase` statement can appear only at procedure level.</span><span class="sxs-lookup"><span data-stu-id="17ab1-110">The `Erase` statement can appear only at procedure level.</span></span> <span data-ttu-id="17ab1-111">This means you can release arrays inside a procedure but not at class or module level.</span><span class="sxs-lookup"><span data-stu-id="17ab1-111">This means you can release arrays inside a procedure but not at class or module level.</span></span>  
  
 <span data-ttu-id="17ab1-112">The `Erase` statement is equivalent to assigning `Nothing` to each array variable.</span><span class="sxs-lookup"><span data-stu-id="17ab1-112">The `Erase` statement is equivalent to assigning `Nothing` to each array variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17ab1-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="17ab1-113">Example</span></span>  
 <span data-ttu-id="17ab1-114">The following example uses the `Erase` statement to clear two arrays and free their memory (1000 and 100 storage elements, respectively).</span><span class="sxs-lookup"><span data-stu-id="17ab1-114">The following example uses the `Erase` statement to clear two arrays and free their memory (1000 and 100 storage elements, respectively).</span></span> <span data-ttu-id="17ab1-115">The `ReDim` statement then assigns a new array instance to the three-dimensional array.</span><span class="sxs-lookup"><span data-stu-id="17ab1-115">The `ReDim` statement then assigns a new array instance to the three-dimensional array.</span></span>  
  
 [!code-vb[VbVbalrStatements#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="17ab1-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="17ab1-116">See also</span></span>

- [<span data-ttu-id="17ab1-117">Nothing</span><span class="sxs-lookup"><span data-stu-id="17ab1-117">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)
- [<span data-ttu-id="17ab1-118">ReDim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="17ab1-118">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
