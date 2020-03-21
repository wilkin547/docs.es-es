---
title: 'Cómo: Aplicar un dibujo a un modelo 3D'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3D models
- 3D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 5b10630ab674fa9489cdf7ad53516a680f19da08
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112185"
---
# <a name="how-to-apply-a-drawing-to-a-3d-model"></a>Cómo: Aplicar un dibujo a un modelo 3D

En este ejemplo se <xref:System.Windows.Media.DrawingBrush> muestra <xref:System.Windows.Media.Media3D.Material> cómo utilizar a como aplicado a un modelo 3D.

El código siguiente <xref:System.Windows.Media.DrawingGroup> define a <xref:System.Windows.Media.DrawingBrush>como el contenido de un archivo .  Se <xref:System.Windows.Media.DrawingBrush> establece como <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> la <xref:System.Windows.Media.Media3D.DiffuseMaterial> propiedad del aplicado a un plano 3D.

> [!NOTE]
> A menudo es deseable definir objetos complejos y valores como el dibujo siguiente como recursos que se pueden reutilizar y simplificar el código. Consulta [Recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md) para obtener más información.

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]

## <a name="example"></a>Ejemplo

El código siguiente muestra el ejemplo completo.

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]

## <a name="see-also"></a>Consulte también

- [Recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Crear una escena 3D](how-to-create-a-3-d-scene.md)
- [Información general sobre objetos Drawing](drawing-objects-overview.md)
- [Descripción general de los gráficos 3D](3-d-graphics-overview.md)
