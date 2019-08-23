---
title: Procedimiento Navegar hacia atrás por el historial de navegación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating back
- navigation [WPF], through navigation history (back)
ms.assetid: 9343234b-d864-441d-b8a7-d895cba80a87
ms.openlocfilehash: 53b32e145390d7052262042c7a793699c163b373
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969355"
---
# <a name="how-to-navigate-back-through-navigation-history"></a><span data-ttu-id="d6921-102">Procedimiento Navegar hacia atrás por el historial de navegación</span><span class="sxs-lookup"><span data-stu-id="d6921-102">How to: Navigate Back Through Navigation History</span></span>
<span data-ttu-id="d6921-103">En este ejemplo se muestra cómo navegar a las entradas en el historial de navegación hacia atrás.</span><span class="sxs-lookup"><span data-stu-id="d6921-103">This example illustrates how to navigate to entries in back navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6921-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d6921-104">Example</span></span>  
 <span data-ttu-id="d6921-105">El código que se ejecuta desde el contenido que se hospeda <xref:System.Windows.Navigation.NavigationWindow>en <xref:System.Windows.Controls.Frame> un <xref:System.Windows.Navigation.NavigationService>, con o Internet Explorer puede navegar de nuevo a través del historial de navegación, una entrada cada vez.</span><span class="sxs-lookup"><span data-stu-id="d6921-105">Code that is running from content that is hosted in a <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> using <xref:System.Windows.Navigation.NavigationService>, or Internet Explorer can navigate back through navigation history, one entry at a time.</span></span>  
  
 <span data-ttu-id="d6921-106">Para navegar hacia atrás en una entrada es necesario comprobar primero que haya entradas en el historial de navegación hacia atrás, mediante la inspección de la propiedad **CanGoBack** , antes de navegar por una entrada, llamando al método **GoBack** .</span><span class="sxs-lookup"><span data-stu-id="d6921-106">Navigating back one entry requires first checking that there are entries in back navigation history, by inspecting the **CanGoBack** property, before navigating back one entry, by calling the **GoBack** method.</span></span> <span data-ttu-id="d6921-107">Esto se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d6921-107">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="d6921-108">**CanGoBack** y **GoBack** se implementan <xref:System.Windows.Navigation.NavigationWindow>mediante <xref:System.Windows.Controls.Frame>, y <xref:System.Windows.Navigation.NavigationService>.</span><span class="sxs-lookup"><span data-stu-id="d6921-108">**CanGoBack** and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d6921-109">Si llama a **GoBack**y no hay ninguna entrada en el historial de navegación hacia atrás <xref:System.InvalidOperationException> , se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="d6921-109">If you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is raised.</span></span>
