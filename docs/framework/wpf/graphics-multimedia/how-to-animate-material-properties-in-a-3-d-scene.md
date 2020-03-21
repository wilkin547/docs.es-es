---
title: 'Cómo: Animar propiedades de material en una escena 3D'
ms.date: 03/30/2017
helpviewer_keywords:
- Material properties [WPF], animating in 3D scenes
- animation [WPF], Material properties in 3D scenes
- 3D scenes [WPF], animating Material properties
ms.assetid: 229fd6eb-7401-4992-b0c9-8b28de230c0f
ms.openlocfilehash: db59debcd7558cde52d8604cb04c8c4e68921825
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112198"
---
# <a name="how-to-animate-material-properties-in-a-3d-scene"></a>Cómo: Animar propiedades de material en una escena 3D
En este ejemplo se <xref:System.Windows.Media.Brush.Opacity%2A> muestra <xref:System.Windows.Media.Media3D.Material> cómo animar la propiedad de la aplicada a un modelo 3D.  
  
 En el ejemplo <xref:System.Windows.Media.LinearGradientBrush> de código <xref:System.Windows.Media.Media3D.Material> siguiente se define el utilizado como el aplicado al objeto 3D.  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline1)]  
  
 La <xref:System.Windows.Media.Brush.Opacity%2A> propiedad <xref:System.Windows.Media.LinearGradientBrush> de esto se anima mediante el ejemplo de código siguiente.  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline2)]  
  
## <a name="example"></a>Ejemplo  
 El código siguiente muestra el ejemplo completo.  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexamplewholepage)]  
  
## <a name="see-also"></a>Consulte también

- [Crear una escena 3D](how-to-create-a-3-d-scene.md)
- [Descripción general de los gráficos 3D](3-d-graphics-overview.md)
