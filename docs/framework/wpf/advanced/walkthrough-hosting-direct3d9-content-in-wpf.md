---
title: 'Tutorial: Hospedar contenido Direct3D9 en WPF'
ms.date: 03/30/2017
helpviewer_keywords:
- Direct3D9 [WPF interoperability], hosting Direct3D9 content
- WPF [WPF], hosting Direct3D9 content
ms.assetid: 60983736-0ab5-42cc-8b16-e9fbde261a43
ms.openlocfilehash: 2c31c044aa50a74255a61da1675037ab3d09f615
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053449"
---
# <a name="walkthrough-hosting-direct3d9-content-in-wpf"></a>Tutorial: Hospedar contenido Direct3D9 en WPF

En este tutorial se muestra cómo hospedar contenido de Direct3D9 en una aplicación Windows Presentation Foundation (WPF).

En este tutorial, realizará las tareas siguientes:

- Cree un proyecto de WPF para hospedar el contenido de Direct3D9.

- Importe el contenido de Direct3D9.

- Mostrar el contenido de Direct3D9 mediante la <xref:System.Windows.Interop.D3DImage> clase.

 Cuando haya terminado, sabrá cómo hospedar contenido de Direct3D9 en una aplicación WPF.

## <a name="prerequisites"></a>Requisitos previos

Necesita los componentes siguientes para completar este tutorial:

- Visual Studio.

- DirectX SDK 9 o posterior.

- Un archivo DLL que contiene contenido de Direct3D9 en un formato compatible con WPF. Para obtener más información, consulte [interoperabilidad](wpf-and-direct3d9-interoperation.md) y [tutorial de WPF y Direct3D9: Crear contenido de Direct3D9 para hospedarlo](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md)en WPF.

## <a name="creating-the-wpf-project"></a>Crear el proyecto de WPF

El primer paso es crear el proyecto para la aplicación WPF.

### <a name="to-create-the-wpf-project"></a>Para crear el proyecto de WPF

Cree un nuevo proyecto de aplicación de WPF C# en `D3DHost`visual denominado. Para obtener más información, vea [Tutorial: Mi primera aplicación](../getting-started/walkthrough-my-first-wpf-desktop-application.md)de escritorio WPF.

MainWindow. XAML se abre en [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].

## <a name="importing-the-direct3d9-content"></a>Importar el contenido de Direct3D9

Importe el contenido de Direct3D9 desde un archivo dll no administrado mediante el `DllImport` atributo.

### <a name="to-import-direct3d9-content"></a>Para importar el contenido de Direct3D9

1. Abra MainWindow.xaml.cs en el editor de código.

2. Reemplace el código generado automáticamente por el código siguiente.

    [!code-csharp[System.Windows.Interop.D3DImage#1](~/samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml.cs#1)]

## <a name="hosting-the-direct3d9-content"></a>Hospedar el contenido de Direct3D9

Por último, utilice <xref:System.Windows.Interop.D3DImage> la clase para hospedar el contenido de Direct3D9.

### <a name="to-host-the-direct3d9-content"></a>Para hospedar el contenido de Direct3D9

1. En MainWindow. XAML, reemplace el código XAML generado automáticamente por el código XAML siguiente.

    [!code-xaml[System.Windows.Interop.D3DImage#10](~/samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml#10)]

2. Compile el proyecto.

3. Copie el archivo DLL que contiene el contenido de Direct3D9 en la carpeta bin/Debug.

4. Presione F5 para ejecutar el proyecto.

    El contenido de Direct3D9 aparece dentro de la aplicación WPF.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Interop.D3DImage>
- [Consideraciones de rendimiento para la interoperabilidad entre Direct3D9 y WPF](performance-considerations-for-direct3d9-and-wpf-interoperability.md)
