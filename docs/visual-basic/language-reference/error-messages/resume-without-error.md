---
title: Reanudar sin error
ms.date: 07/20/2015
f1_keywords:
- vbrID20
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
ms.openlocfilehash: 61332486b20af66af24eac06b222a38353578c16
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59300910"
---
# <a name="resume-without-error"></a><span data-ttu-id="3827e-102">Reanudar sin error</span><span class="sxs-lookup"><span data-stu-id="3827e-102">Resume without error</span></span>
<span data-ttu-id="3827e-103">Un `Resume` aparecido instrucción fuera del código de control de errores o el código pasó de un controlador de errores, aunque se ha producido ningún error.</span><span class="sxs-lookup"><span data-stu-id="3827e-103">A `Resume` statement appeared outside error-handling code, or the code jumped into an error handler even though there was no error.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3827e-104">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="3827e-104">To correct this error</span></span>  
  
1. <span data-ttu-id="3827e-105">Mover el `Resume` instrucción en un controlador de errores, o eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="3827e-105">Move the `Resume` statement into an error handler, or delete it.</span></span>  
  
2. <span data-ttu-id="3827e-106">No se pueden producir los saltos a etiquetas en los procedimientos, de modo que busque el procedimiento para la etiqueta que identifica el controlador de errores.</span><span class="sxs-lookup"><span data-stu-id="3827e-106">Jumps to labels cannot occur across procedures, so search the procedure for the label that identifies the error handler.</span></span> <span data-ttu-id="3827e-107">Si encuentra una etiqueta duplicada especificada como destino de un `GoTo` instrucción que no sea un `On Error GoTo` instrucción, cambiar la etiqueta de línea para que coincida con su destino pretendido.</span><span class="sxs-lookup"><span data-stu-id="3827e-107">If you find a duplicate label specified as the target of a `GoTo` statement that isn't an `On Error GoTo` statement, change the line label to agree with its intended target.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3827e-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="3827e-108">See also</span></span>

- [<span data-ttu-id="3827e-109">Resume (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="3827e-109">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)
- [<span data-ttu-id="3827e-110">On Error (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="3827e-110">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
