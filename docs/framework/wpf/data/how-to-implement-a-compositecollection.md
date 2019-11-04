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
# <a name="how-to-implement-a-compositecollection"></a><span data-ttu-id="5f1e9-102">Cómo: Implementar una CompositeCollection</span><span class="sxs-lookup"><span data-stu-id="5f1e9-102">How to: Implement a CompositeCollection</span></span>
## <a name="example"></a><span data-ttu-id="5f1e9-103">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5f1e9-103">Example</span></span>  
 <span data-ttu-id="5f1e9-104">En el ejemplo siguiente se muestra cómo mostrar varias colecciones y elementos como una lista utilizando la clase <xref:System.Windows.Data.CompositeCollection>.</span><span class="sxs-lookup"><span data-stu-id="5f1e9-104">The following example shows how to display multiple collections and items as one list using the <xref:System.Windows.Data.CompositeCollection> class.</span></span> <span data-ttu-id="5f1e9-105">En este ejemplo, `GreekGods` es una <xref:System.Collections.ObjectModel.ObservableCollection%601> de `GreekGod` objetos personalizados.</span><span class="sxs-lookup"><span data-stu-id="5f1e9-105">In this example, `GreekGods` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `GreekGod` custom objects.</span></span> <span data-ttu-id="5f1e9-106">Las plantillas de datos se definen para que `GreekGod` objetos y `GreekHero` objetos aparezcan con un color de primer plano dorado y aguamarina, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="5f1e9-106">Data templates are defined so that `GreekGod` objects and `GreekHero` objects appear with a gold and a cyan foreground color respectively.</span></span>  
  
 [!code-xaml[CompositeCollections#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="5f1e9-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f1e9-107">See also</span></span>

- <xref:System.Windows.Data.CollectionContainer>
- <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>
- <xref:System.Windows.Data.XmlDataProvider>
- <xref:System.Windows.DataTemplate>
- [<span data-ttu-id="5f1e9-108">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="5f1e9-108">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="5f1e9-109">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="5f1e9-109">How-to Topics</span></span>](data-binding-how-to-topics.md)
