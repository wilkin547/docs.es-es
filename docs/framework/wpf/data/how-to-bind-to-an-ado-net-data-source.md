---
title: "C&#243;mo: Enlazar a un origen de datos ADO.NET | Microsoft Docs"
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
  - "orígenes de datos de ADO.NET, enlazar"
  - "enlace, a orígenes de datos de ADO.NET"
  - "enlace de datos, enlazar a orígenes de datos de ADO.NET"
ms.assetid: a70c6d7b-7b38-4fdf-b655-4804db7c8315
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Enlazar a un origen de datos ADO.NET
En este ejemplo se muestra cómo enlazar un control <xref:System.Windows.Controls.ListBox> de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] a un `DataSet` de [!INCLUDE[TLA#tla_adonet](../../../../includes/tlasharptla-adonet-md.md)].  
  
## Ejemplo  
 En este ejemplo, se utiliza un objeto `OleDbConnection` para conectar al origen de datos, que es un archivo `Access MDB` especificado en la cadena de conexión.  Una vez establecida la conexión, se crea un objeto `OleDbDataAdpater`.  El objeto `OleDbDataAdpater` ejecuta una instrucción select de [!INCLUDE[TLA#tla_sql](../../../../includes/tlasharptla-sql-md.md)] para recuperar el conjunto de registros de la base de datos.  Los resultados del comando de [!INCLUDE[TLA2#tla_sql](../../../../includes/tla2sharptla-sql-md.md)] se almacenan en una `DataTable` de `DataSet` llamando al método `Fill` de `OleDbDataAdapter`.  El elemento `DataTable` de este ejemplo se denomina `BookTable`.  A continuación, en el ejemplo se establece la propiedad <xref:System.Windows.FrameworkElement.DataContext%2A> de <xref:System.Windows.Controls.ListBox> en el objeto `DataSet`.  
  
 [!code-csharp[ADODataSet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 Después, se puede enlazar la propiedad <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> de <xref:System.Windows.Controls.ListBox> al elemento `BookTable` de `DataSet`:  
  
 [!code-xml[ADODataSet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#2)]  
  
 `BookItemTemplate` es el objeto <xref:System.Windows.DataTemplate> que define cómo aparecen los datos:  
  
 [!code-xml[ADODataSet#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#3)]  
  
 `IntColorConverter` convierte un valor `int` en un color.  Al utilizar este convertidor, el color de la propiedad <xref:System.Windows.Controls.TextBlock.Background%2A> del tercer objeto <xref:System.Windows.Controls.TextBlock> aparece verde si el valor de `NumPages` es inferior a 350 y rojo si no es así.  La implementación del convertidor no se muestra aquí.  
  
## Vea también  
 <xref:System.Windows.Data.BindingListCollectionView>   
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)