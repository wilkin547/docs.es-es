---
title: "C&#243;mo: Usar SelectedValue, SelectedValuePath y SelectedItem | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Control (clase), SelectedItem (propiedades)"
  - "Control (clase), SelectedValue (propiedades)"
  - "Control (clase), SelectedValuePath (propiedades)"
  - "Control (clase), TreeView (propiedades)"
  - "SelectedValue, SelectedItem (propiedades)"
  - "SelectedValue, SelectedValuePath (propiedades)"
  - "TreeView (control), SelectedItem (propiedades)"
  - "TreeView (control), SelectedValue (propiedades)"
  - "TreeView (control), SelectedValuePath (propiedades)"
ms.assetid: 2fc92ad4-f02c-4f89-bbe9-d4978a7af0db
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Usar SelectedValue, SelectedValuePath y SelectedItem
En este ejemplo se muestra cómo utilizar las propiedades <xref:System.Windows.Controls.TreeView.SelectedValue%2A> y <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> para especificar un valor para <xref:System.Windows.Controls.TreeView.SelectedItem%2A> de <xref:System.Windows.Controls.TreeView>.  
  
## Ejemplo  
 La propiedad <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> proporciona una manera de especificar <xref:System.Windows.Controls.TreeView.SelectedValue%2A> para <xref:System.Windows.Controls.TreeView.SelectedItem%2A> en <xref:System.Windows.Controls.TreeView>.  <xref:System.Windows.Controls.TreeView.SelectedItem%2A> representa un objeto en la colección <xref:System.Windows.Controls.ItemsControl.Items%2A> y <xref:System.Windows.Controls.TreeView> muestra el valor de una propiedad única del elemento seleccionado.  La propiedad <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> especifica la ruta de acceso a la propiedad que se usa para determinar el valor de la propiedad <xref:System.Windows.Controls.TreeView.SelectedValue%2A>.  En los ejemplos de este tema se ilustra este concepto.  
  
 En el ejemplo siguiente se muestra un objeto <xref:System.Windows.Data.XmlDataProvider> que contiene información de empleado.  
  
 [!code-xml[TreeViewSelectedValue#XMLDataProvider](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#xmldataprovider)]  
  
 En el ejemplo siguiente se define un objeto <xref:System.Windows.HierarchicalDataTemplate> que muestra los elementos de datos `EmployeeName` y `EmployeeWorkDay` de `Employee`.  Observe que <xref:System.Windows.HierarchicalDataTemplate> no especifica `EmployeeNumber` como parte de la plantilla.  
  
 [!code-xml[TreeViewSelectedValue#HierarchicalDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#hierarchicaldatatemplate)]  
  
 En el ejemplo siguiente se muestra un objeto <xref:System.Windows.Controls.TreeView> que utiliza la <xref:System.Windows.HierarchicalDataTemplate> previamente definida y que establece la propiedad <xref:System.Windows.Controls.TreeView.SelectedValue%2A> en `EmployeeNumber`.  Cuando se selecciona un elemento de datos `EmployeeName` en <xref:System.Windows.Controls.TreeView>, la propiedad <xref:System.Windows.Controls.TreeView.SelectedItem%2A> devuelve el elemento de datos `EmployeeInfo` correspondiente a `EmployeeName`.  Sin embargo, debido a que la propiedad <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> de <xref:System.Windows.Controls.TreeView> está establecida en `EmployeeNumber`, la propiedad <xref:System.Windows.Controls.TreeView.SelectedValue%2A> se establece en `EmployeeNumber`.  
  
 [!code-xml[TreeViewSelectedValue#SelectedValuePath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#selectedvaluepath)]  
  
## Vea también  
 <xref:System.Windows.Controls.TreeView>   
 <xref:System.Windows.Controls.TreeViewItem>   
 [Introducción a TreeView](../../../../docs/framework/wpf/controls/treeview-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/treeview-how-to-topics.md)