---
title: 'Cómo: Aplicar material a la parte anterior y posterior de un objeto 3D'
ms.date: 03/30/2017
helpviewer_keywords:
- 3-D objects [WPF], applying Material class
- Material class [WPF], applying to both sides of 3-D object
- classes [WPF], Material
ms.assetid: d93c8ad6-4939-4d29-9544-4d16d98093c1
ms.openlocfilehash: 0ccf0aa045886f0731cd22ecdc8e14fa6af55fd2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-apply-material-to-the-front-and-back-of-a-3-d-object"></a>Cómo: Aplicar material a la parte anterior y posterior de un objeto 3D
En el ejemplo siguiente se muestra cómo aplicar un <xref:System.Windows.Media.Media3D.Material> de objetos al principio y el reverso un 3D y animar el objeto para mostrar ambos lados del objeto. El <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> propiedad de un <xref:System.Windows.Media.Media3D.GeometryModel3D> se usa para aplicar un color rojo <xref:System.Windows.Media.Brush> a la parte frontal del objeto y el <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> propiedad de la <xref:System.Windows.Media.Media3D.GeometryModel3D> se usa para aplicar un azul <xref:System.Windows.Media.Brush> a la parte posterior del objeto. El código siguiente muestra la aplicación de los materiales al objeto:  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexampleinline1)]  
  
## <a name="example"></a>Ejemplo  
 El código siguiente muestra el ejemplo completo.  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexamplewholepage)]  
  
## <a name="see-also"></a>Vea también  
 [Crear una escena 3D](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)  
 [Información general sobre gráficos 3D](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [Animar propiedades de material en una escena 3D](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-material-properties-in-a-3-d-scene.md)  
 [Aplicar material emisor a un objeto tridimensional](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-emissive-material-to-a-3-d-object.md)
