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
ms.openlocfilehash: 71d427c2d602efbd92dc0128b1fada85a987904a
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "77123628"
---
# <a name="passing-a-uri-to-the-windows-runtime"></a>Pasar un URI a Windows Runtime
Los métodos de Windows Runtime solo aceptan URI absolutos. Si pasa un URI relativo a un método Windows Runtime, se produce una excepción <xref:System.ArgumentException>. Este es el motivo: cuando se usa el Windows Runtime en .NET Framework código, la clase <xref:Windows.Foundation.Uri?displayProperty=nameWithType> aparece como <xref:System.Uri?displayProperty=nameWithType> en IntelliSense. La clase <xref:System.Uri?displayProperty=nameWithType> permite los URI relativos, pero la clase <xref:Windows.Foundation.Uri?displayProperty=nameWithType> no. Esto también se aplica a los métodos que se exponen en Windows Runtime componentes. Si su componente expone un método que toma un URI, la firma de su código incluye <xref:System.Uri?displayProperty=nameWithType>. Sin embargo, para los usuarios del componente, la firma incluye <xref:Windows.Foundation.Uri?displayProperty=nameWithType>. Un URI que se pase a su componente debe ser absoluto.  
  
En este tema se muestra cómo detectar un URI absoluto y cómo crear uno al hacer referencia a un recurso del paquete de la aplicación.  
  
## <a name="detecting-and-using-an-absolute-uri"></a>Detectar y usar un URI absoluto  
Use la propiedad <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> para asegurarse de que un URI sea absoluto antes de pasarlo al Windows Runtime. Utilizar esta propiedad es más eficaz que detectar y gestionar la excepción <xref:System.ArgumentException>.  
  
## <a name="using-an-absolute-uri-for-a-resource-in-the-app-package"></a>Usar un URI absoluto para un recurso del paquete de la aplicación  
Si desea especificar un URI para un recurso incluido en el paquete de la aplicación, puede usar los esquemas `ms-appx` o `ms-appx-web` para crear un URI absoluto.  
  
En el ejemplo siguiente se muestra cómo establecer la propiedad <xref:Windows.UI.Xaml.Controls.WebView.Source%2A> para un control <xref:Windows.UI.Xaml.Controls.WebView> y la propiedad <xref:Windows.UI.Xaml.Controls.Image.Source%2A> de un control <xref:Windows.UI.Xaml.Controls.Image> en los recursos incluidos en una carpeta denominada pages, mediante XAML y código.  
  
[!code-xaml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
Para obtener más información sobre estos esquemas, consulte [esquemas de URI](/windows/uwp/app-resources/uri-schemes) en el centro de desarrollo de Windows.  
  
## <a name="see-also"></a>Consulte también

- [Compatibilidad de .NET Framework con las aplicaciones de la Tienda Windows y Windows Runtime](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
