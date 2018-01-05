---
title: "Cómo: navegar hacia atrás en el historial de navegación"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating back
- navigation [WPF], through navigation history (back)
ms.assetid: 9343234b-d864-441d-b8a7-d895cba80a87
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e3bfc809dbe76c17859cb3fcd83f8a293a24b308
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-navigate-back-through-navigation-history"></a><span data-ttu-id="151d9-102">Cómo: navegar hacia atrás en el historial de navegación</span><span class="sxs-lookup"><span data-stu-id="151d9-102">How to: Navigate Back Through Navigation History</span></span>
<span data-ttu-id="151d9-103">Este ejemplo muestra cómo navegar hacia atrás en las entradas historial de navegación.</span><span class="sxs-lookup"><span data-stu-id="151d9-103">This example illustrates how to navigate to entries in back navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="151d9-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="151d9-104">Example</span></span>  
 <span data-ttu-id="151d9-105">Código que se ejecuta desde el contenido que se hospeda en un <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> usar <xref:System.Windows.Navigation.NavigationService>, o [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)] puede navegar hacia atrás por el historial de navegación, una entrada a la vez.</span><span class="sxs-lookup"><span data-stu-id="151d9-105">Code that is running from content that is hosted in a <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> use <xref:System.Windows.Navigation.NavigationService>, or [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)] can navigate back through navigation history, one entry at a time.</span></span>  
  
 <span data-ttu-id="151d9-106">Navegación volver una entrada es preciso comprobar primero que hay entradas en el historial de navegación hacia atrás, inspeccionando el **CanGoBack** propiedad, antes de navegar por volver a una entrada, mediante una llamada a la **GoBack** método.</span><span class="sxs-lookup"><span data-stu-id="151d9-106">Navigating back one entry requires first checking that there are entries in back navigation history, by inspecting the **CanGoBack** property, before navigating back one entry, by calling the **GoBack** method.</span></span> <span data-ttu-id="151d9-107">Esto se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="151d9-107">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="151d9-108">**CanGoBack** y **GoBack** se implementan mediante <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, y <xref:System.Windows.Navigation.NavigationService>.</span><span class="sxs-lookup"><span data-stu-id="151d9-108">**CanGoBack** and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="151d9-109">Si se llama a **GoBack**, y no hay entradas en el historial de navegación hacia atrás, un <xref:System.InvalidOperationException> se genera.</span><span class="sxs-lookup"><span data-stu-id="151d9-109">If you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is raised.</span></span>
