---
title: Procedimiento Cambiar la alineación horizontal de una columna en un control ListView
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], horizontal alignment [WPF]
ms.assetid: b9573e44-9dad-4d14-939c-7859ca372758
ms.openlocfilehash: 07d5fd0830f98032e76b963cb32b35fd18b50475
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54605233"
---
# <a name="how-to-change-the-horizontal-alignment-of-a-column-in-a-listview"></a>Procedimiento Cambiar la alineación horizontal de una columna en un control ListView
De forma predeterminada, el contenido de cada columna en un <xref:System.Windows.Controls.ListViewItem> está alineado a izquierda. Puede cambiar la alineación de cada columna especificando un <xref:System.Windows.DataTemplate> y estableciendo el <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> propiedad del elemento dentro de la <xref:System.Windows.DataTemplate>. Este tema se muestra cómo un <xref:System.Windows.Controls.ListView> alinea su contenido de forma predeterminada y cómo cambiar la alineación de una columna en un <xref:System.Windows.Controls.ListView>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, los datos en el `Title` y `ISBN` columnas está alineado a izquierda.  
  
 [!code-xaml[ListViewHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 Para cambiar la alineación de la `ISBN` columna, deberá especificar que la <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> propiedad de cada uno <xref:System.Windows.Controls.ListViewItem> es <xref:System.Windows.HorizontalAlignment.Stretch>, de modo que los elementos de cada <xref:System.Windows.Controls.ListViewItem> pueden abarcar o colocarse a lo largo de todo el ancho de cada columna. Dado que el <xref:System.Windows.Controls.ListView> está enlazado a un origen de datos, deberá crear un estilo que establece el <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>. A continuación, deberá usar un <xref:System.Windows.DataTemplate> para mostrar el contenido en lugar de usar el <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> propiedad. Para mostrar el `ISBN` de cada plantilla, el <xref:System.Windows.DataTemplate> solo puede contener un <xref:System.Windows.Controls.TextBlock> que tiene su <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> propiedad establecida en <xref:System.Windows.HorizontalAlignment.Right>.  
  
 En el ejemplo siguiente se define el estilo y <xref:System.Windows.DataTemplate> necesaria para realizar la `ISBN` columna alineada a la derecha y los cambios el <xref:System.Windows.Controls.GridViewColumn> para hacer referencia a la <xref:System.Windows.DataTemplate>.  
  
 [!code-xaml[ListViewHowTos#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#3)]  
[!code-xaml[ListViewHowTos#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#4)]  
  
## <a name="see-also"></a>Vea también
- [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [Información general sobre plantillas de datos](../../../../docs/framework/wpf/data/data-templating-overview.md)
- [Enlazar a datos XML mediante XMLDataProvider y consultas XPath](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [Información general sobre ListView](../../../../docs/framework/wpf/controls/listview-overview.md)
