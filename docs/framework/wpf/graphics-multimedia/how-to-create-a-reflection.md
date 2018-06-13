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
ms.openlocfilehash: c791dbbe02faaba790c650d482db092702730fa6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560581"
---
# <a name="how-to-create-a-reflection"></a><span data-ttu-id="b5487-102">Cómo: Crear una reflexión</span><span class="sxs-lookup"><span data-stu-id="b5487-102">How to: Create a Reflection</span></span>
<span data-ttu-id="b5487-103">Este ejemplo muestra cómo utilizar un <xref:System.Windows.Media.VisualBrush> para crear un reflejo.</span><span class="sxs-lookup"><span data-stu-id="b5487-103">This example shows how to use a <xref:System.Windows.Media.VisualBrush> to create a reflection.</span></span> <span data-ttu-id="b5487-104">Dado que un <xref:System.Windows.Media.VisualBrush> puede mostrar un objeto visual existente, puede utilizar esta capacidad para producir efectos visuales interesantes, tales como reflexiones y ampliaciones.</span><span class="sxs-lookup"><span data-stu-id="b5487-104">Because a <xref:System.Windows.Media.VisualBrush> can display an existing visual, you can use this capability to produce interesting visual effects, such as reflections and magnification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5487-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b5487-105">Example</span></span>  
 <span data-ttu-id="b5487-106">En el ejemplo siguiente se usa un <xref:System.Windows.Media.VisualBrush> para crear un reflejo de una <xref:System.Windows.Controls.Border> que contiene varios elementos.</span><span class="sxs-lookup"><span data-stu-id="b5487-106">The following example uses a <xref:System.Windows.Media.VisualBrush> to create a reflection of a <xref:System.Windows.Controls.Border> that contains several elements.</span></span> <span data-ttu-id="b5487-107">En la ilustración siguiente se muestra el resultado que genera el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b5487-107">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="b5487-108">![Un objeto Visual de reflejan](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")</span><span class="sxs-lookup"><span data-stu-id="b5487-108">![A reflected Visual object](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")</span></span>  
<span data-ttu-id="b5487-109">Objeto Visual reflejado</span><span class="sxs-lookup"><span data-stu-id="b5487-109">A reflected Visual object</span></span>  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 <span data-ttu-id="b5487-110">Para obtener el ejemplo completo, que incluye ejemplos que muestran cómo ampliar partes de la pantalla y la creación de reflejos, vea [VisualBrush Sample](http://go.microsoft.com/fwlink/?LinkID=160049).</span><span class="sxs-lookup"><span data-stu-id="b5487-110">For the complete sample, which includes examples that show how to magnify parts of the screen and how to create reflections, see [VisualBrush Sample](http://go.microsoft.com/fwlink/?LinkID=160049).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5487-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5487-111">See Also</span></span>  
 <xref:System.Windows.Media.VisualBrush>  
 [<span data-ttu-id="b5487-112">Pintar con imágenes, dibujos y elementos visuales</span><span class="sxs-lookup"><span data-stu-id="b5487-112">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
