---
title: "C&#243;mo: Especificar el modo de edici&#243;n del control DataGridView de formularios Windows Forms | Microsoft Docs"
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
  - "cuadrículas de datos, editar modo"
  - "DataGridView (control) [Windows Forms], editar modo"
ms.assetid: 93e117e8-94c4-411b-ba31-645e475ed85c
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# C&#243;mo: Especificar el modo de edici&#243;n del control DataGridView de formularios Windows Forms
De forma predeterminada, los usuarios pueden modificar el contenido de la celda del cuadro de texto de <xref:System.Windows.Forms.DataGridView> escribiendo en él o presionando F2.  De esta forma se coloca la celda en modo de edición si se cumplen todas las condiciones siguientes:  
  
-   El origen de datos subyacente admite la edición.  
  
-   Se habilita el control <xref:System.Windows.Forms.DataGridView>.  
  
-   El valor de propiedad <xref:System.Windows.Forms.DataGridView.EditMode%2A> no es <xref:System.Windows.Forms.DataGridViewEditMode>.  
  
-   Las propiedades `ReadOnly` de la celda, fila, columna y control están establecidas `false`.  
  
 En modo de edición, el usuario puede cambiar el valor de la celda y presionar INTRO para confirmar el cambio o ESC para devolver a la celda a su valor original.  
  
 Puede configurar un control <xref:System.Windows.Forms.DataGridView> para que una celda pase al modo de edición tan pronto como se convierta en la celda actual.  Este comportamiento de las teclas INTRO y ESC no cambia en este caso, pero la celda continúa en modo de edición después de que el valor se haya confirmado o revertido.  También puede configurar el control para que la celda pase a modo de edición sólo cuando los usuarios escriban en la celda o cuando los usuarios presionen F2.  Finalmente, puede evitar que las celdas pasen al modo de edición excepto cuando llame al método <xref:System.Windows.Forms.DataGridView.BeginEdit%2A>.  
  
### Para cambiar el modo de edición de un control DataGridView  
  
-   Establezca la propiedad <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=fullName> en la enumeración <xref:System.Windows.Forms.DataGridViewEditMode> apropiada.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#067](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#067)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#067](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#067)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.  
  
-   Referencias a los ensamblados <xref:System> y <xref:System.Windows.Forms>.  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=fullName>   
 [Entrada de datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)