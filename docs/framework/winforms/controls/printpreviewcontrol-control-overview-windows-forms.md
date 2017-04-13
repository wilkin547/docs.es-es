---
title: "Informaci&#243;n general sobre el control PrintPreviewControl (formularios Windows Forms) | Microsoft Docs"
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
  - "PrintPreviewControl"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "vista previa de impresión"
  - "PrintPreviewControl (control)"
ms.assetid: 4513c6c7-5e9b-4f4c-82ca-00f993a26955
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Informaci&#243;n general sobre el control PrintPreviewControl (formularios Windows Forms)
El control <xref:System.Windows.Forms.PrintPreviewControl> de formularios Windows Forms se utiliza para mostrar un [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) tal como aparecerá cuando se imprima.  Este control no tiene botones ni otros elementos de interfaz de usuario, por lo que habitualmente sólo se utiliza <xref:System.Windows.Forms.PrintPreviewControl> cuando se desea crear una interfaz de usuario propia para la vista previa de impresión.  Si se desea la interfaz de usuario estándar, utilice un control <xref:System.Windows.Forms.PrintPreviewDialog>; vea [Información general sobre el control PrintPreviewDialog](../../../../docs/framework/winforms/controls/printpreviewdialog-control-overview-windows-forms.md) para obtener información general.  
  
## Propiedades principales  
 La propiedad principal del control es <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>, que establece el documento para la vista preliminar.  El documento debe ser un objeto <xref:System.Drawing.Printing.PrintDocument>.  Para obtener información general sobre la creación los documentos para imprimir, vea [\<missing\>](../../../../docs/framework/winforms/controls/printdocument-component-overview-windows-forms.md) y [Windows Forms Print Support](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md).  Las propiedades <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> y <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> determinan el número de páginas que se muestran horizontal y verticalmente en el control.  La función de suavizado de contorno puede hacer que el texto aparezca más nítido, pero también hace que la presentación sea más lenta; para utilizarla, establezca la propiedad <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> en `true`.  
  
## Vea también  
 <xref:System.Windows.Forms.PrintPreviewControl>   
 [Información general sobre el control PrintPreviewDialog](../../../../docs/framework/winforms/controls/printpreviewdialog-control-overview-windows-forms.md)   
 [PrintPreviewControl \(Control\)](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-windows-forms.md)   
 [Controles y componentes de cuadros de diálogo](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)