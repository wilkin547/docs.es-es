---
title: Las instrucciones "#Region" y "#End Region" no son válidas en los cuerpos de método y operaciones lambda de varias líneas
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: c792fa1a42bde22959ae21439cb2a0a1e4be343f
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162289"
---
# <a name="bc32025-region-and-end-region-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a><span data-ttu-id="c02a2-102">BC32025: las instrucciones ' #Region ' y ' #End region ' no son válidas en cuerpos de método o expresiones lambda de varias líneas</span><span class="sxs-lookup"><span data-stu-id="c02a2-102">BC32025: '#Region' and '#End Region' statements are not valid within method bodies/multiline lambdas</span></span>

<span data-ttu-id="c02a2-103">El `#Region` bloque se debe declarar en el nivel de clase, módulo o espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="c02a2-103">The `#Region` block must be declared at a class, module, or namespace level.</span></span> <span data-ttu-id="c02a2-104">Una región contraíble puede incluir uno o varios procedimientos, pero no puede comenzar ni finalizar dentro de un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c02a2-104">A collapsible region can include one or more procedures, but it cannot begin or end inside of a procedure.</span></span>

 <span data-ttu-id="c02a2-105">**Identificador de error:** BC32025</span><span class="sxs-lookup"><span data-stu-id="c02a2-105">**Error ID:** BC32025</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="c02a2-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="c02a2-106">To correct this error</span></span>

1. <span data-ttu-id="c02a2-107">Asegúrese de que el procedimiento anterior finaliza correctamente con una `End Function` `End Sub` instrucción o.</span><span class="sxs-lookup"><span data-stu-id="c02a2-107">Ensure that the preceding procedure is properly terminated with an `End Function` or `End Sub` statement.</span></span>

2. <span data-ttu-id="c02a2-108">Asegúrese de que `#Region` las `#End Region` directivas y están en el mismo bloque de código.</span><span class="sxs-lookup"><span data-stu-id="c02a2-108">Ensure that the `#Region` and `#End Region` directives are in the same code block.</span></span>

## <a name="see-also"></a><span data-ttu-id="c02a2-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="c02a2-109">See also</span></span>

- [<span data-ttu-id="c02a2-110">#Region (Directiva)</span><span class="sxs-lookup"><span data-stu-id="c02a2-110">#Region Directive</span></span>](../directives/region-directive.md)
