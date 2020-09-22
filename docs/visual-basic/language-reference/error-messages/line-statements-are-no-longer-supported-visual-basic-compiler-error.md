---
title: Ya no se admiten instrucciones 'Line' (error del compilador de Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
ms.openlocfilehash: 4ca1538dbde0d585b7b421d60cde4531c00e9145
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873836"
---
# <a name="line-statements-are-no-longer-supported-visual-basic-compiler-error"></a><span data-ttu-id="562d8-102">Ya no se admiten instrucciones 'Line' (error del compilador de Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="562d8-102">'Line' statements are no longer supported (Visual Basic Compiler Error)</span></span>

<span data-ttu-id="562d8-103">Ya no se admiten instrucciones de línea.</span><span class="sxs-lookup"><span data-stu-id="562d8-103">Line statements are no longer supported.</span></span> <span data-ttu-id="562d8-104">La funcionalidad de e/s de archivos está disponible como `Microsoft.VisualBasic.FileSystem.LineInput` y la funcionalidad de gráficos está disponible como `System.Drawing.Graphics.DrawLine` .</span><span class="sxs-lookup"><span data-stu-id="562d8-104">File I/O functionality is available as `Microsoft.VisualBasic.FileSystem.LineInput` and graphics functionality is available as `System.Drawing.Graphics.DrawLine`.</span></span>  
  
 <span data-ttu-id="562d8-105">**Identificador de error:** BC30830</span><span class="sxs-lookup"><span data-stu-id="562d8-105">**Error ID:** BC30830</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="562d8-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="562d8-106">To correct this error</span></span>  
  
1. <span data-ttu-id="562d8-107">Si se realiza el acceso a archivos, use `Microsoft.VisualBasic.FileSystem.LineInput` .</span><span class="sxs-lookup"><span data-stu-id="562d8-107">If performing file access, use `Microsoft.VisualBasic.FileSystem.LineInput`.</span></span>  
  
2. <span data-ttu-id="562d8-108">Si está realizando gráficos, use `System.Drawing.Graphics.Drawline`.</span><span class="sxs-lookup"><span data-stu-id="562d8-108">If performing graphics, use `System.Drawing.Graphics.Drawline`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="562d8-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="562d8-109">See also</span></span>

- <xref:System.IO>
- <xref:System.Drawing>
- [<span data-ttu-id="562d8-110">Acceso a archivos con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="562d8-110">File Access with Visual Basic</span></span>](../../developing-apps/programming/drives-directories-files/file-access.md)
