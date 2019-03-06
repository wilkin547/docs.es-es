---
title: Procedimiento Transformar la escala de un modelo 3D
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], 3-D objects
- 3-D objects [WPF], scaling
ms.assetid: f3fdfe33-f7dc-44b0-84a5-e43b89947f35
ms.openlocfilehash: afe18cea95be945313ef78a690c58950a3fff9b0
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378787"
---
# <a name="how-to-transform-the-scale-of-a-3-d-model"></a>Procedimiento Transformar la escala de un modelo 3D
En este ejemplo se muestra cómo escalar un objeto 3D. Para escalar un objeto 3D, use un <xref:System.Windows.Media.Media3D.ScaleTransform3D>. El <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>, y <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> propiedades, cambie el tamaño del elemento por el factor que especifique. Por ejemplo, un <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> valor de 1,5 ajusta un objeto al 150 por ciento de su ancho original. Un <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> valor de 0,5 reduce el alto de un objeto en un 50%. El código siguiente muestra mediante un <xref:System.Windows.Media.Media3D.ScaleTransform3D> como la transformación para un <xref:System.Windows.Media.Media3D.GeometryModel3D>.  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexampleinline1)]  
  
## <a name="example"></a>Ejemplo  
 El código siguiente muestra el ejemplo completo.  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexamplewholepage)]  
  
## <a name="see-also"></a>Vea también
- [Animar traslaciones 3D](how-to-animate-3-d-translations.md)
- [Crear una escena 3D](how-to-create-a-3-d-scene.md)
- [Información general sobre gráficos 3D](3-d-graphics-overview.md)
