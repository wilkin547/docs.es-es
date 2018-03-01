---
title: "&#39; #Region &#39; y &#39; #End Region &#39; las instrucciones no son válidas dentro de expresiones lambda de multilínea de cuerpos de método"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 614d0c7324bfbf07bc5736c799e8b54937ead081
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="39region39-and-39end-region39-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a><span data-ttu-id="609a3-102">&#39; #Region &#39; y &#39; #End Region &#39; las instrucciones no son válidas dentro de expresiones lambda de varias líneas/cuerpos de método</span><span class="sxs-lookup"><span data-stu-id="609a3-102">&#39;#Region&#39; and &#39;#End Region&#39; statements are not valid within method bodies/multiline lambdas</span></span>
<span data-ttu-id="609a3-103">El `#Region` bloque debe declararse en un nivel de clase, módulo o espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="609a3-103">The `#Region` block must be declared at a class, module, or namespace level.</span></span> <span data-ttu-id="609a3-104">Una región contraíble puede incluir uno o varios procedimientos, pero no puede comenzar ni terminar dentro de un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="609a3-104">A collapsible region can include one or more procedures, but it cannot begin or end inside of a procedure.</span></span>  
  
 <span data-ttu-id="609a3-105">**Id. de error:** BC32025</span><span class="sxs-lookup"><span data-stu-id="609a3-105">**Error ID:** BC32025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="609a3-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="609a3-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="609a3-107">Asegúrese de que el procedimiento anterior esté terminado correctamente con un `End Function` o `End Sub` instrucción.</span><span class="sxs-lookup"><span data-stu-id="609a3-107">Ensure that the preceding procedure is properly terminated with an `End Function` or `End Sub` statement.</span></span>  
  
2.  <span data-ttu-id="609a3-108">Asegúrese de que el `#Region` y `#End Region` directivas están en el mismo bloque de código.</span><span class="sxs-lookup"><span data-stu-id="609a3-108">Ensure that the `#Region` and `#End Region` directives are in the same code block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="609a3-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="609a3-109">See Also</span></span>  
 [<span data-ttu-id="609a3-110">#Region (directiva)</span><span class="sxs-lookup"><span data-stu-id="609a3-110">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)
