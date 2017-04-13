---
title: "C&#243;mo: Rechazar las actualizaciones autom&#225;ticas de cuadros de di&#225;logo de archivos | Microsoft Docs"
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
  - "OpenFileDialog [Windows Forms], rechazar actualización automática"
  - "[Windows Forms] del cuadro de diálogo de archivo, rechazar actualización automática"
  - "Cuadro de diálogo de archivo de Windows Vista cuadro, rechazar actualización automática"
  - "SaveFileDialog [Windows Forms], rechazar actualización automática"
  - "AutoUpgradeEnabled (propiedad)"
ms.assetid: 522e482e-cc01-48b1-8d59-9617dc2c4ac1
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Rechazar las actualizaciones autom&#225;ticas de cuadros de di&#225;logo de archivos
Cuando el <xref:System.Windows.Forms.OpenFileDialog> y <xref:System.Windows.Forms.SaveFileDialog> clases se utilizan en una aplicación, su apariencia y comportamiento dependen de la versión de Windows que se ejecuta la aplicación. Cuando una aplicación que se creó en el [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] o se muestra anteriormente en [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)], <xref:System.Windows.Forms.OpenFileDialog> y <xref:System.Windows.Forms.SaveFileDialog> se muestran con el [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] apariencia y comportamiento. A partir de la [!INCLUDE[net_v30_short](../../../../includes/net-v30-short-md.md)], puede optar por la actualización automática para mostrar el <xref:System.Windows.Forms.OpenFileDialog> y <xref:System.Windows.Forms.SaveFileDialog> con una [!INCLUDE[winxp](../../../../includes/winxp-md.md)]: estilo de apariencia y comportamiento.  
  
### <a name="to-opt-out-of-file-dialog-box-automatic-upgrade"></a>Para no participar en actualizaciones automáticas de cuadros de diálogo de archivo  
  
1.  Establecer el <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> propiedad de <xref:System.Windows.Forms.OpenFileDialog> o <xref:System.Windows.Forms.SaveFileDialog> a `false` antes de mostrar el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.FileDialog>