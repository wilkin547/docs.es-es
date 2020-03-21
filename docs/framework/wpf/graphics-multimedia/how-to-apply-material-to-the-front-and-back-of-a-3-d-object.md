---
title: 'Cómo: Aplicar material en la parte delantera y trasera de un objeto 3D'
ms.date: 03/30/2017
helpviewer_keywords:
- 3D objects [WPF], applying Material class
- Material class [WPF], applying to both sides of 3D object
- classes [WPF], Material
ms.assetid: d93c8ad6-4939-4d29-9544-4d16d98093c1
ms.openlocfilehash: 5c24879d97e7857fb07fcef4a9ba8efa901e4a39
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112146"
---
# <a name="how-to-apply-material-to-the-front-and-back-of-a-3d-object"></a>Cómo: Aplicar material en la parte delantera y trasera de un objeto 3D
En el ejemplo siguiente <xref:System.Windows.Media.Media3D.Material> se muestra cómo aplicar a a la parte delantera y trasera de un objeto 3D y animar el objeto para mostrar ambos lados del objeto. La <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> propiedad <xref:System.Windows.Media.Media3D.GeometryModel3D> de a se <xref:System.Windows.Media.Brush> utiliza para aplicar un rojo <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> a <xref:System.Windows.Media.Media3D.GeometryModel3D> la parte frontal <xref:System.Windows.Media.Brush> del objeto y la propiedad de la se utiliza para aplicar un azul a la parte posterior del objeto. El código siguiente muestra la aplicación de los materiales al objeto:  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexampleinline1)]  
  
## <a name="example"></a>Ejemplo  
 El código siguiente muestra el ejemplo completo.  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexamplewholepage)]  
  
## <a name="see-also"></a>Consulte también

- [Crear una escena 3D](how-to-create-a-3-d-scene.md)
- [Descripción general de los gráficos 3D](3-d-graphics-overview.md)
- [Animar propiedades de material en una escena 3D](how-to-animate-material-properties-in-a-3-d-scene.md)
- [Aplicar material emisivo a un objeto 3D](how-to-apply-emissive-material-to-a-3-d-object.md)
