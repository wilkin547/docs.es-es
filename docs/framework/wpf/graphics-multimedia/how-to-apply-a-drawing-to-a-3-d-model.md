---
title: 'Cómo: Aplicar un dibujo a un modelo 3D'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3-D models
- 3-D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 311a3ac1d9fa219a3a365d506d9d0c3e8b6bc229
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459369"
---
# <a name="how-to-apply-a-drawing-to-a-3-d-model"></a>Cómo: Aplicar un dibujo a un modelo 3D

En este ejemplo se muestra cómo usar un <xref:System.Windows.Media.DrawingBrush> como <xref:System.Windows.Media.Media3D.Material> aplicado a un modelo 3D.

En el código siguiente se define un <xref:System.Windows.Media.DrawingGroup> como contenido de un <xref:System.Windows.Media.DrawingBrush>.  El <xref:System.Windows.Media.DrawingBrush> se establece como la propiedad <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> de la <xref:System.Windows.Media.Media3D.DiffuseMaterial> que se aplica a un plano 3D.

> [!NOTE]
> A menudo es conveniente definir objetos y valores complejos como el dibujo siguiente como recursos que se pueden volver a usar y simplificar el código. Vea [recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md) para obtener más información.

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]

## <a name="example"></a>Ejemplo

En el código siguiente se muestra el ejemplo completo.

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]

## <a name="see-also"></a>Vea también

- [Recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Crear una escena 3D](how-to-create-a-3-d-scene.md)
- [Información general sobre objetos Drawing](drawing-objects-overview.md)
- [Información general sobre gráficos 3D](3-d-graphics-overview.md)
