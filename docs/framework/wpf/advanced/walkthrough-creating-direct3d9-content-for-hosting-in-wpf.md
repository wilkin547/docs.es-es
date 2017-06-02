---
title: "Tutorial: Crear contenido Direct3D9 para hospedarlo en WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Direct3D9 [interoperabilidad de WPF], crear contenido Direct3D9"
  - "WPF, crear contenido Direct3D9"
ms.assetid: 286e98bc-1eaa-4b5e-923d-3490a9cca5fc
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Tutorial: Crear contenido Direct3D9 para hospedarlo en WPF
En este tutorial se muestra cómo crear contenido de Direct3D9 apropiado para su hospedaje en una aplicación de Windows Presentation Foundation \(WPF\).  Para obtener más información sobre cómo hospedar contenido de Direct3D9 en aplicaciones WPF, vea [Interoperabilidad entre WPF y Direct3D9](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md).  
  
 En este tutorial realizará las siguientes tareas:  
  
-   Crear un proyecto de Direct3D9.  
  
-   Configurar el proyecto de Direct3D9 para su hospedaje en una aplicación de WPF.  
  
 Cuando haya terminado, tendrá una DLL que incluirá el contenido de Direct3D9 para su uso en una aplicación de WPF.  
  
## Requisitos previos  
 Necesita los componentes siguientes para completar este tutorial:  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
-   DirectX SDK 9 o posterior.  
  
## Crear el proyecto de Direct3D9  
 El primer paso consiste en crear y configurar el proyecto de Direct3D9.  
  
#### Para crear el proyecto de Direct3D9  
  
1.  Cree un nuevo proyecto de Win32 en C\+\+ denominado `D3DContent`.  
  
     Se abre el Asistente para aplicaciones Win32 y muestra la pantalla de bienvenida.  
  
2.  Haga clic en **Siguiente**.  
  
     Aparece la pantalla Configuración de la aplicación.  
  
3.  En la sección **Tipo de aplicación:**, seleccione la opción **DLL**.  
  
4.  Haga clic en **Finalizar**.  
  
     Se genera el proyecto de D3DContent.  
  
5.  En el Explorador de soluciones, haga clic con el botón secundario en el proyecto D3DContent y seleccione **Propiedades**.  
  
     Se abre el cuadro de diálogo **Páginas de propiedades de D3DContent**.  
  
6.  Seleccione el nodo **C\/C\+\+**.  
  
7.  En el campo **Directorios de inclusión adicionales**, especifique la ubicación de la carpeta de inclusión de DirectX.  La ubicación predeterminada de esta carpeta es %Archivos de programa%\\Microsoft DirectX SDK \(*versión*\)\\Include.  
  
8.  Haga doble clic en el nodo **Vinculador** para expandirlo.  
  
9. En el campo **Directorios de bibliotecas adicionales**, especifique la ubicación de la carpeta de bibliotecas de DirectX.  La ubicación predeterminada de esta carpeta es %Archivos de programa%\\Microsoft DirectX SDK \(*versión*\)\\Lib\\x86.  
  
10. Seleccione el nodo **Entrada**.  
  
11. En el campo **Dependencias adicionales**, agregue los archivos `d3d9.lib` y `d3dx9.lib`.  
  
12. En el Explorador de soluciones, agregue al proyecto un nuevo archivo de definición de módulo \(.def\) denominado `D3DContent.def`.  
  
## Crear el contenido de Direct3D9  
 Para obtener el máximo rendimiento, el contenido de Direct3D9 debe utilizar valores determinados.  En el código siguiente se muestra cómo crear una superficie de Direct3D9 que presenta características de máximo rendimiento.  Para obtener más información, vea [Consideraciones de rendimiento para la interoperabilidad entre Direct3D9 y WPF](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md).  
  
#### Para crear contenido de Direct3D9  
  
1.  Con el Explorador de soluciones, agregue tres clases de C\+\+ al proyecto con los nombres siguientes.  
  
     `CRenderer` \(con destructor virtual\)  
  
     `CRendererManager`  
  
     `CTriangleRenderer`  
  
2.  En el editor de código, abra Renderer.h y reemplace el código generado automáticamente por el código siguiente.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#RendererH](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.h#rendererh)]  
  
3.  En el editor de código, abra Renderer.cpp y reemplace el código generado automáticamente por el código siguiente.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#RendererCPP](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderercpp)]  
  
4.  En el editor de código, abra RendererManager.h y reemplace el código generado automáticamente por el código siguiente.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerH](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.h#renderermanagerh)]  
  
5.  En el editor de código, abra RendererManager.cpp y reemplace el código generado automáticamente por el código siguiente.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerCPP](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanagercpp)]  
  
6.  En el editor de código, abra TriangleRenderer.h y reemplace el código generado automáticamente por el código siguiente.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererH](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.h#trianglerendererh)]  
  
7.  En el editor de código, abra TriangleRenderer.cpp y reemplace el código generado automáticamente por el código siguiente.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererCPP](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.cpp#trianglerenderercpp)]  
  
8.  En el editor de código, abra stdafx.h y reemplace el código generado automáticamente por el código siguiente.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#StdafxH](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/stdafx.h#stdafxh)]  
  
9. En el editor de código, abra dllmain.cpp y reemplace el código generado automáticamente por el código siguiente.  
  
     [!code-cpp[System.Windows.Interop.D3DImage#DllMain](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/dllmain.cpp#dllmain)]  
  
10. Abra D3DContent.def en el editor de código.  
  
11. Reemplace el código generado automáticamente por el código siguiente.  
  
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
  
12. Compile el proyecto.  
  
## Pasos siguientes  
  
-   Hospede el contenido de Direct3D9 en una aplicación de WPF.  Para obtener más información, vea [Tutorial: Hospedar contenido Direct3D9 en WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-direct3d9-content-in-wpf.md).  
  
## Vea también  
 <xref:System.Windows.Interop.D3DImage>   
 [Consideraciones de rendimiento para la interoperabilidad entre Direct3D9 y WPF](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md)   
 [Tutorial: Hospedar contenido Direct3D9 en WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-direct3d9-content-in-wpf.md)