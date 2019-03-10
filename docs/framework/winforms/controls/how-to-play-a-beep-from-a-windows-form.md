---
title: Filtrar Reproducir un sonido desde Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sounds [Windows Forms], beep
- Windows Forms, sounds
- sounds [Windows Forms], playing
- forms [Windows Forms], sounds
- examples [Windows Forms], sounds
ms.assetid: 7ea5cded-4888-4f35-8f28-5cab1a55c973
ms.openlocfilehash: d04bf4bd45aa6ba5dfe231d5f69c2b2a13765373
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57710438"
---
# <a name="how-to-play-a-beep-from-a-windows-form"></a><span data-ttu-id="050eb-102">Procedimiento Reproducir un sonido desde Windows Forms</span><span class="sxs-lookup"><span data-stu-id="050eb-102">How to: Play a Beep from a Windows Form</span></span>
<span data-ttu-id="050eb-103">En este ejemplo se reproduce un sonido en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="050eb-103">This example plays a beep at run time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="050eb-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="050eb-104">Example</span></span>  
  
```vb  
Public Sub OnePing()  
    Beep()  
End Sub  
```  
  
```csharp  
public void onePing()  
{  
    SystemSounds.Beep.Play();  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="050eb-105">El sonido reproducido el C# código de ejemplo viene determinada por la <xref:System.Media.SystemSounds.Beep%2A> configuración de sonido del sistema.</span><span class="sxs-lookup"><span data-stu-id="050eb-105">The sound played in the C# code sample is determined by the <xref:System.Media.SystemSounds.Beep%2A> system sound setting.</span></span> <span data-ttu-id="050eb-106">Para obtener más información, consulta <xref:System.Media.SystemSounds>.</span><span class="sxs-lookup"><span data-stu-id="050eb-106">For more information, see <xref:System.Media.SystemSounds>.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="050eb-107">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="050eb-107">Compiling the Code</span></span>  
 <span data-ttu-id="050eb-108">Para C#, este ejemplo requiere una referencia a la <xref:System.Media?displayProperty=nameWithType> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="050eb-108">For C#, this example requires  a reference to the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="050eb-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="050eb-109">See also</span></span>
- <xref:Microsoft.VisualBasic.Interaction.Beep%2A>
- <xref:System.Media.SoundPlayer>
- [<span data-ttu-id="050eb-110">Cómo: Reproducir un sonido del sistema desde Windows Forms</span><span class="sxs-lookup"><span data-stu-id="050eb-110">How to: Play a System Sound from a Windows Form</span></span>](how-to-play-a-system-sound-from-a-windows-form.md)
- [<span data-ttu-id="050eb-111">Cómo: Reproducir un sonido desde Windows Forms</span><span class="sxs-lookup"><span data-stu-id="050eb-111">How to: Play a Sound from a Windows Form</span></span>](how-to-play-a-sound-from-a-windows-form.md)
