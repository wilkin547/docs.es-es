---
title: "Informaci&#243;n general sobre el componente PrintDocument (formularios Windows Forms) | Microsoft Docs"
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
  - "PrintDocument"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "PrintDocument (componente) [Windows Forms], acerca del componente PrintDocument"
  - "imprimir [Windows Forms], PrintDocument (componente)"
ms.assetid: b59b4b60-dce5-42ca-8421-3a54a2f7bab0
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Informaci&#243;n general sobre el componente PrintDocument (formularios Windows Forms)
El componente [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) de formularios Windows Forms se utiliza para establecer las propiedades que describen qué se imprime y, a continuación, imprimir el documento dentro de aplicaciones para Windows.  Puede utilizarse junto con el componente [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) para controlar todos los aspectos de la impresión de documentos.  
  
## Trabajar con el componente PrintDocument  
 Dos de los principales escenarios que implican al componente <xref:System.Drawing.Printing.PrintDocument> son:  
  
-   Trabajos de impresión sencillos, tales como la impresión de un archivo de texto individual.  En este caso, deberá agregar el componente <xref:System.Drawing.Printing.PrintDocument> a un Windows Form y, a continuación, agregar la lógica de programación que imprime un archivo en el controlador de eventos <xref:System.Drawing.Printing.PrintDocument.PrintPage>.  La lógica de programación debe culminar en el método <xref:System.Drawing.Printing.PrintDocument.Print%2A> para imprimir el documento.  Este método envía a la impresora un objeto <xref:System.Drawing.Graphics>, incluido en la propiedad <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> de la clase <xref:System.Drawing.Printing.PrintPageEventArgs>.  Para obtener un ejemplo en el que se muestra cómo imprimir un documento de texto mediante el componente <xref:System.Drawing.Printing.PrintDocument>, vea [How to: Print a Multi\-Page Text File in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).  
  
-   Trabajos de impresión más complejos como, por ejemplo, una situación en la que se desee reutilizar la lógica de impresión escrita.  En este caso, deberá derivar un nuevo componente del componente <xref:System.Drawing.Printing.PrintDocument> e invalidar \(vea [Overrides](../Topic/Overrides%20\(Visual%20Basic\).md) para Visual Basic u [override](../Topic/override%20\(C%23%20Reference\).md) para C\#\) el evento <xref:System.Drawing.Printing.PrintDocument.PrintPage>.  
  
 Cuando se agrega a un formulario, el componente <xref:System.Drawing.Printing.PrintDocument> aparece en la bandeja de la parte inferior del Diseñador de Windows Forms.  
  
## Vea también  
 <xref:System.Drawing.Graphics>   
 <xref:System.Drawing.Printing.PrintDocument>   
 [Windows Forms Print Support](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)   
 [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)