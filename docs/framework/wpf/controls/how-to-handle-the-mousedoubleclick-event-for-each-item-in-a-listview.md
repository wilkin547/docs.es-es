---
title: Procedimiento Controlar el evento MouseDoubleClick para cada elemento de un control ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: 2a201eefba6e2623cfd7f733b85e271ce1c4e177
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54576062"
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a>Procedimiento Controlar el evento MouseDoubleClick para cada elemento de un control ListView
Para controlar un evento para un elemento en un <xref:System.Windows.Controls.ListView>, deberá agregar un controlador de eventos a cada <xref:System.Windows.Controls.ListViewItem>. Cuando un <xref:System.Windows.Controls.ListView> está enlazado a un origen de datos, no cree explícitamente un <xref:System.Windows.Controls.ListViewItem>, pero se puede controlar el evento para cada elemento mediante la adición de un <xref:System.Windows.EventSetter> a un estilo de un <xref:System.Windows.Controls.ListViewItem>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un enlace de datos <xref:System.Windows.Controls.ListView> y crea un <xref:System.Windows.Style> para agregar un controlador de eventos a cada <xref:System.Windows.Controls.ListViewItem>.  
  
 [!code-xaml[ListViewHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 El ejemplo siguiente se controla el <xref:System.Windows.Controls.Control.MouseDoubleClick> eventos.  
  
 [!code-csharp[ListViewHowTos#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
>  Aunque es más común para enlazar un <xref:System.Windows.Controls.ListView> a un origen de datos, puede utilizar un estilo para agregar un controlador de eventos a cada <xref:System.Windows.Controls.ListViewItem> en una no enlazado a datos <xref:System.Windows.Controls.ListView> independientemente de si crea explícitamente una <xref:System.Windows.Controls.ListViewItem>.  Para obtener más información acerca de forma explícita e implícitamente creado <xref:System.Windows.Controls.ListViewItem> los controles, vea <xref:System.Windows.Controls.ItemsControl>.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Xml.XmlElement>
- [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)
- [Enlazar a datos XML mediante XMLDataProvider y consultas XPath](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [Información general sobre ListView](../../../../docs/framework/wpf/controls/listview-overview.md)
