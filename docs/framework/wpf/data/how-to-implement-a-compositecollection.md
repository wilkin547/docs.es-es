---
title: "Cómo: Implementar una CompositeCollection"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: data binding [WPF], CompositeCollection class
ms.assetid: 0d8fc84c-7920-427f-8ad7-d55ca656c170
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d7d9610c6c507ebdebdb5690dcb7aec19599ee80
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-a-compositecollection"></a><span data-ttu-id="d67c1-102">Cómo: Implementar una CompositeCollection</span><span class="sxs-lookup"><span data-stu-id="d67c1-102">How to: Implement a CompositeCollection</span></span>
## <a name="example"></a><span data-ttu-id="d67c1-103">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d67c1-103">Example</span></span>  
 <span data-ttu-id="d67c1-104">En el ejemplo siguiente se muestra cómo mostrar varias colecciones y elementos como una lista con los <xref:System.Windows.Data.CompositeCollection> clase.</span><span class="sxs-lookup"><span data-stu-id="d67c1-104">The following example shows how to display multiple collections and items as one list using the <xref:System.Windows.Data.CompositeCollection> class.</span></span> <span data-ttu-id="d67c1-105">En este ejemplo, `GreekGods` es un <xref:System.Collections.ObjectModel.ObservableCollection%601> de `GreekGod` objetos personalizados.</span><span class="sxs-lookup"><span data-stu-id="d67c1-105">In this example, `GreekGods` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `GreekGod` custom objects.</span></span> <span data-ttu-id="d67c1-106">Se definen plantillas de datos para que `GreekGod` objetos y `GreekHero` objetos aparecen con un gold y un color de primer plano cian respectivamente.</span><span class="sxs-lookup"><span data-stu-id="d67c1-106">Data templates are defined so that `GreekGod` objects and `GreekHero` objects appear with a gold and a cyan foreground color respectively.</span></span>  
  
 [!code-xaml[CompositeCollections#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="d67c1-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="d67c1-107">See Also</span></span>  
 <xref:System.Windows.Data.CollectionContainer>  
 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>  
 <xref:System.Windows.Data.XmlDataProvider>  
 <xref:System.Windows.DataTemplate>  
 [<span data-ttu-id="d67c1-108">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="d67c1-108">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="d67c1-109">Temas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="d67c1-109">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
