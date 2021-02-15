---
description: 'Más información acerca de: no se pudo obtener el nombre completo del sistema operativo debido a un error interno'
title: No se pudo obtener el nombre completo del sistema operativo debido a un error interno
ms.date: 07/20/2015
f1_keywords:
- vbrDiagnosticInfo_FullOSName
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
ms.openlocfilehash: d274a08728b084b21309862de69e2fded5c164da
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100463499"
---
# <a name="could-not-obtain-full-operation-system-name-due-to-internal-error"></a><span data-ttu-id="0ee86-103">No se pudo obtener el nombre completo del sistema operativo debido a un error interno</span><span class="sxs-lookup"><span data-stu-id="0ee86-103">Could not obtain full operation system name due to internal error</span></span>

<span data-ttu-id="0ee86-104">No se pudo obtener el nombre completo del sistema operativo debido a un error interno.</span><span class="sxs-lookup"><span data-stu-id="0ee86-104">Could not obtain full operation system name due to internal error.</span></span> <span data-ttu-id="0ee86-105">La causa podría ser que WMI no exista en la máquina actual.</span><span class="sxs-lookup"><span data-stu-id="0ee86-105">This might be caused by WMI not existing on the current machine.</span></span>  
  
 <span data-ttu-id="0ee86-106">Error al llamar a la propiedad `My.Computer.Info.OSFullName` .</span><span class="sxs-lookup"><span data-stu-id="0ee86-106">A call to the `My.Computer.Info.OSFullName` property failed.</span></span> <span data-ttu-id="0ee86-107">Una posible causa de este error es que Instrumental de administración de Windows (WMI) no esté instalado en el equipo actual.</span><span class="sxs-lookup"><span data-stu-id="0ee86-107">A possible cause for this failure is if Windows Management Instrumentation (WMI) is not installed on the current computer.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0ee86-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="0ee86-108">To correct this error</span></span>  
  
1. <span data-ttu-id="0ee86-109">Agregue un bloque `Try...Catch` alrededor de la llamada a la propiedad `My.Computer.Info.OSFullName` .</span><span class="sxs-lookup"><span data-stu-id="0ee86-109">Add a `Try...Catch` block around the call to the `My.Computer.Info.OSFullName` property.</span></span>  
  
2. <span data-ttu-id="0ee86-110">Para obtener más información acerca de WMI y cómo instalarlo, vaya a y busque "Instrumental de administración de Windows Core".</span><span class="sxs-lookup"><span data-stu-id="0ee86-110">For more information about WMI and how to install it, go to  and search for "Windows Management Instrumentation Core".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ee86-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0ee86-111">See also</span></span>

- [<span data-ttu-id="0ee86-112">My. Computer. info. OSFullName</span><span class="sxs-lookup"><span data-stu-id="0ee86-112">My.Computer.Info.OSFullName</span></span>](xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName)
- [<span data-ttu-id="0ee86-113">Controlar y generar excepciones en .NET</span><span class="sxs-lookup"><span data-stu-id="0ee86-113">Handling and throwing exceptions in .NET</span></span>](../../standard/exceptions/index.md)
- [<span data-ttu-id="0ee86-114">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="0ee86-114">Try...Catch...Finally Statement</span></span>](../language-reference/statements/try-catch-finally-statement.md)
