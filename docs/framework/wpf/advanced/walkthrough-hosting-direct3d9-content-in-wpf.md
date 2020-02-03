---
title: Hospedar contenido de Direct3D9 en WPF
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Direct3D9 [WPF interoperability], hosting Direct3D9 content
- WPF [WPF], hosting Direct3D9 content
ms.assetid: 60983736-0ab5-42cc-8b16-e9fbde261a43
ms.openlocfilehash: e65b0c59268b44abed289e54181bf0bda9355664
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742607"
---
# <a name="walkthrough-hosting-direct3d9-content-in-wpf"></a><span data-ttu-id="66531-102">Tutorial: Hospedar contenido Direct3D9 en WPF</span><span class="sxs-lookup"><span data-stu-id="66531-102">Walkthrough: Hosting Direct3D9 Content in WPF</span></span>

<span data-ttu-id="66531-103">En este tutorial se muestra cómo hospedar contenido de Direct3D9 en una aplicación Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="66531-103">This walkthrough shows how to host Direct3D9 content in a Windows Presentation Foundation (WPF) application.</span></span>

<span data-ttu-id="66531-104">En este tutorial, realizará las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="66531-104">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="66531-105">Cree un proyecto de WPF para hospedar el contenido de Direct3D9.</span><span class="sxs-lookup"><span data-stu-id="66531-105">Create a WPF project to host the Direct3D9 content.</span></span>

- <span data-ttu-id="66531-106">Importe el contenido de Direct3D9.</span><span class="sxs-lookup"><span data-stu-id="66531-106">Import the Direct3D9 content.</span></span>

- <span data-ttu-id="66531-107">Mostrar el contenido de Direct3D9 mediante la clase <xref:System.Windows.Interop.D3DImage>.</span><span class="sxs-lookup"><span data-stu-id="66531-107">Display the Direct3D9 content by using the <xref:System.Windows.Interop.D3DImage> class.</span></span>

 <span data-ttu-id="66531-108">Cuando haya terminado, sabrá cómo hospedar contenido de Direct3D9 en una aplicación WPF.</span><span class="sxs-lookup"><span data-stu-id="66531-108">When you are finished, you will know how to host Direct3D9 content in a WPF application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="66531-109">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="66531-109">Prerequisites</span></span>

<span data-ttu-id="66531-110">Necesitará los componentes siguientes para completar este tutorial:</span><span class="sxs-lookup"><span data-stu-id="66531-110">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="66531-111">Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="66531-111">Visual Studio.</span></span>

- <span data-ttu-id="66531-112">DirectX SDK 9 o posterior.</span><span class="sxs-lookup"><span data-stu-id="66531-112">DirectX SDK 9 or later.</span></span>

