---
title: Procedimiento Aplicar un dibujo a un modelo 3D
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3-D models
- 3-D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 8ac24fdf8d7e407e10764c17fcc12121aa5f51d7
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "67662810"
---
# <a name="how-to-apply-a-drawing-to-a-3-d-model"></a>Procedimiento Aplicar un dibujo a un modelo 3D
En este ejemplo se muestra cómo usar un <xref:System.Windows.Media.DrawingBrush> como el <xref:System.Windows.Media.Media3D.Material> aplicado a un modelo 3D.  
  
 El código siguiente define un <xref:System.Windows.Media.DrawingGroup> como el contenido de un <xref:System.Windows.Media.DrawingBrush>.  El <xref:System.Windows.Media.DrawingBrush> se establece como el <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> propiedad de la <xref:System.Windows.Media.Media3D.DiffuseMaterial> aplicado a un plano 3D.  
  
 **Nota:** A menudo es conveniente definir los objetos complejos y los valores como el siguiente dibujo como recursos que se pueden reutilizar y simplificarán el código. Consulte [recursos XAML](../advanced/xaml-resources.md) para obtener más información.  
  
 [!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]  
  
## <a name="example"></a>Ejemplo  
 El código siguiente muestra el ejemplo completo.  
  
 [!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]  
  
## <a name="see-also"></a>Vea también

- [Recursos XAML](../advanced/xaml-resources.md)
- [Crear una escena 3D](how-to-create-a-3-d-scene.md)
- [Información general sobre objetos Drawing](drawing-objects-overview.md)
- [Información general sobre gráficos 3D](3-d-graphics-overview.md)
