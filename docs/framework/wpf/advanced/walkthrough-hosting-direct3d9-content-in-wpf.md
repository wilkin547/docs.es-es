---
title: 'Tutorial: Hospedar contenido Direct3D9 en WPF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Direct3D9 [WPF interoperability], hosting Direct3D9 content
- WPF [WPF], hosting Direct3D9 content
ms.assetid: 60983736-0ab5-42cc-8b16-e9fbde261a43
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5ad6ac99a77e3477499a871e269cc7faa7a59f12
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-hosting-direct3d9-content-in-wpf"></a>Tutorial: Hospedar contenido Direct3D9 en WPF
Este tutorial muestra cómo hospedar contenido de Direct3D9 en una aplicación de Windows Presentation Foundation (WPF).  
  
 En este tutorial, realizará las tareas siguientes:  
  
-   Cree un proyecto WPF para hospedar el contenido de Direct3D9.  
  
-   Importar el contenido de Direct3D9.  
  
-   Mostrar el contenido de Direct3D9 mediante la <xref:System.Windows.Interop.D3DImage> clase.  
  
 Cuando haya terminado, sabrá cómo hospedar contenido de Direct3D9 en una aplicación WPF.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Necesita los componentes siguientes para completar este tutorial:  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
-   DirectX SDK 9 o posterior.  
  
-   Un archivo DLL que contiene el contenido de Direct3D9 en un formato compatible con WPF. Para obtener más información, consulte [WPF y Direct3D9 interoperación](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md) y [Tutorial: crear contenido Direct3D9 para el hospedaje en WPF](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).  
  
## <a name="creating-the-wpf-project"></a>Crear el proyecto WPF  
 El primer paso es crear el proyecto para la aplicación de WPF.  
  
#### <a name="to-create-the-wpf-project"></a>Para crear el proyecto de WPF  
  
-   Crear un nuevo proyecto de aplicación WPF en Visual C# llamado `D3DHost`. Para obtener más información, vea [Cómo: Crear un nuevo proyecto de aplicación de WPF](http://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).  
  
     MainWindow.xaml se abrirá en el [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
## <a name="importing-the-direct3d9-content"></a>Importar el contenido de Direct3D9  
 Importar el contenido de Direct3D9 desde una DLL no administrada mediante el `DllImport` atributo.  
  
#### <a name="to-import-direct3d9-content"></a>Para importar el contenido de Direct3D9  
  
1.  Abra MainWindow.xaml.cs en el Editor de código.  
  
2.  Reemplace el código generado automáticamente por el código siguiente.  
  
     [!code-csharp[System.Windows.Interop.D3DImage#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml.cs#1)]  
  
## <a name="hosting-the-direct3d9-content"></a>Hospedar el contenido de Direct3D9  
 Por último, utilice la <xref:System.Windows.Interop.D3DImage> clase para hospedar el contenido de Direct3D9.  
  
#### <a name="to-host-the-direct3d9-content"></a>Para hospedar el contenido de Direct3D9  
  
1.  En MainWindow.xaml, reemplace el XAML generado automáticamente por el código XAML siguiente.  
  
     [!code-xaml[System.Windows.Interop.D3DImage#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml#10)]  
  
2.  Compile el proyecto.  
  
3.  Copie la DLL que contiene el contenido de Direct3D9 en la carpeta bin/Debug.  
  
4.  Presione F5 para ejecutar el proyecto.  
  
     El contenido de Direct3D9 aparece dentro de la aplicación de WPF.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Interop.D3DImage>  
 [Consideraciones de rendimiento para la interoperabilidad entre Direct3D9 y WPF](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md)
