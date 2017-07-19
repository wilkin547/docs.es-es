---
title: "C&#243;mo: Quitar columnas generadas autom&#225;ticamente desde un control DataGridView de formularios Windows Forms | Microsoft Docs"
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
  - "columnas [Windows Forms], quitar"
  - "DataGridView (control) [Windows Forms], quitar columnas"
ms.assetid: 92e28d98-95a3-446c-9150-41b7c7e5be15
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Quitar columnas generadas autom&#225;ticamente desde un control DataGridView de formularios Windows Forms
Cuando el control <xref:System.Windows.Forms.DataGridView> se establece para generar automáticamente las columnas basadas en datos desde un origen de datos, puede omitir ciertas columnas de forma selectiva.  Para ello, puede llamar al método <xref:System.Windows.Forms.DataGridViewColumnCollection.Remove%2A> en la colección <xref:System.Windows.Forms.DataGridView.Columns%2A>.  También puede ocultar las columnas en la vista estableciendo la propiedad <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> en `false`.  Esta técnica resulta útil cuando desea mostrar las columnas ocultas en determinadas condiciones, o cuando necesita tener acceso a los datos de las columnas sin mostrarlas.  
  
### Para quitar las columnas generadas automáticamente  
  
-   Llame al método <xref:System.Windows.Forms.DataGridViewColumnCollection.Remove%2A> en la colección <xref:System.Windows.Forms.DataGridView.Columns%2A>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#111](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#111)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#111](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#111)]  
  
### Para ocultar las columnas generadas automáticamente  
  
-   Establezca la propiedad <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> de la columna en `false`.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#112](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#112)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#112](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#112)]  
  
## Ejemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#110)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#110)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1` enlazado a una tabla que contiene las columnas `Fax` y `CustomerID`, como las de la tabla `Customers` de la base de datos de ejemplo Northwind.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=fullName> y <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumnCollection.Remove%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=fullName>   
 [Mostrar datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)