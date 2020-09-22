---
title: Instrucción Erase
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: 33d88b5ce71ceab8d4b4b59d356c53a804c360be
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873291"
---
# <a name="erase-statement-visual-basic"></a><span data-ttu-id="33396-102">Erase (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="33396-102">Erase Statement (Visual Basic)</span></span>

<span data-ttu-id="33396-103">Se usa para liberar las variables de matriz y desasignar la memoria usada para sus elementos.</span><span class="sxs-lookup"><span data-stu-id="33396-103">Used to release array variables and deallocate the memory used for their elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33396-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33396-104">Syntax</span></span>  
  
```vb  
Erase arraylist  
```  
  
## <a name="parts"></a><span data-ttu-id="33396-105">Partes</span><span class="sxs-lookup"><span data-stu-id="33396-105">Parts</span></span>  

 `arraylist`  
 <span data-ttu-id="33396-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="33396-106">Required.</span></span> <span data-ttu-id="33396-107">Lista de variables de matriz que se van a borrar.</span><span class="sxs-lookup"><span data-stu-id="33396-107">List of array variables to be erased.</span></span> <span data-ttu-id="33396-108">Las variables se separan con comas.</span><span class="sxs-lookup"><span data-stu-id="33396-108">Multiple variables are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33396-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="33396-109">Remarks</span></span>  

 <span data-ttu-id="33396-110">La `Erase` instrucción solo puede aparecer en el nivel de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="33396-110">The `Erase` statement can appear only at procedure level.</span></span> <span data-ttu-id="33396-111">Esto significa que puede liberar matrices dentro de un procedimiento, pero no en el nivel de clase o módulo.</span><span class="sxs-lookup"><span data-stu-id="33396-111">This means you can release arrays inside a procedure but not at class or module level.</span></span>  
  
 <span data-ttu-id="33396-112">La `Erase` instrucción es equivalente a asignar `Nothing` a cada variable de matriz.</span><span class="sxs-lookup"><span data-stu-id="33396-112">The `Erase` statement is equivalent to assigning `Nothing` to each array variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33396-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="33396-113">Example</span></span>  

 <span data-ttu-id="33396-114">En el ejemplo siguiente se usa la `Erase` instrucción para borrar dos matrices y liberar su memoria (elementos de almacenamiento 1000 y 100, respectivamente).</span><span class="sxs-lookup"><span data-stu-id="33396-114">The following example uses the `Erase` statement to clear two arrays and free their memory (1000 and 100 storage elements, respectively).</span></span> <span data-ttu-id="33396-115">`ReDim`A continuación, la instrucción asigna una nueva instancia de matriz a la matriz de tres dimensiones.</span><span class="sxs-lookup"><span data-stu-id="33396-115">The `ReDim` statement then assigns a new array instance to the three-dimensional array.</span></span>  
  
 [!code-vb[VbVbalrStatements#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="33396-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="33396-116">See also</span></span>

- [<span data-ttu-id="33396-117">Nothing</span><span class="sxs-lookup"><span data-stu-id="33396-117">Nothing</span></span>](../nothing.md)
- [<span data-ttu-id="33396-118">Instrucción ReDim</span><span class="sxs-lookup"><span data-stu-id="33396-118">ReDim Statement</span></span>](redim-statement.md)
