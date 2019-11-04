---
title: 'Cómo: Ordenar y agrupar datos mediante una vista en XAML'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], grouping data in views in XAML
- XAML [WPF], sorting data in views
- grouping data in views in XAML [WPF]
- data binding [WPF], sorting data in views in XAML
- sorting data in views in XAML [WPF]
- XAML [WPF], grouping data in views
- views [WPF], sorting data
- views [WPF], grouping data
ms.assetid: 145c8c3f-dbdd-4d0d-816f-90b35eba7eda
ms.openlocfilehash: 9e42dd330535f71438ab7af3dca9d078e9dfd8d3
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460124"
---
# <a name="how-to-sort-and-group-data-using-a-view-in-xaml"></a>Cómo: Ordenar y agrupar datos mediante una vista en XAML
En este ejemplo se muestra cómo crear una vista de una colección de datos en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Las vistas permiten la funcionalidad de agrupación, ordenación, filtrado y noción de un elemento actual.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, el recurso estático denominado *lugares* se define como una colección de objetos *Place* , en la que *cada uno de* los objetos se compone de un nombre de ciudad y el estado. El prefijo *src* se asigna al espacio de nombres donde se definen los *lugares* de origen de datos. El prefijo *SCM* se asigna a `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` y a las asignaciones de *DAT* a `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.  
  
 En el ejemplo siguiente se crea una vista de la recopilación de datos que se ordena por el nombre de la ciudad y se agrupa por el estado.  
  
 [!code-xaml[CollectionViewSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 A continuación, la vista puede ser un origen de enlace, como en el ejemplo siguiente:  
  
 [!code-xaml[CollectionViewSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 Para los enlaces a los datos XML definidos en un recurso de <xref:System.Windows.Data.XmlDataProvider>, anteponga un símbolo @ al nombre XML.  
  
 [!code-xaml[CollectionViewSource#XDPChunk](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xaml[CollectionViewSource#Attribute](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Data.CollectionViewSource>
- [Obtener la vista predeterminada de una colección de datos](how-to-get-the-default-view-of-a-data-collection.md)
- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
