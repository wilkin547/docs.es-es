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
# <a name="how-to-navigate-forward-or-back-through-navigation-history"></a>Procedimiento Navegar hacia delante o hacia atrás por el historial de navegación
En este ejemplo se muestra cómo navegar hacia delante o hacia atrás a entradas del historial de navegación.  
  
## <a name="example"></a>Ejemplo  
 Código que se ejecuta desde el contenido de los siguientes hosts puede navegar hacia delante o hacia atrás por el historial de navegación, una entrada a la vez.  
  
- <xref:System.Windows.Navigation.NavigationWindow> Uso de <xref:System.Windows.Navigation.NavigationService>  
  
- <xref:System.Windows.Controls.Frame> Uso de <xref:System.Windows.Navigation.NavigationService>  
  
- [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)]  
  
 Antes de que puede navegar por una entrada directa, debe comprobar primero que hay entradas en el historial de avance de navegación inspeccionando el **CanGoForward** propiedad. Para navegar por una entrada directa, llame a la **GoForward** método. Esto se muestra en el ejemplo siguiente:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 Antes de que puede navegar hacer una copia de una entrada, primero debe comprobar que hay entradas en el historial de retroceso de navegación inspeccionando el **CanGoBack** propiedad. Para navegar por entrada, llame a la **GoBack** método. Esto se muestra en el ejemplo siguiente:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 **CanGoForward**, **GoForward**, **CanGoBack**, y **GoBack** se implementan mediante <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, y <xref:System.Windows.Navigation.NavigationService>.  
  
> [!NOTE]
>  Si se llama a **GoForward**, y no hay ninguna entrada en el historial de avance de navegación, o si se llama a **GoBack**, y no hay ninguna entrada en el historial de navegación hacia atrás, un <xref:System.InvalidOperationException> se produce.
