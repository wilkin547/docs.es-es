---
title: "How to: Capture User Input from a PrintDialog at Run Time | Microsoft Docs"
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
  - "print options, changing at run time"
  - "printing [Windows Forms], options"
  - "print options"
  - "run time, changing print options"
ms.assetid: 438501d8-9a70-4fb3-aae6-e46579aba0c6
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# How to: Capture User Input from a PrintDialog at Run Time
Aunque se pueden establecer opciones de impresión en tiempo de diseño, a veces se desean cambiar estas opciones en tiempo de ejecución, sobre todo debido a las opciones seleccionadas por el usuario.  Puede capturar los datos proporcionados por el usuario para imprimir un documento usando los componentes <xref:System.Windows.Forms.PrintDialog> y <xref:System.Drawing.Printing.PrintDocument>.  
  
### Para cambiar las opciones de impresión mediante programación  
  
1.  Agregue un componente <xref:System.Windows.Forms.PrintDialog> y otro <xref:System.Drawing.Printing.PrintDocument> al formulario.  
  
2.  Establezca la propiedad <xref:System.Windows.Forms.PrintDialog.Document%2A> de <xref:System.Windows.Forms.PrintDialog> en el <xref:System.Drawing.Printing.PrintDocument> agregado al formulario.  
  
    ```vb  
    PrintDialog1.Document = PrintDocument1  
  
    ```  
  
    ```csharp  
    printDialog1.Document = PrintDocument1;  
  
    ```  
  
    ```cpp  
    printDialog1->Document = PrintDocument1;  
    ```  
  
3.  Muestre el componente <xref:System.Windows.Forms.PrintDialog> mediante el método <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>.  
  
    ```vb  
    PrintDialog1.ShowDialog()  
  
    ```  
  
    ```csharp  
    printDialog1.ShowDialog();  
  
    ```  
  
    ```cpp  
    printDialog1->ShowDialog();  
    ```  
  
4.  Las opciones de impresión seleccionadas por el usuario en el cuadro de diálogo se copiarán en la propiedad <xref:System.Drawing.Printing.PrinterSettings> del componente <xref:System.Drawing.Printing.PrintDocument>.  
  
## Vea también  
 [How to: Print a Multi\-Page Text File in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)   
 [Windows Forms Print Support](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)