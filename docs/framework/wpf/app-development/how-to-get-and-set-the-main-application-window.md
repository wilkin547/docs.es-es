---
title: "Cómo: obtener y establecer la ventana de la aplicación principal"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- windows objects [WPF], setting
- setting windows objects [WPF]
- windows objects [WPF], getting
- getting windows objects [WPF]
ms.assetid: ec902bc4-4a59-46f5-8ec1-963b46789356
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0d6bca158172fd3fc31526287c6d4a9928a8ea0c
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-get-and-set-the-main-application-window"></a><span data-ttu-id="956ae-102">Cómo: obtener y establecer la ventana de la aplicación principal</span><span class="sxs-lookup"><span data-stu-id="956ae-102">How to: Get and Set the Main Application Window</span></span>
<span data-ttu-id="956ae-103">En este ejemplo se muestra cómo obtener y establecer la ventana de la aplicación principal.</span><span class="sxs-lookup"><span data-stu-id="956ae-103">This example shows how to get and set the main application window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="956ae-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="956ae-104">Example</span></span>  
 <span data-ttu-id="956ae-105">La primera <xref:System.Windows.Window> que se crea una instancia de un [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] aplicación se establece automáticamente en <xref:System.Windows.Application> como la ventana de la aplicación principal.</span><span class="sxs-lookup"><span data-stu-id="956ae-105">The first <xref:System.Windows.Window> that is instantiated within a [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] application is automatically set by <xref:System.Windows.Application> as the main application window.</span></span> <span data-ttu-id="956ae-106">La primera <xref:System.Windows.Window> como instancias tendrán más probable es que la ventana que se especifica como el inicio [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] (consulte <xref:System.Windows.Application.StartupUri%2A>).</span><span class="sxs-lookup"><span data-stu-id="956ae-106">The first <xref:System.Windows.Window> to be instantiated will most likely be the window that is specified as the startup [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] (see <xref:System.Windows.Application.StartupUri%2A>).</span></span>  
  
 <span data-ttu-id="956ae-107">La primera <xref:System.Windows.Window> pudo también puede crear una instancia mediante código.</span><span class="sxs-lookup"><span data-stu-id="956ae-107">The first <xref:System.Windows.Window> could also be instantiated using code.</span></span> <span data-ttu-id="956ae-108">Un ejemplo es abrir una ventana durante el inicio de la aplicación, similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="956ae-108">One example is opening a window during application startup, like the following:</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/App.xaml.cs#firstwindowusingcodecodebehind)]
 [!code-vb[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/application.xaml.vb#firstwindowusingcodecodebehind)]  
  
 <span data-ttu-id="956ae-109">A veces, crear instancias de la primera <xref:System.Windows.Window> es realmente no la ventana de aplicación principal, por ejemplo, una pantalla de presentación.</span><span class="sxs-lookup"><span data-stu-id="956ae-109">Sometimes, the first instantiated <xref:System.Windows.Window> is not actually the main application window e.g. a splash screen.</span></span> <span data-ttu-id="956ae-110">En este caso, puede especificar la ventana de aplicación principal mediante código similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="956ae-110">In this case, you can specify the main application window using markup, like the following:</span></span>  
  
 [!code-xaml[ApplicationMainWindowSnippets#SetApplicationMainWindowXAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/ApplicationMainWindowSnippets/XAML/App.xaml#setapplicationmainwindowxaml)]  
  
 <span data-ttu-id="956ae-111">Si se especifica la ventana principal de forma manual o automática, puede obtener la ventana principal de <xref:System.Windows.Application.MainWindow%2A> con el código siguiente, similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="956ae-111">Whether the main window is specified automatically or manually, you can get the main window from <xref:System.Windows.Application.MainWindow%2A> using the following code, like the following:</span></span>  
  
 [!code-csharp[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationMainWindowSnippets/CSharp/App.xaml.cs#getapplicationmainwindowcode)]
 [!code-vb[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationMainWindowSnippets/visualbasic/application.xaml.vb#getapplicationmainwindowcode)]
