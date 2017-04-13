---
title: "C&#243;mo: Habilitar la reordenaci&#243;n de columnas en el control DataGridView de formularios Windows Forms | Microsoft Docs"
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
  - "columnas [Windows Forms], reordenar"
  - "cuadrículas de datos, volver a ordenar columnas"
  - "DataGridView (control) [Windows Forms], orden de columnas"
ms.assetid: cc20eae3-e4db-493f-95ce-a4215e29472a
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Habilitar la reordenaci&#243;n de columnas en el control DataGridView de formularios Windows Forms
Al habilitar la reordenación de columnas en el control <xref:System.Windows.Forms.DataGridView>, los usuarios pueden mover una columna a una nueva posición arrastrando el encabezado de la columna con el mouse.  En el control <xref:System.Windows.Forms.DataGridView>, el valor de la propiedad <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=fullName> determina si los usuarios pueden mover las columnas a otras posiciones.  
  
 Visual Studio es compatible con esta tarea.  Consulte también [Cómo: Habilitar la reordenación de columnas en el control DataGridView de Windows Forms mediante el Diseñador](http://msdn.microsoft.com/library/8xwtyc86\(v=vs.110\))  
  
### Para habilitar mediante programación la reordenación de columnas  
  
-   Establezca la propiedad <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=fullName> en `true`.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#060](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#060)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#060](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#060)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=fullName> y <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=fullName>   
 [Características básicas de columnas, filas y celdas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)   
 [Cómo: Inmovilizar columnas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-freeze-columns-in-the-windows-forms-datagridview-control.md)