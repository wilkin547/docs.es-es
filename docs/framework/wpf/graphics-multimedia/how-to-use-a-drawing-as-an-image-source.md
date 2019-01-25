---
title: Procedimiento Usar un dibujo como el origen de una imagen
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], drawings [WPF], as image sources
- image sources [WPF], drawings
- drawings [WPF], as image sources
ms.assetid: dcf71c7b-9e86-4b8e-8e39-0d0ce0389ef4
ms.openlocfilehash: 01c8cd65128ce4e78dcbf9e38519091767b7ba2f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54499280"
---
# <a name="how-to-use-a-drawing-as-an-image-source"></a><span data-ttu-id="9e2e9-102">Procedimiento Usar un dibujo como el origen de una imagen</span><span class="sxs-lookup"><span data-stu-id="9e2e9-102">How to: Use a Drawing as an Image Source</span></span>
<span data-ttu-id="9e2e9-103">En este ejemplo se muestra cómo usar un <xref:System.Windows.Media.Drawing> como el <xref:System.Windows.Controls.Image.Source%2A> para un <xref:System.Windows.Controls.Image> control.</span><span class="sxs-lookup"><span data-stu-id="9e2e9-103">This example shows how to use a <xref:System.Windows.Media.Drawing> as the <xref:System.Windows.Controls.Image.Source%2A> for an <xref:System.Windows.Controls.Image> control.</span></span> <span data-ttu-id="9e2e9-104">Para mostrar un <xref:System.Windows.Media.Drawing> con un <xref:System.Windows.Controls.Image> controlar, use un <xref:System.Windows.Media.DrawingImage> como el <xref:System.Windows.Controls.Image> del control <xref:System.Windows.Controls.Image.Source%2A> y establezca el <xref:System.Windows.Media.DrawingImage> del objeto <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> propiedad para el dibujo que desea mostrar.</span><span class="sxs-lookup"><span data-stu-id="9e2e9-104">To display a <xref:System.Windows.Media.Drawing> with an <xref:System.Windows.Controls.Image> control, use a <xref:System.Windows.Media.DrawingImage> as the <xref:System.Windows.Controls.Image> control's <xref:System.Windows.Controls.Image.Source%2A> and set the <xref:System.Windows.Media.DrawingImage> object's <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> property to the drawing you want to display.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e2e9-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9e2e9-105">Example</span></span>  
 <span data-ttu-id="9e2e9-106">En el ejemplo siguiente se usa un <xref:System.Windows.Media.DrawingImage> y un <xref:System.Windows.Controls.Image> control para mostrar un <xref:System.Windows.Media.GeometryDrawing>.</span><span class="sxs-lookup"><span data-stu-id="9e2e9-106">The following example uses a <xref:System.Windows.Media.DrawingImage> and an <xref:System.Windows.Controls.Image> control to display a <xref:System.Windows.Media.GeometryDrawing>.</span></span> <span data-ttu-id="9e2e9-107">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="9e2e9-107">This example produces the following output:</span></span>  
  
 <span data-ttu-id="9e2e9-108">![GeometryDrawing de dos elipses](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span><span class="sxs-lookup"><span data-stu-id="9e2e9-108">![A GeometryDrawing of two ellipses](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span></span>  
<span data-ttu-id="9e2e9-109">DrawingImage</span><span class="sxs-lookup"><span data-stu-id="9e2e9-109">A DrawingImage</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="9e2e9-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e2e9-110">See also</span></span>
- <xref:System.Windows.Freezable.Freeze%2A>
- [<span data-ttu-id="9e2e9-111">Dibujar una imagen usando un objeto ImageDrawing</span><span class="sxs-lookup"><span data-stu-id="9e2e9-111">Draw an Image Using ImageDrawing</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-draw-an-image-using-imagedrawing.md)
- [<span data-ttu-id="9e2e9-112">Información general sobre objetos Drawing</span><span class="sxs-lookup"><span data-stu-id="9e2e9-112">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
- [<span data-ttu-id="9e2e9-113">Información general sobre objetos Freezable</span><span class="sxs-lookup"><span data-stu-id="9e2e9-113">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)
- [<span data-ttu-id="9e2e9-114">PresentationOptions:Freeze (Atributo)</span><span class="sxs-lookup"><span data-stu-id="9e2e9-114">PresentationOptions:Freeze Attribute</span></span>](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)
