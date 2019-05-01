---
title: Procedimiento Obtener y establecer la ventana principal de una aplicación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- windows objects [WPF], setting
- setting windows objects [WPF]
- windows objects [WPF], getting
- getting windows objects [WPF]
ms.assetid: ec902bc4-4a59-46f5-8ec1-963b46789356
ms.openlocfilehash: ea8333aa82f1159afb438215940ee1e7c2605e96
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947802"
---
# <a name="how-to-get-and-set-the-main-application-window"></a><span data-ttu-id="c6c33-102">Procedimiento Obtener y establecer la ventana principal de una aplicación</span><span class="sxs-lookup"><span data-stu-id="c6c33-102">How to: Get and Set the Main Application Window</span></span>
<span data-ttu-id="c6c33-103">En este ejemplo se muestra cómo obtener y establecer la ventana principal de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c6c33-103">This example shows how to get and set the main application window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6c33-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c6c33-104">Example</span></span>  
 <span data-ttu-id="c6c33-105">La primera <xref:System.Windows.Window> que se crea una instancia dentro de un Windows Presentation Foundation (WPF) aplicación establece automáticamente <xref:System.Windows.Application> como la ventana principal de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c6c33-105">The first <xref:System.Windows.Window> that is instantiated within a Windows Presentation Foundation (WPF) application is automatically set by <xref:System.Windows.Application> as the main application window.</span></span> <span data-ttu-id="c6c33-106">La primera <xref:System.Windows.Window> a ser más probablemente se produzca con instancias de la ventana que se especifica como el inicio [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] (consulte <xref:System.Windows.Application.StartupUri%2A>).</span><span class="sxs-lookup"><span data-stu-id="c6c33-106">The first <xref:System.Windows.Window> to be instantiated will most likely be the window that is specified as the startup [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] (see <xref:System.Windows.Application.StartupUri%2A>).</span></span>  
  
 <span data-ttu-id="c6c33-107">La primera <xref:System.Windows.Window> también puede crearse mediante código.</span><span class="sxs-lookup"><span data-stu-id="c6c33-107">The first <xref:System.Windows.Window> could also be instantiated using code.</span></span> <span data-ttu-id="c6c33-108">Un ejemplo es abrir una ventana durante el inicio de la aplicación, similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="c6c33-108">One example is opening a window during application startup, like the following:</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/App.xaml.cs#firstwindowusingcodecodebehind)]
 [!code-vb[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/application.xaml.vb#firstwindowusingcodecodebehind)]  
  
 <span data-ttu-id="c6c33-109">A veces, crea una instancia de la primera <xref:System.Windows.Window> es realmente no la ventana principal de la aplicación, por ejemplo, una pantalla de presentación.</span><span class="sxs-lookup"><span data-stu-id="c6c33-109">Sometimes, the first instantiated <xref:System.Windows.Window> is not actually the main application window e.g. a splash screen.</span></span> <span data-ttu-id="c6c33-110">En este caso, puede especificar la ventana principal de la aplicación mediante código similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="c6c33-110">In this case, you can specify the main application window using markup, like the following:</span></span>  
  
 [!code-xaml[ApplicationMainWindowSnippets#SetApplicationMainWindowXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/ApplicationMainWindowSnippets/XAML/App.xaml#setapplicationmainwindowxaml)]  
  
 <span data-ttu-id="c6c33-111">Si se especifica la ventana principal de forma automática o manual, puede obtener la ventana principal de <xref:System.Windows.Application.MainWindow%2A> con el siguiente código similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="c6c33-111">Whether the main window is specified automatically or manually, you can get the main window from <xref:System.Windows.Application.MainWindow%2A> using the following code, like the following:</span></span>  
  
 [!code-csharp[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationMainWindowSnippets/CSharp/App.xaml.cs#getapplicationmainwindowcode)]
 [!code-vb[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationMainWindowSnippets/visualbasic/application.xaml.vb#getapplicationmainwindowcode)]
