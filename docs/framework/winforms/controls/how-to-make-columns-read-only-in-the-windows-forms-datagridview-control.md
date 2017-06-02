---
title: "C&#243;mo: Crear columnas de s&#243;lo lectura en el control DataGridView de formularios Windows Forms | Microsoft Docs"
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
  - "cuadrículas de datos, columnas de sólo lectura"
  - "DataGridView (control) [Windows Forms], columnas de sólo lectura"
ms.assetid: 2bb73ebb-1a55-4362-9fda-e50574c087d5
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# C&#243;mo: Crear columnas de s&#243;lo lectura en el control DataGridView de formularios Windows Forms
No todos los datos están diseñados para ser editados.  En el control <xref:System.Windows.Forms.DataGridView>, el valor de propiedad <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> de la columna determina si los usuarios pueden editar las celdas de esa columna.  Para obtener información acerca de cómo hacer que el control sea completamente de solo lectura, consulte [Cómo: Impedir la adición y eliminación de filas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md).  
  
 Visual Studio es compatible con esta tarea.  Consulte también [Cómo: Crear columnas de solo lectura en el control DataGridView de Windows Forms mediante el Diseñador](http://msdn.microsoft.com/library/xd4k3c7e%20\(v=vs.110\)).  
  
### Para que hacer que una columna sea de solo lectura mediante programación  
  
-   Establezca la propiedad <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=fullName> en `true`.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#064](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#064)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#064](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#064)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1` con una columna denominada `CompanyName`.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=fullName> y <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=fullName>   
 [Características básicas de columnas, filas y celdas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)   
 [Cómo: Impedir la adición y eliminación de filas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md)