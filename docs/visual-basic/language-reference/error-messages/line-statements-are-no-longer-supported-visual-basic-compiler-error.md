---
description: "Más información sobre: BC30830: las instrucciones ' line ' ya no se admiten"
title: Ya no se admiten instrucciones 'Line' (error del compilador de Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
ms.openlocfilehash: 16696856cee365171000e7b0abc206c42d3f3174
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795877"
---
# <a name="bc30830-line-statements-are-no-longer-supported"></a><span data-ttu-id="4c585-103">BC30830: ya no se admiten instrucciones ' line '</span><span class="sxs-lookup"><span data-stu-id="4c585-103">BC30830: 'Line' statements are no longer supported</span></span>

<span data-ttu-id="4c585-104">Ya no se admiten instrucciones de línea.</span><span class="sxs-lookup"><span data-stu-id="4c585-104">Line statements are no longer supported.</span></span> <span data-ttu-id="4c585-105">La funcionalidad de e/s de archivos está disponible como `Microsoft.VisualBasic.FileSystem.LineInput` y la funcionalidad de gráficos está disponible como `System.Drawing.Graphics.DrawLine` .</span><span class="sxs-lookup"><span data-stu-id="4c585-105">File I/O functionality is available as `Microsoft.VisualBasic.FileSystem.LineInput` and graphics functionality is available as `System.Drawing.Graphics.DrawLine`.</span></span>

 <span data-ttu-id="4c585-106">**Identificador de error:** BC30830</span><span class="sxs-lookup"><span data-stu-id="4c585-106">**Error ID:** BC30830</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="4c585-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="4c585-107">To correct this error</span></span>

- <span data-ttu-id="4c585-108">Si se realiza el acceso a archivos, use `Microsoft.VisualBasic.FileSystem.LineInput` .</span><span class="sxs-lookup"><span data-stu-id="4c585-108">If performing file access, use `Microsoft.VisualBasic.FileSystem.LineInput`.</span></span>

- <span data-ttu-id="4c585-109">Si está realizando gráficos, use `System.Drawing.Graphics.Drawline`.</span><span class="sxs-lookup"><span data-stu-id="4c585-109">If performing graphics, use `System.Drawing.Graphics.Drawline`.</span></span>

## <a name="see-also"></a><span data-ttu-id="4c585-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c585-110">See also</span></span>

- <xref:System.IO>
- <xref:System.Drawing>
- [<span data-ttu-id="4c585-111">Acceso a archivos con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4c585-111">File Access with Visual Basic</span></span>](../../developing-apps/programming/drives-directories-files/file-access.md)
