---
title: "C&#243;mo: Controlar el evento MouseDoubleClick para cada elemento de un control ListView | Microsoft Docs"
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
  - "ListView (controles), MouseDoubleClick (evento)"
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# C&#243;mo: Controlar el evento MouseDoubleClick para cada elemento de un control ListView
Para administrar un evento de un elemento en un control <xref:System.Windows.Controls.ListView>, se debe agregar un controlador de eventos a cada <xref:System.Windows.Controls.ListViewItem>.  Cuando <xref:System.Windows.Controls.ListView> se enlaza a un origen de datos, no se crea explícitamente un elemento <xref:System.Windows.Controls.ListViewItem>, pero el evento de cada elemento se puede controlar agregando <xref:System.Windows.EventSetter> a un estilo de <xref:System.Windows.Controls.ListViewItem>.  
  
## Ejemplo  
 En el ejemplo siguiente se crea un control <xref:System.Windows.Controls.ListView> enlazado a datos y también se crea un objeto <xref:System.Windows.Style> para agregar un controlador de eventos a cada <xref:System.Windows.Controls.ListViewItem>.  
  
 [!code-xml[ListViewHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xml[ListViewHowTos#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xml[ListViewHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 En el siguiente ejemplo se controla el evento <xref:System.Windows.Controls.Control.MouseDoubleClick>.  
  
 [!code-csharp[ListViewHowTos#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
>  Aunque lo más común es enlazar un control <xref:System.Windows.Controls.ListView> a un origen de datos, puede utilizar un estilo para agregar un controlador de eventos a cada <xref:System.Windows.Controls.ListViewItem> de un control <xref:System.Windows.Controls.ListView> no enlazado a datos, tanto si crea el control <xref:System.Windows.Controls.ListViewItem> de manera explícita como si no.  Para obtener más información acerca de controles <xref:System.Windows.Controls.ListViewItem> creados de manera explícita e implícita, vea <xref:System.Windows.Controls.ItemsControl>.  
  
## Vea también  
 <xref:System.Xml.XmlElement>   
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Enlazar a datos XML mediante XMLDataProvider y consultas XPath](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)   
 [Información general sobre ListView](../../../../docs/framework/wpf/controls/listview-overview.md)