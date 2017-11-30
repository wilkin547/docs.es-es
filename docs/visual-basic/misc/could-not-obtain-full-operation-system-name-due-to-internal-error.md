---
title: No se pudo obtener el nombre completo del sistema operativo debido a un error interno
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrDiagnosticInfo_FullOSName
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 65796c41d2a9fbd03517e7b15bc6b566ba4364fb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="could-not-obtain-full-operation-system-name-due-to-internal-error"></a><span data-ttu-id="dfc22-102">No se pudo obtener el nombre completo del sistema operativo debido a un error interno</span><span class="sxs-lookup"><span data-stu-id="dfc22-102">Could not obtain full operation system name due to internal error</span></span>
<span data-ttu-id="dfc22-103">No se pudo obtener el nombre completo del sistema operativo debido a un error interno.</span><span class="sxs-lookup"><span data-stu-id="dfc22-103">Could not obtain full operation system name due to internal error.</span></span> <span data-ttu-id="dfc22-104">La causa podría ser que WMI no exista en la máquina actual.</span><span class="sxs-lookup"><span data-stu-id="dfc22-104">This might be caused by WMI not existing on the current machine.</span></span>  
  
 <span data-ttu-id="dfc22-105">Error al llamar a la propiedad `My.Computer.Info.OSFullName` .</span><span class="sxs-lookup"><span data-stu-id="dfc22-105">A call to the `My.Computer.Info.OSFullName` property failed.</span></span> <span data-ttu-id="dfc22-106">Una posible causa de este error es que Instrumental de administración de Windows (WMI) no esté instalado en el equipo actual.</span><span class="sxs-lookup"><span data-stu-id="dfc22-106">A possible cause for this failure is if Windows Management Instrumentation (WMI) is not installed on the current computer.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="dfc22-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="dfc22-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="dfc22-108">Agregue un bloque `Try...Catch` alrededor de la llamada a la propiedad `My.Computer.Info.OSFullName` .</span><span class="sxs-lookup"><span data-stu-id="dfc22-108">Add a `Try...Catch` block around the call to the `My.Computer.Info.OSFullName` property.</span></span>  
  
2.  <span data-ttu-id="dfc22-109">Para obtener más información acerca de WMI y cómo instalarlo, vaya a y buscan "Windows Management Instrumentation Core".</span><span class="sxs-lookup"><span data-stu-id="dfc22-109">For more information about WMI and how to install it, go to  and search for "Windows Management Instrumentation Core".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfc22-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="dfc22-110">See Also</span></span>  
 [<span data-ttu-id="dfc22-111">Propiedad My.Computer.Info.OSFullName</span><span class="sxs-lookup"><span data-stu-id="dfc22-111">My.Computer.Info.OSFullName Property</span></span>](http://msdn.microsoft.com/en-us/b3b0fbd1-4dc5-428a-ad04-0d9fc9c2a9be)  
 [<span data-ttu-id="dfc22-112">Excepciones y control de errores en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dfc22-112">Exception and Error Handling in Visual Basic</span></span>](http://msdn.microsoft.com/en-us/3e351e73-cf23-40ab-8b60-05794160529e)  
 [<span data-ttu-id="dfc22-113">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="dfc22-113">Try...Catch...Finally Statement</span></span>](../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
