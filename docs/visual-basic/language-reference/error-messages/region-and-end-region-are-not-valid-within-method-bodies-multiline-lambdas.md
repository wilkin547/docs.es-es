---
title: Las instrucciones '#Region' y '#End Region' no son válidas dentro de lambda de varias líneas cuerpos de método
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: deef3de645040d7c3d95b1a6c8a25fcf10de881b
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58842712"
---
# <a name="region-and-end-region-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a><span data-ttu-id="031c1-102">Las instrucciones '#Region' y '#End Region' no son válidas en los cuerpos de método y operaciones lambda de varias líneas</span><span class="sxs-lookup"><span data-stu-id="031c1-102">'#Region' and '#End Region' statements are not valid within method bodies/multiline lambdas</span></span>
<span data-ttu-id="031c1-103">El `#Region` bloque debe declararse en un nivel de clase, módulo o espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="031c1-103">The `#Region` block must be declared at a class, module, or namespace level.</span></span> <span data-ttu-id="031c1-104">Una región contraíble puede incluir uno o varios procedimientos, pero no puede comenzar ni terminar dentro de un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="031c1-104">A collapsible region can include one or more procedures, but it cannot begin or end inside of a procedure.</span></span>  
  
 <span data-ttu-id="031c1-105">**Identificador de error:** BC32025</span><span class="sxs-lookup"><span data-stu-id="031c1-105">**Error ID:** BC32025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="031c1-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="031c1-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="031c1-107">Asegúrese de que el procedimiento anterior esté terminado correctamente con un `End Function` o `End Sub` instrucción.</span><span class="sxs-lookup"><span data-stu-id="031c1-107">Ensure that the preceding procedure is properly terminated with an `End Function` or `End Sub` statement.</span></span>  
  
2.  <span data-ttu-id="031c1-108">Asegúrese de que el `#Region` y `#End Region` las directivas tienen el mismo bloque de código.</span><span class="sxs-lookup"><span data-stu-id="031c1-108">Ensure that the `#Region` and `#End Region` directives are in the same code block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="031c1-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="031c1-109">See also</span></span>

- [<span data-ttu-id="031c1-110">#Region (directiva)</span><span class="sxs-lookup"><span data-stu-id="031c1-110">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)
