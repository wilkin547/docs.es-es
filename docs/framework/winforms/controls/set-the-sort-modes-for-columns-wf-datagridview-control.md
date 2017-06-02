---
title: "C&#243;mo: Establecer modos de ordenaci&#243;n de columnas en el control DataGridView de formularios Windows Forms | Microsoft Docs"
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
  - "cuadrículas de datos, ordenar datos"
  - "DataGridView (control) [Windows Forms], modo de ordenación"
  - "ordenar, cuadrículas de datos"
ms.assetid: 57dfed60-a608-40d5-86f9-d65686ffb325
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Establecer modos de ordenaci&#243;n de columnas en el control DataGridView de formularios Windows Forms
En el control <xref:System.Windows.Forms.DataGridView>, las columnas de cuadro de texto utilizan de forma predeterminada la ordenación automática, mientras otros tipos de columna no se ordenan automáticamente.  Algunas veces, se querrán reemplazar estos valores predeterminados.  Por ejemplo, se pueden mostrar imágenes en lugar de texto, números o valores de celda de enumeración.  Aunque no se pueden ordenar las imágenes, se pueden ordenar los valores subyacentes que representan.  
  
 En el control <xref:System.Windows.Forms.DataGridView>, el valor de propiedad <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> de una columna determina su comportamiento de ordenación.  
  
 En el procedimiento siguiente se muestra la columna `Priority` de [Cómo: Personalizar el formato de los datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  Esta columna es una columna de imagen y no se puede ordenar de forma predeterminada.  Sin embargo, contiene valores de celda reales que son cadenas, por tanto se puede ordenar automáticamente.  
  
### Para establecer el modo de ordenación para una columna  
  
-   Establezca la propiedad <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=fullName>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#066](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#066)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#066](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#066)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1` que contiene una columna denominada `Priority`.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=fullName> y <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=fullName>   
 [Ordenar datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/sorting-data-in-the-windows-forms-datagridview-control.md)   
 [Modos de ordenación de columnas del control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md)   
 [Cómo: Personalizar la ordenación en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)