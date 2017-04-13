---
title: "Informaci&#243;n general sobre el componente FontDialog (formularios Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "FontDialog"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Fuente (cuadro de diálogo)"
  - "Fuente (cuadro de diálogo), Windows Forms"
  - "FontDialog (componente) [Windows Forms], acerca del componente FontDialog"
ms.assetid: daf46e57-1b4b-4b7a-bad0-b50ca7ba75dc
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Informaci&#243;n general sobre el componente FontDialog (formularios Windows Forms)
El componente <xref:System.Windows.Forms.FontDialog> de formularios Windows Forms es un cuadro de diálogo preconfigurado, que es el cuadro de diálogo **Fuente** estándar de Windows utilizado para mostrar las fuentes que están instaladas actualmente en el sistema.  Utilícelo dentro de la aplicación para Windows como una solución sencilla para la selección de fuentes, en lugar de configurar un cuadro de diálogo propio.  
  
 De forma predeterminada, el cuadro de diálogo muestra cuadros de lista para la fuente, el estilo de fuente y el tamaño; casillas como Tachado y Subrayado; una lista desplegable para Script.  \(Script son los diferentes scripts que están disponibles para una fuente determinada, por ejemplo, hebreo o japonés.\) Para mostrar el cuadro de diálogo de fuente, llame al método <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>.  
  
## Propiedades principales  
 El componente dispone de varias propiedades que configuran su apariencia.  Las propiedades que establecen las selecciones del cuadro de diálogo son <xref:System.Windows.Forms.FontDialog.Font%2A> y <xref:System.Windows.Forms.FontDialog.Color%2A>.  La propiedad <xref:System.Windows.Forms.FontDialog.Font%2A> establece la fuente, estilo, tamaño, script y efectos; por ejemplo, `Arial, 10pt, style=Italic, Strikeout`.  
  
## Vea también  
 <xref:System.Windows.Forms.FontDialog>   
 [FontDialog](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md)