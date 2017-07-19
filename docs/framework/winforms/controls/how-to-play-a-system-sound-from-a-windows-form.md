---
title: "C&#243;mo: Reproducir un sonido del sistema desde Windows Forms | Microsoft Docs"
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
  - "sonidos, reproducir para eventos del sistema"
  - "reproducir sonidos, formularios Windows Forms"
  - "sonidos del sistema, reproducir desde Windows Forms"
  - "reproducir sonidos, sistema"
  - "SoundPlayer (clase), sonidos del sistema"
  - "sonidos, reproducción"
  - "ejemplos [Windows Forms], sonidos"
ms.assetid: afb206ff-4824-4804-a8d4-185bf5ad8e7c
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Reproducir un sonido del sistema desde Windows Forms
El siguiente código de ejemplo reproduce la `Exclamation` sonido del sistema en tiempo de ejecución. Para obtener más información acerca de los sonidos de sistema, consulte <xref:System.Media.SystemSounds>.  
  
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
  
-   Una referencia a la <xref:System.Media?displayProperty=fullName> espacio de nombres.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Media.SoundPlayer>   
 <xref:System.Media.SystemSounds>   
 [Cómo: reproducir un sonido desde un formulario Windows Forms](../../../../docs/framework/winforms/controls/how-to-play-a-beep-from-a-windows-form.md)   
 [Cómo: reproducir un sonido desde un formulario Windows Forms](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)