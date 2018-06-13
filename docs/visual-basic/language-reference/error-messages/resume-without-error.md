---
title: Reanudar sin error
ms.date: 07/20/2015
f1_keywords:
- vbrID20
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
ms.openlocfilehash: 5e45f713a433365b4bbc8286154a3b877b08ec59
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33597880"
---
# <a name="resume-without-error"></a><span data-ttu-id="e955f-102">Reanudar sin error</span><span class="sxs-lookup"><span data-stu-id="e955f-102">Resume without error</span></span>
<span data-ttu-id="e955f-103">Un `Resume` instrucción ha aparecido fuera del código de control de errores o el código salta en un controlador de errores, incluso si se ha producido ningún error.</span><span class="sxs-lookup"><span data-stu-id="e955f-103">A `Resume` statement appeared outside error-handling code, or the code jumped into an error handler even though there was no error.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e955f-104">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="e955f-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="e955f-105">Mover el `Resume` instrucción en un controlador de errores, o eliminarla.</span><span class="sxs-lookup"><span data-stu-id="e955f-105">Move the `Resume` statement into an error handler, or delete it.</span></span>  
  
2.  <span data-ttu-id="e955f-106">Los saltos a etiquetas no se pueden realizar a través de procedimientos, de modo que busque el procedimiento para la etiqueta que identifica el controlador de errores.</span><span class="sxs-lookup"><span data-stu-id="e955f-106">Jumps to labels cannot occur across procedures, so search the procedure for the label that identifies the error handler.</span></span> <span data-ttu-id="e955f-107">Si encuentra una etiqueta duplicada especificada como destino de un `GoTo` instrucción que no sea un `On Error GoTo` (instrucción), cambie la etiqueta de línea para que coincida con su destino pretendido.</span><span class="sxs-lookup"><span data-stu-id="e955f-107">If you find a duplicate label specified as the target of a `GoTo` statement that isn't an `On Error GoTo` statement, change the line label to agree with its intended target.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e955f-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="e955f-108">See Also</span></span>  
 [<span data-ttu-id="e955f-109">Resume (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e955f-109">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)  
 [<span data-ttu-id="e955f-110">On Error (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e955f-110">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
