---
title: 'Cómo: Implementar una CompositeCollection'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], CompositeCollection class
ms.assetid: 0d8fc84c-7920-427f-8ad7-d55ca656c170
ms.openlocfilehash: b3450cdc476b7090251a06b5b2b2718d29e18209
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454025"
---
# <a name="how-to-implement-a-compositecollection"></a>Cómo: Implementar una CompositeCollection
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo mostrar varias colecciones y elementos como una lista utilizando la clase <xref:System.Windows.Data.CompositeCollection>. En este ejemplo, `GreekGods` es una <xref:System.Collections.ObjectModel.ObservableCollection%601> de `GreekGod` objetos personalizados. Las plantillas de datos se definen para que `GreekGod` objetos y `GreekHero` objetos aparezcan con un color de primer plano dorado y aguamarina, respectivamente.  
  
 [!code-xaml[CompositeCollections#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Data.CollectionContainer>
- <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>
- <xref:System.Windows.Data.XmlDataProvider>
- <xref:System.Windows.DataTemplate>
- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
