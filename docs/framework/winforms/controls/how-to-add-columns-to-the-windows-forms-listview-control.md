---
title: "C&#243;mo: Agregar columnas al control ListView de formularios Windows Forms | Microsoft Docs"
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
  - "columnas [Windows Forms], agregar a controles ListView"
  - "vistas de lista, agregar columnas"
  - "ListView (control) [Windows Forms], agregar encabezados de columna"
ms.assetid: 79174274-12ee-4a5d-80db-6ec02976d010
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# C&#243;mo: Agregar columnas al control ListView de formularios Windows Forms
En la vista Detalles, el control <xref:System.Windows.Forms.ListView> puede mostrar varias columnas para cada elemento de la lista.  Puede utilizar las columnas para mostrar al usuario información de diversos tipos acerca de cada elemento de la lista.  Por ejemplo, una lista de archivos puede mostrar el nombre de archivo, el tipo de archivo, el tamaño y la fecha de la última modificación.  Para obtener información sobre cómo rellenar las columnas una vez creadas, vea [Cómo: Mostrar subelementos en columnas con el control ListView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).  
  
### Para agregar columnas mediante programación  
  
1.  Establezca la propiedad <xref:System.Windows.Forms.ListView.View%2A> del control en <xref:System.Windows.Forms.View>.  
  
2.  Utilice el método <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> de la propiedad <xref:System.Windows.Forms.ListView.Columns%2A> de la vista de la lista.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#31)]  
  
## Vea también  
 <xref:System.Windows.Forms.ListView>   
 [ListView \(Control\)](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)   
 [Información general del control ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)