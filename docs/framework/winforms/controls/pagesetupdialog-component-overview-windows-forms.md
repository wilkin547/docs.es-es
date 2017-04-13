---
title: "Informaci&#243;n general sobre el componente PageSetupDialog (formularios Windows Forms) | Microsoft Docs"
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
  - "PageSetupDialog"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Configurar página (cuadro de diálogo), mostrar"
  - "PageSetupDialog (componente)"
ms.assetid: 791caacb-a5ca-4fca-bad9-1a5721ad697c
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Informaci&#243;n general sobre el componente PageSetupDialog (formularios Windows Forms)
El componente <xref:System.Windows.Forms.PageSetupDialog> de formularios Windows Forms es un cuadro de diálogo preconfigurado que permite establecer los detalles de la página para imprimir en aplicaciones Windows.  Utilícelo dentro de la aplicación para Windows como una solución sencilla para establecer las preferencias de página, en lugar de configurar un cuadro de diálogo propio.  Puede permitir que los usuarios establezcan ajustes de borde y margen, encabezados y pies de página, y orientación vertical y horizontal.  Al basarse en cuadros de diálogo estándar de Windows, creará aplicaciones cuya funcionalidad básica les resultará inmediatamente familiar a los usuarios.  
  
## Propiedades y métodos principales  
 Utilice el método <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> para mostrar el cuadro de diálogo en tiempo de ejecución.  En este componente pueden establecerse propiedades relacionadas con una sola página \(clase <xref:System.Drawing.Printing.PrintDocument>\) o con cualquier documento \(clase <xref:System.Drawing.Printing.PageSettings>\).  Además, el componente <xref:System.Windows.Forms.PageSetupDialog> puede utilizarse para determinar opciones específicas de la impresora, que se almacenan en la clase <xref:System.Drawing.Printing.PrinterSettings>.  
  
 Cuando se agrega a un formulario, el componente <xref:System.Windows.Forms.PageSetupDialog> aparece en la bandeja de la parte inferior del Diseñador de Windows Forms.  
  
## Vea también  
 <xref:System.Windows.Forms.PageSetupDialog>   
 [PageSetupDialog](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)