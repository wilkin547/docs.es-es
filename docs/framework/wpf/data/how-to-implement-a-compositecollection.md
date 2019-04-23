---
title: Procedimiento Implementar una CompositeCollection
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], CompositeCollection class
ms.assetid: 0d8fc84c-7920-427f-8ad7-d55ca656c170
ms.openlocfilehash: 8361c2bfa9c125aeadf0a62ca86af1855e5c3dbc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59091171"
---
# <a name="how-to-implement-a-compositecollection"></a><span data-ttu-id="629d0-102">Procedimiento Implementar una CompositeCollection</span><span class="sxs-lookup"><span data-stu-id="629d0-102">How to: Implement a CompositeCollection</span></span>
## <a name="example"></a><span data-ttu-id="629d0-103">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="629d0-103">Example</span></span>  
 <span data-ttu-id="629d0-104">El ejemplo siguiente muestra cómo mostrar varias colecciones y elementos como una lista con los <xref:System.Windows.Data.CompositeCollection> clase.</span><span class="sxs-lookup"><span data-stu-id="629d0-104">The following example shows how to display multiple collections and items as one list using the <xref:System.Windows.Data.CompositeCollection> class.</span></span> <span data-ttu-id="629d0-105">En este ejemplo, `GreekGods` es un <xref:System.Collections.ObjectModel.ObservableCollection%601> de `GreekGod` objetos personalizados.</span><span class="sxs-lookup"><span data-stu-id="629d0-105">In this example, `GreekGods` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `GreekGod` custom objects.</span></span> <span data-ttu-id="629d0-106">Las plantillas de datos se definen para que `GreekGod` objetos y `GreekHero` objetos aparecen con un gold y un color de primer plano cian, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="629d0-106">Data templates are defined so that `GreekGod` objects and `GreekHero` objects appear with a gold and a cyan foreground color respectively.</span></span>  
  
 [!code-xaml[CompositeCollections#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="629d0-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="629d0-107">See also</span></span>

- <xref:System.Windows.Data.CollectionContainer>
- <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>
- <xref:System.Windows.Data.XmlDataProvider>
- <xref:System.Windows.DataTemplate>
- [<span data-ttu-id="629d0-108">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="629d0-108">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="629d0-109">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="629d0-109">How-to Topics</span></span>](data-binding-how-to-topics.md)
