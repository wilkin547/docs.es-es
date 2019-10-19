---
title: 'Cómo: obtener y establecer la ventana principal de la aplicación'
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
ms.openlocfilehash: 5894761c4b6258cbf90d369a722ffc5abca51885
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582558"
---
# <a name="how-to-get-and-set-the-main-application-window"></a>Cómo: obtener y establecer la ventana principal de la aplicación
En este ejemplo se muestra cómo obtener y establecer la ventana de la aplicación principal.  
  
## <a name="example"></a>Ejemplo  
 La primera <xref:System.Windows.Window> de la que se crean instancias dentro de una aplicación Windows Presentation Foundation (WPF) se establece automáticamente <xref:System.Windows.Application> como la ventana principal de la aplicación. Lo más probable es que el primer <xref:System.Windows.Window> del que se van a crear instancias sea la ventana que se especifica como el identificador uniforme de recursos (URI) de inicio (vea <xref:System.Windows.Application.StartupUri%2A>).  
  
 También se pueden crear instancias del primer <xref:System.Windows.Window> mediante código. Un ejemplo es abrir una ventana durante el inicio de la aplicación, como la siguiente:  
  
 [!code-csharp[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/App.xaml.cs#firstwindowusingcodecodebehind)]
 [!code-vb[HOWTOWindowManagementSnippets#FirstWindowUsingCodeCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/application.xaml.vb#firstwindowusingcodecodebehind)]  
  
 A veces, el primer <xref:System.Windows.Window> con instancias no es realmente la ventana principal de la aplicación, por ejemplo, una pantalla de presentación. En este caso, puede especificar la ventana de la aplicación principal con el marcado, como se indica a continuación:  
  
 [!code-xaml[ApplicationMainWindowSnippets#SetApplicationMainWindowXAML](~/samples/snippets/xaml/VS_Snippets_Wpf/ApplicationMainWindowSnippets/XAML/App.xaml#setapplicationmainwindowxaml)]  
  
 Si la ventana principal se especifica de forma automática o manual, puede obtener la ventana principal de <xref:System.Windows.Application.MainWindow%2A> mediante el código siguiente, como se indica a continuación:  
  
 [!code-csharp[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationMainWindowSnippets/CSharp/App.xaml.cs#getapplicationmainwindowcode)]
 [!code-vb[ApplicationMainWindowSnippets#GetApplicationMainWindowCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationMainWindowSnippets/visualbasic/application.xaml.vb#getapplicationmainwindowcode)]
