---
title: "Cómo: Navegar hacia delante o hacia atrás por el historial de navegación"
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
- history [WPF], navigating forward
- navigation [WPF], through navigation history (forward)
ms.assetid: 5939d574-5f53-469e-85f5-1f2b13607caa
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 78fd9fec6a93c100da6b4e7174376a963ae8beb2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-navigate-forward-or-back-through-navigation-history"></a><span data-ttu-id="50933-102">Cómo: Navegar hacia delante o hacia atrás por el historial de navegación</span><span class="sxs-lookup"><span data-stu-id="50933-102">How to: Navigate Forward or Back Through Navigation History</span></span>
<span data-ttu-id="50933-103">En este ejemplo se muestra cómo navegar hacia delante o hacia atrás hacia las entradas en el historial de navegación.</span><span class="sxs-lookup"><span data-stu-id="50933-103">This example illustrates how to navigate forward or back to entries in navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50933-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="50933-104">Example</span></span>  
 <span data-ttu-id="50933-105">Código que se ejecuta desde el contenido de los siguientes hosts puede navegar hacia delante o hacia atrás por el historial de navegación, una entrada a la vez.</span><span class="sxs-lookup"><span data-stu-id="50933-105">Code that runs from content in the following hosts can navigate forward or back through navigation history, one entry at a time.</span></span>  
  
-   <span data-ttu-id="50933-106"><xref:System.Windows.Navigation.NavigationWindow>uso de<xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="50933-106"><xref:System.Windows.Navigation.NavigationWindow> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
-   <span data-ttu-id="50933-107"><xref:System.Windows.Controls.Frame>uso de<xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="50933-107"><xref:System.Windows.Controls.Frame> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
-   [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)]  
  
 <span data-ttu-id="50933-108">Antes de que puede navegar hacia delante con una entrada, debe comprobar primero que hay entradas en el historial de navegación hacia atrás inspeccionando el **CanGoForward** propiedad.</span><span class="sxs-lookup"><span data-stu-id="50933-108">Before you can navigate forward one entry, you must first check that there are entries in forward navigation history by inspecting the **CanGoForward** property.</span></span> <span data-ttu-id="50933-109">Para navegar hacia delante con una entrada, se llama a la **GoForward** método.</span><span class="sxs-lookup"><span data-stu-id="50933-109">To navigate forward one entry, you call the **GoForward** method.</span></span> <span data-ttu-id="50933-110">Esto se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="50933-110">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 <span data-ttu-id="50933-111">Antes de que puede navegar atrás una entrada, primero debe comprobar que hay entradas en el historial de navegación hacia atrás inspeccionando el **CanGoBack** propiedad.</span><span class="sxs-lookup"><span data-stu-id="50933-111">Before you can navigate back one entry, you must first check that there are entries in back navigation history by inspecting the **CanGoBack** property.</span></span> <span data-ttu-id="50933-112">Para navegar por entrada, se llama a la **GoBack** método.</span><span class="sxs-lookup"><span data-stu-id="50933-112">To navigate back one entry, you call the **GoBack** method.</span></span> <span data-ttu-id="50933-113">Esto se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="50933-113">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="50933-114">**CanGoForward**, **GoForward**, **CanGoBack**, y **GoBack** se implementan mediante <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, y <xref:System.Windows.Navigation.NavigationService>.</span><span class="sxs-lookup"><span data-stu-id="50933-114">**CanGoForward**, **GoForward**, **CanGoBack**, and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="50933-115">Si se llama a **GoForward**, y no hay entradas en el historial de navegación hacia atrás, o si se llama a **GoBack**, y no hay entradas en el historial de navegación hacia atrás, un <xref:System.InvalidOperationException> se produce.</span><span class="sxs-lookup"><span data-stu-id="50933-115">If you call **GoForward**, and there are no entries in forward navigation history, or if you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is thrown.</span></span>
