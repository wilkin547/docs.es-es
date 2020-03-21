---
title: 'Cómo: Animar traducciones 3D'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3D translations
- 3D translations [WPF], animating
ms.assetid: d4eece1f-0cd2-4a2c-8370-293354c380e4
ms.openlocfilehash: 7d4fff9c74663bd220ad5d15a983bcb639621afd
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112263"
---
# <a name="how-to-animate-3d-translations"></a>Cómo: Animar traducciones 3D
En este tema se muestra cómo animar un conjunto de transformación de traducción en un modelo 3D.  
  
 El código siguiente muestra <xref:System.Windows.Media.Media3D.TranslateTransform3D> la aplicación <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> de <xref:System.Windows.Media.Media3D.GeometryModel3D>un objeto a la propiedad de un archivo .  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline1)]  
  
 La <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> propiedad <xref:System.Windows.Media.Media3D.TranslateTransform3D> de este objeto se anima utilizando el código siguiente.  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline2)]  
  
## <a name="example"></a>Ejemplo  
 El código siguiente muestra el ejemplo completo.  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationexamplewholepage)]  
  
## <a name="see-also"></a>Consulte también

- [Información general sobre animaciones](animation-overview.md)
- [Crear una escena 3D](how-to-create-a-3-d-scene.md)
- [Descripción general de los gráficos 3D](3-d-graphics-overview.md)
- [Información general sobre transformaciones](transforms-overview.md)
