---
title: "C&#243;mo: Aplicar un estilo a una fila en un control ListView que implementa una clase GridView | Microsoft Docs"
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
  - "Controles GridView, aplicar estilos a filas"
  - "aplicar estilos a filas de ListView mediante la implementación de GridView"
  - "ListView (controles), aplicar estilos a las filas con GridView"
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Aplicar un estilo a una fila en un control ListView que implementa una clase GridView
Este ejemplo muestra cómo aplicar estilo a una fila en un <xref:System.Windows.Controls.ListView> control que implementa un <xref:System.Windows.Controls.GridView><xref:System.Windows.Controls.ListView.View%2A> modo.  
  
## <a name="example"></a>Ejemplo  
 Puede aplicar el estilo de una fila en un <xref:System.Windows.Controls.ListView> control estableciendo un <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> en el <xref:System.Windows.Controls.ListView> control. Establecer el estilo de sus elementos que se representan como <xref:System.Windows.Controls.ListViewItem> objetos. El <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> referencias la <xref:System.Windows.Controls.ControlTemplate> objetos que se utilizan para mostrar el contenido de la fila.  
  
 El ejemplo completo, que se extraen los ejemplos siguientes, muestra una colección de información de la canción que se almacena en un [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] base de datos. Cada canción de la base de datos tiene un campo de clasificación y el valor de este campo especifica cómo mostrar una fila de información de la canción.  
  
 En el ejemplo siguiente se muestra cómo definir <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> para el <xref:System.Windows.Controls.ListViewItem> objetos que representan las canciones de la colección de canciones. El <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> referencias <xref:System.Windows.Controls.ControlTemplate> objetos que especifican cómo mostrar una fila de información de la canción.  
  
 [!code-xml[ListViewItemStyleSnippet#ItemContainerStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 El ejemplo siguiente muestra un <xref:System.Windows.Controls.ControlTemplate> que agrega la cadena de texto `"Strongly Recommended"` a la fila. Esta plantilla se hace referencia en el <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> y se muestra cuando la calificación de la canción tiene un valor de 5 (5). El <xref:System.Windows.Controls.ControlTemplate> incluye un <xref:System.Windows.Controls.GridViewRowPresenter> objeto que distribuye el contenido de la fila en las columnas de acuerdo con la <xref:System.Windows.Controls.GridView> modo de vista.  
  
 [!code-xml[ListViewItemStyleSnippet#ControlTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 En el ejemplo siguiente se define <xref:System.Windows.Controls.GridView>.  
  
 [!code-xml[ListViewItemStyleSnippet#GridView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.ListView>   
 <xref:System.Windows.Controls.GridView>   
 [Temas de procedimientos](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)   
 [Información general sobre ListView](../../../../docs/framework/wpf/controls/listview-overview.md)   
 [Estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)