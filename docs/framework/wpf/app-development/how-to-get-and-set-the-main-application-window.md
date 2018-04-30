---
title: 'Cómo: obtener y establecer la ventana de la aplicación principal'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
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
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9bdc96c509f88650edd93ba4a7f595e2b161db39
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
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
