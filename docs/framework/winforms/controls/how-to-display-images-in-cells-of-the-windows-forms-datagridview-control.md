---
title: "C&#243;mo: Mostrar im&#225;genes en celdas del control DataGridView de formularios Windows Forms | Microsoft Docs"
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
  - "celdas, mostrar imágenes"
  - "cuadrículas de datos, mostrar imágenes en celdas"
  - "cuadrículas de datos, mostrar en cuadrículas"
  - "DataGridView (control) [Windows Forms], mostrar imágenes"
ms.assetid: 53b13d31-1b56-476d-9ab4-18bfac138a22
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Mostrar im&#225;genes en celdas del control DataGridView de formularios Windows Forms
Una imagen o gráfico es uno de los valores que se pueden mostrar en una fila de datos.  Con frecuencia, estos gráficos pueden ser la fotografía de un empleado o el logotipo de una compañía.  
  
 La incorporación de imágenes es un proceso muy sencillo cuando se muestran los datos en el control <xref:System.Windows.Forms.DataGridView>.  El control <xref:System.Windows.Forms.DataGridView> controla de forma nativa cualquier formato de imagen admitido por la clase <xref:System.Drawing.Image>, así como el formato de imagen de OLE utilizado por algunas bases de datos.  
  
 Si el origen de datos del control <xref:System.Windows.Forms.DataGridView> tiene una columna de imágenes, el control <xref:System.Windows.Forms.DataGridView> las mostrará automáticamente.  
  
 En el ejemplo de código siguiente se muestra cómo extraer un icono desde un recurso incrustado y lo convierte en un mapa de bits para mostrarlo en cada celda de una columna de imagen.  Para obtener otro ejemplo que reemplaza los valores de celda textuales con las imágenes correspondientes, vea [Cómo: Personalizar el formato de los datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
## Ejemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#050](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#050)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#050](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#050)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.  
  
-   Un recurso de icono incrustado denominado `tree.ico`.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=fullName>, <xref:System.Windows.Forms?displayProperty=fullName> y <xref:System.Drawing?displayProperty=fullName>.  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 [Características básicas de columnas, filas y celdas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)   
 [Cómo: Personalizar el formato de los datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)