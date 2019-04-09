---
title: Filtrar Crear una reflexión
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating reflections [WPF]
- brushes [WPF], creating reflections
- reflections [WPF], creating
ms.assetid: 4f017e16-ab80-43c7-98df-03b6bddbb203
ms.openlocfilehash: 61b597cd36fcf0d60f215d9b5403f3b42b21dec4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59105266"
---
# <a name="how-to-create-a-reflection"></a>Filtrar Crear una reflexión
En este ejemplo se muestra cómo usar un <xref:System.Windows.Media.VisualBrush> para crear un reflejo. Dado que un <xref:System.Windows.Media.VisualBrush> puede mostrar un objeto visual existente, puede utilizar esta capacidad para producir efectos visuales interesantes, como reflejos y aumentos.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.VisualBrush> para crear un reflejo de una <xref:System.Windows.Controls.Border> que contiene varios elementos. En la ilustración siguiente se muestra el resultado que genera el ejemplo.  
  
 ![Un objeto Visual de reflejan](./media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")  
Objeto Visual reflejado  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 Para el ejemplo completo, que incluye ejemplos que muestran cómo aumentar partes de la pantalla y cómo crear reflejos, vea [ejemplo de VisualBrush](https://go.microsoft.com/fwlink/?LinkID=160049).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.VisualBrush>
- [Pintar con imágenes, dibujos y elementos visuales](painting-with-images-drawings-and-visuals.md)
