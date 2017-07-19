---
title: "C&#243;mo: Obtener y establecer la celda actual en el control DataGridView de formularios Windows Forms | Microsoft Docs"
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
  - "celdas, obtener y establecer activas"
  - "DataGridView (control) [Windows Forms], obtener celda activa"
  - "DataGridView (control) [Windows Forms], establecer celda activa"
ms.assetid: b0e41e57-493a-4bd0-9376-a6f76723540c
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Obtener y establecer la celda actual en el control DataGridView de formularios Windows Forms
La interacción con <xref:System.Windows.Forms.DataGridView> requiere a menudo que se detecte mediante programación la celda que está activa actualmente.  También puede necesitar cambiar la celda actual.  Puede realizar estas tareas con la propiedad <xref:System.Windows.Forms.DataGridView.CurrentCell%2A>.  
  
> [!NOTE]
>  No puede establecer la celda actual en una fila o columna cuya propiedad <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> está establecida en `false`.  
  
 Dependiendo del modo de selección del control <xref:System.Windows.Forms.DataGridView>, el cambio de la celda actual puede cambiar la selección.  Para obtener más información, vea [Modos de selección en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md).  
  
### Para obtener mediante programación la celda actual  
  
-   Utilice la propiedad <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> del control <xref:System.Windows.Forms.DataGridView>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### Para establecer mediante programación la celda actual  
  
-   Utilice la propiedad <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> del control <xref:System.Windows.Forms.DataGridView>.  En el ejemplo de código siguiente, la celda actual se establece en la fila 0, columna 1.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Controles <xref:System.Windows.Forms.Button> denominados `getCurrentCellButton` y `setCurrentCellButton`.  En [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], debe asociar los eventos <xref:System.Windows.Forms.Control.Click> para cada botón al controlador de eventos asociado en el código de ejemplo.  
  
-   Un control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=fullName> y <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=fullName>   
 [Características básicas de columnas, filas y celdas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)   
 [Modos de selección en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md)