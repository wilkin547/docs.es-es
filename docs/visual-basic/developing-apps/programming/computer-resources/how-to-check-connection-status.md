---
title: Procedimiento para comprobar el estado de conexión en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- Web connections [Visual Basic]
- IsAvailable property [Visual Basic], about IsAvailable
- connections [Visual Basic], checking status
- connection status [Visual Basic]
ms.assetid: 4d9ee8ab-9a6f-4279-ace4-b75afc976a74
ms.openlocfilehash: c7a43fd154616e516f8c5e7d36d25f34924649ac
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54499965"
---
# <a name="how-to-check-connection-status-in-visual-basic"></a><span data-ttu-id="b62fc-102">Procedimiento para comprobar el estado de conexión en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b62fc-102">How to: Check Connection Status in Visual Basic</span></span>
<span data-ttu-id="b62fc-103">La propiedad <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable> puede usarse para determinar si el equipo tiene una conexión activa a una red o a Internet.</span><span class="sxs-lookup"><span data-stu-id="b62fc-103">The <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable> property can be used to determine whether the computer has a working network or Internet connection.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-check-whether-a-computer-has-a-working-connection"></a><span data-ttu-id="b62fc-104">Para comprobar si un equipo tiene una conexión activa</span><span class="sxs-lookup"><span data-stu-id="b62fc-104">To check whether a computer has a working connection</span></span>  
  
-   <span data-ttu-id="b62fc-105">Determine si la propiedad `IsAvailable` es `True` o `False`.</span><span class="sxs-lookup"><span data-stu-id="b62fc-105">Determine whether the `IsAvailable` property is `True` or `False`.</span></span> <span data-ttu-id="b62fc-106">El código siguiente comprueba el estado de la propiedad y lo notifica:</span><span class="sxs-lookup"><span data-stu-id="b62fc-106">The following code checks the property's status and reports it:</span></span>  
  
     [!code-vb[VbResourceTasks#3](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-check-connection-status_1.vb)]  
  
     <span data-ttu-id="b62fc-107">Este ejemplo de código también está disponible como fragmento de código de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="b62fc-107">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="b62fc-108">En el selector de fragmentos de código, se encuentra en **Conectividad y redes**.</span><span class="sxs-lookup"><span data-stu-id="b62fc-108">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="b62fc-109">Para obtener más información, vea [Fragmentos de código](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="b62fc-109">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b62fc-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="b62fc-110">See also</span></span>
- <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable>
