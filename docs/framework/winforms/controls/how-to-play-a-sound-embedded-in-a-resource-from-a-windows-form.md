---
title: "C&#243;mo: Reproducir un sonido incrustado en un recurso desde Windows Forms | Microsoft Docs"
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
  - "sonidos, reproducir desde recursos"
  - "recursos [Windows Forms], reproducir sonidos"
  - "reproducir sonidos desde recursos"
  - "SoundPlayer (clase), reproducir sonidos desde recursos"
ms.assetid: 7d148bb6-8a1e-47d7-a08d-35828d2e688f
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# C&#243;mo: Reproducir un sonido incrustado en un recurso desde Windows Forms
Puede usar el <xref:System.Media.SoundPlayer> clase para reproducir un sonido desde un recurso incrustado.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Windows.Forms.Sound#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Sound/CS/soundtestform.cs#10)]
 [!code-vb[System.Windows.Forms.Sound#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Sound/VB/soundtestform.vb#10)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
 Importar el <xref:System.Media?displayProperty=fullName> espacio de nombres.  
  
 Incluir el archivo de sonido como un recurso incrustado en el proyecto.  
  
 Reemplace "<>\>" con el nombre del ensamblado en el que se incrusta el archivo de sonido. No incluya el sufijo ".dll".  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Media.SoundPlayer>   
 [Cómo: reproducir un sonido desde un formulario Windows Forms](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)   
 [Cómo: repetir un sonido reproducido en un formulario Windows Forms](../../../../docs/framework/winforms/controls/how-to-loop-a-sound-playing-on-a-windows-form.md)