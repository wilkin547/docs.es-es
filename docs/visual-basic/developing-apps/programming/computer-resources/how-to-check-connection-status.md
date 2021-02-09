---
description: 'Más información acerca de: Procedimiento: para comprobar el estado de conexión en Visual Basic'
title: Procedimiento para comprobar el estado de la conexión
ms.date: 07/20/2015
helpviewer_keywords:
- Web connections [Visual Basic]
- IsAvailable property [Visual Basic], about IsAvailable
- connections [Visual Basic], checking status
- connection status [Visual Basic]
ms.assetid: 4d9ee8ab-9a6f-4279-ace4-b75afc976a74
ms.openlocfilehash: c568e3be5d8fedb1ae12c748110b23218deaf069
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797749"
---
# <a name="how-to-check-connection-status-in-visual-basic"></a><span data-ttu-id="b6c6c-103">Cómo: Comprobar el estado de conexión en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b6c6c-103">How to: Check Connection Status in Visual Basic</span></span>

<span data-ttu-id="b6c6c-104">La propiedad <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable> puede usarse para determinar si el equipo tiene una conexión activa a una red o a Internet.</span><span class="sxs-lookup"><span data-stu-id="b6c6c-104">The <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable> property can be used to determine whether the computer has a working network or Internet connection.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-check-whether-a-computer-has-a-working-connection"></a><span data-ttu-id="b6c6c-105">Para comprobar si un equipo tiene una conexión activa</span><span class="sxs-lookup"><span data-stu-id="b6c6c-105">To check whether a computer has a working connection</span></span>  
  
- <span data-ttu-id="b6c6c-106">Determine si la propiedad `IsAvailable` es `True` o `False`.</span><span class="sxs-lookup"><span data-stu-id="b6c6c-106">Determine whether the `IsAvailable` property is `True` or `False`.</span></span> <span data-ttu-id="b6c6c-107">El código siguiente comprueba el estado de la propiedad y lo notifica:</span><span class="sxs-lookup"><span data-stu-id="b6c6c-107">The following code checks the property's status and reports it:</span></span>  
  
     [!code-vb[VbResourceTasks#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#3)]  
  
     <span data-ttu-id="b6c6c-108">Este ejemplo de código también está disponible como fragmento de código de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="b6c6c-108">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="b6c6c-109">En el selector de fragmentos de código, se encuentra en **Conectividad y redes**.</span><span class="sxs-lookup"><span data-stu-id="b6c6c-109">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="b6c6c-110">Para obtener más información, vea [Fragmentos de código](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="b6c6c-110">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6c6c-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6c6c-111">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable>
