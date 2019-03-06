---
title: Filtrar Animar traslaciones 3D
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3-D translations
- 3-D translations [WPF], animating
ms.assetid: d4eece1f-0cd2-4a2c-8370-293354c380e4
ms.openlocfilehash: 0290beac5a92a955b39d0b8fcc24705346c2964a
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57351923"
---
# <a name="how-to-animate-3-d-translations"></a>Filtrar Animar traslaciones 3D
Este tema muestra cómo animar una transformación de traslación establecida en un [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] modelo.  
  
 El código siguiente muestra la aplicación de un <xref:System.Windows.Media.Media3D.TranslateTransform3D> de objeto para el <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> propiedad de un <xref:System.Windows.Media.Media3D.GeometryModel3D>.  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline1)]  
  
 El <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> propiedad de este <xref:System.Windows.Media.Media3D.TranslateTransform3D> objeto se anima mediante el código siguiente.  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline2)]  
  
## <a name="example"></a>Ejemplo  
 El código siguiente muestra el ejemplo completo.  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationexamplewholepage)]  
  
## <a name="see-also"></a>Vea también
- [Información general sobre animaciones](animation-overview.md)
- [Crear una escena 3D](how-to-create-a-3-d-scene.md)
- [Información general sobre gráficos 3D](3-d-graphics-overview.md)
- [Información general sobre transformaciones](transforms-overview.md)
