---
title: "C&#243;mo: Agregar informaci&#243;n sobre herramientas a celdas individuales en un control DataGridView de formularios Windows Forms | Microsoft Docs"
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
  - "cuadrículas de datos, agregar información sobre herramientas"
  - "DataGridView (control) [Windows Forms], agregar información sobre herramientas"
  - "información sobre herramientas [Windows Forms], agregar a cuadrículas de datos"
ms.assetid: 2a81f9de-d58b-4ea8-bc0b-8d93c2f4cf78
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# C&#243;mo: Agregar informaci&#243;n sobre herramientas a celdas individuales en un control DataGridView de formularios Windows Forms
De manera predeterminada, la información sobre herramientas se utiliza para mostrar los valores de celdas de <xref:System.Windows.Forms.DataGridView> que son demasiado pequeñas para mostrar su contenido completo.  Sin embargo, puede reemplazar este comportamiento para establecer los valores de texto de información sobre herramientas en celdas individuales.  Resulta útil para mostrar a los usuarios información adicional sobre una celda o para proporcionarles otra descripción del contenido de la celda.  Por ejemplo, si tiene una fila que muestra los iconos de estado, puede proporcionar explicaciones de texto mediante la información sobre herramientas.  
  
 También puede deshabilitar la presentación de la información sobre herramientas en las celdas estableciendo la propiedad <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=fullName> en `false`.  
  
### Para agregar una información sobre herramientas a una celda  
  
-   Establezca la propiedad <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=fullName>.  
  
     [!code-cpp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/cpp/datagridviewcell.tooltiptext.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/CS/datagridviewcell.tooltiptext.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/VB/datagridviewcell.tooltiptext.vb#1)]  
  
## Compilar el código  
  
-   Para este ejemplo se necesita:  
  
-   Un control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1` que contiene una columna denominada `Rating` para mostrar valores de cadena de uno a cuatro símbolos de asterisco \("\*"\).  Se debe asociar el evento <xref:System.Windows.Forms.DataGridView.CellFormatting> del control al método de control de eventos mostrado en el ejemplo.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=fullName> y <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## Programación eficaz  
 Cuando enlace el control <xref:System.Windows.Forms.DataGridView> a un origen de datos externo o proporcione su propio origen de datos implementando el modo virtual, se puede encontrar con problemas relacionados con el rendimiento.  Para evitar una disminución del rendimiento cuando se trabaja con grandes cantidades de datos, controle el evento <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> en lugar de configurar la propiedad <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> de varias celdas.  Cuando controle este evento, obtener el valor de la propiedad <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> de una celda provoca el evento y devuelve el valor de la propiedad <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=fullName> tal como se ha especificado en el controlador de eventos.  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewCell>   
 <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=fullName>   
 [Programar con celdas, filas y columnas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)