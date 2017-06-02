---
title: "C&#243;mo: Enlazar un objeto TreeView a datos que tienen una profundidad indeterminable | Microsoft Docs"
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
  - "TreeView (control) [WPF], enlazar a datos de profundidad indeterminada"
ms.assetid: daddcd74-1b0f-4ffd-baeb-ec934c5e0f53
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Enlazar un objeto TreeView a datos que tienen una profundidad indeterminable
Puede haber ocasiones en las que desee enlazar un elemento <xref:System.Windows.Controls.TreeView> a un origen de datos cuya profundidad no se conoce.  Esto puede ocurrir cuando los datos son de naturaleza recursiva, como en un sistema de archivos, donde las carpetas pueden contener carpetas, o la estructura organizativa de una compañía, donde los empleados dependen directamente de otros empleados.  
  
 El origen de datos debe tener un modelo de objetos jerárquico.  Por ejemplo, una clase `Employee` puede contener una colección de objetos Employee que dependan directamente de un empleado.  Si los datos se representan de forma no jerárquica, debe compilar una representación jerárquica de los datos.  
  
 Si se establece la propiedad <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A?displayProperty=fullName> y <xref:System.Windows.Controls.ItemsControl> genera un elemento <xref:System.Windows.Controls.ItemsControl> para cada elemento secundario, el elemento <xref:System.Windows.Controls.ItemsControl> secundario utiliza el mismo objeto <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> que el elemento primario.  Por ejemplo, si establece la propiedad <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> en un elemento <xref:System.Windows.Controls.TreeView> enlazado a datos, cada <xref:System.Windows.Controls.TreeViewItem> que se genera utiliza el objeto <xref:System.Windows.DataTemplate> asignado a la propiedad <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> de <xref:System.Windows.Controls.TreeView>.  
  
 <xref:System.Windows.HierarchicalDataTemplate> permite especificar la propiedad <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> para <xref:System.Windows.Controls.TreeViewItem>, o cualquier <xref:System.Windows.Controls.HeaderedItemsControl>, en la plantilla de datos.  Si se establece la propiedad <xref:System.Windows.HierarchicalDataTemplate.ItemsSource%2A?displayProperty=fullName>, ese valor se utiliza al aplicar <xref:System.Windows.HierarchicalDataTemplate>.  Mediante un elemento <xref:System.Windows.HierarchicalDataTemplate>, puede establecer la propiedad <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> de forma recursiva para cada <xref:System.Windows.Controls.TreeViewItem> en <xref:System.Windows.Controls.TreeView>.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo enlazar <xref:System.Windows.Controls.TreeView> a datos jerárquicos y utilizar <xref:System.Windows.HierarchicalDataTemplate> para especificar la propiedad <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> para cada elemento <xref:System.Windows.Controls.TreeViewItem>.  <xref:System.Windows.Controls.TreeView> enlaza a datos XML que representan a los empleados de una compañía.  Cada elemento `Employee` puede contener otros elementos `Employee` para indicar las dependencias entre empleados.  Dado que los datos son recursivos, el elemento <xref:System.Windows.HierarchicalDataTemplate> puede aplicarse a cada nivel.  
  
 [!code-xml[TreeViewWithUnknownDepth#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewWithUnknownDepth/CS/Window1.xaml#1)]  
  
## Vea también  
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Información general sobre plantillas de datos](../../../../docs/framework/wpf/data/data-templating-overview.md)