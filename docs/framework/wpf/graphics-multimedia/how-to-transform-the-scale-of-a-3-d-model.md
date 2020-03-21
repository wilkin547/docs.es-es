---
title: 'Cómo: Transformar la Escala de un Modelo 3D'
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], 3D objects
- 3D objects [WPF], scaling
ms.assetid: f3fdfe33-f7dc-44b0-84a5-e43b89947f35
ms.openlocfilehash: be41a0e10929912c1b54bf7140d743d9453199bf
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111990"
---
# <a name="how-to-transform-the-scale-of-a-3d-model"></a>Cómo: Transformar la Escala de un Modelo 3D
En este ejemplo se muestra cómo escalar un objeto 3D. Para escalar un objeto 3D, utilice un <xref:System.Windows.Media.Media3D.ScaleTransform3D>archivo . Las <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>propiedades <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> , , y cambian el tamaño del elemento según el factor que especifique. Por ejemplo, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> un valor de 1,5 estira un objeto al 150 por ciento de su ancho original. Un <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> valor de 0,5 reduce la altura de un objeto en un 50 por ciento. El código siguiente <xref:System.Windows.Media.Media3D.ScaleTransform3D> muestra el uso <xref:System.Windows.Media.Media3D.GeometryModel3D>de a como transformación para un archivo .  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexampleinline1)]  
  
## <a name="example"></a>Ejemplo  
 El código siguiente muestra el ejemplo completo.  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexamplewholepage)]  
  
## <a name="see-also"></a>Consulte también

- [Animate 3D Translations](how-to-animate-3-d-translations.md)
- [Crear una escena 3D](how-to-create-a-3-d-scene.md)
- [Descripción general de los gráficos 3D](3-d-graphics-overview.md)
