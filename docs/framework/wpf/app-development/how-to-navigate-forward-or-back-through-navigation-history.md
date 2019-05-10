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
ms.openlocfilehash: 00a41fcf85583ec0d081a2fa099f3a77cfcd2900
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625351"
---
# <a name="how-to-navigate-forward-or-back-through-navigation-history"></a><span data-ttu-id="1427f-102">Procedimiento Navegar hacia delante o hacia atrás por el historial de navegación</span><span class="sxs-lookup"><span data-stu-id="1427f-102">How to: Navigate Forward or Back Through Navigation History</span></span>
<span data-ttu-id="1427f-103">En este ejemplo se muestra cómo navegar hacia delante o hacia atrás a entradas del historial de navegación.</span><span class="sxs-lookup"><span data-stu-id="1427f-103">This example illustrates how to navigate forward or back to entries in navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1427f-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1427f-104">Example</span></span>  
 <span data-ttu-id="1427f-105">Código que se ejecuta desde el contenido de los siguientes hosts puede navegar hacia delante o hacia atrás por el historial de navegación, una entrada a la vez.</span><span class="sxs-lookup"><span data-stu-id="1427f-105">Code that runs from content in the following hosts can navigate forward or back through navigation history, one entry at a time.</span></span>  
  
- <span data-ttu-id="1427f-106"><xref:System.Windows.Navigation.NavigationWindow> Uso de <xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="1427f-106"><xref:System.Windows.Navigation.NavigationWindow> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
- <span data-ttu-id="1427f-107"><xref:System.Windows.Controls.Frame> Uso de <xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="1427f-107"><xref:System.Windows.Controls.Frame> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
- [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)]  
  
 <span data-ttu-id="1427f-108">Antes de que puede navegar por una entrada directa, debe comprobar primero que hay entradas en el historial de avance de navegación inspeccionando el **CanGoForward** propiedad.</span><span class="sxs-lookup"><span data-stu-id="1427f-108">Before you can navigate forward one entry, you must first check that there are entries in forward navigation history by inspecting the **CanGoForward** property.</span></span> <span data-ttu-id="1427f-109">Para navegar por una entrada directa, llame a la **GoForward** método.</span><span class="sxs-lookup"><span data-stu-id="1427f-109">To navigate forward one entry, you call the **GoForward** method.</span></span> <span data-ttu-id="1427f-110">Esto se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1427f-110">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 <span data-ttu-id="1427f-111">Antes de que puede navegar hacer una copia de una entrada, primero debe comprobar que hay entradas en el historial de retroceso de navegación inspeccionando el **CanGoBack** propiedad.</span><span class="sxs-lookup"><span data-stu-id="1427f-111">Before you can navigate back one entry, you must first check that there are entries in back navigation history by inspecting the **CanGoBack** property.</span></span> <span data-ttu-id="1427f-112">Para navegar por entrada, llame a la **GoBack** método.</span><span class="sxs-lookup"><span data-stu-id="1427f-112">To navigate back one entry, you call the **GoBack** method.</span></span> <span data-ttu-id="1427f-113">Esto se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1427f-113">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="1427f-114">**CanGoForward**, **GoForward**, **CanGoBack**, y **GoBack** se implementan mediante <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, y <xref:System.Windows.Navigation.NavigationService>.</span><span class="sxs-lookup"><span data-stu-id="1427f-114">**CanGoForward**, **GoForward**, **CanGoBack**, and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1427f-115">Si se llama a **GoForward**, y no hay ninguna entrada en el historial de avance de navegación, o si se llama a **GoBack**, y no hay ninguna entrada en el historial de navegación hacia atrás, un <xref:System.InvalidOperationException> se produce.</span><span class="sxs-lookup"><span data-stu-id="1427f-115">If you call **GoForward**, and there are no entries in forward navigation history, or if you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is thrown.</span></span>
