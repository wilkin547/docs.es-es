---
title: "C&#243;mo: Utilizar la plantilla de filas para personalizar filas en el control DataGridView de formularios Windows Forms | Microsoft Docs"
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
  - "cuadrículas de datos, personalizar filas"
  - "DataGridView (control) [Windows Forms], personalizar filas"
ms.assetid: 6db61607-7e57-4a84-8d63-9d6a7ed7f9ff
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Utilizar la plantilla de filas para personalizar filas en el control DataGridView de formularios Windows Forms
El control <xref:System.Windows.Forms.DataGridView> utiliza la plantilla de filas como base para todas las filas que agrega al control, ya sea mediante el enlace a datos o cuanto llama al método <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=fullName> sin especificar una fila existente para utilizar.  
  
 La plantilla de filas ofrece un control sobre la apariencia y comportamiento de las filas mayor que el que proporciona la propiedad <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>.  Con la plantilla de filas, puede establecer cualquier propiedad <xref:System.Windows.Forms.DataGridViewRow>, incluso <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>.  
  
 En ciertas situaciones, se debe utilizar la plantilla de filas para lograr un efecto determinado.  Por ejemplo, la información de alto de fila no se puede almacenar en un <xref:System.Windows.Forms.DataGridViewCellStyle>, por tanto, se debe utilizar una plantilla de filas para cambiar el alto predeterminado utilizado por todas las filas.  La plantilla de filas también es útil cuando crea sus propias clases derivadas de <xref:System.Windows.Forms.DataGridViewRow> y desea el tipo personalizado cuando se agregan nuevas filas al control.  
  
> [!NOTE]
>  Sólo se utiliza la plantilla de filas cuando se agregan filas.  No se pueden cambiar las filas existentes cambiando la plantilla de filas.  
  
### Para utilizar la plantilla de filas  
  
-   Establezca las propiedades en el objeto recuperado desde la propiedad <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=fullName>.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.RowTemplate#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CPP/datagridviewrowtemplate.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridView.RowTemplate#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CS/datagridviewrowtemplate.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridView.RowTemplate#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/VB/datagridviewrowtemplate.vb#1)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=fullName>, <xref:System.Drawing?displayProperty=fullName> y <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewCellStyle>   
 <xref:System.Windows.Forms.DataGridViewRow>   
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=fullName>   
 [Estilo y formato básicos del control DataGridView en formularios Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)   
 [Estilos de celda en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)