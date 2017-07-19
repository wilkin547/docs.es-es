---
title: "C&#243;mo: Agregar una columna independiente a un control DataGridView de formularios Windows Forms enlazado a datos | Microsoft Docs"
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
  - "columnas [Windows Forms], datos sin enlazar"
  - "cuadrículas de datos, agregar columnas sin enlazar"
  - "DataGridView (control) [Windows Forms], datos sin enlazar"
ms.assetid: f7bdc4d8-ba8e-421b-ad62-82d936f01372
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Agregar una columna independiente a un control DataGridView de formularios Windows Forms enlazado a datos
Los datos que muestra en el control <xref:System.Windows.Forms.DataGridView> proceden por lo general de un origen de datos, pero es posible que desee mostrar una columna de datos que no proceda de dicho origen de datos.  Este tipo de columna se denomina columna independiente.  Las columnas independientes pueden adoptar muchas formas.  Con frecuencia, se utilizan para permitir acceder a los detalles de una fila de datos.  
  
 En el ejemplo de código siguiente, se explica cómo crear una columna sin enlazar con botones **Detalles** para mostrar una tabla secundaria relacionada con una fila determinada de una tabla primaria al implementar un escenario principal\-detalle.  Para responder a los clics en los botones, implemente un controlador de eventos <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=fullName> que muestra un formulario que contiene la tabla secundaria.  
  
 Visual Studio es compatible con esta tarea.  Consulte también [Cómo: Agregar y quitar columnas en el control DataGridView de Windows Forms mediante el Diseñador](http://msdn.microsoft.com/library/dyyesckz\(v=vs.110\))  
  
## Ejemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#010](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#010)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#010](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#010)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=fullName> y <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 [Mostrar datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)   
 [Modos de presentación de datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)