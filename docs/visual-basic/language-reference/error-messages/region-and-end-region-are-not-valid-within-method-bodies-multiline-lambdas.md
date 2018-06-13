---
title: '&#39;#Region&#39; y &#39;#End Region&#39; instrucciones no son válidas dentro de expresiones lambda de multilínea de cuerpos de método'
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: bf3843e0ec3009f3dc7d60e91c340a7f20543231
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593238"
---
# <a name="39region39-and-39end-region39-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a><span data-ttu-id="5f6f7-102">&#39;#Region&#39; y &#39;#End Region&#39; instrucciones no son válidas dentro de expresiones lambda de varias líneas/cuerpos de método</span><span class="sxs-lookup"><span data-stu-id="5f6f7-102">&#39;#Region&#39; and &#39;#End Region&#39; statements are not valid within method bodies/multiline lambdas</span></span>
<span data-ttu-id="5f6f7-103">El `#Region` bloque debe declararse en un nivel de clase, módulo o espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="5f6f7-103">The `#Region` block must be declared at a class, module, or namespace level.</span></span> <span data-ttu-id="5f6f7-104">Una región contraíble puede incluir uno o varios procedimientos, pero no puede comenzar ni terminar dentro de un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="5f6f7-104">A collapsible region can include one or more procedures, but it cannot begin or end inside of a procedure.</span></span>  
  
 <span data-ttu-id="5f6f7-105">**Id. de error:** BC32025</span><span class="sxs-lookup"><span data-stu-id="5f6f7-105">**Error ID:** BC32025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5f6f7-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="5f6f7-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="5f6f7-107">Asegúrese de que el procedimiento anterior esté terminado correctamente con un `End Function` o `End Sub` instrucción.</span><span class="sxs-lookup"><span data-stu-id="5f6f7-107">Ensure that the preceding procedure is properly terminated with an `End Function` or `End Sub` statement.</span></span>  
  
2.  <span data-ttu-id="5f6f7-108">Asegúrese de que el `#Region` y `#End Region` directivas están en el mismo bloque de código.</span><span class="sxs-lookup"><span data-stu-id="5f6f7-108">Ensure that the `#Region` and `#End Region` directives are in the same code block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f6f7-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f6f7-109">See Also</span></span>  
 [<span data-ttu-id="5f6f7-110">#Region (directiva)</span><span class="sxs-lookup"><span data-stu-id="5f6f7-110">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)
