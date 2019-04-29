---
title: Procedimiento Filtrar datos en una vista
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- views [WPF], filtering data
- filtering data in views [WPF]
- data binding [WPF], filtering data in views
ms.assetid: c76e8606-4cc4-45a8-9110-e2ec66dc6afd
ms.openlocfilehash: a31c07e6be26f67cc29813a14745ecf4a83ab98a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61931534"
---
# <a name="how-to-filter-data-in-a-view"></a>Procedimiento Filtrar datos en una vista
En este ejemplo se muestra cómo filtrar datos en una vista.  
  
## <a name="example"></a>Ejemplo  
 Para crear un filtro, defina un método que proporciona la lógica de filtrado. El método se utiliza como una devolución de llamada y acepta un parámetro de tipo `object`. El método siguiente devuelve todos los `Order` los objetos que tienen el `filled` propiedad establecida en "No", filtrando el resto de los objetos.  
  
 [!code-csharp[SortFilter#2](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#2)]
 [!code-vb[SortFilter#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#2)]  
  
 A continuación, puede aplicar el filtro, como se muestra en el ejemplo siguiente. En este ejemplo, `myCollectionView` es un <xref:System.Windows.Data.ListCollectionView> objeto.  
  
 [!code-csharp[SortFilter#Filter](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#filter)]
 [!code-vb[SortFilter#Filter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#filter)]  
  
 Para deshacer el filtrado, puede establecer el <xref:System.Windows.Data.CollectionView.Filter%2A> propiedad `null`:  
  
 [!code-csharp[SortFilter#Unfilter](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#unfilter)]
 [!code-vb[SortFilter#Unfilter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#unfilter)]  
  
 Para obtener información acerca de cómo crear u obtener una vista, consulte [obtener la vista predeterminada de una colección de datos](how-to-get-the-default-view-of-a-data-collection.md). Para obtener un ejemplo completo, vea [ordenar y filtrar elementos en un ejemplo de vista](https://go.microsoft.com/fwlink/?LinkID=160040).  
  
 Si el objeto de vista procede de un <xref:System.Windows.Data.CollectionViewSource> objeto, aplicar lógica de filtrado mediante el establecimiento de un controlador de eventos para el <xref:System.Windows.Data.CollectionViewSource.Filter> eventos. En el ejemplo siguiente, `listingDataView` es una instancia de <xref:System.Windows.Data.CollectionViewSource>.  
  
 [!code-csharp[DataBindingLab#10](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 La siguiente muestra la implementación del ejemplo `ShowOnlyBargainsFilter` controlador de eventos de filtro. Este controlador de eventos usa el <xref:System.Windows.Data.FilterEventArgs.Accepted%2A> propiedad para filtrar `AuctionItem` objetos que tienen un `CurrentPrice` de $25 o mayor.  
  
 [!code-csharp[DataBindingLab#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Data.CollectionView.CanFilter%2A>
- <xref:System.Windows.Data.BindingListCollectionView.CustomFilter%2A>
- [Información general sobre el enlace de datos](data-binding-overview.md)
- [Ordenar datos en una vista](how-to-sort-data-in-a-view.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
