---
description: 'Más información acerca de: resume sin errores'
title: Reanudar sin error
ms.date: 07/20/2015
f1_keywords:
- vbrID20
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
ms.openlocfilehash: a2284484be65ae975c6e09499ec19e3cfd8d4a04
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792016"
---
# <a name="resume-without-error"></a><span data-ttu-id="d8978-103">Reanudar sin error</span><span class="sxs-lookup"><span data-stu-id="d8978-103">Resume without error</span></span>

<span data-ttu-id="d8978-104">Una `Resume` instrucción aparecía fuera del código de control de errores o el código saltó a un controlador de errores, aunque no se haya producido ningún error.</span><span class="sxs-lookup"><span data-stu-id="d8978-104">A `Resume` statement appeared outside error-handling code, or the code jumped into an error handler even though there was no error.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d8978-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="d8978-105">To correct this error</span></span>  
  
1. <span data-ttu-id="d8978-106">Mueva la `Resume` instrucción a un controlador de errores o elimínela.</span><span class="sxs-lookup"><span data-stu-id="d8978-106">Move the `Resume` statement into an error handler, or delete it.</span></span>  
  
2. <span data-ttu-id="d8978-107">Los saltos a las etiquetas no pueden producirse en los procedimientos, por lo que busque en el procedimiento la etiqueta que identifica el controlador de errores.</span><span class="sxs-lookup"><span data-stu-id="d8978-107">Jumps to labels cannot occur across procedures, so search the procedure for the label that identifies the error handler.</span></span> <span data-ttu-id="d8978-108">Si encuentra una etiqueta duplicada especificada como destino de una `GoTo` instrucción que no es una `On Error GoTo` instrucción, cambie la etiqueta de línea para que coincida con su destino previsto.</span><span class="sxs-lookup"><span data-stu-id="d8978-108">If you find a duplicate label specified as the target of a `GoTo` statement that isn't an `On Error GoTo` statement, change the line label to agree with its intended target.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8978-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8978-109">See also</span></span>

- [<span data-ttu-id="d8978-110">Resume (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="d8978-110">Resume Statement</span></span>](../statements/resume-statement.md)
- [<span data-ttu-id="d8978-111">Instrucción On Error</span><span class="sxs-lookup"><span data-stu-id="d8978-111">On Error Statement</span></span>](../statements/on-error-statement.md)
