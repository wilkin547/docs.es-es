---
title: 'Cómo: Crear una escena 3D'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scenes [WPF], 3D
- 3D scenes
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
ms.openlocfilehash: 36453894e06e7b59f339c21713449140c17f6851
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112107"
---
# <a name="how-to-create-a-3d-scene"></a>Cómo: Crear una escena 3D
En este ejemplo se muestra cómo crear un objeto 3D que se parece a una hoja plana de papel que se ha girado. A <xref:System.Windows.Controls.Viewport3D> junto con los siguientes componentes se utilizan para crear esta escena 3D simple:  
  
- Se crea una <xref:System.Windows.Media.Media3D.PerspectiveCamera>cámara con un archivo . La cámara especifica qué parte de la escena 3D es visible.  
  
- Se crea una malla para especificar la forma del objeto <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> 3D (hoja de papel) utilizando la propiedad de <xref:System.Windows.Media.Media3D.GeometryModel3D>.  
  
- Se especifica que se especifique un material que se mostrará en la <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> superficie <xref:System.Windows.Media.Media3D.GeometryModel3D>del objeto (gradiente lineal en esta muestra) utilizando la propiedad de .  
  
- Se crea una luz para <xref:System.Windows.Media.Media3D.DirectionalLight>brillar sobre el objeto utilizando .  
  
## <a name="example"></a>Ejemplo  
 El código siguiente muestra cómo crear una escena 3D en XAML.  
  
 [!code-xaml[3DGallery_snip#Basic3DShapeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## <a name="example"></a>Ejemplo  
 El código siguiente muestra cómo crear la misma escena 3D en código de procedimiento.  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## <a name="see-also"></a>Consulte también

- [Descripción general de los gráficos 3D](3-d-graphics-overview.md)
