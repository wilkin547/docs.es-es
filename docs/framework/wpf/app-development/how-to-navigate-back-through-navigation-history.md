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
ms.openlocfilehash: c489a1593b3d1f22fe1ad6e648d3f8a3f7a6cd44
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947789"
---
# <a name="how-to-navigate-back-through-navigation-history"></a>Procedimiento Navegar hacia atrás por el historial de navegación
En este ejemplo se muestra cómo navegar hacia atrás en las entradas historial de navegación.  
  
## <a name="example"></a>Ejemplo  
 Código que se ejecuta desde el contenido que se hospeda en un <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> mediante <xref:System.Windows.Navigation.NavigationService>, o [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)] puede navegar hacia atrás por el historial de navegación, una entrada a la vez.  
  
 Al ir atrás una entrada es preciso comprobar primero que hay entradas en el historial de navegación hacia atrás, inspeccionando el **CanGoBack** propiedad, antes de navegar por hacer una copia de una entrada, mediante una llamada a la **GoBack** método. Esto se muestra en el ejemplo siguiente:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 **CanGoBack** y **GoBack** se implementan mediante <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, y <xref:System.Windows.Navigation.NavigationService>.  
  
> [!NOTE]
>  Si se llama a **GoBack**, y no hay ninguna entrada en el historial de navegación hacia atrás, un <xref:System.InvalidOperationException> se genera.
