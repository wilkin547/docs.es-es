---
title: 'Cómo: Crear una reflexión'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating reflections [WPF]
- brushes [WPF], creating reflections
- reflections [WPF], creating
ms.assetid: 4f017e16-ab80-43c7-98df-03b6bddbb203
ms.openlocfilehash: 8a5ed345c0aa25312bd74799264e1f66ab4554e0
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452063"
---
# <a name="how-to-create-a-reflection"></a><span data-ttu-id="ce005-102">Cómo: Crear una reflexión</span><span class="sxs-lookup"><span data-stu-id="ce005-102">How to: Create a Reflection</span></span>
<span data-ttu-id="ce005-103">En este ejemplo se muestra cómo utilizar una <xref:System.Windows.Media.VisualBrush> para crear una reflexión.</span><span class="sxs-lookup"><span data-stu-id="ce005-103">This example shows how to use a <xref:System.Windows.Media.VisualBrush> to create a reflection.</span></span> <span data-ttu-id="ce005-104">Dado que un <xref:System.Windows.Media.VisualBrush> puede mostrar un visual existente, puede usar esta capacidad para generar efectos visuales interesantes, como reflejos y ampliación.</span><span class="sxs-lookup"><span data-stu-id="ce005-104">Because a <xref:System.Windows.Media.VisualBrush> can display an existing visual, you can use this capability to produce interesting visual effects, such as reflections and magnification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce005-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ce005-105">Example</span></span>  
 <span data-ttu-id="ce005-106">En el ejemplo siguiente se usa una <xref:System.Windows.Media.VisualBrush> para crear un reflejo de una <xref:System.Windows.Controls.Border> que contiene varios elementos.</span><span class="sxs-lookup"><span data-stu-id="ce005-106">The following example uses a <xref:System.Windows.Media.VisualBrush> to create a reflection of a <xref:System.Windows.Controls.Border> that contains several elements.</span></span> <span data-ttu-id="ce005-107">En la ilustración siguiente se muestra el resultado que genera el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ce005-107">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="ce005-108">![Objeto Visual reflejado](./media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")</span><span class="sxs-lookup"><span data-stu-id="ce005-108">![A reflected Visual object](./media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")</span></span>  
<span data-ttu-id="ce005-109">Objeto Visual reflejado</span><span class="sxs-lookup"><span data-stu-id="ce005-109">A reflected Visual object</span></span>  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 <span data-ttu-id="ce005-110">Para obtener el ejemplo completo, que incluye ejemplos que muestran cómo ampliar partes de la pantalla y cómo crear reflejos, vea [ejemplo de VisualBrush](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush).</span><span class="sxs-lookup"><span data-stu-id="ce005-110">For the complete sample, which includes examples that show how to magnify parts of the screen and how to create reflections, see [VisualBrush Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce005-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ce005-111">See also</span></span>

- <xref:System.Windows.Media.VisualBrush>
- [<span data-ttu-id="ce005-112">Pintar con imágenes, dibujos y elementos visuales</span><span class="sxs-lookup"><span data-stu-id="ce005-112">Painting with Images, Drawings, and Visuals</span></span>](painting-with-images-drawings-and-visuals.md)
