---
description: 'Obtenga más información sobre: Pasar un URI a Windows Runtime'
title: Pasar un URI a Windows Runtime
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Runtime, .NET Framework support for
- Windows Runtime, passing a URI to
ms.assetid: 3eb5ce6f-f304-4f87-8e81-0f25092f5ad4
ms.openlocfilehash: 918f8ea71f4b23aeaf2a1295f2edd043a73a95ed
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "102402272"
---
# <a name="passing-a-uri-to-the-windows-runtime"></a><span data-ttu-id="ceba7-103">Pasar un URI a Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="ceba7-103">Passing a URI to the Windows Runtime</span></span>

<span data-ttu-id="ceba7-104">Los métodos de Windows Runtime solo aceptan URI absolutos.</span><span class="sxs-lookup"><span data-stu-id="ceba7-104">Windows Runtime methods accept only absolute URIs.</span></span> <span data-ttu-id="ceba7-105">Si se pasa un URI relativo a un método de Windows Runtime, se produce una excepción <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="ceba7-105">If you pass a relative URI to a Windows Runtime method, an <xref:System.ArgumentException> exception is thrown.</span></span> <span data-ttu-id="ceba7-106">El motivo es el siguiente: cuando se usa Windows Runtime en el código de .NET Framework, la clase <xref:Windows.Foundation.Uri?displayProperty=nameWithType> aparece como <xref:System.Uri?displayProperty=nameWithType> en Intellisense.</span><span class="sxs-lookup"><span data-stu-id="ceba7-106">Here's why: When you use the Windows Runtime in .NET Framework code, the <xref:Windows.Foundation.Uri?displayProperty=nameWithType> class appears as <xref:System.Uri?displayProperty=nameWithType> in Intellisense.</span></span> <span data-ttu-id="ceba7-107">La clase <xref:System.Uri?displayProperty=nameWithType> permite los URI relativos, pero la clase <xref:Windows.Foundation.Uri?displayProperty=nameWithType> no.</span><span class="sxs-lookup"><span data-stu-id="ceba7-107">The <xref:System.Uri?displayProperty=nameWithType> class allows relative URIs, but the <xref:Windows.Foundation.Uri?displayProperty=nameWithType> class does not.</span></span> <span data-ttu-id="ceba7-108">Esto también ocurre con los métodos que usted expone en componentes de Windows Runtime.</span><span class="sxs-lookup"><span data-stu-id="ceba7-108">This is also true for methods you expose in Windows Runtime Components.</span></span> <span data-ttu-id="ceba7-109">Si su componente expone un método que toma un URI, la firma de su código incluye <xref:System.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ceba7-109">If your component exposes a method that takes a URI, the signature in your code includes <xref:System.Uri?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ceba7-110">Sin embargo, para los usuarios del componente, la firma incluye <xref:Windows.Foundation.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ceba7-110">However, to users of your component, the signature includes <xref:Windows.Foundation.Uri?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ceba7-111">Un URI que se pase a su componente debe ser absoluto.</span><span class="sxs-lookup"><span data-stu-id="ceba7-111">A URI that is passed to your component must be an absolute URI.</span></span>  
  
<span data-ttu-id="ceba7-112">En este tema se muestra cómo detectar un URI absoluto y cómo crear uno al hacer referencia a un recurso del paquete de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ceba7-112">This topic shows how to detect an absolute URI and how to create one when referring to a resource in the app package.</span></span>  
  
## <a name="detecting-and-using-an-absolute-uri"></a><span data-ttu-id="ceba7-113">Detectar y usar un URI absoluto</span><span class="sxs-lookup"><span data-stu-id="ceba7-113">Detecting and using an absolute URI</span></span>  

<span data-ttu-id="ceba7-114">Use la propiedad <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> para asegurarse de que un URI sea absoluto antes de pasarlo a Windows Runtime.</span><span class="sxs-lookup"><span data-stu-id="ceba7-114">Use the <xref:System.Uri.IsAbsoluteUri%2A?displayProperty=nameWithType> property to ensure that a URI is absolute before passing it to the Windows Runtime.</span></span> <span data-ttu-id="ceba7-115">Utilizar esta propiedad es más eficaz que detectar y gestionar la excepción <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="ceba7-115">Using this property is more efficient than catching and handling the <xref:System.ArgumentException> exception.</span></span>  
  
## <a name="using-an-absolute-uri-for-a-resource-in-the-app-package"></a><span data-ttu-id="ceba7-116">Usar un URI absoluto para un recurso del paquete de la aplicación</span><span class="sxs-lookup"><span data-stu-id="ceba7-116">Using an absolute URI for a resource in the app package</span></span>  

<span data-ttu-id="ceba7-117">Si desea especificar un URI para un recurso incluido en el paquete de la aplicación, puede usar los esquemas `ms-appx` o `ms-appx-web` para crear un URI absoluto.</span><span class="sxs-lookup"><span data-stu-id="ceba7-117">If you want to specify a URI for a resource that your app package contains, you can use the `ms-appx` or `ms-appx-web` scheme to create an absolute URI.</span></span>  
  
<span data-ttu-id="ceba7-118">En el ejemplo siguiente se muestra cómo establecer la propiedad <xref:Windows.UI.Xaml.Controls.WebView.Source%2A> de un control <xref:Windows.UI.Xaml.Controls.WebView> y la propiedad <xref:Windows.UI.Xaml.Controls.Image.Source%2A> de un control <xref:Windows.UI.Xaml.Controls.Image> en recursos incluidos en una carpeta denominada "Pages", usando para ello XAML y código.</span><span class="sxs-lookup"><span data-stu-id="ceba7-118">The following example shows how to set the <xref:Windows.UI.Xaml.Controls.WebView.Source%2A> property for a <xref:Windows.UI.Xaml.Controls.WebView> control and the <xref:Windows.UI.Xaml.Controls.Image.Source%2A> property for an <xref:Windows.UI.Xaml.Controls.Image> control to resources that are contained in a folder named Pages, using both XAML and code.</span></span>  
  
[!code-xaml[System.URIToWindowsURI#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml#1)]  
[!code-csharp[System.URIToWindowsURI#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.uritowindowsuri/cs/mainpage.xaml.cs#2)]
[!code-vb[System.URIToWindowsURI#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.uritowindowsuri/vb/mainpage.xaml.vb#2)]  
  
<span data-ttu-id="ceba7-119">Para obtener más información sobre estos esquemas, consulte [Esquemas de URI](/windows/uwp/app-resources/uri-schemes) en el Centro de desarrollo de Windows.</span><span class="sxs-lookup"><span data-stu-id="ceba7-119">For more information about these schemes, see [URI schemes](/windows/uwp/app-resources/uri-schemes) in the Windows Dev Center.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ceba7-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ceba7-120">See also</span></span>

- [<span data-ttu-id="ceba7-121">Compatibilidad de .NET Framework con las aplicaciones de la Tienda Windows y Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="ceba7-121">.NET Framework Support for Windows Store Apps and Windows Runtime</span></span>](support-for-windows-store-apps-and-windows-runtime.md)
