---
title: "C&#243;mo: Crear un modo de vista personalizado para un control ListView | Microsoft Docs"
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
  - "ListView (controles), crear un modo de vista personalizado"
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Crear un modo de vista personalizado para un control ListView
En este ejemplo se muestra cómo crear un modo de <xref:System.Windows.Controls.ListView.View%2A> personalizado para un control <xref:System.Windows.Controls.ListView>.  
  
## Ejemplo  
 Debe utilizar la clase <xref:System.Windows.Controls.ViewBase> al crear una vista personalizada para el control <xref:System.Windows.Controls.ListView>.  En el ejemplo siguiente se muestra un modo de vista que se denomina `PlainView`, derivado de la clase <xref:System.Windows.Controls.ViewBase>.  
  
 [!code-csharp[ListViewCustomView#PlainView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 Para aplicar un estilo a la vista personalizada, utilice la clase <xref:System.Windows.Style>.  En el ejemplo siguiente se define un estilo \(<xref:System.Windows.Style>\) para el modo de vista `PlainView`.  En el ejemplo anterior, este estilo se establece como el valor de la propiedad <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> que se define para `PlainView`.  
  
 [!code-xml[ListViewCustomView#PlainViewStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 Para definir el diseño de los datos en un modo de vista personalizado, defina un objeto <xref:System.Windows.DataTemplate>.  En el ejemplo siguiente se define un objeto <xref:System.Windows.DataTemplate> que se puede utilizar para mostrar datos en el modo de vista `PlainView`.  
  
 [!code-xml[ListViewCustomView#PlainViewDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 En el ejemplo siguiente se muestra cómo definir una clave de recurso \(<xref:System.Windows.ResourceKey>\) para el modo de vista `PlainView` que utiliza el objeto <xref:System.Windows.DataTemplate> definido en el ejemplo anterior.  
  
 [!code-xml[ListViewCustomView#PlainViewtileView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 Un control <xref:System.Windows.Controls.ListView> puede utilizar una vista personalizada si se establece la propiedad <xref:System.Windows.Controls.ListView.View%2A> en la clave de recurso.  En el ejemplo siguiente se muestra cómo especificar `PlainView` como el modo de vista para <xref:System.Windows.Controls.ListView>.  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 Para obtener el ejemplo completo, vea [ListView with Multiple Views Sample](http://go.microsoft.com/fwlink/?LinkID=160013).  
  
## Vea también  
 <xref:System.Windows.Controls.ListView>   
 <xref:System.Windows.Controls.GridView>   
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)   
 [Información general sobre ListView](../../../../docs/framework/wpf/controls/listview-overview.md)   
 [Información general sobre GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)