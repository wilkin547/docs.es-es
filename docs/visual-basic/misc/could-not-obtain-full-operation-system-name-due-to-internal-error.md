---
title: No se pudo obtener el nombre completo del sistema operativo debido a un error interno
ms.date: 07/20/2015
f1_keywords:
- vbrDiagnosticInfo_FullOSName
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
ms.openlocfilehash: 67e8fb5e906800d28bf15714463b7ff6ae585693
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402283"
---
# <a name="could-not-obtain-full-operation-system-name-due-to-internal-error"></a><span data-ttu-id="e3a3e-102">No se pudo obtener el nombre completo del sistema operativo debido a un error interno</span><span class="sxs-lookup"><span data-stu-id="e3a3e-102">Could not obtain full operation system name due to internal error</span></span>
<span data-ttu-id="e3a3e-103">No se pudo obtener el nombre completo del sistema operativo debido a un error interno.</span><span class="sxs-lookup"><span data-stu-id="e3a3e-103">Could not obtain full operation system name due to internal error.</span></span> <span data-ttu-id="e3a3e-104">La causa podría ser que WMI no exista en la máquina actual.</span><span class="sxs-lookup"><span data-stu-id="e3a3e-104">This might be caused by WMI not existing on the current machine.</span></span>  
  
 <span data-ttu-id="e3a3e-105">Error al llamar a la propiedad `My.Computer.Info.OSFullName` .</span><span class="sxs-lookup"><span data-stu-id="e3a3e-105">A call to the `My.Computer.Info.OSFullName` property failed.</span></span> <span data-ttu-id="e3a3e-106">Una posible causa de este error es que Instrumental de administración de Windows (WMI) no esté instalado en el equipo actual.</span><span class="sxs-lookup"><span data-stu-id="e3a3e-106">A possible cause for this failure is if Windows Management Instrumentation (WMI) is not installed on the current computer.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e3a3e-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="e3a3e-107">To correct this error</span></span>  
  
1. <span data-ttu-id="e3a3e-108">Agregue un bloque `Try...Catch` alrededor de la llamada a la propiedad `My.Computer.Info.OSFullName` .</span><span class="sxs-lookup"><span data-stu-id="e3a3e-108">Add a `Try...Catch` block around the call to the `My.Computer.Info.OSFullName` property.</span></span>  
  
2. <span data-ttu-id="e3a3e-109">Para obtener más información acerca de WMI y cómo instalarlo, vaya a y busque "Instrumental de administración de Windows Core".</span><span class="sxs-lookup"><span data-stu-id="e3a3e-109">For more information about WMI and how to install it, go to  and search for "Windows Management Instrumentation Core".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3a3e-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e3a3e-110">See also</span></span>

- [<span data-ttu-id="e3a3e-111">My. Computer. info. OSFullName</span><span class="sxs-lookup"><span data-stu-id="e3a3e-111">My.Computer.Info.OSFullName</span></span>](xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName)
- [<span data-ttu-id="e3a3e-112">Controlar y generar excepciones en .NET</span><span class="sxs-lookup"><span data-stu-id="e3a3e-112">Handling and throwing exceptions in .NET</span></span>](../../standard/exceptions/index.md)
- [<span data-ttu-id="e3a3e-113">Instrucción Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="e3a3e-113">Try...Catch...Finally Statement</span></span>](../language-reference/statements/try-catch-finally-statement.md)
