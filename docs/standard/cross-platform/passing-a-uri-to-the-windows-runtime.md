---
title: Pasar un URI a Windows Runtime
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Runtime, .NET Framework support for
- Windows Runtime, passing a URI to
ms.assetid: 3eb5ce6f-f304-4f87-8e81-0f25092f5ad4
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 4ef77fb9e196abf046e0d4648a49b5d4d3fad47e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="passing-a-uri-to-the-windows-runtime"></a><span data-ttu-id="778a2-102">Pasar un URI a Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="778a2-102">Passing a URI to the Windows Runtime</span></span>
<span data-ttu-id="778a2-103">Los métodos de Windows Runtime solo aceptan URI absolutos.</span><span class="sxs-lookup"><span data-stu-id="778a2-103">Windows Runtime methods accept only absolute URIs.</span></span> <span data-ttu-id="778a2-104">Si se pasa un URI relativo a un método [!INCLUDE[wrt](../../../includes/wrt-md.md)], se produce una excepción <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="778a2-104">If you pass a relative URI to a [!INCLUDE[wrt](../../../includes/wrt-md.md)] method, an <xref:System.ArgumentException> exception is thrown.</span></span> <span data-ttu-id="778a2-105">Esta es la razón: cuando se usa el [!INCLUDE[wrt](../../../includes/wrt-md.md)] en el código de .NET Framework, el [Windows.Foundation.Uri](http://go.microsoft.com/fwlink/p/?LinkId=238376) clase aparece como <xref:System.Uri?displayProperty=nameWithType> en Intellisense.</span><span class="sxs-lookup"><span data-stu-id="778a2-105">Here's why: When you use the [!INCLUDE[wrt](../../../includes/wrt-md.md)] in .NET Framework code, the [Windows.Foundation.Uri](http://go.microsoft.com/fwlink/p/?LinkId=238376) class appears as <xref:System.Uri?displayProperty=nameWithType> in Intellisense.</span></span> <span data-ttu-id="778a2-106">El <xref:System.Uri?displayProperty=nameWithType> clase permite identificadores URI relativos, pero la [Windows.Foundation.Uri](http://go.microsoft.com/fwlink/p/?LinkId=238376) clase no lo hace.</span><span class="sxs-lookup"><span data-stu-id="778a2-106">The <xref:System.Uri?displayProperty=nameWithType> class allows relative URIs, but the [Windows.Foundation.Uri](http://go.microsoft.com/fwlink/p/?LinkId=238376) class does not.</span></span> <span data-ttu-id="778a2-107">Esto también ocurre con los métodos que usted expone en componentes de [!INCLUDE[wrt](../../../includes/wrt-md.md)].</span><span class="sxs-lookup"><span data-stu-id="778a2-107">This is also true for methods you expose in [!INCLUDE[wrt](../../../includes/wrt-md.md)] Components.</span></span> <span data-ttu-id="778a2-108">Si su componente expone un método que toma un URI, la firma de su código incluye <xref:System.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="778a2-108">If your component exposes a method that takes a URI, the signature in your code includes <xref:System.Uri?displayProperty=nameWithType>.</span></span> <span data-ttu-id="778a2-109">Sin embargo, para los usuarios del componente, la firma incluye [Windows.Foundation.Uri](http://go.microsoft.com/fwlink/p/?LinkId=238376).</span><span class="sxs-lookup"><span data-stu-id="778a2-109">However, to users of your component, the signature includes [Windows.Foundation.Uri](http://go.microsoft.com/fwlink/p/?LinkId=238376).</span></span> <span data-ttu-id="778a2-110">Un URI que se pase a su componente debe ser absoluto.</span><span class="sxs-lookup"><span data-stu-id="778a2-110">A URI that is passed to your component must be an absolute URI.</span></span>  
  
 <span data-ttu-id="778a2-111">En este tema se muestra cómo detectar un URI absoluto y cómo crear uno al hacer referencia a un recurso del paquete de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="778a2-111">This topic shows how to detect an absolute URI and how to create one when referring to a resource in the app package.</span></span>  
  
## <a name="detecting-and-using-an-absolute-uri"></a><span data-ttu-id="778a2-112">Detectar y usar un URI absoluto</span><span class="sxs-lookup"><span data-stu-id="778a2-112">Detecting and using an absolute URI</span></span>  
 <span data-ttu-id="778a2-113">Use la propiedad <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> para asegurarse de que un URI sea absoluto antes de pasarlo a [!INCLUDE[wrt](../../../includes/wrt-md.md)].</span><span class="sxs-lookup"><span data-stu-id="778a2-113">Use the <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> property to ensure that a URI is absolute before passing it to the [!INCLUDE[wrt](../../../includes/wrt-md.md)].</span></span> <span data-ttu-id="778a2-114">Utilizar esta propiedad es más eficaz que detectar y gestionar la excepción <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="778a2-114">Using this property is more efficient than catching and handling the <xref:System.ArgumentException> exception.</span></span>  
  
## <a name="using-an-absolute-uri-for-a-resource-in-the-app-package"></a><span data-ttu-id="778a2-115">Usar un URI absoluto para un recurso del paquete de la aplicación</span><span class="sxs-lookup"><span data-stu-id="778a2-115">Using an absolute URI for a resource in the app package</span></span>  
 <span data-ttu-id="778a2-116">Si desea especificar un URI para un recurso incluido en el paquete de la aplicación, puede usar los esquemas `ms-appx` o `ms-appx-web` para crear un URI absoluto.</span><span class="sxs-lookup"><span data-stu-id="778a2-116">If you want to specify a URI for a resource that your app package contains, you can use the `ms-appx` or `ms-appx-web` scheme to create an absolute URI.</span></span>  
  
 <span data-ttu-id="778a2-117">En el ejemplo siguiente se muestra cómo establecer el [origen](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.webview.source.aspx) propiedad para un [WebView](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.webview.aspx) control y la [origen](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.image.source.aspx) propiedad para un [imagen](http://msdn.microsoft.com/library/windows/apps/br242752.aspx) control a los recursos que se encuentran en una carpeta denominada páginas, utilizando XAML y código.</span><span class="sxs-lookup"><span data-stu-id="778a2-117">The following example shows how to set the [Source](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.webview.source.aspx) property for a [WebView](http://msdn.microsoft.com/library/windows/apps/xaml/windows.ui.xaml.controls.webview.aspx) control and the [Source](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.image.source.aspx) property for an [Image](http://msdn.microsoft.com/library/windows/apps/br242752.aspx) control to resources that are contained in a folder named Pages, using both XAML and code.</span></span>  
  
 [!code-xaml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
 <span data-ttu-id="778a2-118">Para obtener más información sobre estos esquemas, vea [esquemas de URI](http://msdn.microsoft.com/library/windows/apps/jj655406.aspx) en el centro de desarrollo de Windows.</span><span class="sxs-lookup"><span data-stu-id="778a2-118">For more information about these schemes, see [URI schemes](http://msdn.microsoft.com/library/windows/apps/jj655406.aspx) in the Windows Dev Center.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="778a2-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="778a2-119">See Also</span></span>  
 [<span data-ttu-id="778a2-120">Compatibilidad de .NET Framework con las aplicaciones de la Tienda Windows y Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="778a2-120">.NET Framework Support for Windows Store Apps and Windows Runtime</span></span>](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
