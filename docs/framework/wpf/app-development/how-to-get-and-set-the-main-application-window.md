---
title: Procedimiento Obtener y establecer la ventana principal de la aplicación
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
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373561"
---
# <a name="how-to-get-and-set-the-main-application-window"></a>Procedimiento Obtener y establecer la ventana principal de la aplicación
En este ejemplo se muestra cómo obtener y establecer la ventana principal de la aplicación.  
  
## <a name="example"></a>Ejemplo  
 La primera <xref:System.Windows.Window> que se crea una instancia dentro de un Windows Presentation Foundation (WPF) aplicación establece automáticamente <xref:System.Windows.Application> como la ventana principal de la aplicación. La primera <xref:System.Windows.Window> a ser más probablemente se produzca con instancias de la ventana que se especifica como el inicio [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] (consulte <xref:System.Windows.Application.StartupUri%2A>).  
  
 La primera <xref:System.Windows.Window> también puede crearse mediante código. Un ejemplo es abrir una ventana durante el inicio de la aplicación, similar al siguiente:  
  
 [!code-csharp[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/App.xaml.cs#firstwindowusingcodecodebehind)]
 [!code-vb[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/application.xaml.vb#firstwindowusingcodecodebehind)]  
  
 A veces, crea una instancia de la primera <xref:System.Windows.Window> es realmente no la ventana principal de la aplicación, por ejemplo, una pantalla de presentación. En este caso, puede especificar la ventana principal de la aplicación mediante código similar al siguiente:  
  
 [!code-xaml[ApplicationMainWindowSnippets#SetApplicationMainWindowXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/ApplicationMainWindowSnippets/XAML/App.xaml#setapplicationmainwindowxaml)]  
  
 Si se especifica la ventana principal de forma automática o manual, puede obtener la ventana principal de <xref:System.Windows.Application.MainWindow%2A> con el siguiente código similar al siguiente:  
  
 [!code-csharp[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationMainWindowSnippets/CSharp/App.xaml.cs#getapplicationmainwindowcode)]
 [!code-vb[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationMainWindowSnippets/visualbasic/application.xaml.vb#getapplicationmainwindowcode)]
