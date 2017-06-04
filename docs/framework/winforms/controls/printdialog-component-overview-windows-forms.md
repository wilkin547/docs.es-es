---
title: "Informaci&#243;n general sobre el componente PrintDialog (formularios Windows Forms) | Microsoft Docs"
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
  - "PrintDialog"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Imprimir (cuadro de diálogo), mostrar"
  - "PrintDialog (componente) [Windows Forms], acerca del componente PrintDialog"
ms.assetid: 8327b8ac-1017-4b5e-a88b-fea9dd56999c
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Informaci&#243;n general sobre el componente PrintDialog (formularios Windows Forms)
El componente [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) de formularios Windows Forms es un cuadro de diálogo preconfigurado que se utiliza para seleccionar una impresora, elegir las páginas que se van a imprimir y determinar otros valores de configuración relacionados con la impresión en aplicaciones para Windows.  Utilícelo como una solución sencilla para seleccionar configuraciones de la impresora o relacionadas con la impresora, en lugar de configurar un cuadro de diálogo propio.  Puede permitir que los usuarios impriman diversas partes de sus documentos: imprimir todo, imprimir un intervalo de páginas seleccionado o imprimir una selección.  Al basarse en cuadros de diálogo estándar de Windows, creará aplicaciones cuya funcionalidad básica les resultará inmediatamente familiar a los usuarios.  El componente <xref:System.Windows.Forms.PrintDialog> hereda de la clase <xref:System.Windows.Forms.CommonDialog>.  
  
## Trabajar con el componente  
 Utilice el método <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> para mostrar el cuadro de diálogo en tiempo de ejecución.  Este componente tiene propiedades relacionadas con un único trabajo de impresión \(clase <xref:System.Drawing.Printing.PrintDocument>\) o con las opciones de una impresora individual \(clase <xref:System.Drawing.Printing.PrinterSettings>\).  Cualquiera de ellas, a su vez, puede ser compartida por múltiples impresoras.  
  
 Cuando se agrega a un formulario, el componente <xref:System.Windows.Forms.PrintDialog> aparece en la bandeja de la parte inferior del Diseñador de Windows Forms.  
  
## Vea también  
 <xref:System.Windows.Forms.PrintDialog>   
 [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)