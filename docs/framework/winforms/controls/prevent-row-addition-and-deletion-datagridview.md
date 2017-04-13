---
title: "C&#243;mo: Impedir la adici&#243;n y eliminaci&#243;n de filas en el control DataGridView de formularios Windows Forms | Microsoft Docs"
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
  - "entrada de datos, deshabilitar en cuadrículas"
  - "cuadrículas de datos, deshabilitar entrada de datos"
  - "DataGridView (control) [Windows Forms], deshabilitar entrada de datos"
ms.assetid: ef9539ce-539b-404e-84b6-ac282b64b88c
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Impedir la adici&#243;n y eliminaci&#243;n de filas en el control DataGridView de formularios Windows Forms
En algunos casos, querrá impedir que los usuarios incluyan nuevas filas de datos o eliminen las filas existentes en el control <xref:System.Windows.Forms.DataGridView>.  La propiedad <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> indica si la fila para nuevos registros está presente en la parte inferior del control, mientras que la propiedad <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> indica si las filas se pueden quitar.  El ejemplo de código siguiente utiliza estas propiedades y también establece la propiedad <xref:System.Windows.Forms.DataGridView.ReadOnly%2A> para que el control sea únicamente de solo lectura.  
  
 Visual Studio es compatible con esta tarea.  Consulte también [Cómo: Impedir la adición y eliminación de filas en el control DataGridView de Windows Forms mediante el Diseñador](http://msdn.microsoft.com/library/k5c88sw3\(v=vs.110\)).  
  
## Ejemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#090](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#090)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#090](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#090)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=fullName> y <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.ReadOnly%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A?displayProperty=fullName>   
 [Características básicas de columnas, filas y celdas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)