---
title: Procedimiento Animar traslaciones 3D
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3-D translations
- 3-D translations [WPF], animating
ms.assetid: d4eece1f-0cd2-4a2c-8370-293354c380e4
ms.openlocfilehash: e73035a48e32e3eec20b44c82b5b9ec6763c1e7c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54653039"
---
# <a name="how-to-animate-3-d-translations"></a>Procedimiento Animar traslaciones 3D
Este tema muestra cómo animar una transformación de traslación establecida en un [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] modelo.  
  
 El código siguiente muestra la aplicación de un <xref:System.Windows.Media.Media3D.TranslateTransform3D> de objeto para el <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> propiedad de un <xref:System.Windows.Media.Media3D.GeometryModel3D>.  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline1)]  
  
 El <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> propiedad de este <xref:System.Windows.Media.Media3D.TranslateTransform3D> objeto se anima mediante el código siguiente.  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline2)]  
  
## <a name="example"></a>Ejemplo  
 El código siguiente muestra el ejemplo completo.  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationexamplewholepage)]  
  
## <a name="see-also"></a>Vea también
- [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [Crear una escena 3D](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)
- [Información general sobre gráficos 3D](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
- [Información general sobre transformaciones](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
