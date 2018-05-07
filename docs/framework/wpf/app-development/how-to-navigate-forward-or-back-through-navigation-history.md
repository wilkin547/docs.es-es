---
title: 'Cómo: Navegar hacia delante o hacia atrás por el historial de navegación'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating forward
- navigation [WPF], through navigation history (forward)
ms.assetid: 5939d574-5f53-469e-85f5-1f2b13607caa
ms.openlocfilehash: ac3b8b71b6adf04d71cf35edbb042b82c57d8e1f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-navigate-forward-or-back-through-navigation-history"></a>Cómo: Navegar hacia delante o hacia atrás por el historial de navegación
En este ejemplo se muestra cómo navegar hacia delante o hacia atrás hacia las entradas en el historial de navegación.  
  
## <a name="example"></a>Ejemplo  
 Código que se ejecuta desde el contenido de los siguientes hosts puede navegar hacia delante o hacia atrás por el historial de navegación, una entrada a la vez.  
  
-   <xref:System.Windows.Navigation.NavigationWindow> Uso de <xref:System.Windows.Navigation.NavigationService>  
  
-   <xref:System.Windows.Controls.Frame> Uso de <xref:System.Windows.Navigation.NavigationService>  
  
-   [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)]  
  
 Antes de que puede navegar hacia delante con una entrada, debe comprobar primero que hay entradas en el historial de navegación hacia atrás inspeccionando el **CanGoForward** propiedad. Para navegar hacia delante con una entrada, se llama a la **GoForward** método. Esto se muestra en el ejemplo siguiente:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 Antes de que puede navegar atrás una entrada, primero debe comprobar que hay entradas en el historial de navegación hacia atrás inspeccionando el **CanGoBack** propiedad. Para navegar por entrada, se llama a la **GoBack** método. Esto se muestra en el ejemplo siguiente:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 **CanGoForward**, **GoForward**, **CanGoBack**, y **GoBack** se implementan mediante <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, y <xref:System.Windows.Navigation.NavigationService>.  
  
> [!NOTE]
>  Si se llama a **GoForward**, y no hay entradas en el historial de navegación hacia atrás, o si se llama a **GoBack**, y no hay entradas en el historial de navegación hacia atrás, un <xref:System.InvalidOperationException> se produce.
