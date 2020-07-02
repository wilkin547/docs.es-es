---
title: 'Cómo: obtener y establecer la ventana principal de la aplicación'
description: Siga este ejemplo para obtener y establecer la ventana principal de la aplicación en Windows Presentation Foundation aplicación (WPF).
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
ms.openlocfilehash: 9bb5bce9b90482796acd8c62e77dc8bd9a850eeb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622684"
---
# <a name="how-to-get-and-set-the-main-application-window"></a>Cómo: obtener y establecer la ventana principal de la aplicación
En este ejemplo se muestra cómo obtener y establecer la ventana de la aplicación principal.  
  
## <a name="example"></a>Ejemplo  
 La primera en la <xref:System.Windows.Window> que se crea una instancia dentro de una aplicación Windows Presentation Foundation (WPF) se establece automáticamente <xref:System.Windows.Application> como la ventana principal de la aplicación. Lo más probable es que la primera vez <xref:System.Windows.Window> que se cree la instancia sea la ventana que se especifica como el identificador uniforme de recursos (URI) de inicio (vea <xref:System.Windows.Application.StartupUri%2A> ).  
  
 <xref:System.Windows.Window>También se puede crear una instancia de la primera mediante código. Un ejemplo es abrir una ventana durante el inicio de la aplicación, como la siguiente:  
  
 [!code-csharp[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/App.xaml.cs#firstwindowusingcodecodebehind)]
 [!code-vb[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/application.xaml.vb#firstwindowusingcodecodebehind)]  
  
 A veces, la primera instancia de <xref:System.Windows.Window> no es realmente la ventana principal de la aplicación, por ejemplo, una pantalla de presentación. En este caso, puede especificar la ventana de la aplicación principal con el marcado, como se indica a continuación:  
  
 [!code-xaml[ApplicationMainWindowSnippets#SetApplicationMainWindowXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/ApplicationMainWindowSnippets/XAML/App.xaml#setapplicationmainwindowxaml)]  
  
 Si la ventana principal se especifica de forma automática o manual, puede obtener la ventana principal <xref:System.Windows.Application.MainWindow%2A> con el código siguiente, como se indica a continuación:  
  
 [!code-csharp[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationMainWindowSnippets/CSharp/App.xaml.cs#getapplicationmainwindowcode)]
 [!code-vb[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationMainWindowSnippets/visualbasic/application.xaml.vb#getapplicationmainwindowcode)]
