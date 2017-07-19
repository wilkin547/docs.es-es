---
title: "C&#243;mo: Reproducir un sonido desde Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "sonidos, Bip"
  - "Formularios Windows Forms, sonidos"
  - "sonidos, reproducción"
  - "formularios, sonidos"
  - "ejemplos [Windows Forms], sonidos"
ms.assetid: 7ea5cded-4888-4f35-8f28-5cab1a55c973
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Reproducir un sonido desde Windows Forms
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
>  El sonido reproducido en el ejemplo de código de C# está determinado por la <xref:System.Media.SystemSounds.Beep%2A> configuración del sistema de sonido. Para obtener más información, consulte <xref:System.Media.SystemSounds>.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para C#, este ejemplo requiere una referencia a la <xref:System.Media?displayProperty=fullName> espacio de nombres.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.Interaction.Beep%2A>   
 <xref:System.Media.SoundPlayer>   
 [Cómo: reproducir un sonido del sistema desde un formulario Windows Forms](../../../../docs/framework/winforms/controls/how-to-play-a-system-sound-from-a-windows-form.md)   
 [Cómo: reproducir un sonido desde un formulario Windows Forms](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)