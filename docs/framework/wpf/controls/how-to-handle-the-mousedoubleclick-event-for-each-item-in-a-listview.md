---
title: Procedimiento Controlar el evento MouseDoubleClick para cada elemento de un control ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: 7e51c810a2e1e4bf4157aa1311255c5547021b60
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962061"
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a>Procedimiento Controlar el evento MouseDoubleClick para cada elemento de un control ListView
Para controlar un evento para un elemento de un <xref:System.Windows.Controls.ListView>, debe agregar un controlador de eventos a cada. <xref:System.Windows.Controls.ListViewItem> Cuando un <xref:System.Windows.Controls.ListView> se enlaza a un origen de datos, no se crea explícitamente un <xref:System.Windows.Controls.ListViewItem>, pero se puede controlar el evento para <xref:System.Windows.EventSetter> cada elemento agregando a un estilo de <xref:System.Windows.Controls.ListViewItem>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un enlazado <xref:System.Windows.Controls.ListView> a datos y se crea un <xref:System.Windows.Style> para agregar un <xref:System.Windows.Controls.ListViewItem>controlador de eventos a cada.  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 En el ejemplo siguiente se <xref:System.Windows.Controls.Control.MouseDoubleClick> controla el evento.  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
> Aunque <xref:System.Windows.Controls.ListView> es más común enlazar un a un origen de datos, puede usar un estilo para agregar un controlador de eventos a cada uno de ellos <xref:System.Windows.Controls.ListViewItem> en un no enlazado <xref:System.Windows.Controls.ListView> a datos, independientemente de si <xref:System.Windows.Controls.ListViewItem>crea explícitamente una.  Para obtener más información acerca de los controles creados <xref:System.Windows.Controls.ListViewItem> explícitamente y <xref:System.Windows.Controls.ItemsControl>de forma implícita, vea.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.XmlElement>
- [Información general sobre el enlace de datos](../data/data-binding-overview.md)
- [Aplicar estilos y plantillas](styling-and-templating.md)
- [Enlazar a datos XML mediante XMLDataProvider y consultas XPath](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [Información general sobre ListView](listview-overview.md)
