---
title: 'Tutorial: Crear contenido Direct3D9 para hospedarlo en WPF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
helpviewer_keywords:
- WPF [WPF], creating Direct3D9 content
- Direct3D9 [WPF interoperability], creating Direct3D9 content
ms.assetid: 286e98bc-1eaa-4b5e-923d-3490a9cca5fc
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 750e5c42158a87c04a7fb0f2a83f126a698bb93f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-creating-direct3d9-content-for-hosting-in-wpf"></a><span data-ttu-id="da66a-102">Tutorial: Crear contenido Direct3D9 para hospedarlo en WPF</span><span class="sxs-lookup"><span data-stu-id="da66a-102">Walkthrough: Creating Direct3D9 Content for Hosting in WPF</span></span>
<span data-ttu-id="da66a-103">Este tutorial muestra cómo crear contenido Direct3D9 que es adecuado para su hospedaje en una aplicación de Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="da66a-103">This walkthrough shows how to create Direct3D9 content that is suitable for hosting in a Windows Presentation Foundation (WPF) application.</span></span> <span data-ttu-id="da66a-104">Para obtener más información acerca de cómo alojar contenido Direct3D9 en aplicaciones de WPF, vea [WPF y Direct3D9 interoperación](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="da66a-104">For more information on hosting Direct3D9 content in WPF applications, see [WPF and Direct3D9 Interoperation](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md).</span></span>  
  
 <span data-ttu-id="da66a-105">En este tutorial, realizará las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="da66a-105">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="da66a-106">Cree un proyecto de Direct3D9.</span><span class="sxs-lookup"><span data-stu-id="da66a-106">Create a Direct3D9 project.</span></span>  
  
-   <span data-ttu-id="da66a-107">Configurar el proyecto de Direct3D9 para su hospedaje en una aplicación WPF.</span><span class="sxs-lookup"><span data-stu-id="da66a-107">Configure the Direct3D9 project for hosting in a WPF application.</span></span>  
  
 <span data-ttu-id="da66a-108">Cuando haya terminado, tendrá una DLL que contiene el contenido de Direct3D9 para su uso en una aplicación WPF.</span><span class="sxs-lookup"><span data-stu-id="da66a-108">When you are finished, you will have a DLL that contains Direct3D9 content for use in a WPF application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="da66a-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="da66a-109">Prerequisites</span></span>  
 <span data-ttu-id="da66a-110">Necesita los componentes siguientes para completar este tutorial:</span><span class="sxs-lookup"><span data-stu-id="da66a-110">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]<span data-ttu-id="da66a-111">.</span><span class="sxs-lookup"><span data-stu-id="da66a-111">.</span></span>  
  
-   <span data-ttu-id="da66a-112">SDK de DirectX 9or más tarde.</span><span class="sxs-lookup"><span data-stu-id="da66a-112">DirectX SDK 9or later.</span></span>  
  
## <a name="creating-the-direct3d9-project"></a><span data-ttu-id="da66a-113">Crear el proyecto de Direct3D9</span><span class="sxs-lookup"><span data-stu-id="da66a-113">Creating the Direct3D9 Project</span></span>  
 <span data-ttu-id="da66a-114">El primer paso es crear y configurar el proyecto de Direct3D9.</span><span class="sxs-lookup"><span data-stu-id="da66a-114">The first step is to create and configure the Direct3D9 project.</span></span>  
  
#### <a name="to-create-the-direct3d9-project"></a><span data-ttu-id="da66a-115">Para crear el proyecto de Direct3D9</span><span class="sxs-lookup"><span data-stu-id="da66a-115">To create the Direct3D9 project</span></span>  
  
1.  <span data-ttu-id="da66a-116">Crear un nuevo proyecto de Win32 en C++ denominado `D3DContent`.</span><span class="sxs-lookup"><span data-stu-id="da66a-116">Create a new Win32 Project in C++ named `D3DContent`.</span></span>  
  
     <span data-ttu-id="da66a-117">El Asistente para aplicaciones de Win32 se abre y muestra la pantalla de bienvenida.</span><span class="sxs-lookup"><span data-stu-id="da66a-117">The Win32 Application Wizard opens and displays the Welcome screen.</span></span>  
  
2.  <span data-ttu-id="da66a-118">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="da66a-118">Click **Next**.</span></span>  
  
     <span data-ttu-id="da66a-119">Aparecerá la pantalla de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="da66a-119">The Application Settings screen appears.</span></span>  
  
3.  <span data-ttu-id="da66a-120">En el **tipo de aplicación:** sección, seleccione la **DLL** opción.</span><span class="sxs-lookup"><span data-stu-id="da66a-120">In the **Application type:** section, select the **DLL** option.</span></span>  
  
