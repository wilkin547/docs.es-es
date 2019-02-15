---
title: No se pudo obtener el nombre completo del sistema operativo debido a un error interno
ms.date: 07/20/2015
f1_keywords:
- vbrDiagnosticInfo_FullOSName
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
ms.openlocfilehash: 5514544a0f5933d557690cee7508d0545e4fdd63
ms.sourcegitcommit: bef803e2025642df39f2f1e046767d89031e0304
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2019
ms.locfileid: "56303623"
---
# <a name="could-not-obtain-full-operation-system-name-due-to-internal-error"></a><span data-ttu-id="d92e8-102">No se pudo obtener el nombre completo del sistema operativo debido a un error interno</span><span class="sxs-lookup"><span data-stu-id="d92e8-102">Could not obtain full operation system name due to internal error</span></span>
<span data-ttu-id="d92e8-103">No se pudo obtener el nombre completo del sistema operativo debido a un error interno.</span><span class="sxs-lookup"><span data-stu-id="d92e8-103">Could not obtain full operation system name due to internal error.</span></span> <span data-ttu-id="d92e8-104">La causa podría ser que WMI no exista en la máquina actual.</span><span class="sxs-lookup"><span data-stu-id="d92e8-104">This might be caused by WMI not existing on the current machine.</span></span>  
  
 <span data-ttu-id="d92e8-105">Error al llamar a la propiedad `My.Computer.Info.OSFullName` .</span><span class="sxs-lookup"><span data-stu-id="d92e8-105">A call to the `My.Computer.Info.OSFullName` property failed.</span></span> <span data-ttu-id="d92e8-106">Una posible causa de este error es que Instrumental de administración de Windows (WMI) no esté instalado en el equipo actual.</span><span class="sxs-lookup"><span data-stu-id="d92e8-106">A possible cause for this failure is if Windows Management Instrumentation (WMI) is not installed on the current computer.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d92e8-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="d92e8-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="d92e8-108">Agregue un bloque `Try...Catch` alrededor de la llamada a la propiedad `My.Computer.Info.OSFullName` .</span><span class="sxs-lookup"><span data-stu-id="d92e8-108">Add a `Try...Catch` block around the call to the `My.Computer.Info.OSFullName` property.</span></span>  
  
2.  <span data-ttu-id="d92e8-109">Para obtener más información acerca de WMI y cómo instalarlo, vaya a y busque "Windows Management Instrumentation Core".</span><span class="sxs-lookup"><span data-stu-id="d92e8-109">For more information about WMI and how to install it, go to  and search for "Windows Management Instrumentation Core".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d92e8-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="d92e8-110">See also</span></span>
- [<span data-ttu-id="d92e8-111">My.Computer.Info.OSFullName</span><span class="sxs-lookup"><span data-stu-id="d92e8-111">My.Computer.Info.OSFullName</span></span>](xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName)
- [<span data-ttu-id="d92e8-112">Controlar y generar excepciones en .NET</span><span class="sxs-lookup"><span data-stu-id="d92e8-112">Handling and throwing exceptions in .NET</span></span>](../../standard/exceptions/index.md)
- [<span data-ttu-id="d92e8-113">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="d92e8-113">Try...Catch...Finally Statement</span></span>](../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
