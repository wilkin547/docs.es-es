---
title: Filtrar Reproducir un sonido del sistema desde Windows Forms
ms.date: 03/30/2017
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
ms.openlocfilehash: b2ac6c4f2e3334a9b4c5ff4d2a6e31b6b9bf3673
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711244"
---
# <a name="how-to-play-a-system-sound-from-a-windows-form"></a>Filtrar Reproducir un sonido del sistema desde Windows Forms
El siguiente código de ejemplo reproduce el sonido del sistema `Exclamation` en tiempo de ejecución. Para obtener más información sobre los sonidos del sistema, consulte <xref:System.Media.SystemSounds>.  
  
## <a name="example"></a>Ejemplo  
  
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
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Una referencia al espacio de nombres <xref:System.Media?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Media.SoundPlayer>
- <xref:System.Media.SystemSounds>
- [Cómo: Reproducir un sonido desde Windows Forms](how-to-play-a-beep-from-a-windows-form.md)
- [Cómo: Reproducir un sonido desde Windows Forms](how-to-play-a-sound-from-a-windows-form.md)
