---
title: Ya no se admiten instrucciones 'Line' (error del compilador de Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
ms.openlocfilehash: a3d243f39f3fc45ca6b1ba0d26892d4c3db56f59
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397303"
---
# <a name="line-statements-are-no-longer-supported-visual-basic-compiler-error"></a><span data-ttu-id="8c6df-102">Ya no se admiten instrucciones 'Line' (error del compilador de Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c6df-102">'Line' statements are no longer supported (Visual Basic Compiler Error)</span></span>
<span data-ttu-id="8c6df-103">Ya no se admiten instrucciones de línea.</span><span class="sxs-lookup"><span data-stu-id="8c6df-103">Line statements are no longer supported.</span></span> <span data-ttu-id="8c6df-104">La funcionalidad de e/s de archivos está disponible como `Microsoft.VisualBasic.FileSystem.LineInput` y la funcionalidad de gráficos está disponible como `System.Drawing.Graphics.DrawLine` .</span><span class="sxs-lookup"><span data-stu-id="8c6df-104">File I/O functionality is available as `Microsoft.VisualBasic.FileSystem.LineInput` and graphics functionality is available as `System.Drawing.Graphics.DrawLine`.</span></span>  
  
 <span data-ttu-id="8c6df-105">**Identificador de error:** BC30830</span><span class="sxs-lookup"><span data-stu-id="8c6df-105">**Error ID:** BC30830</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8c6df-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="8c6df-106">To correct this error</span></span>  
  
1. <span data-ttu-id="8c6df-107">Si se realiza el acceso a archivos, use `Microsoft.VisualBasic.FileSystem.LineInput` .</span><span class="sxs-lookup"><span data-stu-id="8c6df-107">If performing file access, use `Microsoft.VisualBasic.FileSystem.LineInput`.</span></span>  
  
2. <span data-ttu-id="8c6df-108">Si está realizando gráficos, use `System.Drawing.Graphics.Drawline`.</span><span class="sxs-lookup"><span data-stu-id="8c6df-108">If performing graphics, use `System.Drawing.Graphics.Drawline`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c6df-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8c6df-109">See also</span></span>

- <xref:System.IO>
- <xref:System.Drawing>
- [<span data-ttu-id="8c6df-110">Acceso a archivos con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8c6df-110">File Access with Visual Basic</span></span>](../../developing-apps/programming/drives-directories-files/file-access.md)
