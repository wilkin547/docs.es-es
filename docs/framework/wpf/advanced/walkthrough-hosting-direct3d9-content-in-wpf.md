---
title: 'Tutorial: Hospedar contenido Direct3D9 en WPF'
ms.date: 03/30/2017
helpviewer_keywords:
- Direct3D9 [WPF interoperability], hosting Direct3D9 content
- WPF [WPF], hosting Direct3D9 content
ms.assetid: 60983736-0ab5-42cc-8b16-e9fbde261a43
ms.openlocfilehash: 1fa4c2347448e23bbf740093541ec2b834df6705
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "48777518"
---
# <a name="walkthrough-hosting-direct3d9-content-in-wpf"></a><span data-ttu-id="72fe6-102">Tutorial: Hospedar contenido Direct3D9 en WPF</span><span class="sxs-lookup"><span data-stu-id="72fe6-102">Walkthrough: Hosting Direct3D9 Content in WPF</span></span>
<span data-ttu-id="72fe6-103">En este tutorial se muestra cómo hospedar contenido Direct3D9 en una aplicación de Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="72fe6-103">This walkthrough shows how to host Direct3D9 content in a Windows Presentation Foundation (WPF) application.</span></span>  
  
 <span data-ttu-id="72fe6-104">En este tutorial, realizará las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="72fe6-104">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="72fe6-105">Cree un proyecto WPF para hospedar contenido Direct3D9.</span><span class="sxs-lookup"><span data-stu-id="72fe6-105">Create a WPF project to host the Direct3D9 content.</span></span>  
  
-   <span data-ttu-id="72fe6-106">Importar el contenido Direct3D9.</span><span class="sxs-lookup"><span data-stu-id="72fe6-106">Import the Direct3D9 content.</span></span>  
  
-   <span data-ttu-id="72fe6-107">Mostrar el contenido Direct3D9 mediante la <xref:System.Windows.Interop.D3DImage> clase.</span><span class="sxs-lookup"><span data-stu-id="72fe6-107">Display the Direct3D9 content by using the <xref:System.Windows.Interop.D3DImage> class.</span></span>  
  
 <span data-ttu-id="72fe6-108">Cuando termine, sabrá cómo hospedar contenido Direct3D9 en una aplicación WPF.</span><span class="sxs-lookup"><span data-stu-id="72fe6-108">When you are finished, you will know how to host Direct3D9 content in a WPF application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="72fe6-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="72fe6-109">Prerequisites</span></span>  
 <span data-ttu-id="72fe6-110">Necesita los componentes siguientes para completar este tutorial:</span><span class="sxs-lookup"><span data-stu-id="72fe6-110">You need the following components to complete this walkthrough:</span></span>  
  
-   <span data-ttu-id="72fe6-111">Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="72fe6-111">Visual Studio.</span></span>  
  
-   <span data-ttu-id="72fe6-112">DirectX SDK 9 o posterior.</span><span class="sxs-lookup"><span data-stu-id="72fe6-112">DirectX SDK 9 or later.</span></span>  
  
