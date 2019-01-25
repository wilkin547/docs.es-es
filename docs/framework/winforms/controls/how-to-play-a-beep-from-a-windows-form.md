---
title: Procedimiento Reproducir un sonido desde Windows Forms
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
ms.openlocfilehash: b847f2f759667eed5dfb6f9168a5c2fc50909cc3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54544515"
---
# <a name="how-to-play-a-beep-from-a-windows-form"></a>Procedimiento Reproducir un sonido desde Windows Forms
En este ejemplo se reproduce un sonido en tiempo de ejecución.  
  
## <a name="example"></a>Ejemplo  
  
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
>  El sonido reproducido el C# código de ejemplo viene determinada por la <xref:System.Media.SystemSounds.Beep%2A> configuración de sonido del sistema. Para obtener más información, consulta <xref:System.Media.SystemSounds>.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para C#, este ejemplo requiere una referencia a la <xref:System.Media?displayProperty=nameWithType> espacio de nombres.  
  
## <a name="see-also"></a>Vea también
- <xref:Microsoft.VisualBasic.Interaction.Beep%2A>
- <xref:System.Media.SoundPlayer>
- [Cómo: Reproducir un sonido del sistema desde Windows Forms](../../../../docs/framework/winforms/controls/how-to-play-a-system-sound-from-a-windows-form.md)
- [Cómo: Reproducir un sonido desde Windows Forms](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)
