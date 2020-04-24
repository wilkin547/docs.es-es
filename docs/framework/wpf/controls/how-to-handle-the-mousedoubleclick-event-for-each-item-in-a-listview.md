---
title: 'Cómo: Controlar el evento MouseDoubleClick para cada elemento de un control ListView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: 7bbc7bad36b3b1f2c92065e5f5699e5a86ac6189
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646107"
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a>Cómo: Controlar el evento MouseDoubleClick para cada elemento de un control ListView
Para controlar un evento para <xref:System.Windows.Controls.ListView>un elemento en un , <xref:System.Windows.Controls.ListViewItem>debe agregar un controlador de eventos a cada . Cuando <xref:System.Windows.Controls.ListView> a está enlazado a un origen de datos, no se crea explícitamente un <xref:System.Windows.Controls.ListViewItem> <xref:System.Windows.EventSetter> , pero se <xref:System.Windows.Controls.ListViewItem>puede controlar el evento para cada elemento agregando un estilo de un .  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente <xref:System.Windows.Controls.ListView> se crea <xref:System.Windows.Style> un enlazado a <xref:System.Windows.Controls.ListViewItem>datos y se crea un controlador para agregar un controlador de eventos a cada .  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 En el ejemplo <xref:System.Windows.Controls.Control.MouseDoubleClick> siguiente se controla el evento.  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
> Aunque es más común <xref:System.Windows.Controls.ListView> enlazar a a un origen de datos, puede <xref:System.Windows.Controls.ListViewItem> usar un estilo para <xref:System.Windows.Controls.ListView> agregar un controlador de <xref:System.Windows.Controls.ListViewItem>eventos a cada uno en un no enlazado a datos, independientemente de si crea explícitamente un archivo .  Para obtener más información acerca <xref:System.Windows.Controls.ListViewItem> de los <xref:System.Windows.Controls.ItemsControl>controles creados explícita e implícitamente, vea .  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Xml.XmlElement>
- [Descripción general del enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Enlazar a datos XML mediante consultas XMLDataProvider y XPath](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [Información general sobre ListView](listview-overview.md)
