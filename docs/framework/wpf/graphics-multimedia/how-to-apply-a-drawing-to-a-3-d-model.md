---
title: Procedimiento Aplicar un dibujo a un modelo 3D
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3-D models
- 3-D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 14470d0adeb948ea46a0720b5713c20fb7d8e6d8
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855880"
---
# <a name="how-to-apply-a-drawing-to-a-3-d-model"></a>Procedimiento Aplicar un dibujo a un modelo 3D

En este ejemplo se muestra cómo utilizar <xref:System.Windows.Media.DrawingBrush> un <xref:System.Windows.Media.Media3D.Material> como aplicado a un modelo 3D.

El código siguiente define <xref:System.Windows.Media.DrawingGroup> como el contenido de un. <xref:System.Windows.Media.DrawingBrush>  Se establece como la <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> propiedad de <xref:System.Windows.Media.Media3D.DiffuseMaterial> que se aplica a un plano 3D. <xref:System.Windows.Media.DrawingBrush>

> [!NOTE]
> A menudo es conveniente definir objetos y valores complejos como el dibujo siguiente como recursos que se pueden volver a usar y simplificar el código. Vea [recursos XAML](../advanced/xaml-resources.md) para obtener más información.

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]

## <a name="example"></a>Ejemplo

En el código siguiente se muestra el ejemplo completo.

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]

## <a name="see-also"></a>Vea también

- [Recursos XAML](../advanced/xaml-resources.md)
- [Crear una escena 3D](how-to-create-a-3-d-scene.md)
- [Información general sobre objetos Drawing](drawing-objects-overview.md)
- [Información general sobre gráficos 3D](3-d-graphics-overview.md)
