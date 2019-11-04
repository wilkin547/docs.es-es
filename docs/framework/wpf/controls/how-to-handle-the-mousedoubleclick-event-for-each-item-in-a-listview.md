---
title: 'Cómo: Controlar el evento MouseDoubleClick para cada elemento de un control ListView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: 25308ee87fb387787e20c8a8887ae8e4e60742b9
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460229"
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a>Cómo: Controlar el evento MouseDoubleClick para cada elemento de un control ListView
Para controlar un evento para un elemento de un <xref:System.Windows.Controls.ListView>, debe agregar un controlador de eventos a cada <xref:System.Windows.Controls.ListViewItem>. Cuando un <xref:System.Windows.Controls.ListView> se enlaza a un origen de datos, no se crea explícitamente un <xref:System.Windows.Controls.ListViewItem>, pero se puede controlar el evento para cada elemento agregando un <xref:System.Windows.EventSetter> a un estilo de un <xref:System.Windows.Controls.ListViewItem>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un <xref:System.Windows.Controls.ListView> enlazado a datos y se crea un <xref:System.Windows.Style> para agregar un controlador de eventos a cada <xref:System.Windows.Controls.ListViewItem>.  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 En el ejemplo siguiente se controla el evento <xref:System.Windows.Controls.Control.MouseDoubleClick>.  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
> Aunque es más común enlazar un <xref:System.Windows.Controls.ListView> a un origen de datos, puede usar un estilo para agregar un controlador de eventos a cada <xref:System.Windows.Controls.ListViewItem> en un <xref:System.Windows.Controls.ListView> no enlazado a datos, independientemente de si crea explícitamente una <xref:System.Windows.Controls.ListViewItem>.  Para obtener más información sobre los controles de <xref:System.Windows.Controls.ListViewItem> creados de forma explícita y implícita, vea <xref:System.Windows.Controls.ItemsControl>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.XmlElement>
- [Información general sobre el enlace de datos](../data/data-binding-overview.md)
- [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Enlazar a datos XML mediante XMLDataProvider y consultas XPath](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [Información general sobre ListView](listview-overview.md)