4.  <span data-ttu-id="da66a-121">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="da66a-121">Click **Finish**.</span></span>  
  
     <span data-ttu-id="da66a-122">Se genera el proyecto D3DContent.</span><span class="sxs-lookup"><span data-stu-id="da66a-122">The D3DContent project is generated.</span></span>  
  
5.  <span data-ttu-id="da66a-123">En el Explorador de soluciones, haga clic en el proyecto D3DContent y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="da66a-123">In Solution Explorer, right-click the D3DContent project and select **Properties**.</span></span>  
  
     <span data-ttu-id="da66a-124">El **páginas de propiedades de D3DContent** abre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="da66a-124">The **D3DContent Property Pages** dialog box opens.</span></span>  
  
6.  <span data-ttu-id="da66a-125">Seleccione el **C/C++** nodo.</span><span class="sxs-lookup"><span data-stu-id="da66a-125">Select the **C/C++** node.</span></span>  
  
7.  <span data-ttu-id="da66a-126">En el **directorios de inclusión adicionales** , especifique la ubicación de DirectX incluir carpeta.</span><span class="sxs-lookup"><span data-stu-id="da66a-126">In the **Additional Include Directories** field, specify the location of the DirectX include folder.</span></span> <span data-ttu-id="da66a-127">La ubicación predeterminada de esta carpeta es %ProgramFiles%\Microsoft DirectX SDK (*versión*) \Include.</span><span class="sxs-lookup"><span data-stu-id="da66a-127">The default location for this folder is %ProgramFiles%\Microsoft DirectX SDK (*version*)\Include.</span></span>  
  
8.  <span data-ttu-id="da66a-128">Haga doble clic en el **vinculador** nodo para expandirlo.</span><span class="sxs-lookup"><span data-stu-id="da66a-128">Double-click the **Linker** node to expand it.</span></span>  
  
9. <span data-ttu-id="da66a-129">En el **directorios de bibliotecas adicionales** campo, especifique la ubicación de la carpeta de bibliotecas de DirectX.</span><span class="sxs-lookup"><span data-stu-id="da66a-129">In the **Additional Library Directories** field, specify the location of the DirectX libraries folder.</span></span> <span data-ttu-id="da66a-130">La ubicación predeterminada de esta carpeta es %ProgramFiles%\Microsoft DirectX SDK (*versión*) \Lib\x86.</span><span class="sxs-lookup"><span data-stu-id="da66a-130">The default location for this folder is %ProgramFiles%\Microsoft DirectX SDK (*version*)\Lib\x86.</span></span>  
  
10. <span data-ttu-id="da66a-131">Seleccione el **entrada** nodo.</span><span class="sxs-lookup"><span data-stu-id="da66a-131">Select the **Input** node.</span></span>  
  
11. <span data-ttu-id="da66a-132">En el **dependencias adicionales** , a continuación, agregue el `d3d9.lib` y `d3dx9.lib` archivos.</span><span class="sxs-lookup"><span data-stu-id="da66a-132">In the **Additional Dependencies** field, add the `d3d9.lib` and `d3dx9.lib` files.</span></span>  
  
12. <span data-ttu-id="da66a-133">En el Explorador de soluciones, agregue un nuevo archivo de definición de módulo (.def) denominado `D3DContent.def` al proyecto.</span><span class="sxs-lookup"><span data-stu-id="da66a-133">In Solution Explorer, add a new module definition file (.def) named `D3DContent.def` to the project.</span></span>  
  
