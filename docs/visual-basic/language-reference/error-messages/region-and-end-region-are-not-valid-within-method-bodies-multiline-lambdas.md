---
description: "Más información sobre: BC32025: las instrucciones ' #Region ' y ' #End region ' no son válidas en los cuerpos de método/expresiones lambda de varias líneas"
title: Las instrucciones "#Region" y "#End Region" no son válidas en los cuerpos de método y operaciones lambda de varias líneas
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: 0746b9caf677699d6fbbf0c5a7063b1b33d86f3a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792029"
---
# <a name="bc32025-region-and-end-region-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a><span data-ttu-id="536e7-103">BC32025: las instrucciones ' #Region ' y ' #End region ' no son válidas en cuerpos de método o expresiones lambda de varias líneas</span><span class="sxs-lookup"><span data-stu-id="536e7-103">BC32025: '#Region' and '#End Region' statements are not valid within method bodies/multiline lambdas</span></span>

<span data-ttu-id="536e7-104">El `#Region` bloque se debe declarar en el nivel de clase, módulo o espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="536e7-104">The `#Region` block must be declared at a class, module, or namespace level.</span></span> <span data-ttu-id="536e7-105">Una región contraíble puede incluir uno o varios procedimientos, pero no puede comenzar ni finalizar dentro de un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="536e7-105">A collapsible region can include one or more procedures, but it cannot begin or end inside of a procedure.</span></span>

 <span data-ttu-id="536e7-106">**Identificador de error:** BC32025</span><span class="sxs-lookup"><span data-stu-id="536e7-106">**Error ID:** BC32025</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="536e7-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="536e7-107">To correct this error</span></span>

1. <span data-ttu-id="536e7-108">Asegúrese de que el procedimiento anterior finaliza correctamente con una `End Function` `End Sub` instrucción o.</span><span class="sxs-lookup"><span data-stu-id="536e7-108">Ensure that the preceding procedure is properly terminated with an `End Function` or `End Sub` statement.</span></span>

2. <span data-ttu-id="536e7-109">Asegúrese de que `#Region` las `#End Region` directivas y están en el mismo bloque de código.</span><span class="sxs-lookup"><span data-stu-id="536e7-109">Ensure that the `#Region` and `#End Region` directives are in the same code block.</span></span>

## <a name="see-also"></a><span data-ttu-id="536e7-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="536e7-110">See also</span></span>

- [<span data-ttu-id="536e7-111">#Region (Directiva)</span><span class="sxs-lookup"><span data-stu-id="536e7-111">#Region Directive</span></span>](../directives/region-directive.md)
