---
title: "C&#243;mo: Crear una escena 3D | Microsoft Docs"
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
  - "escenas 3D"
  - "crear, escenas 3D"
  - "escenas, 3D"
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Crear una escena 3D
En este ejemplo se muestra cómo crear un objeto 3D que parece una hoja de papel plana que se ha girado.  Para crear esta escena 3D sencilla se utiliza un objeto <xref:System.Windows.Controls.Viewport3D> junto con los componentes siguientes:  
  
-   Se crea una cámara mediante un objeto <xref:System.Windows.Media.Media3D.PerspectiveCamera>.  La cámara especifica qué parte de la escena 3D está visible.  
  
-   Se crea una malla para especificar la forma del objeto 3D \(hoja de papel\) mediante la propiedad <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> de <xref:System.Windows.Media.Media3D.GeometryModel3D>.  
  
-   Se especifica el material que se mostrará en la superficie del objeto \(degradado lineal en este ejemplo\) mediante la propiedad <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> de <xref:System.Windows.Media.Media3D.GeometryModel3D>.  
  
-   Se crea una luz que ilumine el objeto mediante <xref:System.Windows.Media.Media3D.DirectionalLight>.  
  
## Ejemplo  
 En el código siguiente se muestra cómo crear una escena 3D en XAML.  
  
 [!code-xml[3DGallery_snip#Basic3DShapeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## Ejemplo  
 En el código siguiente se muestra cómo crear la misma escena 3D mediante código de procedimiento.  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## Vea también  
 [Información general sobre gráficos 3D](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)