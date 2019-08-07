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
ms.openlocfilehash: 86590c2794339ac22cbc8ec5e11224736133e870
ms.sourcegitcommit: 10736f243dd2296212e677e207102c463e5f143e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2019
ms.locfileid: "68817979"
---
# <a name="how-to-navigate-back-through-navigation-history"></a>Procedimiento Navegar hacia atrás por el historial de navegación
En este ejemplo se muestra cómo navegar a las entradas en el historial de navegación hacia atrás.  
  
## <a name="example"></a>Ejemplo  
 El código que se ejecuta desde el contenido que se hospeda <xref:System.Windows.Navigation.NavigationWindow>en <xref:System.Windows.Controls.Frame> un <xref:System.Windows.Navigation.NavigationService>, con o Internet Explorer puede navegar de nuevo a través del historial de navegación, una entrada cada vez.  
  
 Para navegar hacia atrás en una entrada es necesario comprobar primero que haya entradas en el historial de navegación hacia atrás, mediante la inspección de la propiedad **CanGoBack** , antes de navegar por una entrada, llamando al método **GoBack** . Esto se muestra en el ejemplo siguiente:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 **CanGoBack** y **GoBack** se implementan <xref:System.Windows.Navigation.NavigationWindow>mediante <xref:System.Windows.Controls.Frame>, y <xref:System.Windows.Navigation.NavigationService>.  
  
> [!NOTE]
>  Si llama a **GoBack**y no hay ninguna entrada en el historial de navegación hacia atrás <xref:System.InvalidOperationException> , se produce una excepción.
