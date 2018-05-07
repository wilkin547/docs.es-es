---
title: 'Cómo: obtener y establecer la ventana de la aplicación principal'
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
ms.openlocfilehash: ae70b482eba8fb4e0bf587def06bb90d751a4312
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-get-and-set-the-main-application-window"></a>Cómo: obtener y establecer la ventana de la aplicación principal
En este ejemplo se muestra cómo obtener y establecer la ventana de la aplicación principal.  
  
## <a name="example"></a>Ejemplo  
 La primera <xref:System.Windows.Window> que se crea una instancia en un Windows Presentation Foundation (WPF) aplicación se establece automáticamente en <xref:System.Windows.Application> como la ventana de la aplicación principal. La primera <xref:System.Windows.Window> como instancias tendrán más probable es que la ventana que se especifica como el inicio [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] (consulte <xref:System.Windows.Application.StartupUri%2A>).  
  
 La primera <xref:System.Windows.Window> pudo también puede crear una instancia mediante código. Un ejemplo es abrir una ventana durante el inicio de la aplicación, similar al siguiente:  
  
 [!code-csharp[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/App.xaml.cs#firstwindowusingcodecodebehind)]
 [!code-vb[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/application.xaml.vb#firstwindowusingcodecodebehind)]  
  
 A veces, crear instancias de la primera <xref:System.Windows.Window> es realmente no la ventana de aplicación principal, por ejemplo, una pantalla de presentación. En este caso, puede especificar la ventana de aplicación principal mediante código similar al siguiente:  
  
 [!code-xaml[ApplicationMainWindowSnippets#SetApplicationMainWindowXAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/ApplicationMainWindowSnippets/XAML/App.xaml#setapplicationmainwindowxaml)]  
  
 Si se especifica la ventana principal de forma manual o automática, puede obtener la ventana principal de <xref:System.Windows.Application.MainWindow%2A> con el código siguiente, similar al siguiente:  
  
 [!code-csharp[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ApplicationMainWindowSnippets/CSharp/App.xaml.cs#getapplicationmainwindowcode)]
 [!code-vb[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationMainWindowSnippets/visualbasic/application.xaml.vb#getapplicationmainwindowcode)]
