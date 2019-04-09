---
title: Filtrar Ordenar y agrupar datos mediante una vista en XAML
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
ms.openlocfilehash: ca4439b574264ebebfda745f0765f750099bc95f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144526"
---
# <a name="how-to-sort-and-group-data-using-a-view-in-xaml"></a>Filtrar Ordenar y agrupar datos mediante una vista en XAML
En este ejemplo se muestra cómo crear una vista de una recolección de datos en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Las vistas permiten para las funcionalidades de agrupación, ordenación, filtrado y la noción de elemento actual.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, el recurso estático denominado *coloca* se define como una colección de *lugar* objetos, donde cada *lugar* objeto está formado por un nombre de ciudad y el estado. El prefijo *src* se asigna al espacio de nombres donde el origen de datos *lugares* está definido. El prefijo *scm* se asigna a `"clr-namespace:System.ComponentModel;assembly=WindowsBase"` y *dat* se asigna a `"clr-namespace:System.Windows.Data;assembly=PresentationFramework"`.  
  
 El ejemplo siguiente crea una vista de la recopilación de datos que se ordenan por el nombre de ciudad y agrupada por el estado.  
  
 [!code-xaml[CollectionViewSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#1)]  
  
 La vista, a continuación, puede ser un origen de enlace, como en el ejemplo siguiente:  
  
 [!code-xaml[CollectionViewSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#2)]  
  
 Para los enlaces a datos XML definidos en un <xref:System.Windows.Data.XmlDataProvider> recursos, delante del nombre de XML con un símbolo @.  
  
 [!code-xaml[CollectionViewSource#XDPChunk](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#xdpchunk)]  
  
 [!code-xaml[CollectionViewSource#Attribute](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionViewSource/CS/window1.xaml#attribute)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Data.CollectionViewSource>
- [Obtener la vista predeterminada de una colección de datos](how-to-get-the-default-view-of-a-data-collection.md)
- [Información general sobre el enlace de datos](data-binding-overview.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
