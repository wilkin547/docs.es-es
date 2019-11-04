---
title: 'Cómo: Cambiar la alineación horizontal de una columna en un control ListView'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], horizontal alignment [WPF]
ms.assetid: b9573e44-9dad-4d14-939c-7859ca372758
ms.openlocfilehash: 5447f1a73b008b2ed4f345eba00f4d631e11e257
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458605"
---
# <a name="how-to-change-the-horizontal-alignment-of-a-column-in-a-listview"></a>Cómo: Cambiar la alineación horizontal de una columna en un control ListView
De forma predeterminada, el contenido de cada columna de un <xref:System.Windows.Controls.ListViewItem> se alinea a la izquierda. Puede cambiar la alineación de cada columna proporcionando un <xref:System.Windows.DataTemplate> y estableciendo la propiedad <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> en el elemento dentro de la <xref:System.Windows.DataTemplate>. En este tema se muestra cómo un <xref:System.Windows.Controls.ListView> alinea su contenido de forma predeterminada y cómo cambiar la alineación de una columna en un <xref:System.Windows.Controls.ListView>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, los datos de las columnas `Title` y `ISBN` están alineados a la izquierda.  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 Para cambiar la alineación de la columna `ISBN`, debe especificar que la propiedad <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> de cada <xref:System.Windows.Controls.ListViewItem> sea <xref:System.Windows.HorizontalAlignment.Stretch>, de modo que los elementos de cada <xref:System.Windows.Controls.ListViewItem> puedan abarcar o colocarse a lo largo de todo el ancho de cada columna. Dado que el <xref:System.Windows.Controls.ListView> se enlaza a un origen de datos, debe crear un estilo que establezca el <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>. A continuación, debe usar un <xref:System.Windows.DataTemplate> para mostrar el contenido en lugar de utilizar la propiedad <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>. Para mostrar el `ISBN` de cada plantilla, el <xref:System.Windows.DataTemplate> solo puede contener un <xref:System.Windows.Controls.TextBlock> que tenga su propiedad <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> establecida en <xref:System.Windows.HorizontalAlignment.Right>.  
  
 En el ejemplo siguiente se define el estilo y <xref:System.Windows.DataTemplate> necesarios para hacer que la columna de `ISBN` se alinee a la derecha y se cambia la <xref:System.Windows.Controls.GridViewColumn> para hacer referencia a la <xref:System.Windows.DataTemplate>.  
  
 [!code-xaml[ListViewHowTos#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#3)]  
[!code-xaml[ListViewHowTos#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#4)]  
  
## <a name="see-also"></a>Vea también

- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Información general sobre plantillas de datos](../data/data-templating-overview.md)
- [Enlazar a datos XML mediante XMLDataProvider y consultas XPath](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [Información general sobre ListView](listview-overview.md)
