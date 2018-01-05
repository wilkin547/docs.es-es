---
title: "Cómo: Aplicar un estilo a una fila en un control ListView que implementa una clase GridView"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1e37d70fe1cb6aefb1404424c1a8f5339e0badf7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a>Cómo: Aplicar un estilo a una fila en un control ListView que implementa una clase GridView
Este ejemplo muestra cómo aplicar estilo a una fila en un <xref:System.Windows.Controls.ListView> control que implementa un <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.ListView.View%2A> modo.  
  
## <a name="example"></a>Ejemplo  
 Puedes aplicar estilo a una fila en un <xref:System.Windows.Controls.ListView> control estableciendo un <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> en el <xref:System.Windows.Controls.ListView> control. Establecer el estilo de sus elementos que se representan como <xref:System.Windows.Controls.ListViewItem> objetos. El <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> referencias el <xref:System.Windows.Controls.ControlTemplate> objetos que se usan para mostrar el contenido de la fila.  
  
 En el ejemplo completo, del cual se extraen los siguientes, se muestra una colección de información de la canción que se almacena en una base de datos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]. Cada canción de la base de datos tiene un campo de clasificación y el valor de este campo especifica cómo mostrar una fila de información de la canción.  
  
 En el ejemplo siguiente se muestra cómo definir <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> para el <xref:System.Windows.Controls.ListViewItem> objetos que representan las canciones de la colección de canciones. El <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> referencias <xref:System.Windows.Controls.ControlTemplate> objetos que especifican cómo mostrar una fila de información de la canción.  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 El ejemplo siguiente muestra un <xref:System.Windows.Controls.ControlTemplate> que agrega la cadena de texto `"Strongly Recommended"` a la fila. Esta plantilla se hace referencia en la <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> y se muestra cuando la calificación de la canción tiene un valor de 5 (5). El <xref:System.Windows.Controls.ControlTemplate> incluye un <xref:System.Windows.Controls.GridViewRowPresenter> objeto que distribuye el contenido de la fila en las columnas tal como se define por la <xref:System.Windows.Controls.GridView> el modo de vista.  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 En el ejemplo siguiente se define <xref:System.Windows.Controls.GridView>.  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [Información general sobre ListView](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)
