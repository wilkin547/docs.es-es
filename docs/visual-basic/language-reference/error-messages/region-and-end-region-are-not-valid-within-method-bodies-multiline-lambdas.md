---
title: Las instrucciones "#Region" y "#End Region" no son válidas en los cuerpos de método y operaciones lambda de varias líneas
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: e3147b6192f54ce85d0fecd6b67f7d80f6281b54
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870885"
---
# <a name="region-and-end-region-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a><span data-ttu-id="4c5da-102">Las instrucciones '#Region' y '#End Region' no son válidas en los cuerpos de método y operaciones lambda de varias líneas</span><span class="sxs-lookup"><span data-stu-id="4c5da-102">'#Region' and '#End Region' statements are not valid within method bodies/multiline lambdas</span></span>

<span data-ttu-id="4c5da-103">El `#Region` bloque se debe declarar en el nivel de clase, módulo o espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="4c5da-103">The `#Region` block must be declared at a class, module, or namespace level.</span></span> <span data-ttu-id="4c5da-104">Una región contraíble puede incluir uno o varios procedimientos, pero no puede comenzar ni finalizar dentro de un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="4c5da-104">A collapsible region can include one or more procedures, but it cannot begin or end inside of a procedure.</span></span>  
  
 <span data-ttu-id="4c5da-105">**Identificador de error:** BC32025</span><span class="sxs-lookup"><span data-stu-id="4c5da-105">**Error ID:** BC32025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4c5da-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="4c5da-106">To correct this error</span></span>  
  
1. <span data-ttu-id="4c5da-107">Asegúrese de que el procedimiento anterior finaliza correctamente con una `End Function` `End Sub` instrucción o.</span><span class="sxs-lookup"><span data-stu-id="4c5da-107">Ensure that the preceding procedure is properly terminated with an `End Function` or `End Sub` statement.</span></span>  
  
2. <span data-ttu-id="4c5da-108">Asegúrese de que `#Region` las `#End Region` directivas y están en el mismo bloque de código.</span><span class="sxs-lookup"><span data-stu-id="4c5da-108">Ensure that the `#Region` and `#End Region` directives are in the same code block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c5da-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4c5da-109">See also</span></span>

- [<span data-ttu-id="4c5da-110">#Region (Directiva)</span><span class="sxs-lookup"><span data-stu-id="4c5da-110">#Region Directive</span></span>](../directives/region-directive.md)
