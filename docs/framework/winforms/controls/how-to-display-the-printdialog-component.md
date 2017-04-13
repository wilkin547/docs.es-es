---
title: "C&#243;mo: Mostrar el componente PrintDialog | Microsoft Docs"
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
  - "Imprimir (cuadro de diálogo), mostrar"
  - "PrintDialog (componente) [Windows Forms], mostrar"
  - "imprimir [Windows Forms], mostrar el cuadro de diálogo Imprimir"
ms.assetid: 745a8db7-0526-4b21-b09d-18e13ed32014
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Mostrar el componente PrintDialog
El componente <xref:System.Windows.Forms.PrintDialog> es el cuadro de diálogo Imprimir de Windows estándar con el que estarán familiarizados muchos de sus usuarios.  Es recomendable utilizar el componente <xref:System.Windows.Forms.PrintDialog>, puesto que la mayor parte de los usuarios se sentirán ya cómodos con él.  
  
### Para mostrar el componente PrintDialog  
  
-   Llame al método <xref:System.Windows.Forms.Form.ShowDialog%2A> desde el código de la aplicación.  
  
     Una vez que se muestra el componente, los usuarios interactúan con él y establecen las propiedades del trabajo de impresión.  Éstas se guardan en la clase [PrinterSettings](frlrfSystemDrawingPrintingPrinterSettingsMembersTopic) \(y la clase [PageSettings](frlrfSystemDrawingPrintingPageSettingsMembersTopic), si el usuario obtiene acceso a [PageSetupDialog](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) mediante el componente <xref:System.Windows.Forms.PrintDialog>\) asociado a ese trabajo de impresión.  A continuación, puede hacer llamadas a las propiedades establecidas para determinar los pormenores del trabajo de impresión.  
  
## Vea también  
 [How to: Create Standard Windows Forms Print Jobs](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)   
 [How to: Capture User Input from a PrintDialog at Run Time](../../../../docs/framework/winforms/advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)   
 [PrintPreviewDialog \(Control\)](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)   
 [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)   
 [Windows Forms Print Support](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)   
 [Controles de Windows Forms](../../../../docs/framework/winforms/controls/index.md)