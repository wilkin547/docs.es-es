---
title: "Tutorial: Hospedar contenido Direct3D9 en WPF | Microsoft Docs"
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
  - "Direct3D9 [interoperabilidad de WPF], hospedar contenido Direct3D9"
  - "WPF, hospedar contenido Direct3D9"
ms.assetid: 60983736-0ab5-42cc-8b16-e9fbde261a43
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Tutorial: Hospedar contenido Direct3D9 en WPF
En este tutorial se muestra cómo hospedar contenido de Direct3D9 en una aplicación de Windows Presentation Foundation \(WPF\).  
  
 En este tutorial realizará las siguientes tareas:  
  
-   Crear un proyecto de WPF para hospedar el contenido de Direct3D9.  
  
-   Importar el contenido de Direct3D9.  
  
-   Mostrar el contenido de Direct3D9 mediante la clase <xref:System.Windows.Interop.D3DImage>.  
  
 Cuando lo complete, sabrá cómo hospedar contenido de Direct3D9 en una aplicación de WPF.  
  
## Requisitos previos  
 Necesita los componentes siguientes para completar este tutorial:  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
-   DirectX SDK 9 o posterior.  
  
-   Una DLL que incluye el contenido de Direct3D9 en un formato compatible con WPF.  Para obtener más información, vea [Interoperabilidad entre WPF y Direct3D9](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md) y [Tutorial: Crear contenido Direct3D9 para hospedarlo en WPF](../../../../docs/framework/wpf/advanced/walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).  
  
## Crear el proyecto de WPF  
 El primer paso consiste en crear el proyecto para la aplicación de WPF.  
  
#### Para crear el proyecto de WPF  
  
-   Cree un nuevo proyecto de aplicación de WPF en Visual C\# denominado `D3DHost`.  Para obtener más información, vea [Cómo: Crear un nuevo proyecto de aplicación de WPF](http://msdn.microsoft.com/es-es/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).  
  
     MainWindow.xaml se abrirá en [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
## Importar el contenido de Direct3D9  
 El contenido de Direct3D9 se importa desde una DLL no administrada; para ello, se utiliza el atributo `DllImport`.  
  
#### Para importar el contenido de Direct3D9  
  
1.  En el Editor de código, abra MainWindow.xaml.cs.  
  
2.  Reemplace el código generado automáticamente por el código siguiente.  
  
     [!code-csharp[System.Windows.Interop.D3DImage#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml.cs#1)]  
  
## Hospedar el contenido de Direct3D9  
 Por último, utilice la clase <xref:System.Windows.Interop.D3DImage> para hospedar el contenido de Direct3D9.  
  
#### Para hospedar el contenido de Direct3D9  
  
1.  En MainWindow.xaml, reemplace el XAML generado automáticamente por el XAML siguiente.  
  
     [!code-xml[System.Windows.Interop.D3DImage#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml#10)]  
  
2.  Compile el proyecto.  
  
3.  Copie en la carpeta bin\/Depurar la DLL que incluye el contenido de Direct3D9.  
  
4.  Presione F5 para ejecutar el proyecto.  
  
     El contenido de Direct3D9 aparece dentro de la aplicación de WPF.  
  
## Vea también  
 <xref:System.Windows.Interop.D3DImage>   
 [Consideraciones de rendimiento para la interoperabilidad entre Direct3D9 y WPF](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md)