-   <span data-ttu-id="72fe6-113">Un archivo DLL que contiene contenido Direct3D9 en un formato compatible con WPF.</span><span class="sxs-lookup"><span data-stu-id="72fe6-113">A DLL that contains Direct3D9 content in a WPF-compatible format.</span></span> <span data-ttu-id="72fe6-114">Para obtener más información, consulte [interoperabilidad entre Direct3D9 y WPF](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md) y [Tutorial: crear contenido Direct3D9 para el hospedaje en WPF](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="72fe6-114">For more information, see [WPF and Direct3D9 Interoperation](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md) and [Walkthrough: Creating Direct3D9 Content for Hosting in WPF](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).</span></span>  
  
## <a name="creating-the-wpf-project"></a><span data-ttu-id="72fe6-115">Crear el proyecto WPF</span><span class="sxs-lookup"><span data-stu-id="72fe6-115">Creating the WPF Project</span></span>  
 <span data-ttu-id="72fe6-116">El primer paso es crear el proyecto para la aplicación de WPF.</span><span class="sxs-lookup"><span data-stu-id="72fe6-116">The first step is to create the project for the WPF application.</span></span>  
  
#### <a name="to-create-the-wpf-project"></a><span data-ttu-id="72fe6-117">Para crear el proyecto de WPF</span><span class="sxs-lookup"><span data-stu-id="72fe6-117">To create the WPF project</span></span>  
  
-   <span data-ttu-id="72fe6-118">Cree un nuevo proyecto de aplicación de WPF en Visual C# denominado `D3DHost`.</span><span class="sxs-lookup"><span data-stu-id="72fe6-118">Create a new WPF Application project in Visual C# named `D3DHost`.</span></span> <span data-ttu-id="72fe6-119">Para obtener más información, vea [Cómo: Crear un nuevo proyecto de aplicación de WPF](https://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span><span class="sxs-lookup"><span data-stu-id="72fe6-119">For more information, see [How to: Create a New WPF Application Project](https://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span></span>  
  
     <span data-ttu-id="72fe6-120">MainWindow.xaml se abre en el [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72fe6-120">MainWindow.xaml opens in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
## <a name="importing-the-direct3d9-content"></a><span data-ttu-id="72fe6-121">Importar el contenido Direct3D9</span><span class="sxs-lookup"><span data-stu-id="72fe6-121">Importing the Direct3D9 Content</span></span>  
 <span data-ttu-id="72fe6-122">Importar el contenido Direct3D9 desde una DLL no administrada mediante el `DllImport` atributo.</span><span class="sxs-lookup"><span data-stu-id="72fe6-122">You import the Direct3D9 content from an unmanaged DLL by using the `DllImport` attribute.</span></span>  
  
#### <a name="to-import-direct3d9-content"></a><span data-ttu-id="72fe6-123">Para importar contenido Direct3D9</span><span class="sxs-lookup"><span data-stu-id="72fe6-123">To import Direct3D9 content</span></span>  
  
1.  <span data-ttu-id="72fe6-124">Abra MainWindow.xaml.cs en el Editor de código.</span><span class="sxs-lookup"><span data-stu-id="72fe6-124">Open MainWindow.xaml.cs in the Code Editor.</span></span>  
  
2.  <span data-ttu-id="72fe6-125">Reemplace el código generado automáticamente por el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="72fe6-125">Replace the automatically generated code with the following code.</span></span>  
  
     [!code-csharp[System.Windows.Interop.D3DImage#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml.cs#1)]  
  
## <a name="hosting-the-direct3d9-content"></a><span data-ttu-id="72fe6-126">Hospedar contenido Direct3D9</span><span class="sxs-lookup"><span data-stu-id="72fe6-126">Hosting the Direct3D9 Content</span></span>  
 <span data-ttu-id="72fe6-127">Por último, use la <xref:System.Windows.Interop.D3DImage> clase para hospedar contenido Direct3D9.</span><span class="sxs-lookup"><span data-stu-id="72fe6-127">Finally, use the <xref:System.Windows.Interop.D3DImage> class to host the Direct3D9 content.</span></span>  
  
#### <a name="to-host-the-direct3d9-content"></a><span data-ttu-id="72fe6-128">Para hospedar contenido Direct3D9</span><span class="sxs-lookup"><span data-stu-id="72fe6-128">To host the Direct3D9 content</span></span>  
  
1.  <span data-ttu-id="72fe6-129">En MainWindow.xaml, reemplace el XAML generado automáticamente por el XAML siguiente.</span><span class="sxs-lookup"><span data-stu-id="72fe6-129">In MainWindow.xaml, replace the automatically generated XAML with the following XAML.</span></span>  
  
     [!code-xaml[System.Windows.Interop.D3DImage#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml#10)]  
  
2.  <span data-ttu-id="72fe6-130">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="72fe6-130">Build the project.</span></span>  
  
3.  <span data-ttu-id="72fe6-131">Copie el archivo DLL que contiene el contenido Direct3D9 en la carpeta bin/Debug.</span><span class="sxs-lookup"><span data-stu-id="72fe6-131">Copy the DLL that contains the Direct3D9 content to the bin/Debug folder.</span></span>  
  
4.  <span data-ttu-id="72fe6-132">Presione F5 para ejecutar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="72fe6-132">Press F5 to run the project.</span></span>  
  
     <span data-ttu-id="72fe6-133">El contenido Direct3D9 aparece dentro de la aplicación de WPF.</span><span class="sxs-lookup"><span data-stu-id="72fe6-133">The Direct3D9 content appears within the WPF application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72fe6-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="72fe6-134">See Also</span></span>  
 <xref:System.Windows.Interop.D3DImage>  
 [<span data-ttu-id="72fe6-135">Consideraciones de rendimiento para la interoperabilidad entre Direct3D9 y WPF</span><span class="sxs-lookup"><span data-stu-id="72fe6-135">Performance Considerations for Direct3D9 and WPF Interoperability</span></span>](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md)
