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
# <a name="how-to-navigate-forward-or-back-through-navigation-history"></a>Procedimiento Navegar hacia delante o hacia atrás por el historial de navegación
En este ejemplo se muestra cómo navegar hacia delante o hacia atrás a las entradas en el historial de navegación.  
  
## <a name="example"></a>Ejemplo  
 El código que se ejecuta desde el contenido de los siguientes hosts puede navegar hacia delante o hacia atrás a través del historial de navegación, una entrada cada vez.  
  
- <xref:System.Windows.Navigation.NavigationWindow>utilizan<xref:System.Windows.Navigation.NavigationService>  
  
- <xref:System.Windows.Controls.Frame>utilizan<xref:System.Windows.Navigation.NavigationService>  
  
- Internet Explorer  
  
 Para poder navegar hacia delante en una entrada, primero debe comprobar que haya entradas en el historial de navegación hacia delante mediante la inspección de la propiedad **CanGoForward** . Para navegar hacia delante en una entrada, llame al método **GoForward** . Esto se muestra en el ejemplo siguiente:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 Para poder navegar hacia atrás en una entrada, primero debe comprobar que haya entradas en el historial de navegación hacia atrás mediante la inspección de la propiedad **CanGoBack** . Para navegar hacia atrás en una entrada, se llama al método **GoBack** . Esto se muestra en el ejemplo siguiente:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 **CanGoForward**, **GoForward**, **CanGoBack**y **GoBack** se implementan mediante <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>y <xref:System.Windows.Navigation.NavigationService>.  
  
> [!NOTE]
> Si llama a **GoForward**y no hay ninguna entrada en el historial de navegación hacia delante, o si llama a **GoBack**y no hay ninguna entrada en el historial de navegación <xref:System.InvalidOperationException> hacia atrás, se produce una excepción.
