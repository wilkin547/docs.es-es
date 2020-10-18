---
title: Ya no se admiten instrucciones 'Line' (error del compilador de Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
ms.openlocfilehash: f34095becf321c6cb4b316b6378a2da0107577ba
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162484"
---
# <a name="bc30830-line-statements-are-no-longer-supported"></a><span data-ttu-id="e5ef3-102">BC30830: ya no se admiten instrucciones ' line '</span><span class="sxs-lookup"><span data-stu-id="e5ef3-102">BC30830: 'Line' statements are no longer supported</span></span>

<span data-ttu-id="e5ef3-103">Ya no se admiten instrucciones de línea.</span><span class="sxs-lookup"><span data-stu-id="e5ef3-103">Line statements are no longer supported.</span></span> <span data-ttu-id="e5ef3-104">La funcionalidad de e/s de archivos está disponible como `Microsoft.VisualBasic.FileSystem.LineInput` y la funcionalidad de gráficos está disponible como `System.Drawing.Graphics.DrawLine` .</span><span class="sxs-lookup"><span data-stu-id="e5ef3-104">File I/O functionality is available as `Microsoft.VisualBasic.FileSystem.LineInput` and graphics functionality is available as `System.Drawing.Graphics.DrawLine`.</span></span>

 <span data-ttu-id="e5ef3-105">**Identificador de error:** BC30830</span><span class="sxs-lookup"><span data-stu-id="e5ef3-105">**Error ID:** BC30830</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="e5ef3-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="e5ef3-106">To correct this error</span></span>

- <span data-ttu-id="e5ef3-107">Si se realiza el acceso a archivos, use `Microsoft.VisualBasic.FileSystem.LineInput` .</span><span class="sxs-lookup"><span data-stu-id="e5ef3-107">If performing file access, use `Microsoft.VisualBasic.FileSystem.LineInput`.</span></span>

- <span data-ttu-id="e5ef3-108">Si está realizando gráficos, use `System.Drawing.Graphics.Drawline`.</span><span class="sxs-lookup"><span data-stu-id="e5ef3-108">If performing graphics, use `System.Drawing.Graphics.Drawline`.</span></span>

## <a name="see-also"></a><span data-ttu-id="e5ef3-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5ef3-109">See also</span></span>

- <xref:System.IO>
- <xref:System.Drawing>
- [<span data-ttu-id="e5ef3-110">Acceso a archivos con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e5ef3-110">File Access with Visual Basic</span></span>](../../developing-apps/programming/drives-directories-files/file-access.md)
