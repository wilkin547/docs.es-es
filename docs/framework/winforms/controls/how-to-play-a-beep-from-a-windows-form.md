---
title: Procedimiento para emitir un bip desde un formulario Windows Forms
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
ms.openlocfilehash: 7fecc5d5b7259b743926713f87d9303596803582
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015808"
---
# <a name="how-to-play-a-beep-from-a-windows-form"></a><span data-ttu-id="c9189-102">Procedimiento para emitir un bip desde un formulario Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c9189-102">How to: Play a Beep from a Windows Form</span></span>
<span data-ttu-id="c9189-103">En este ejemplo se reproduce un sonido en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c9189-103">This example plays a beep at run time.</span></span>

## <a name="example"></a><span data-ttu-id="c9189-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c9189-104">Example</span></span>

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
> <span data-ttu-id="c9189-105">El sonido que se reproduce en el C# ejemplo de código <xref:System.Media.SystemSounds.Beep%2A> está determinado por la configuración de sonido del sistema.</span><span class="sxs-lookup"><span data-stu-id="c9189-105">The sound played in the C# code sample is determined by the <xref:System.Media.SystemSounds.Beep%2A> system sound setting.</span></span> <span data-ttu-id="c9189-106">Para obtener más información, consulta <xref:System.Media.SystemSounds>.</span><span class="sxs-lookup"><span data-stu-id="c9189-106">For more information, see <xref:System.Media.SystemSounds>.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="c9189-107">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="c9189-107">Compiling the Code</span></span>
 <span data-ttu-id="c9189-108">Para C#, este ejemplo requiere una referencia al <xref:System.Media?displayProperty=nameWithType> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="c9189-108">For C#, this example requires  a reference to the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="c9189-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="c9189-109">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Beep%2A>
- <xref:System.Media.SoundPlayer>
- [<span data-ttu-id="c9189-110">Procedimientos: Reproducir un sonido del sistema desde Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c9189-110">How to: Play a System Sound from a Windows Form</span></span>](how-to-play-a-system-sound-from-a-windows-form.md)
- [<span data-ttu-id="c9189-111">Cómo: Reproducir un sonido desde Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c9189-111">How to: Play a Sound from a Windows Form</span></span>](how-to-play-a-sound-from-a-windows-form.md)
