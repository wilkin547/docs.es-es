---
title: No se pudo obtener el nombre completo del sistema operativo debido a un error interno
ms.date: 07/20/2015
f1_keywords:
- vbrDiagnosticInfo_FullOSName
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
ms.openlocfilehash: 744d549b9313727af2feb82e45c24b729cae7262
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91079092"
---
# <a name="could-not-obtain-full-operation-system-name-due-to-internal-error"></a><span data-ttu-id="f4035-102">No se pudo obtener el nombre completo del sistema operativo debido a un error interno</span><span class="sxs-lookup"><span data-stu-id="f4035-102">Could not obtain full operation system name due to internal error</span></span>

<span data-ttu-id="f4035-103">No se pudo obtener el nombre completo del sistema operativo debido a un error interno.</span><span class="sxs-lookup"><span data-stu-id="f4035-103">Could not obtain full operation system name due to internal error.</span></span> <span data-ttu-id="f4035-104">La causa podría ser que WMI no exista en la máquina actual.</span><span class="sxs-lookup"><span data-stu-id="f4035-104">This might be caused by WMI not existing on the current machine.</span></span>  
  
 <span data-ttu-id="f4035-105">Error al llamar a la propiedad `My.Computer.Info.OSFullName` .</span><span class="sxs-lookup"><span data-stu-id="f4035-105">A call to the `My.Computer.Info.OSFullName` property failed.</span></span> <span data-ttu-id="f4035-106">Una posible causa de este error es que Instrumental de administración de Windows (WMI) no esté instalado en el equipo actual.</span><span class="sxs-lookup"><span data-stu-id="f4035-106">A possible cause for this failure is if Windows Management Instrumentation (WMI) is not installed on the current computer.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f4035-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="f4035-107">To correct this error</span></span>  
  
1. <span data-ttu-id="f4035-108">Agregue un bloque `Try...Catch` alrededor de la llamada a la propiedad `My.Computer.Info.OSFullName` .</span><span class="sxs-lookup"><span data-stu-id="f4035-108">Add a `Try...Catch` block around the call to the `My.Computer.Info.OSFullName` property.</span></span>  
  
2. <span data-ttu-id="f4035-109">Para obtener más información acerca de WMI y cómo instalarlo, vaya a y busque "Instrumental de administración de Windows Core".</span><span class="sxs-lookup"><span data-stu-id="f4035-109">For more information about WMI and how to install it, go to  and search for "Windows Management Instrumentation Core".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4035-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4035-110">See also</span></span>

- [<span data-ttu-id="f4035-111">My. Computer. info. OSFullName</span><span class="sxs-lookup"><span data-stu-id="f4035-111">My.Computer.Info.OSFullName</span></span>](xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName)
- [<span data-ttu-id="f4035-112">Controlar y generar excepciones en .NET</span><span class="sxs-lookup"><span data-stu-id="f4035-112">Handling and throwing exceptions in .NET</span></span>](../../standard/exceptions/index.md)
- [<span data-ttu-id="f4035-113">Try... Detectar... Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="f4035-113">Try...Catch...Finally Statement</span></span>](../language-reference/statements/try-catch-finally-statement.md)
