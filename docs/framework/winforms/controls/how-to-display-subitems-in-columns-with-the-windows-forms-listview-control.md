---
title: "C&#243;mo: Mostrar subelementos en columnas con el control ListView de formularios Windows Forms | Microsoft Docs"
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
  - "vista de detalles"
  - "elementos de lista"
  - "ListView (control) [Windows Forms], agregar objetos ListSubItem"
  - "subelementos"
ms.assetid: e465f044-cde7-4fd9-a687-788a73a0f554
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Mostrar subelementos en columnas con el control ListView de formularios Windows Forms
El control <xref:System.Windows.Forms.ListView> de formularios Windows Forms puede mostrar texto adicional, o subelementos, para cada elemento de la vista Details.  La primera columna muestra el texto del elemento; por ejemplo, el número del empleado.  La segunda, tercera y siguientes columnas muestran el primero, segundo y siguientes subelementos asociados.  
  
### Para agregar subelementos a un elemento de lista  
  
1.  Agregue las columnas necesarias.  Como la primera columna mostrará la propiedad <xref:System.Windows.Forms.ListView.Text%2A> del elemento, necesita una columna más que subelementos haya.  Para obtener más información sobre cómo agregar columnas, vea [Cómo: Agregar columnas al control ListView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md).  
  
2.  Llame al método <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> de la colección que devuelve la propiedad <xref:System.Windows.Forms.ListViewItem.SubItems%2A> de un elemento.  El siguiente ejemplo de código establece el nombre de empleado y el departamento para un elemento de la lista.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#61)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#61)]  
  
## Vea también  
 [Información general del control ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)   
 [Cómo: Agregar y quitar elementos con el control ListView de Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)   
 [Cómo: Agregar columnas al control ListView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)   
 [Cómo: Mostrar iconos del control ListView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)   
 [Cómo: Agregar información personalizada a los controles TreeView o ListView \(formularios Windows Forms\)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)