---
title: "C&#243;mo: Navegar hacia delante o hacia atr&#225;s por el historial de navegaci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "history, navegación, navegar hacia delante"
  - "navegación, por el historial de navegación (hacia delante)"
ms.assetid: 5939d574-5f53-469e-85f5-1f2b13607caa
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Navegar hacia delante o hacia atr&#225;s por el historial de navegaci&#243;n
En este ejemplo se muestra cómo navegar hacia delante o a entradas del historial de navegación.  
  
## Ejemplo  
 El código que se ejecuta de contenido en los hosts siguientes puede navegar hacia delante o para con el historial de navegación, una entrada al mismo tiempo.  
  
-   <xref:System.Windows.Navigation.NavigationWindow> mediante <xref:System.Windows.Navigation.NavigationService>  
  
-   <xref:System.Windows.Controls.Frame> mediante <xref:System.Windows.Navigation.NavigationService>  
  
-   [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)]  
  
 Antes de poder navegar hacia delante una entrada, debe comprobar primero que haya entradas subsiguientes en el historial de navegación inspeccionando la propiedad de **CanGoForward** .  Para navegar a la entrada siguiente, llame al método de **GoForward** .  Esto se muestra en el siguiente ejemplo:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 Antes de poder navegar a la entrada una, debe comprobar primero que haya entradas del historial de navegación inspeccionando la propiedad de **CanGoBack** .  Para navegar a la entrada una, llama al método de **GoBack** .  Esto se muestra en el siguiente ejemplo:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 **CanGoForward**, **GoForward**, **CanGoBack**, y **GoBack** se implementan mediante <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, y <xref:System.Windows.Navigation.NavigationService>.  
  
> [!NOTE]
>  Si llama a **GoForward**, y no hay entradas subsiguientes en el historial de navegación, o si llama a **GoBack**, y no hay ninguna entrada en el historial de navegación, se produce <xref:System.InvalidOperationException> .