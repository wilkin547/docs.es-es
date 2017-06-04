---
title: "Windows Forms Print Support | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Windows Forms, printing"
  - "printing [Windows Forms]"
  - "forms, printing (using designer)"
  - "printing, Windows Forms, support"
  - "printing [Windows Forms], print support"
ms.assetid: a4a2960c-eb70-48e2-b641-cfb222704e46
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Windows Forms Print Support
Imprimir en formularios Windows Forms se compone principalmente de utilizar el componente [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) para permitir que el usuario imprima y el control [PrintPreviewDialog \(Control\)](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md), los componentes [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) y [PageSetupDialog](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md), para proporcionar una interfaz gráfica que resulte familiar a los usuarios acostumbrados al sistema operativo Windows.  
  
 Habitualmente, se crea una nueva instancia del componente <xref:System.Drawing.Printing.PrintDocument>, se establecen las propiedades que describen qué se va a imprimir mediante las clases <xref:System.Drawing.Printing.PrinterSettings> y <xref:System.Drawing.Printing.PageSettings>, y se llama al método <xref:System.Drawing.Printing.PrintDocument.Print%2A> para imprimir realmente el documento.  
  
 Durante el proceso de impresión desde una aplicación basada en Windows, el componente <xref:System.Drawing.Printing.PrintDocument> mostrará un cuadro de diálogo de anulación de la impresión para avisar a los usuarios de que la impresión está en curso y permitir la cancelación del trabajo de impresión.  
  
## En esta sección  
 [How to: Create Standard Windows Forms Print Jobs](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)  
 Explica cómo utilizar el componente <xref:System.Drawing.Printing.PrintDocument> para imprimir desde un Windows Form.  
  
 [How to: Capture User Input from a PrintDialog at Run Time](../../../../docs/framework/winforms/advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 Explica cómo modificar las opciones de impresión seleccionadas mediante programación con el componente <xref:System.Windows.Forms.PrintDialog>.  
  
 [Cómo: Seleccionar las impresoras conectadas al equipo de un usuario en formularios Windows Forms](../../../../docs/framework/winforms/advanced/how-to-choose-the-printers-attached-to-user-computer-in-windows-forms.md)  
 Describe cómo cambiar la impresora utilizada para la impresión mediante el componente <xref:System.Windows.Forms.PrintDialog> en tiempo de ejecución.  
  
 [How to: Print Graphics in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)  
 Describe cómo enviar gráficos a la impresora.  
  
 [How to: Print a Multi\-Page Text File in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 Describe cómo enviar texto a la impresora.  
  
 [How to: Complete Windows Forms Print Jobs](../../../../docs/framework/winforms/advanced/how-to-complete-windows-forms-print-jobs.md)  
 Explica cómo alertar a los usuarios cuando se completa un trabajo de impresión.  
  
 [How to: Print a Windows Form](../../../../docs/framework/winforms/advanced/how-to-print-a-windows-form.md)  
 Muestra cómo imprimir una copia del formulario actual.  
  
 [Cómo: Imprimir en Windows Forms a través de la vista previa de impresión](../../../../docs/framework/winforms/advanced/how-to-print-in-windows-forms-using-print-preview.md)  
 Muestra cómo utilizar <xref:System.Windows.Forms.PrintPreviewDialog> para imprimir un documento.  
  
## Secciones relacionadas  
 [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)  
 Explica el uso del componente <xref:System.Drawing.Printing.PrintDocument>.  
  
 [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)  
 Explica el uso del componente <xref:System.Windows.Forms.PrintDialog>.  
  
 [PrintPreviewDialog \(Control\)](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 Explica el uso del control <xref:System.Windows.Forms.PrintPreviewDialog>.  
  
 [PageSetupDialog](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)  
 Explica el uso del componente <xref:System.Windows.Forms.PageSetupDialog>.  
  
 <xref:System.Drawing.Printing>  
 Describe las clases del espacio de nombres <xref:System.Drawing.Printing>.