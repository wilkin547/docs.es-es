---
title: "C&#243;mo: Especificar valores predeterminados para nuevas filas en el control DataGridView de formularios Windows Forms | Microsoft Docs"
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
  - "cuadrículas de datos, valores predeterminados para filas nuevas"
  - "DataGridView (control) [Windows Forms], entrada de datos"
  - "DataGridView (control) [Windows Forms], valores predeterminados para filas nuevas"
  - "filas, especificar valores predeterminados"
ms.assetid: 8d127963-d9f8-4e4e-9f7f-beb66688f1f2
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Especificar valores predeterminados para nuevas filas en el control DataGridView de formularios Windows Forms
Puede hacer que la entrada de datos sea más cómoda si la aplicación rellena los valores predeterminados para las filas recientemente agregadas.  Con la clase <xref:System.Windows.Forms.DataGridView>, puede rellenar los valores predeterminados con el evento <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded>.  Este evento se provoca cuando el usuario introduce la fila para los nuevos registros.  Cuando el código controla este evento, puede rellenar las celdas deseadas con valores de su elección.  
  
 En el ejemplo de código siguiente se muestra cómo especificar valores predeterminados para las nuevas filas mediante el evento <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded>.  
  
## Ejemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#120)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#120)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.  
  
-   Una función `NewCustomerId` para generar valores de `CustomerID` únicos.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=fullName> y <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=fullName>   
 [Entrada de datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)   
 [Utilizar la fila de nuevos registros en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)