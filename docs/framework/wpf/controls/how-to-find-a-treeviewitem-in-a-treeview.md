---
title: "C&#243;mo: Buscar un TreeViewItem en un TreeView | Microsoft Docs"
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
  - "TreeView (control) [WPF], buscar un TreeViewItem"
  - "TreeViewItem [WPF], buscar"
ms.assetid: 72ecd40c-3939-4e01-b617-5e9daa6074d9
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Buscar un TreeViewItem en un TreeView
El control <xref:System.Windows.Controls.TreeView> proporciona una manera cómoda de mostrar datos jerárquicos.  Si el <xref:System.Windows.Controls.TreeView> se enlaza a un origen de datos, la propiedad <xref:System.Windows.Controls.TreeView.SelectedItem%2A> proporciona una forma cómoda de recuperar rápidamente el objeto de datos seleccionado.  Suele ser preferible trabajar con el objeto de datos subyacente, pero a veces es posible que tenga que manipular el objeto <xref:System.Windows.Controls.TreeViewItem> que contiene los datos mediante programación.  Por ejemplo, es posible que necesite expandir <xref:System.Windows.Controls.TreeViewItem> mediante programación, o seleccionar otro elemento en <xref:System.Windows.Controls.TreeView>.  
  
 Para encontrar un control <xref:System.Windows.Controls.TreeViewItem> que contenga un objeto de datos concreto, debe recorrer cada nivel de <xref:System.Windows.Controls.TreeView>.  Los elementos de <xref:System.Windows.Controls.TreeView> también pueden virtualizarse para mejorar el rendimiento.  En caso de que los elementos estén virtualizados, también debe materializar un <xref:System.Windows.Controls.TreeViewItem> para comprobar si contiene el objeto de datos.  
  
## Ejemplo  
  
## Descripción  
 En el ejemplo siguiente se busca en <xref:System.Windows.Controls.TreeView> un objeto específico y se devuelve el control <xref:System.Windows.Controls.TreeViewItem> que contiene el objeto.  El ejemplo garantiza que se cree una instancia de cada <xref:System.Windows.Controls.TreeViewItem> para poder buscar sus elementos secundarios.  Este ejemplo también funciona si <xref:System.Windows.Controls.TreeView> no utiliza elementos virtualizados.  
  
> [!NOTE]
>  El siguiente ejemplo funciona para cualquier <xref:System.Windows.Controls.TreeView>, independientemente del modelo de datos subyacente. Se realizan búsquedas en cada <xref:System.Windows.Controls.TreeViewItem>, hasta que se encuentra el objeto.  Otra técnica que tiene mejor rendimiento es buscar en el modelo de datos el objeto especificado, realizar un seguimiento de su ubicación dentro de la jerarquía de datos y, a continuación, buscar el objeto <xref:System.Windows.Controls.TreeViewItem> correspondiente en <xref:System.Windows.Controls.TreeView>.  Sin embargo, la técnica que ofrece un mejor rendimiento requiere conocimientos del modelo de datos y no se puede generalizar para ningún <xref:System.Windows.Controls.TreeView> dado.  
  
## Código  
 [!code-csharp[TreeViewFindTVI#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[TreeViewFindTVI#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#1)]  
  
 El código anterior se basa en un <xref:System.Windows.Controls.VirtualizingStackPanel> personalizado que expone un método denominado `BringIntoView`.  En el código siguiente se define el <xref:System.Windows.Controls.VirtualizingStackPanel> personalizado.  
  
 [!code-csharp[TreeViewFindTVI#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#2)]
 [!code-vb[TreeViewFindTVI#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#2)]  
  
 En el XAML siguiente se muestra cómo crear un control <xref:System.Windows.Controls.TreeView> que use el objeto <xref:System.Windows.Controls.VirtualizingStackPanel> personalizado.  
  
 [!code-xml[TreeViewFindTVI#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml#3)]  
  
## Vea también  
 [Mejorar el rendimiento de un control TreeView](../../../../docs/framework/wpf/controls/how-to-improve-the-performance-of-a-treeview.md)