## <a name="creating-the-direct3d9-content"></a><span data-ttu-id="da66a-134">Crear el contenido de Direct3D9</span><span class="sxs-lookup"><span data-stu-id="da66a-134">Creating the Direct3D9 Content</span></span>  
 <span data-ttu-id="da66a-135">Para obtener el mejor rendimiento, el contenido de Direct3D9 debe utilizar valores determinados.</span><span class="sxs-lookup"><span data-stu-id="da66a-135">To get the best performance, your Direct3D9 content must use particular settings.</span></span> <span data-ttu-id="da66a-136">El código siguiente muestra cómo crear una superficie de Direct3D9 con las mejores características de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="da66a-136">The following code shows how to create a Direct3D9 surface that has the best performance characteristics.</span></span> <span data-ttu-id="da66a-137">Para obtener más información, consulte [consideraciones de rendimiento para la interoperabilidad de WPF y Direct3D9](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="da66a-137">For more information, see [Performance Considerations for Direct3D9 and WPF Interoperability](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md).</span></span>  
  
#### <a name="to-create-the-direct3d9-content"></a><span data-ttu-id="da66a-138">Para crear el Direct3D9 contenido</span><span class="sxs-lookup"><span data-stu-id="da66a-138">To create the Direct3D9 content</span></span>  
  
1.  <span data-ttu-id="da66a-139">Mediante el Explorador de soluciones, agregue tres clases de C++ al proyecto denominado lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="da66a-139">Using Solution Explorer, add three C++ classes to the project named the following.</span></span>  
  
     <span data-ttu-id="da66a-140">`CRenderer`(con destructor virtual)</span><span class="sxs-lookup"><span data-stu-id="da66a-140">`CRenderer` (with virtual destructor)</span></span>  
  
     `CRendererManager`  
  
     `CTriangleRenderer`  
  
2.  <span data-ttu-id="da66a-141">En el Editor de código, abra Renderer.h y reemplace el código generado automáticamente por el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="da66a-141">Open Renderer.h in the Code Editor and replace the automatically generated code with the following code.</span></span>  
  
     [!code-cpp[System.Windows.Interop.D3DImage#RendererH](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.h#rendererh)]  
  
3.  <span data-ttu-id="da66a-142">En el Editor de código, abra Renderer.cpp y reemplace el código generado automáticamente por el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="da66a-142">Open Renderer.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>  
  
     [!code-cpp[System.Windows.Interop.D3DImage#RendererCPP](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderercpp)]  
  
4.  <span data-ttu-id="da66a-143">En el Editor de código, abra RendererManager.h y reemplace el código generado automáticamente por el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="da66a-143">Open RendererManager.h in the Code Editor and replace the automatically generated code with the following code.</span></span>  
  
     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerH](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.h#renderermanagerh)]  
  
5.  <span data-ttu-id="da66a-144">En el Editor de código, abra RendererManager.cpp y reemplace el código generado automáticamente por el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="da66a-144">Open RendererManager.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>  
  
     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerCPP](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanagercpp)]  
  
6.  <span data-ttu-id="da66a-145">En el Editor de código, abra TriangleRenderer.h y reemplace el código generado automáticamente por el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="da66a-145">Open TriangleRenderer.h in the Code Editor and replace the automatically generated code with the following code.</span></span>  
  
     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererH](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.h#trianglerendererh)]  
  
7.  <span data-ttu-id="da66a-146">En el Editor de código, abra TriangleRenderer.cpp y reemplace el código generado automáticamente por el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="da66a-146">Open TriangleRenderer.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>  
  
     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererCPP](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.cpp#trianglerenderercpp)]  
  
8.  <span data-ttu-id="da66a-147">Abra stdafx.h en el Editor de código y reemplace el código generado automáticamente por el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="da66a-147">Open stdafx.h in the Code Editor and replace the automatically generated code with the following code.</span></span>  
  
     [!code-cpp[System.Windows.Interop.D3DImage#StdafxH](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/stdafx.h#stdafxh)]  
  
9. <span data-ttu-id="da66a-148">En el Editor de código, abra dllmain.cpp y reemplace el código generado automáticamente por el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="da66a-148">Open dllmain.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>  
  
     [!code-cpp[System.Windows.Interop.D3DImage#DllMain](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/dllmain.cpp#dllmain)]  
  
10. <span data-ttu-id="da66a-149">Abra D3DContent.def en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="da66a-149">Open D3DContent.def in the code editor.</span></span>  
  
11. <span data-ttu-id="da66a-150">Reemplace el código generado automáticamente por el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="da66a-150">Replace the automatically generated code with the following code.</span></span>  
  
    ```  
    LIBRARY "D3DContent"  
  
    EXPORTS  
  
    SetSize  
    SetAlpha  
    SetNumDesiredSamples  
    SetAdapter  
  
    GetBackBufferNoRef  
    Render  
    Destroy  
    ```  
  
12. <span data-ttu-id="da66a-151">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="da66a-151">Build the project.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="da66a-152">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="da66a-152">Next Steps</span></span>  
  
-   <span data-ttu-id="da66a-153">Hospedar el contenido de Direct3D9 en una aplicación WPF.</span><span class="sxs-lookup"><span data-stu-id="da66a-153">Host the Direct3D9 content in a WPF application.</span></span> <span data-ttu-id="da66a-154">Para obtener más información, consulte [Tutorial: hospedar contenido Direct3D9 en WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-direct3d9-content-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="da66a-154">For more information, see [Walkthrough: Hosting Direct3D9 Content in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-direct3d9-content-in-wpf.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da66a-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="da66a-155">See Also</span></span>  
 <xref:System.Windows.Interop.D3DImage>  
 [<span data-ttu-id="da66a-156">Consideraciones de rendimiento para la interoperabilidad entre Direct3D9 y WPF</span><span class="sxs-lookup"><span data-stu-id="da66a-156">Performance Considerations for Direct3D9 and WPF Interoperability</span></span>](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md)  
 [<span data-ttu-id="da66a-157">Tutorial: Hospedar contenido Direct3D9 en WPF</span><span class="sxs-lookup"><span data-stu-id="da66a-157">Walkthrough: Hosting Direct3D9 Content in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-direct3d9-content-in-wpf.md)
