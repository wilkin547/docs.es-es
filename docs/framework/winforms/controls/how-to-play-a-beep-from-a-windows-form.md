---
title: "Cómo: Reproducir un sonido desde Windows Forms"
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
- sounds [Windows Forms], beep
- Windows Forms, sounds
- sounds [Windows Forms], playing
- forms [Windows Forms], sounds
- examples [Windows Forms], sounds
ms.assetid: 7ea5cded-4888-4f35-8f28-5cab1a55c973
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c0c0c369756547231c0f8171bdfa940cb353544b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-play-a-beep-from-a-windows-form"></a>Cómo: Reproducir un sonido desde Windows Forms
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
>  El sonido que se reproducen en el ejemplo de código de C# está determinado por la <xref:System.Media.SystemSounds.Beep%2A> configuración del sistema de sonido. Para obtener más información, consulta <xref:System.Media.SystemSounds>.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 En C#, este ejemplo necesita una referencia a la <xref:System.Media?displayProperty=nameWithType> espacio de nombres.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.Interaction.Beep%2A>  
 <xref:System.Media.SoundPlayer>  
 [Reproducir un sonido del sistema desde Windows Forms](../../../../docs/framework/winforms/controls/how-to-play-a-system-sound-from-a-windows-form.md)  
 [Cómo: Reproducir un sonido desde Windows Forms](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)
