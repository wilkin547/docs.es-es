---
title: Filtrar para emitir un bip desde un formulario Windows Forms
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
ms.openlocfilehash: 0aa01f600873dd8853e1c33d5443448835e11455
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59146229"
---
# <a name="how-to-play-a-beep-from-a-windows-form"></a>Filtrar para emitir un bip desde un formulario Windows Forms
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
- [Filtrar para reproducir un sonido del sistema desde un formulario Windows Forms](how-to-play-a-system-sound-from-a-windows-form.md)
- [Filtrar para reproducir un sonido desde un formulario Windows Forms](how-to-play-a-sound-from-a-windows-form.md)
