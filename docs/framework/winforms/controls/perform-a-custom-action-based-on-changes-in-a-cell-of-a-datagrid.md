---
title: "C&#243;mo: Llevar a cabo una acci&#243;n personalizada en funci&#243;n de los cambios que se realicen en una celda de un control DataGridView de formularios Windows Forms | Microsoft Docs"
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
  - "celdas, detectar cambios"
  - "cuadrículas de datos, detectar cambios en celdas"
  - "DataGridView (control) [Windows Forms], detectar cambios en celdas"
ms.assetid: 7fa44d01-97f4-4ccb-a149-bc72628d2c36
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Llevar a cabo una acci&#243;n personalizada en funci&#243;n de los cambios que se realicen en una celda de un control DataGridView de formularios Windows Forms
El control <xref:System.Windows.Forms.DataGridView> tiene varios eventos que puede utilizar para detectar los cambios en el estado de celdas <xref:System.Windows.Forms.DataGridView>.  Dos de los más utilizados son los eventos <xref:System.Windows.Forms.DataGridView.CellValueChanged> y <xref:System.Windows.Forms.DataGridView.CellStateChanged>.  
  
### Para detectar cambios en los valores de celdas de DataGridView  
  
-   Escriba un controlador para el evento <xref:System.Windows.Forms.DataGridView.CellValueChanged>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#130)]  
  
### Para detectar cambios en los estados de celdas de DataGridView  
  
-   Escriba un controlador para el evento <xref:System.Windows.Forms.DataGridView.CellStateChanged>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#135](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#135)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#135](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#135)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.  En C\#, los controladores de eventos se deben conectar a los eventos correspondientes.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=fullName> y <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.CellValueChanged?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.CellStateChanged?displayProperty=fullName>   
 [Programar con celdas, filas y columnas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)   
 [Tutorial: Validar datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)