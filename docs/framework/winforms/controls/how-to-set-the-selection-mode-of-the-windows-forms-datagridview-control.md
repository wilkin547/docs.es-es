---
title: "C&#243;mo: Establecer el modelo de selecci&#243;n del control DataGridView de formularios Windows Forms | Microsoft Docs"
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
  - "cuadrículas de datos, modo de selección"
  - "DataGridView (control) [Windows Forms], modo de selección"
  - "selección, modos en el control DataGridView"
ms.assetid: 2f241643-7f82-4583-8757-03494f63b465
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Establecer el modelo de selecci&#243;n del control DataGridView de formularios Windows Forms
En el ejemplo de código siguiente se muestra cómo configurar un control <xref:System.Windows.Forms.DataGridView> para que, si se hace clic en cualquier sitio dentro de una fila, seleccione automáticamente toda la fila, y de tal forma que sólo se pueda seleccionar una fila a la vez.  
  
## Ejemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#065](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#065)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#065](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#065)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=fullName> y <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>   
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>   
 <xref:System.Windows.Forms.DataGridViewSelectionMode>   
 [Selección y uso del Portapapeles con el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)   
 [Modos de selección en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md)