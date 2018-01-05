---
title: "Cómo: Crear una escena 3D"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scenes [WPF], 3-D
- 3-D scenes
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f52642a1764a7db01d4ca330f3bf25bdca10fa06
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-3-d-scene"></a>Cómo: Crear una escena 3D
En este ejemplo se muestra cómo crear un objeto 3D que parece una hoja de papel que se ha girado plana. Un <xref:System.Windows.Controls.Viewport3D> junto con los siguientes componentes se utilizan para crear esta escena 3D sencilla:  
  
-   Se crea una cámara mediante un <xref:System.Windows.Media.Media3D.PerspectiveCamera>. La cámara especifica qué parte de la escena 3D es visible.  
  
-   Se crea una malla para especificar la forma de objeto 3D (hoja de papel) mediante la <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> propiedad de <xref:System.Windows.Media.Media3D.GeometryModel3D>.  
  
-   Se especifica el material que se mostrará en la superficie del objeto (degradado lineal en este ejemplo) con el <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> propiedad de <xref:System.Windows.Media.Media3D.GeometryModel3D>.  
  
-   Se crea una luz para destacar en el objeto utilizando <xref:System.Windows.Media.Media3D.DirectionalLight>.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente muestra cómo crear una escena 3D en XAML.  
  
 [!code-xaml[3DGallery_snip#Basic3DShapeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## <a name="example"></a>Ejemplo  
 El código siguiente muestra cómo crear la misma escena 3D en código de procedimiento.  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre gráficos 3D](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
