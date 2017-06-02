---
title: "C&#243;mo: Manipular columnas y filas mediante ColumnDefinitionsCollections y RowDefinitionsCollections | Microsoft Docs"
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
  - "clases, ColumnDefinitionCollection"
  - "clases, RowDefinitionCollection"
  - "ColumnDefinitionCollection (clase)"
  - "controles, Grid (clase)"
  - "Grid (control), ColumnDefinitionCollection (clase)"
  - "Grid (control), RowDefinitionCollection (clase)"
  - "RowDefinitionCollection (clase)"
ms.assetid: bfc7160a-45f2-4e17-9961-df414dfb13c5
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Manipular columnas y filas mediante ColumnDefinitionsCollections y RowDefinitionsCollections
En este ejemplo se muestra cómo usar los métodos de las clases <xref:System.Windows.Controls.ColumnDefinitionCollection> y <xref:System.Windows.Controls.RowDefinitionCollection> para realizar acciones como agregar, borrar o contar el contenido de filas o columnas.  Por ejemplo, puede llamar al método <xref:System.Windows.Controls.ColumnDefinitionCollection.Add%2A>, <xref:System.Windows.Controls.ColumnDefinitionCollection.Clear%2A> o <xref:System.Windows.Controls.ColumnDefinitionCollection.Count%2A> agregar, borrar o contar los elementos incluidos en un objeto <xref:System.Windows.Controls.ColumnDefinition> o <xref:System.Windows.Controls.RowDefinition>.  
  
## Ejemplo  
 En el ejemplo siguiente se crea un elemento <xref:System.Windows.Controls.Grid> con `grid1` como <xref:System.Windows.FrameworkElement.Name%2A>.  <xref:System.Windows.Controls.Grid> contiene un objeto <xref:System.Windows.Controls.StackPanel> que contiene elementos <xref:System.Windows.Controls.Button>, cada uno de los cuales está controlado por un método de recopilación diferente.  Al hacer clic en un objeto <xref:System.Windows.Controls.Button>, se activa una llamada a método en el archivo de código subyacente.  
  
 [!code-xml[ColumnDefinitionsGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml#1)]  
  
 En este ejemplo se define una serie de métodos personalizados, cada uno de los cuales se corresponde con un evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click> del archivo de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  Puede cambiar el número de filas y columnas de <xref:System.Windows.Controls.Grid> de varias maneras \(por ejemplo, agregando o quitando filas y columnas\) y puede contar el número total de filas y columnas.  Para evitar que se produzcan excepciones <xref:System.ArgumentOutOfRangeException> y <xref:System.ArgumentException>, puede usar la funcionalidad de comprobación de errores que proporciona el método <xref:System.Windows.Controls.ColumnDefinitionCollection.RemoveRange%2A>.  
  
 [!code-csharp[ColumnDefinitionsGrid#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ColumnDefinitionsGrid/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ColumnDefinitionsGrid#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ColumnDefinitionsGrid/VisualBasic/Window1.xaml.vb#2)]  
  
## Vea también  
 <xref:System.Windows.Controls.Grid>   
 <xref:System.Windows.Controls.ColumnDefinitionCollection>   
 <xref:System.Windows.Controls.RowDefinitionCollection>