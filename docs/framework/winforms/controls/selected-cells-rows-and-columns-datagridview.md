---
title: "C&#243;mo: Obtener las celdas, filas y columnas seleccionadas en el control DataGridView de formularios Windows Forms | Microsoft Docs"
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
  - "DataGridView (control) [Windows Forms], obtener selección"
  - "obtener selección, DataGridView (control) [Windows Forms]"
  - "selección, DataGridView (control) [Windows Forms]"
ms.assetid: d93c4b5b-498e-49bc-982a-2229d61778e4
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# C&#243;mo: Obtener las celdas, filas y columnas seleccionadas en el control DataGridView de formularios Windows Forms
Puede obtener celdas, filas o columnas seleccionadas desde un control <xref:System.Windows.Forms.DataGridView> mediante las propiedades correspondientes: <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> y <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>.  En los procedimientos siguientes, obtendrá las celdas seleccionadas y mostrará los índices de fila y columna en un <xref:System.Windows.Forms.MessageBox>.  
  
### Para obtener las celdas seleccionadas en un control DataGridView  
  
-   Utilice la propiedad <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>.  
  
    > [!NOTE]
    >  Utilice el método <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> para no mostrar un número potencialmente grande de celdas.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#10)]  
  
### Para obtener las filas seleccionadas en un control DataGridView  
  
-   Utilice la propiedad <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>.  Para permitir a los usuarios seleccionar las filas, debe establecer la propiedad <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> en <xref:System.Windows.Forms.DataGridViewSelectionMode> o <xref:System.Windows.Forms.DataGridViewSelectionMode>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#20)]  
  
### Para obtener las columnas seleccionadas en un control DataGridView  
  
-   Utilice la propiedad <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>.  Para permitir a los usuarios seleccionar las columnas, debe establecer la propiedad <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> en <xref:System.Windows.Forms.DataGridViewSelectionMode> o <xref:System.Windows.Forms.DataGridViewSelectionMode>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#30)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Controles <xref:System.Windows.Forms.Button> denominados `selectedCellsButton`, `selectedRowsButton` y `selectedColumnsButton`, cada uno ellos con controladores para el evento <xref:System.Windows.Forms.Control.Click> asociado.  
  
-   Un control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=fullName>, <xref:System.Windows.Forms?displayProperty=fullName> y <xref:System.Text?displayProperty=fullName>.  
  
## Programación eficaz  
 Las colecciones descritas en este tema no se realizan con eficacia cuando se selecciona un gran número de celdas, filas o columnas.  Para obtener más información sobre cómo utilizar estas colecciones con grandes cantidades de datos, vea [Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>   
 <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>   
 <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>   
 <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>   
 <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>   
 [Selección y uso del Portapapeles con el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)