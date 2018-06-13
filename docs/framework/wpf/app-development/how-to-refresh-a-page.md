---
title: 'Cómo: actualizar la página'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pages [WPF], refreshing
- refreshing pages [WPF]
ms.assetid: 06dd1bbd-81c4-40ad-ac0d-7a5b326b1465
ms.openlocfilehash: 27735450360206e0a15ecae00cc9d45f93e4e838
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546535"
---
# <a name="how-to-refresh-a-page"></a><span data-ttu-id="26efb-102">Cómo: actualizar la página</span><span class="sxs-lookup"><span data-stu-id="26efb-102">How to: Refresh a Page</span></span>
<span data-ttu-id="26efb-103">Este ejemplo muestra cómo llamar a la <xref:System.Windows.Navigation.NavigationWindow.Refresh%2A> método para actualizar el contenido actual de un <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="26efb-103">This example shows how to call the <xref:System.Windows.Navigation.NavigationWindow.Refresh%2A> method to refresh the current content in a <xref:System.Windows.Navigation.NavigationWindow>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26efb-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="26efb-104">Example</span></span>  
 <span data-ttu-id="26efb-105"><xref:System.Windows.Navigation.NavigationWindow.Refresh%2A> actualiza el contenido actual en un <xref:System.Windows.Navigation.NavigationWindow> para volver a cargar desde su origen.</span><span class="sxs-lookup"><span data-stu-id="26efb-105"><xref:System.Windows.Navigation.NavigationWindow.Refresh%2A> refreshes the current content in a <xref:System.Windows.Navigation.NavigationWindow> to be reloaded from its source.</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateRefreshCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/MainWindow.xaml.cs#navigaterefreshcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateRefreshCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/mainwindow.xaml.vb#navigaterefreshcode)]
