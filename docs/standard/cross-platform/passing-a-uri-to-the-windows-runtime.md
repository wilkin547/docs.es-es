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
# <a name="passing-a-uri-to-the-windows-runtime"></a><span data-ttu-id="6f320-102">Pasar un URI a Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="6f320-102">Passing a URI to the Windows Runtime</span></span>
<span data-ttu-id="6f320-103">Los métodos de Windows Runtime solo aceptan URI absolutos.</span><span class="sxs-lookup"><span data-stu-id="6f320-103">Windows Runtime methods accept only absolute URIs.</span></span> <span data-ttu-id="6f320-104">Si pasa un URI relativo a un método Windows Runtime, se produce una excepción <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="6f320-104">If you pass a relative URI to a Windows Runtime method, an <xref:System.ArgumentException> exception is thrown.</span></span> <span data-ttu-id="6f320-105">Este es el motivo: cuando se usa el Windows Runtime en .NET Framework código, la clase <xref:Windows.Foundation.Uri?displayProperty=nameWithType> aparece como <xref:System.Uri?displayProperty=nameWithType> en IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="6f320-105">Here's why: When you use the Windows Runtime in .NET Framework code, the <xref:Windows.Foundation.Uri?displayProperty=nameWithType> class appears as <xref:System.Uri?displayProperty=nameWithType> in Intellisense.</span></span> <span data-ttu-id="6f320-106">La clase <xref:System.Uri?displayProperty=nameWithType> permite los URI relativos, pero la clase <xref:Windows.Foundation.Uri?displayProperty=nameWithType> no.</span><span class="sxs-lookup"><span data-stu-id="6f320-106">The <xref:System.Uri?displayProperty=nameWithType> class allows relative URIs, but the <xref:Windows.Foundation.Uri?displayProperty=nameWithType> class does not.</span></span> <span data-ttu-id="6f320-107">Esto también se aplica a los métodos que se exponen en Windows Runtime componentes.</span><span class="sxs-lookup"><span data-stu-id="6f320-107">This is also true for methods you expose in Windows Runtime Components.</span></span> <span data-ttu-id="6f320-108">Si su componente expone un método que toma un URI, la firma de su código incluye <xref:System.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6f320-108">If your component exposes a method that takes a URI, the signature in your code includes <xref:System.Uri?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6f320-109">Sin embargo, para los usuarios del componente, la firma incluye <xref:Windows.Foundation.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6f320-109">However, to users of your component, the signature includes <xref:Windows.Foundation.Uri?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6f320-110">Un URI que se pase a su componente debe ser absoluto.</span><span class="sxs-lookup"><span data-stu-id="6f320-110">A URI that is passed to your component must be an absolute URI.</span></span>  
  
<span data-ttu-id="6f320-111">En este tema se muestra cómo detectar un URI absoluto y cómo crear uno al hacer referencia a un recurso del paquete de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6f320-111">This topic shows how to detect an absolute URI and how to create one when referring to a resource in the app package.</span></span>  
  
## <a name="detecting-and-using-an-absolute-uri"></a><span data-ttu-id="6f320-112">Detectar y usar un URI absoluto</span><span class="sxs-lookup"><span data-stu-id="6f320-112">Detecting and using an absolute URI</span></span>  
<span data-ttu-id="6f320-113">Use la propiedad <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> para asegurarse de que un URI sea absoluto antes de pasarlo al Windows Runtime.</span><span class="sxs-lookup"><span data-stu-id="6f320-113">Use the <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> property to ensure that a URI is absolute before passing it to the Windows Runtime.</span></span> <span data-ttu-id="6f320-114">Utilizar esta propiedad es más eficaz que detectar y gestionar la excepción <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="6f320-114">Using this property is more efficient than catching and handling the <xref:System.ArgumentException> exception.</span></span>  
  
## <a name="using-an-absolute-uri-for-a-resource-in-the-app-package"></a><span data-ttu-id="6f320-115">Usar un URI absoluto para un recurso del paquete de la aplicación</span><span class="sxs-lookup"><span data-stu-id="6f320-115">Using an absolute URI for a resource in the app package</span></span>  
<span data-ttu-id="6f320-116">Si desea especificar un URI para un recurso incluido en el paquete de la aplicación, puede usar los esquemas `ms-appx` o `ms-appx-web` para crear un URI absoluto.</span><span class="sxs-lookup"><span data-stu-id="6f320-116">If you want to specify a URI for a resource that your app package contains, you can use the `ms-appx` or `ms-appx-web` scheme to create an absolute URI.</span></span>  
  
<span data-ttu-id="6f320-117">En el ejemplo siguiente se muestra cómo establecer la propiedad <xref:Windows.UI.Xaml.Controls.WebView.Source%2A> para un control <xref:Windows.UI.Xaml.Controls.WebView> y la propiedad <xref:Windows.UI.Xaml.Controls.Image.Source%2A> de un control <xref:Windows.UI.Xaml.Controls.Image> en los recursos incluidos en una carpeta denominada pages, mediante XAML y código.</span><span class="sxs-lookup"><span data-stu-id="6f320-117">The following example shows how to set the <xref:Windows.UI.Xaml.Controls.WebView.Source%2A> property for a <xref:Windows.UI.Xaml.Controls.WebView> control and the <xref:Windows.UI.Xaml.Controls.Image.Source%2A> property for an <xref:Windows.UI.Xaml.Controls.Image> control to resources that are contained in a folder named Pages, using both XAML and code.</span></span>  
  
[!code-xaml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
<span data-ttu-id="6f320-118">Para obtener más información sobre estos esquemas, consulte [esquemas de URI](/windows/uwp/app-resources/uri-schemes) en el centro de desarrollo de Windows.</span><span class="sxs-lookup"><span data-stu-id="6f320-118">For more information about these schemes, see [URI schemes](/windows/uwp/app-resources/uri-schemes) in the Windows Dev Center.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f320-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6f320-119">See also</span></span>

- [<span data-ttu-id="6f320-120">Compatibilidad de .NET Framework con las aplicaciones de la Tienda Windows y Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="6f320-120">.NET Framework Support for Windows Store Apps and Windows Runtime</span></span>](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
