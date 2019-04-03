---
title: Erase (Instrucción, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: bf3eb6476dc1485faeddab475f29e508175d3378
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58840411"
---
# <a name="erase-statement-visual-basic"></a><span data-ttu-id="3eee0-102">Erase (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3eee0-102">Erase Statement (Visual Basic)</span></span>
<span data-ttu-id="3eee0-103">Se utiliza para liberar variables de matriz y desasignar la memoria utilizada para sus elementos.</span><span class="sxs-lookup"><span data-stu-id="3eee0-103">Used to release array variables and deallocate the memory used for their elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3eee0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3eee0-104">Syntax</span></span>  
  
```  
Erase arraylist  
```  
  
## <a name="parts"></a><span data-ttu-id="3eee0-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="3eee0-105">Parts</span></span>  
 `arraylist`  
 <span data-ttu-id="3eee0-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="3eee0-106">Required.</span></span> <span data-ttu-id="3eee0-107">Lista de variables de matriz debe borrarse.</span><span class="sxs-lookup"><span data-stu-id="3eee0-107">List of array variables to be erased.</span></span> <span data-ttu-id="3eee0-108">Las variables se separan con comas.</span><span class="sxs-lookup"><span data-stu-id="3eee0-108">Multiple variables are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3eee0-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3eee0-109">Remarks</span></span>  
 <span data-ttu-id="3eee0-110">El `Erase` instrucción sólo puede aparecer en el nivel de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="3eee0-110">The `Erase` statement can appear only at procedure level.</span></span> <span data-ttu-id="3eee0-111">Esto significa que puede publicar matrices dentro de un procedimiento, pero no en el nivel de clase o módulo.</span><span class="sxs-lookup"><span data-stu-id="3eee0-111">This means you can release arrays inside a procedure but not at class or module level.</span></span>  
  
 <span data-ttu-id="3eee0-112">El `Erase` instrucción es equivalente a asignar `Nothing` a cada variable de matriz.</span><span class="sxs-lookup"><span data-stu-id="3eee0-112">The `Erase` statement is equivalent to assigning `Nothing` to each array variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3eee0-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3eee0-113">Example</span></span>  
 <span data-ttu-id="3eee0-114">En el ejemplo siguiente se usa el `Erase` instrucción borrar dos matrices y liberar su memoria (1000 y 100 elementos de almacenamiento, respectivamente).</span><span class="sxs-lookup"><span data-stu-id="3eee0-114">The following example uses the `Erase` statement to clear two arrays and free their memory (1000 and 100 storage elements, respectively).</span></span> <span data-ttu-id="3eee0-115">El `ReDim` instrucción, a continuación, asigna una nueva instancia de matriz a la matriz tridimensional.</span><span class="sxs-lookup"><span data-stu-id="3eee0-115">The `ReDim` statement then assigns a new array instance to the three-dimensional array.</span></span>  
  
 [!code-vb[VbVbalrStatements#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="3eee0-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="3eee0-116">See also</span></span>

- [<span data-ttu-id="3eee0-117">Nothing</span><span class="sxs-lookup"><span data-stu-id="3eee0-117">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)
- [<span data-ttu-id="3eee0-118">ReDim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="3eee0-118">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
