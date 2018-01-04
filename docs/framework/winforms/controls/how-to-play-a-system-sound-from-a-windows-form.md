---
title: "Cómo: Reproducir un sonido del sistema desde Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sounds [Windows Forms], playing for system events
- playing sounds [Windows Forms], Windows Forms
- system sounds [Windows Forms], playing from Windows Forms
- playing sounds [Windows Forms], system
- SoundPlayer class [Windows Forms], system sounds
- sounds [Windows Forms], playing
- examples [Windows Forms], sounds
ms.assetid: afb206ff-4824-4804-a8d4-185bf5ad8e7c
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7b620b7386752e531a8d5252159c5f172176890a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-play-a-system-sound-from-a-windows-form"></a><span data-ttu-id="1509e-102">Cómo: Reproducir un sonido del sistema desde Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1509e-102">How to: Play a System Sound from a Windows Form</span></span>
<span data-ttu-id="1509e-103">El siguiente código de ejemplo reproduce el sonido del sistema `Exclamation` en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1509e-103">The following code example plays the `Exclamation` system sound at run time.</span></span> <span data-ttu-id="1509e-104">Para obtener más información acerca de sonidos del sistema, consulte <xref:System.Media.SystemSounds>.</span><span class="sxs-lookup"><span data-stu-id="1509e-104">For more information about system sounds, see <xref:System.Media.SystemSounds>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1509e-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1509e-105">Example</span></span>  
  
```vb  
Public Sub PlayExclamation()  
    SystemSounds.Exclamation.Play()  
End Sub  
```  
  
```csharp  
public void playExclamation()  
{  
    SystemSounds.Exclamation.Play();  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1509e-106">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="1509e-106">Compiling the Code</span></span>  
 <span data-ttu-id="1509e-107">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="1509e-107">This example requires:</span></span>  
  
-   <span data-ttu-id="1509e-108">Una referencia al espacio de nombres <xref:System.Media?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1509e-108">A reference to the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1509e-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="1509e-109">See Also</span></span>  
 <xref:System.Media.SoundPlayer>  
 <xref:System.Media.SystemSounds>  
 [<span data-ttu-id="1509e-110">Reproducir un sonido desde Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1509e-110">How to: Play a Beep from a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-play-a-beep-from-a-windows-form.md)  
 [<span data-ttu-id="1509e-111">Cómo: Reproducir un sonido desde Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1509e-111">How to: Play a Sound from a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)
