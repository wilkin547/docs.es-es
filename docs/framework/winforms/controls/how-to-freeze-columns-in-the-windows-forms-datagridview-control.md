---
title: "C&#243;mo: Inmovilizar columnas en el control DataGridView de formularios Windows Forms | Microsoft Docs"
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
  - "columnas [Windows Forms], congelar"
  - "DataGridView (control) [Windows Forms], columnas siempre a la vista"
  - "DataGridView (control) [Windows Forms], columnas congeladas"
ms.assetid: 2ef8b1de-782e-4867-af8d-58171ab5c106
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# C&#243;mo: Inmovilizar columnas en el control DataGridView de formularios Windows Forms
Cuando los usuarios ven los datos mostrados en un control <xref:System.Windows.Forms.DataGridView> de Windows Forms, a veces deben hacer referencia a una sola columna o a un conjunto de columnas con frecuencia.  Por ejemplo, cuando se muestra una tabla de información de clientes que contiene muchas columnas, resulta útil mostrar el nombre del cliente y dejar que otras columnas puedan desplazarse fuera del área visible.  
  
 Para conseguir este comportamiento, puede inmovilizar las columnas en el control.  Al inmovilizar una columna, también se inmovilizan todas las columnas situadas a su izquierda \(o a su derecha en los scripts de idioma de derecha a izquierda\).  Las columnas inmovilizadas permanecen en su lugar mientras que todas las demás columnas se pueden desplazar.  
  
> [!NOTE]
>  Si se habilita la reordenación de columnas, las columnas inmovilizadas se tratan como un grupo distinto de las columnas no inmovilizadas.  Los usuarios pueden cambiar la ubicación de las columnas en los grupos, pero no pueden mover una columna de un grupo a otro.  
  
 La propiedad <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> de una columna determina si la columna es visible siempre dentro de la cuadrícula.  
  
 Visual Studio es compatible con esta tarea.  Consulte también [Cómo: Inmovilizar columnas en el control DataGridView de Windows Forms mediante el Diseñador](http://msdn.microsoft.com/library/717ss6s6%20\(v=vs.110\)).  
  
### Para inmovilizar una columna mediante programación  
  
-   Establezca la propiedad <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=fullName> en `true`.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#061](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#061)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#061](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#061)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un control <xref:System.Windows.Forms.DataGridView> llamado `dataGridView1` que contiene una columna llamada `AddToCartButton`.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=fullName> y <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView>   
 [Características básicas de columnas, filas y celdas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)   
 [Cómo: Habilitar la reordenación de columnas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-enable-column-reordering-in-the-windows-forms-datagridview-control.md)