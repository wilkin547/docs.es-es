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
ms.openlocfilehash: 7152fb02abf430c0d0e27b82550e4006e3958e93
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288893"
---
# <a name="passing-a-uri-to-the-windows-runtime"></a>Pasar un URI a Windows Runtime
Los métodos de Windows Runtime solo aceptan URI absolutos. Si pasa un URI relativo a un método Windows Runtime, <xref:System.ArgumentException> se produce una excepción. Este es el motivo: cuando se usa el Windows Runtime en .NET Framework código, la <xref:Windows.Foundation.Uri?displayProperty=nameWithType> clase aparece como <xref:System.Uri?displayProperty=nameWithType> en IntelliSense. La <xref:System.Uri?displayProperty=nameWithType> clase permite los URI relativos, pero la <xref:Windows.Foundation.Uri?displayProperty=nameWithType> clase no. Esto también se aplica a los métodos que se exponen en Windows Runtime componentes. Si su componente expone un método que toma un URI, la firma de su código incluye <xref:System.Uri?displayProperty=nameWithType>. Sin embargo, para los usuarios del componente, la firma incluye <xref:Windows.Foundation.Uri?displayProperty=nameWithType> . Un URI que se pase a su componente debe ser absoluto.  
  
En este tema se muestra cómo detectar un URI absoluto y cómo crear uno al hacer referencia a un recurso del paquete de la aplicación.  
  
## <a name="detecting-and-using-an-absolute-uri"></a>Detectar y usar un URI absoluto  
Utilice la <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> propiedad para asegurarse de que un URI sea absoluto antes de pasarlo a la Windows Runtime. Utilizar esta propiedad es más eficaz que detectar y gestionar la excepción <xref:System.ArgumentException>.  
  
## <a name="using-an-absolute-uri-for-a-resource-in-the-app-package"></a>Usar un URI absoluto para un recurso del paquete de la aplicación  
Si desea especificar un URI para un recurso incluido en el paquete de la aplicación, puede usar los esquemas `ms-appx` o `ms-appx-web` para crear un URI absoluto.  
  
En el ejemplo siguiente se muestra cómo establecer la <xref:Windows.UI.Xaml.Controls.WebView.Source%2A> propiedad de un <xref:Windows.UI.Xaml.Controls.WebView> control y la <xref:Windows.UI.Xaml.Controls.Image.Source%2A> propiedad de un <xref:Windows.UI.Xaml.Controls.Image> control en los recursos incluidos en una carpeta denominada pages, mediante XAML y código.  
  
[!code-xaml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
Para obtener más información sobre estos esquemas, consulte [Esquemas de URI](/windows/uwp/app-resources/uri-schemes) en el Centro de desarrollo de Windows.  
  
## <a name="see-also"></a>Consulte también

- [Compatibilidad de .NET Framework con las aplicaciones de la Tienda Windows y Windows en tiempo de ejecución](support-for-windows-store-apps-and-windows-runtime.md)
