---
title: Reanudar sin error
ms.date: 07/20/2015
f1_keywords:
- vbrID20
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
ms.openlocfilehash: 6dd6805151de52a5e0cf51c520485c0e8558e0a7
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870837"
---
# <a name="resume-without-error"></a><span data-ttu-id="72716-102">Reanudar sin error</span><span class="sxs-lookup"><span data-stu-id="72716-102">Resume without error</span></span>

<span data-ttu-id="72716-103">Una `Resume` instrucción aparecía fuera del código de control de errores o el código saltó a un controlador de errores, aunque no se haya producido ningún error.</span><span class="sxs-lookup"><span data-stu-id="72716-103">A `Resume` statement appeared outside error-handling code, or the code jumped into an error handler even though there was no error.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="72716-104">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="72716-104">To correct this error</span></span>  
  
1. <span data-ttu-id="72716-105">Mueva la `Resume` instrucción a un controlador de errores o elimínela.</span><span class="sxs-lookup"><span data-stu-id="72716-105">Move the `Resume` statement into an error handler, or delete it.</span></span>  
  
2. <span data-ttu-id="72716-106">Los saltos a las etiquetas no pueden producirse en los procedimientos, por lo que busque en el procedimiento la etiqueta que identifica el controlador de errores.</span><span class="sxs-lookup"><span data-stu-id="72716-106">Jumps to labels cannot occur across procedures, so search the procedure for the label that identifies the error handler.</span></span> <span data-ttu-id="72716-107">Si encuentra una etiqueta duplicada especificada como destino de una `GoTo` instrucción que no es una `On Error GoTo` instrucción, cambie la etiqueta de línea para que coincida con su destino previsto.</span><span class="sxs-lookup"><span data-stu-id="72716-107">If you find a duplicate label specified as the target of a `GoTo` statement that isn't an `On Error GoTo` statement, change the line label to agree with its intended target.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72716-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="72716-108">See also</span></span>

- [<span data-ttu-id="72716-109">Resume (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="72716-109">Resume Statement</span></span>](../statements/resume-statement.md)
- [<span data-ttu-id="72716-110">Instrucción On Error</span><span class="sxs-lookup"><span data-stu-id="72716-110">On Error Statement</span></span>](../statements/on-error-statement.md)
