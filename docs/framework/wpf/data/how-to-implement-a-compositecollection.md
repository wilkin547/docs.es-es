---
title: "Cómo: Implementar una CompositeCollection"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], CompositeCollection class
ms.assetid: 0d8fc84c-7920-427f-8ad7-d55ca656c170
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b33e3a61b91c2f9e2362a270216038d61770b815
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-a-compositecollection"></a><span data-ttu-id="1f888-102">Cómo: Implementar una CompositeCollection</span><span class="sxs-lookup"><span data-stu-id="1f888-102">How to: Implement a CompositeCollection</span></span>
## <a name="example"></a><span data-ttu-id="1f888-103">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1f888-103">Example</span></span>  
 <span data-ttu-id="1f888-104">En el ejemplo siguiente se muestra cómo mostrar varias colecciones y elementos como una lista con los <xref:System.Windows.Data.CompositeCollection> clase.</span><span class="sxs-lookup"><span data-stu-id="1f888-104">The following example shows how to display multiple collections and items as one list using the <xref:System.Windows.Data.CompositeCollection> class.</span></span> <span data-ttu-id="1f888-105">En este ejemplo, `GreekGods` es un <xref:System.Collections.ObjectModel.ObservableCollection%601> de `GreekGod` objetos personalizados.</span><span class="sxs-lookup"><span data-stu-id="1f888-105">In this example, `GreekGods` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `GreekGod` custom objects.</span></span> <span data-ttu-id="1f888-106">Se definen plantillas de datos para que `GreekGod` objetos y `GreekHero` objetos aparecen con un gold y un color de primer plano cian respectivamente.</span><span class="sxs-lookup"><span data-stu-id="1f888-106">Data templates are defined so that `GreekGod` objects and `GreekHero` objects appear with a gold and a cyan foreground color respectively.</span></span>  
  
 [!code-xaml[CompositeCollections#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="1f888-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f888-107">See Also</span></span>  
 <xref:System.Windows.Data.CollectionContainer>  
 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>  
 <xref:System.Windows.Data.XmlDataProvider>  
 <xref:System.Windows.DataTemplate>  
 [<span data-ttu-id="1f888-108">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="1f888-108">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="1f888-109">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="1f888-109">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
