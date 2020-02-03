---
title: Crear contenido de Direct3D9 para el hospedaje
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- WPF [WPF], creating Direct3D9 content
- Direct3D9 [WPF interoperability], creating Direct3D9 content
ms.assetid: 286e98bc-1eaa-4b5e-923d-3490a9cca5fc
ms.openlocfilehash: 847ee74da5b295c2c9d3824b3df74f94bc98a4db
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76727919"
---
# <a name="walkthrough-creating-direct3d9-content-for-hosting-in-wpf"></a>Tutorial: Crear contenido Direct3D9 para hospedarlo en WPF
En este tutorial se muestra cómo crear contenido de Direct3D9 que es adecuado para hospedar en una aplicación Windows Presentation Foundation (WPF). Para obtener más información sobre cómo hospedar contenido de Direct3D9 en aplicaciones WPF, consulte [interoperabilidad de WPF y Direct3D9](wpf-and-direct3d9-interoperation.md).

 En este tutorial, realizará las tareas siguientes:

- Cree un proyecto de Direct3D9.

- Configure el proyecto de Direct3D9 para hospedarlo en una aplicación WPF.

 Cuando haya terminado, tendrá un archivo DLL que contiene el contenido de Direct3D9 para usarlo en una aplicación de WPF.

## <a name="prerequisites"></a>Prerequisites
 Necesitará los componentes siguientes para completar este tutorial:

- Visual Studio 2010.

- DirectX SDK 9 o posterior.

## <a name="creating-the-direct3d9-project"></a>Crear el proyecto de Direct3D9
 El primer paso es crear y configurar el proyecto de Direct3D9.

#### <a name="to-create-the-direct3d9-project"></a>Para crear el proyecto de Direct3D9

1. Cree un nuevo proyecto de Win32 C++ en el `D3DContent`con nombre.

     Se abre el Asistente para aplicaciones Win32 y se muestra la pantalla de bienvenida.

2. Haga clic en **Next**.

     Aparece la pantalla Configuración de la aplicación.

3. En la sección **tipo de aplicación:** , seleccione la opción **dll** .

4. Haga clic en **Finalizar**

     Se genera el proyecto D3DContent.

5. En Explorador de soluciones, haga clic con el botón derecho en el proyecto D3DContent y seleccione **propiedades**.

     Se abre el cuadro de diálogo **páginas de propiedades de D3DContent** .

6. Seleccione el nodo **CC++ /** .

7. En el campo **directorios de inclusión adicionales** , especifique la ubicación de la carpeta de inclusión de DirectX. La ubicación predeterminada de esta carpeta es%ProgramFiles%\Microsoft DirectX SDK (*versión*) \Include.

8. Haga doble clic en el nodo del **enlazador** para expandirlo.

9. En el campo **directorios de bibliotecas adicionales** , especifique la ubicación de la carpeta de bibliotecas de DirectX. La ubicación predeterminada de esta carpeta es%ProgramFiles%\Microsoft DirectX SDK (*versión*) \Lib\x86.

10. Seleccione el nodo de **entrada** .

11. En el campo **dependencias adicionales** , agregue los archivos `d3d9.lib` y `d3dx9.lib`.

12. En Explorador de soluciones, agregue un nuevo archivo de definición de módulo (. def) denominado `D3DContent.def` al proyecto.

## <a name="creating-the-direct3d9-content"></a>Crear el contenido de Direct3D9
 Para obtener el mejor rendimiento, el contenido de Direct3D9 debe usar una configuración determinada. En el código siguiente se muestra cómo crear una superficie de Direct3D9 que tenga las mejores características de rendimiento. Para obtener más información, vea [consideraciones de rendimiento para la interoperabilidad de Direct3D9 y WPF](performance-considerations-for-direct3d9-and-wpf-interoperability.md).

#### <a name="to-create-the-direct3d9-content"></a>Para crear el contenido de Direct3D9

1. Con Explorador de soluciones, agregue tres C++ clases al proyecto con el nombre siguiente.

     `CRenderer` (con destructor virtual)

     `CRendererManager`

     `CTriangleRenderer`

2. Abra renderer. h en el editor de código y reemplace el código generado automáticamente por el código siguiente.

     [!code-cpp[System.Windows.Interop.D3DImage#RendererH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.h#rendererh)]

3. Abra renderer. cpp en el editor de código y reemplace el código generado automáticamente por el código siguiente.

     [!code-cpp[System.Windows.Interop.D3DImage#RendererCPP](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderercpp)]

4. Abra RendererManager. h en el editor de código y reemplace el código generado automáticamente por el código siguiente.

     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.h#renderermanagerh)]

5. Abra RendererManager. cpp en el editor de código y reemplace el código generado automáticamente por el código siguiente.

     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerCPP](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanagercpp)]

6. Abra TriangleRenderer. h en el editor de código y reemplace el código generado automáticamente por el código siguiente.

     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.h#trianglerendererh)]

7. Abra TriangleRenderer. cpp en el editor de código y reemplace el código generado automáticamente por el código siguiente.

     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererCPP](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.cpp#trianglerenderercpp)]

8. Abra stdafx. h en el editor de código y reemplace el código generado automáticamente por el código siguiente.

     [!code-cpp[System.Windows.Interop.D3DImage#StdafxH](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/stdafx.h#stdafxh)]

9. Abra DllMain. cpp en el editor de código y reemplace el código generado automáticamente por el código siguiente.

     [!code-cpp[System.Windows.Interop.D3DImage#DllMain](~/samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/dllmain.cpp#dllmain)]

10. Abra D3DContent. def en el editor de código.

11. Reemplace el código generado automáticamente por el código siguiente.

    ```cpp
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

## <a name="next-steps"></a>Pasos siguientes

- Hospede el contenido de Direct3D9 en una aplicación WPF. Para obtener más información, consulte [Tutorial: hospedar contenido de Direct3D9 en WPF](walkthrough-hosting-direct3d9-content-in-wpf.md).

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Interop.D3DImage>
- [Consideraciones de rendimiento para la interoperabilidad entre Direct3D9 y WPF](performance-considerations-for-direct3d9-and-wpf-interoperability.md)
- [Tutorial: Hospedar contenido Direct3D9 en WPF](walkthrough-hosting-direct3d9-content-in-wpf.md)