- <span data-ttu-id="66531-113">Un archivo DLL que contiene contenido de Direct3D9 en un formato compatible con WPF.</span><span class="sxs-lookup"><span data-stu-id="66531-113">A DLL that contains Direct3D9 content in a WPF-compatible format.</span></span> <span data-ttu-id="66531-114">Para obtener más información, consulte [interoperabilidad de WPF y Direct3D9](wpf-and-direct3d9-interoperation.md) y [Tutorial: crear contenido de Direct3D9 para hospedarlo en WPF](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="66531-114">For more information, see [WPF and Direct3D9 Interoperation](wpf-and-direct3d9-interoperation.md) and [Walkthrough: Creating Direct3D9 Content for Hosting in WPF](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).</span></span>

## <a name="creating-the-wpf-project"></a><span data-ttu-id="66531-115">Crear el proyecto de WPF</span><span class="sxs-lookup"><span data-stu-id="66531-115">Creating the WPF Project</span></span>

<span data-ttu-id="66531-116">El primer paso es crear el proyecto para la aplicación WPF.</span><span class="sxs-lookup"><span data-stu-id="66531-116">The first step is to create the project for the WPF application.</span></span>

### <a name="to-create-the-wpf-project"></a><span data-ttu-id="66531-117">Para crear el proyecto de WPF</span><span class="sxs-lookup"><span data-stu-id="66531-117">To create the WPF project</span></span>

<span data-ttu-id="66531-118">Cree un nuevo proyecto de aplicación de WPF C# en visual con el nombre `D3DHost`.</span><span class="sxs-lookup"><span data-stu-id="66531-118">Create a new WPF Application project in Visual C# named `D3DHost`.</span></span> <span data-ttu-id="66531-119">Para obtener más información, vea [Tutorial: Mi primera aplicación de escritorio WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span><span class="sxs-lookup"><span data-stu-id="66531-119">For more information, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

<span data-ttu-id="66531-120">MainWindow. XAML se abre en WPF Designer.</span><span class="sxs-lookup"><span data-stu-id="66531-120">MainWindow.xaml opens in the WPF Designer.</span></span>

## <a name="importing-the-direct3d9-content"></a><span data-ttu-id="66531-121">Importar el contenido de Direct3D9</span><span class="sxs-lookup"><span data-stu-id="66531-121">Importing the Direct3D9 Content</span></span>

<span data-ttu-id="66531-122">Importe el contenido de Direct3D9 desde un archivo DLL no administrado mediante el `DllImport` atributo.</span><span class="sxs-lookup"><span data-stu-id="66531-122">You import the Direct3D9 content from an unmanaged DLL by using the `DllImport` attribute.</span></span>

### <a name="to-import-direct3d9-content"></a><span data-ttu-id="66531-123">Para importar el contenido de Direct3D9</span><span class="sxs-lookup"><span data-stu-id="66531-123">To import Direct3D9 content</span></span>

1. <span data-ttu-id="66531-124">Abra MainWindow.xaml.cs en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="66531-124">Open MainWindow.xaml.cs in the Code Editor.</span></span>

2. <span data-ttu-id="66531-125">Reemplace el código generado automáticamente por el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="66531-125">Replace the automatically generated code with the following code.</span></span>

    [!code-csharp[System.Windows.Interop.D3DImage#1](~/samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml.cs#1)]

## <a name="hosting-the-direct3d9-content"></a><span data-ttu-id="66531-126">Hospedar el contenido de Direct3D9</span><span class="sxs-lookup"><span data-stu-id="66531-126">Hosting the Direct3D9 Content</span></span>

<span data-ttu-id="66531-127">Por último, utilice la clase <xref:System.Windows.Interop.D3DImage> para hospedar el contenido de Direct3D9.</span><span class="sxs-lookup"><span data-stu-id="66531-127">Finally, use the <xref:System.Windows.Interop.D3DImage> class to host the Direct3D9 content.</span></span>

### <a name="to-host-the-direct3d9-content"></a><span data-ttu-id="66531-128">Para hospedar el contenido de Direct3D9</span><span class="sxs-lookup"><span data-stu-id="66531-128">To host the Direct3D9 content</span></span>

1. <span data-ttu-id="66531-129">En MainWindow. XAML, reemplace el código XAML generado automáticamente por el código XAML siguiente.</span><span class="sxs-lookup"><span data-stu-id="66531-129">In MainWindow.xaml, replace the automatically generated XAML with the following XAML.</span></span>

    [!code-xaml[System.Windows.Interop.D3DImage#10](~/samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml#10)]

2. <span data-ttu-id="66531-130">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="66531-130">Build the project.</span></span>

3. <span data-ttu-id="66531-131">Copie el archivo DLL que contiene el contenido de Direct3D9 en la carpeta bin/Debug.</span><span class="sxs-lookup"><span data-stu-id="66531-131">Copy the DLL that contains the Direct3D9 content to the bin/Debug folder.</span></span>

4. <span data-ttu-id="66531-132">Presione F5 para ejecutar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="66531-132">Press F5 to run the project.</span></span>

    <span data-ttu-id="66531-133">El contenido de Direct3D9 aparece dentro de la aplicación WPF.</span><span class="sxs-lookup"><span data-stu-id="66531-133">The Direct3D9 content appears within the WPF application.</span></span>

## <a name="see-also"></a><span data-ttu-id="66531-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="66531-134">See also</span></span>

- <xref:System.Windows.Interop.D3DImage>
- [<span data-ttu-id="66531-135">Consideraciones de rendimiento para la interoperabilidad entre Direct3D9 y WPF</span><span class="sxs-lookup"><span data-stu-id="66531-135">Performance Considerations for Direct3D9 and WPF Interoperability</span></span>](performance-considerations-for-direct3d9-and-wpf-interoperability.md)
