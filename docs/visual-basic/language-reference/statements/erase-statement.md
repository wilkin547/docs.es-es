---
title: "Erase (Instrucción, Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 45a2b439cf5ad04d59cea59bb21d345d0057b322
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="erase-statement-visual-basic"></a><span data-ttu-id="ef073-102">Erase (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ef073-102">Erase Statement (Visual Basic)</span></span>
<span data-ttu-id="ef073-103">Se utiliza para liberar variables de matriz y desasignar la memoria utilizada para sus elementos.</span><span class="sxs-lookup"><span data-stu-id="ef073-103">Used to release array variables and deallocate the memory used for their elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef073-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ef073-104">Syntax</span></span>  
  
```  
Erase arraylist  
```  
  
## <a name="parts"></a><span data-ttu-id="ef073-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="ef073-105">Parts</span></span>  
 `arraylist`  
 <span data-ttu-id="ef073-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="ef073-106">Required.</span></span> <span data-ttu-id="ef073-107">Lista de variables de matriz que se va a borrar.</span><span class="sxs-lookup"><span data-stu-id="ef073-107">List of array variables to be erased.</span></span> <span data-ttu-id="ef073-108">Las variables se separan con comas.</span><span class="sxs-lookup"><span data-stu-id="ef073-108">Multiple variables are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef073-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ef073-109">Remarks</span></span>  
 <span data-ttu-id="ef073-110">El `Erase` instrucción puede aparecer en el nivel de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="ef073-110">The `Erase` statement can appear only at procedure level.</span></span> <span data-ttu-id="ef073-111">Esto significa que puede liberar matrices dentro de un procedimiento pero no en el nivel de clase o módulo.</span><span class="sxs-lookup"><span data-stu-id="ef073-111">This means you can release arrays inside a procedure but not at class or module level.</span></span>  
  
 <span data-ttu-id="ef073-112">El `Erase` instrucción es equivalente a asignar `Nothing` a cada variable de matriz.</span><span class="sxs-lookup"><span data-stu-id="ef073-112">The `Erase` statement is equivalent to assigning `Nothing` to each array variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef073-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ef073-113">Example</span></span>  
 <span data-ttu-id="ef073-114">En el ejemplo siguiente se usa el `Erase` instrucción borrar dos matrices y liberar su memoria (1000 y 100 elementos de almacenamiento, respectivamente).</span><span class="sxs-lookup"><span data-stu-id="ef073-114">The following example uses the `Erase` statement to clear two arrays and free their memory (1000 and 100 storage elements, respectively).</span></span> <span data-ttu-id="ef073-115">El `ReDim` , a continuación, la instrucción asigna una nueva instancia de matriz a la matriz tridimensional.</span><span class="sxs-lookup"><span data-stu-id="ef073-115">The `ReDim` statement then assigns a new array instance to the three-dimensional array.</span></span>  
  
 [!code-vb[VbVbalrStatements#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/erase-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ef073-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef073-116">See Also</span></span>  
 [<span data-ttu-id="ef073-117">Nothing</span><span class="sxs-lookup"><span data-stu-id="ef073-117">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)  
 [<span data-ttu-id="ef073-118">ReDim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ef073-118">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
