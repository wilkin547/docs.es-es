---
title: 'Cómo: Filtrar datos en una vista'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- views [WPF], filtering data
- filtering data in views [WPF]
- data binding [WPF], filtering data in views
ms.assetid: c76e8606-4cc4-45a8-9110-e2ec66dc6afd
ms.openlocfilehash: ea49897ca5e9cb6b639cf7d98ff05bd287c51761
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73453482"
---
# <a name="how-to-filter-data-in-a-view"></a>Cómo: Filtrar datos en una vista
En este ejemplo se muestra cómo filtrar datos en una vista.  
  
## <a name="example"></a>Ejemplo  
 Para crear un filtro, defina un método que proporcione la lógica de filtrado. El método se utiliza como devolución de llamada y acepta un parámetro de tipo `object`. El método siguiente devuelve todos los objetos `Order` con la propiedad `filled` establecida en "no", filtrando el resto de los objetos.  
  
 [!code-csharp[SortFilter#2](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#2)]
 [!code-vb[SortFilter#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#2)]  
  
 Después, puede aplicar el filtro, tal y como se muestra en el ejemplo siguiente. En este ejemplo, `myCollectionView` es un objeto <xref:System.Windows.Data.ListCollectionView>.  
  
 [!code-csharp[SortFilter#Filter](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#filter)]
 [!code-vb[SortFilter#Filter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#filter)]  
  
 Para deshacer el filtrado, puede establecer la propiedad <xref:System.Windows.Data.CollectionView.Filter%2A> en `null`:  
  
 [!code-csharp[SortFilter#Unfilter](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#unfilter)]
 [!code-vb[SortFilter#Unfilter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#unfilter)]  
  
 Para obtener información sobre cómo crear u obtener una vista, vea [obtener la vista predeterminada de una recolección de datos](how-to-get-the-default-view-of-a-data-collection.md). Para obtener el ejemplo completo, vea [ordenar y filtrar elementos en un ejemplo de vista](https://go.microsoft.com/fwlink/?LinkID=160040).  
  
 Si el objeto de vista procede de un objeto <xref:System.Windows.Data.CollectionViewSource>, aplique la lógica de filtrado estableciendo un controlador de eventos para el evento <xref:System.Windows.Data.CollectionViewSource.Filter>. En el ejemplo siguiente, `listingDataView` es una instancia de <xref:System.Windows.Data.CollectionViewSource>.  
  
 [!code-csharp[DataBindingLab#10](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 A continuación se muestra la implementación del ejemplo de controlador de eventos `ShowOnlyBargainsFilter` Filter. Este controlador de eventos usa la propiedad <xref:System.Windows.Data.FilterEventArgs.Accepted%2A> para filtrar `AuctionItem` objetos que tienen un `CurrentPrice` de $25 o superior.  
  
 [!code-csharp[DataBindingLab#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Data.CollectionView.CanFilter%2A>
- <xref:System.Windows.Data.BindingListCollectionView.CustomFilter%2A>
- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Ordenar datos en una vista](how-to-sort-data-in-a-view.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
