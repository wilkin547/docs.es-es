---
title: Procedimiento Navegar hacia delante o hacia atrás por el historial de navegación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating forward
- navigation [WPF], through navigation history (forward)
ms.assetid: 5939d574-5f53-469e-85f5-1f2b13607caa
ms.openlocfilehash: 76a78debdce14123cc465ac9abf4db906fe0a2df
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69961350"
---
# <a name="how-to-navigate-forward-or-back-through-navigation-history"></a><span data-ttu-id="39480-102">Procedimiento Navegar hacia delante o hacia atrás por el historial de navegación</span><span class="sxs-lookup"><span data-stu-id="39480-102">How to: Navigate Forward or Back Through Navigation History</span></span>
<span data-ttu-id="39480-103">En este ejemplo se muestra cómo navegar hacia delante o hacia atrás a las entradas en el historial de navegación.</span><span class="sxs-lookup"><span data-stu-id="39480-103">This example illustrates how to navigate forward or back to entries in navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39480-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="39480-104">Example</span></span>  
 <span data-ttu-id="39480-105">El código que se ejecuta desde el contenido de los siguientes hosts puede navegar hacia delante o hacia atrás a través del historial de navegación, una entrada cada vez.</span><span class="sxs-lookup"><span data-stu-id="39480-105">Code that runs from content in the following hosts can navigate forward or back through navigation history, one entry at a time.</span></span>  
  
- <span data-ttu-id="39480-106"><xref:System.Windows.Navigation.NavigationWindow>utilizan<xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="39480-106"><xref:System.Windows.Navigation.NavigationWindow> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
- <span data-ttu-id="39480-107"><xref:System.Windows.Controls.Frame>utilizan<xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="39480-107"><xref:System.Windows.Controls.Frame> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
- <span data-ttu-id="39480-108">Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="39480-108">Internet Explorer</span></span>  
  
 <span data-ttu-id="39480-109">Para poder navegar hacia delante en una entrada, primero debe comprobar que haya entradas en el historial de navegación hacia delante mediante la inspección de la propiedad **CanGoForward** .</span><span class="sxs-lookup"><span data-stu-id="39480-109">Before you can navigate forward one entry, you must first check that there are entries in forward navigation history by inspecting the **CanGoForward** property.</span></span> <span data-ttu-id="39480-110">Para navegar hacia delante en una entrada, llame al método **GoForward** .</span><span class="sxs-lookup"><span data-stu-id="39480-110">To navigate forward one entry, you call the **GoForward** method.</span></span> <span data-ttu-id="39480-111">Esto se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="39480-111">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 <span data-ttu-id="39480-112">Para poder navegar hacia atrás en una entrada, primero debe comprobar que haya entradas en el historial de navegación hacia atrás mediante la inspección de la propiedad **CanGoBack** .</span><span class="sxs-lookup"><span data-stu-id="39480-112">Before you can navigate back one entry, you must first check that there are entries in back navigation history by inspecting the **CanGoBack** property.</span></span> <span data-ttu-id="39480-113">Para navegar hacia atrás en una entrada, se llama al método **GoBack** .</span><span class="sxs-lookup"><span data-stu-id="39480-113">To navigate back one entry, you call the **GoBack** method.</span></span> <span data-ttu-id="39480-114">Esto se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="39480-114">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="39480-115">**CanGoForward**, **GoForward**, **CanGoBack**y **GoBack** se implementan mediante <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>y <xref:System.Windows.Navigation.NavigationService>.</span><span class="sxs-lookup"><span data-stu-id="39480-115">**CanGoForward**, **GoForward**, **CanGoBack**, and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="39480-116">Si llama a **GoForward**y no hay ninguna entrada en el historial de navegación hacia delante, o si llama a **GoBack**y no hay ninguna entrada en el historial de navegación <xref:System.InvalidOperationException> hacia atrás, se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="39480-116">If you call **GoForward**, and there are no entries in forward navigation history, or if you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is thrown.</span></span>
