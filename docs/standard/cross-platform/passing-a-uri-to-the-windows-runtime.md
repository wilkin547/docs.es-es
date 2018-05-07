---
title: Pasar un URI a Windows Runtime
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Runtime, .NET Framework support for
- Windows Runtime, passing a URI to
ms.assetid: 3eb5ce6f-f304-4f87-8e81-0f25092f5ad4
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7a31a1246fe311c36e7457327c79aeeef30e7813
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="passing-a-uri-to-the-windows-runtime"></a>Pasar un URI a Windows Runtime
Los métodos de Windows Runtime solo aceptan URI absolutos. Si se pasa un URI relativo a un método [!INCLUDE[wrt](../../../includes/wrt-md.md)], se produce una excepción <xref:System.ArgumentException>. Esta es la razón: cuando se usa el [!INCLUDE[wrt](../../../includes/wrt-md.md)] en el código de .NET Framework, el <xref:Windows.Foundation.Uri?displayProperty=nameWithType> clase aparece como <xref:System.Uri?displayProperty=nameWithType> en Intellisense. El <xref:System.Uri?displayProperty=nameWithType> clase permite identificadores URI relativos, pero la <xref:Windows.Foundation.Uri?displayProperty=nameWithType> clase no lo hace. Esto también ocurre con los métodos que usted expone en componentes de [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Si su componente expone un método que toma un URI, la firma de su código incluye <xref:System.Uri?displayProperty=nameWithType>. Sin embargo, para los usuarios del componente, la firma incluye <xref:Windows.Foundation.Uri?displayProperty=nameWithType>. Un URI que se pase a su componente debe ser absoluto.  
  
 En este tema se muestra cómo detectar un URI absoluto y cómo crear uno al hacer referencia a un recurso del paquete de la aplicación.  
  
## <a name="detecting-and-using-an-absolute-uri"></a>Detectar y usar un URI absoluto  
 Use la propiedad <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> para asegurarse de que un URI sea absoluto antes de pasarlo a [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Utilizar esta propiedad es más eficaz que detectar y gestionar la excepción <xref:System.ArgumentException>.  
  
## <a name="using-an-absolute-uri-for-a-resource-in-the-app-package"></a>Usar un URI absoluto para un recurso del paquete de la aplicación  
 Si desea especificar un URI para un recurso incluido en el paquete de la aplicación, puede usar los esquemas `ms-appx` o `ms-appx-web` para crear un URI absoluto.  
  
 En el ejemplo siguiente se muestra cómo establecer el [origen](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.webview.source.aspx) propiedad para un [WebView](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.webview.aspx) control y la [origen](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.image.source.aspx) propiedad para un [imagen](http://msdn.microsoft.com/library/windows/apps/br242752.aspx) control a los recursos que se encuentran en una carpeta denominada páginas, utilizando XAML y código.  
  
 [!code-xaml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
 Para obtener más información sobre estos esquemas, vea [esquemas de URI](http://msdn.microsoft.com/library/windows/apps/jj655406.aspx) en el centro de desarrollo de Windows.  
  
## <a name="see-also"></a>Vea también  
 [Compatibilidad de .NET Framework con las aplicaciones de la Tienda Windows y Windows Runtime](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
