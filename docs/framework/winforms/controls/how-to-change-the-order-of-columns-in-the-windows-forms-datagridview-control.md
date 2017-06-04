---
title: "C&#243;mo: Cambiar el orden de las columnas en el control DataGridView de formularios Windows Forms | Microsoft Docs"
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
  - "columnas [Windows Forms], cambiar el orden"
  - "cuadrículas de datos, cambiar el orden de columna"
  - "DataGridView (control) [Windows Forms], orden de columnas"
ms.assetid: 5e9ac3bc-b0f0-48cb-a3d5-b005af905395
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# C&#243;mo: Cambiar el orden de las columnas en el control DataGridView de formularios Windows Forms
Cuando se usa un control <xref:System.Windows.Forms.DataGridView> para mostrar datos desde un origen de datos, a veces las columnas del esquema del origen de datos no aparecen en el orden que quiere que se muestren.  Puede cambiar el orden de visualización de las columnas mediante la propiedad <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A> de la clase <xref:System.Windows.Forms.DataGridViewColumn>.  
  
 En el ejemplo de código siguiente, se cambia de posición de algunas de las columnas generadas automáticamente cuando se enlaza a la tabla Customers de la base de datos de ejemplo Northwind.  Para obtener más información sobre cómo enlazar el control <xref:System.Windows.Forms.DataGridView> a una tabla de base de datos, consulte [Cómo: Enlazar datos al control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md).  
  
 Visual Studio es compatible con esta tarea.  Consulte también [Cómo: Cambiar el orden de las columnas en el control DataGridView de Windows Forms mediante el Diseñador](http://msdn.microsoft.com/library/hb1dk7ax\(v=vs.110\)).  
  
## Ejemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#040](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#040)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#040](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#040)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un control <xref:System.Windows.Forms.DataGridView> denominado `customersDataGridView` que está enlazado a una tabla con los nombres de columna indicados, como la tabla `Customers` en la base de datos de ejemplo Northwind.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=fullName>, <xref:System.Windows.Forms?displayProperty=fullName>, <xref:System.Data?displayProperty=fullName> y <xref:System.Xml?displayProperty=fullName>.  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewColumn>   
 <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=fullName>   
 [Mostrar datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)   
 [Cómo: Enlazar datos al control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md)