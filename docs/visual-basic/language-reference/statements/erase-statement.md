---
description: 'Más información sobre: instrucción Erase (Visual Basic)'
title: Instrucción Erase
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: 295abec89f3d69f8f2641a5a3d574a2d10f98474
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99769161"
---
# <a name="erase-statement-visual-basic"></a><span data-ttu-id="44e97-103">Erase (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="44e97-103">Erase Statement (Visual Basic)</span></span>

<span data-ttu-id="44e97-104">Se usa para liberar las variables de matriz y desasignar la memoria usada para sus elementos.</span><span class="sxs-lookup"><span data-stu-id="44e97-104">Used to release array variables and deallocate the memory used for their elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44e97-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="44e97-105">Syntax</span></span>  
  
```vb  
Erase arraylist  
```  
  
## <a name="parts"></a><span data-ttu-id="44e97-106">Partes</span><span class="sxs-lookup"><span data-stu-id="44e97-106">Parts</span></span>  

 `arraylist`  
 <span data-ttu-id="44e97-107">Necesario.</span><span class="sxs-lookup"><span data-stu-id="44e97-107">Required.</span></span> <span data-ttu-id="44e97-108">Lista de variables de matriz que se van a borrar.</span><span class="sxs-lookup"><span data-stu-id="44e97-108">List of array variables to be erased.</span></span> <span data-ttu-id="44e97-109">Las variables se separan con comas.</span><span class="sxs-lookup"><span data-stu-id="44e97-109">Multiple variables are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44e97-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="44e97-110">Remarks</span></span>  

 <span data-ttu-id="44e97-111">La `Erase` instrucción solo puede aparecer en el nivel de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="44e97-111">The `Erase` statement can appear only at procedure level.</span></span> <span data-ttu-id="44e97-112">Esto significa que puede liberar matrices dentro de un procedimiento, pero no en el nivel de clase o módulo.</span><span class="sxs-lookup"><span data-stu-id="44e97-112">This means you can release arrays inside a procedure but not at class or module level.</span></span>  
  
 <span data-ttu-id="44e97-113">La `Erase` instrucción es equivalente a asignar `Nothing` a cada variable de matriz.</span><span class="sxs-lookup"><span data-stu-id="44e97-113">The `Erase` statement is equivalent to assigning `Nothing` to each array variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44e97-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="44e97-114">Example</span></span>  

 <span data-ttu-id="44e97-115">En el ejemplo siguiente se usa la `Erase` instrucción para borrar dos matrices y liberar su memoria (elementos de almacenamiento 1000 y 100, respectivamente).</span><span class="sxs-lookup"><span data-stu-id="44e97-115">The following example uses the `Erase` statement to clear two arrays and free their memory (1000 and 100 storage elements, respectively).</span></span> <span data-ttu-id="44e97-116">`ReDim`A continuación, la instrucción asigna una nueva instancia de matriz a la matriz de tres dimensiones.</span><span class="sxs-lookup"><span data-stu-id="44e97-116">The `ReDim` statement then assigns a new array instance to the three-dimensional array.</span></span>  
  
 [!code-vb[VbVbalrStatements#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="44e97-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="44e97-117">See also</span></span>

- [<span data-ttu-id="44e97-118">Nothing</span><span class="sxs-lookup"><span data-stu-id="44e97-118">Nothing</span></span>](../nothing.md)
- [<span data-ttu-id="44e97-119">Instrucción ReDim</span><span class="sxs-lookup"><span data-stu-id="44e97-119">ReDim Statement</span></span>](redim-statement.md)
