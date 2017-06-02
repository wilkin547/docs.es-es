---
title: "Informaci&#243;n general sobre el control PrintPreviewDialog (formularios Windows Forms) | Microsoft Docs"
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
  - "PrintPreviewDialog"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "PrintPreviewDialog (control) (mediante el diseñador), acerca de PrintPreviewDialog"
ms.assetid: efd4ee8d-6edd-47ec-88e4-4a4759bd2384
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Informaci&#243;n general sobre el control PrintPreviewDialog (formularios Windows Forms)
El control <xref:System.Windows.Forms.PrintPreviewDialog> de formularios Windows Forms es un cuadro de diálogo preconfigurado que se utiliza para mostrar la presentación de [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) cuando se imprima.  Utilícelo dentro de la aplicación para Windows como una solución sencilla, en lugar de configurar un cuadro de diálogo propio.  El control contiene botones para imprimir, acercar, mostrar una o varias páginas y cerrar el cuadro de diálogo.  
  
## Propiedades y métodos principales  
 La propiedad principal del control es <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, que establece el documento para la vista preliminar.  El documento debe ser un objeto <xref:System.Drawing.Printing.PrintDocument>.  Para que se muestre el cuadro de diálogo, llame al método <xref:System.Windows.Forms.Form.ShowDialog%2A>.  La función de suavizado de contorno puede hacer que el texto aparezca más nítido, pero también hace que la presentación sea más lenta; para utilizarla, establezca la propiedad <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> en `true`.  
  
 Ciertas propiedades están disponibles a través de <xref:System.Windows.Forms.PrintPreviewControl>, contenida en <xref:System.Windows.Forms.PrintPreviewDialog>.  \(No tiene que agregar este control <xref:System.Windows.Forms.PrintPreviewDialog> al formulario; se incluye automáticamente en el cuadro de diálogo <xref:System.Windows.Forms.PrintPreviewControl> cuando se agrega el cuadro de diálogo al formulario.\) Algunos ejemplos de propiedades disponibles a través de <xref:System.Windows.Forms.PrintPreviewControl> son las propiedades <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> y <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A>, que determinan el número de páginas que se muestran horizontal y verticalmente en el control.  Se puede tener acceso a la propiedad <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> como `PrintPreviewDialog1.PrintPreviewControl.Columns` en [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], `printPreviewDialog1.PrintPreviewControl.Columns` en [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] o `printPreviewDialog1->PrintPreviewControl->Columns` en [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)].  
  
## Vea también  
 <xref:System.Windows.Forms.PrintPreviewDialog>   
 [Información general sobre el control PrintPreviewControl](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-overview-windows-forms.md)   
 [PrintPreviewDialog \(Control\)](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)   
 [Controles y componentes de cuadros de diálogo](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)