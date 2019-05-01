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
ms.openlocfilehash: 4c20ebfab45a24cf34b1476fb94dae6913fb4d99
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947763"
---
# <a name="how-to-navigate-forward-or-back-through-navigation-history"></a><span data-ttu-id="77f62-102">Procedimiento Navegar hacia delante o hacia atrás por el historial de navegación</span><span class="sxs-lookup"><span data-stu-id="77f62-102">How to: Navigate Forward or Back Through Navigation History</span></span>
<span data-ttu-id="77f62-103">En este ejemplo se muestra cómo navegar hacia delante o hacia atrás a entradas del historial de navegación.</span><span class="sxs-lookup"><span data-stu-id="77f62-103">This example illustrates how to navigate forward or back to entries in navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="77f62-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="77f62-104">Example</span></span>  
 <span data-ttu-id="77f62-105">Código que se ejecuta desde el contenido de los siguientes hosts puede navegar hacia delante o hacia atrás por el historial de navegación, una entrada a la vez.</span><span class="sxs-lookup"><span data-stu-id="77f62-105">Code that runs from content in the following hosts can navigate forward or back through navigation history, one entry at a time.</span></span>  
  
- <span data-ttu-id="77f62-106"><xref:System.Windows.Navigation.NavigationWindow> Uso de <xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="77f62-106"><xref:System.Windows.Navigation.NavigationWindow> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
- <span data-ttu-id="77f62-107"><xref:System.Windows.Controls.Frame> Uso de <xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="77f62-107"><xref:System.Windows.Controls.Frame> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
- [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)]  
  
 <span data-ttu-id="77f62-108">Antes de que puede navegar por una entrada directa, debe comprobar primero que hay entradas en el historial de avance de navegación inspeccionando el **CanGoForward** propiedad.</span><span class="sxs-lookup"><span data-stu-id="77f62-108">Before you can navigate forward one entry, you must first check that there are entries in forward navigation history by inspecting the **CanGoForward** property.</span></span> <span data-ttu-id="77f62-109">Para navegar por una entrada directa, llame a la **GoForward** método.</span><span class="sxs-lookup"><span data-stu-id="77f62-109">To navigate forward one entry, you call the **GoForward** method.</span></span> <span data-ttu-id="77f62-110">Esto se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="77f62-110">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 <span data-ttu-id="77f62-111">Antes de que puede navegar hacer una copia de una entrada, primero debe comprobar que hay entradas en el historial de retroceso de navegación inspeccionando el **CanGoBack** propiedad.</span><span class="sxs-lookup"><span data-stu-id="77f62-111">Before you can navigate back one entry, you must first check that there are entries in back navigation history by inspecting the **CanGoBack** property.</span></span> <span data-ttu-id="77f62-112">Para navegar por entrada, llame a la **GoBack** método.</span><span class="sxs-lookup"><span data-stu-id="77f62-112">To navigate back one entry, you call the **GoBack** method.</span></span> <span data-ttu-id="77f62-113">Esto se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="77f62-113">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="77f62-114">**CanGoForward**, **GoForward**, **CanGoBack**, y **GoBack** se implementan mediante <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, y <xref:System.Windows.Navigation.NavigationService>.</span><span class="sxs-lookup"><span data-stu-id="77f62-114">**CanGoForward**, **GoForward**, **CanGoBack**, and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="77f62-115">Si se llama a **GoForward**, y no hay ninguna entrada en el historial de avance de navegación, o si se llama a **GoBack**, y no hay ninguna entrada en el historial de navegación hacia atrás, un <xref:System.InvalidOperationException> se produce.</span><span class="sxs-lookup"><span data-stu-id="77f62-115">If you call **GoForward**, and there are no entries in forward navigation history, or if you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is thrown.</span></span>
