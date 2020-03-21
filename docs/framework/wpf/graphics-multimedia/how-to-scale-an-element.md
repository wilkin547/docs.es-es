---
title: 'Cómo: Ajustar la escala de un elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], elements
- graphics [WPF], scaling elements
ms.assetid: 18158d94-bbe7-4f6a-814e-84d27fa748bf
ms.openlocfilehash: 34d954f68747be9eedc0ef71634e0c18b411d260
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112055"
---
# <a name="how-to-scale-an-element"></a><span data-ttu-id="1847c-102">Cómo: Ajustar la escala de un elemento</span><span class="sxs-lookup"><span data-stu-id="1847c-102">How to: Scale an Element</span></span>
<span data-ttu-id="1847c-103">En este ejemplo se <xref:System.Windows.Media.ScaleTransform> muestra cómo utilizar a para escalar un elemento.</span><span class="sxs-lookup"><span data-stu-id="1847c-103">This example shows how to use a <xref:System.Windows.Media.ScaleTransform> to scale an element.</span></span>  
  
 <span data-ttu-id="1847c-104">Utilice <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> las <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> propiedades y para cambiar el tamaño del elemento según el factor que especifique.</span><span class="sxs-lookup"><span data-stu-id="1847c-104">Use the <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> and <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> properties to resize the element by the factor you specify.</span></span> <span data-ttu-id="1847c-105">Por ejemplo, <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> un valor de 1,5 estira el elemento al 150 por ciento de su ancho original.</span><span class="sxs-lookup"><span data-stu-id="1847c-105">For example, a <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> value of 1.5 stretches the element to 150 percent of its original width.</span></span> <span data-ttu-id="1847c-106">Un <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> valor de 0,5 reduce la altura de un elemento en un 50 por ciento.</span><span class="sxs-lookup"><span data-stu-id="1847c-106">A <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> value of 0.5 shrinks the height of an element by 50 percent.</span></span>  
  
 <span data-ttu-id="1847c-107">Utilice <xref:System.Windows.Media.ScaleTransform.CenterX%2A> las <xref:System.Windows.Media.ScaleTransform.CenterY%2A> propiedades y para especificar el punto que es el centro de la operación de escala.</span><span class="sxs-lookup"><span data-stu-id="1847c-107">Use the <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A> properties to specify the point that is the center of the scale operation.</span></span> <span data-ttu-id="1847c-108">De forma <xref:System.Windows.Media.ScaleTransform> predeterminada, a se centra en el punto (0,0), que corresponde a la esquina superior izquierda del rectángulo.</span><span class="sxs-lookup"><span data-stu-id="1847c-108">By default, a <xref:System.Windows.Media.ScaleTransform> is centered at the point (0,0), which corresponds to the upper-left corner of the rectangle.</span></span> <span data-ttu-id="1847c-109">Esto tiene el efecto de mover el elemento y también de <xref:System.Windows.Media.Transform>hacerlo parecer más grande, porque cuando se aplica un , se cambia el espacio de coordenadas en el que reside el objeto.</span><span class="sxs-lookup"><span data-stu-id="1847c-109">This has the effect of moving the element and also of making it appear larger, because when you apply a <xref:System.Windows.Media.Transform>, you change the coordinate space in which the object resides.</span></span>  
  
 <span data-ttu-id="1847c-110">En el ejemplo <xref:System.Windows.Media.ScaleTransform> siguiente se utiliza a para duplicar <xref:System.Windows.Shapes.Rectangle>el tamaño de un 50 por 50 .</span><span class="sxs-lookup"><span data-stu-id="1847c-110">The following example uses a <xref:System.Windows.Media.ScaleTransform> to double the size of a 50-by-50 <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="1847c-111">El <xref:System.Windows.Media.ScaleTransform> tiene un valor de 0 <xref:System.Windows.Media.ScaleTransform.CenterX%2A> (valor predeterminado) para ambos y <xref:System.Windows.Media.ScaleTransform.CenterY%2A>.</span><span class="sxs-lookup"><span data-stu-id="1847c-111">The <xref:System.Windows.Media.ScaleTransform> has a value of 0 (the default) for both <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1847c-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1847c-112">Example</span></span>  
 [!code-xaml[transformsSample#21](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#21)]  
  
 <span data-ttu-id="1847c-113">Normalmente, se <xref:System.Windows.Media.ScaleTransform.CenterX%2A> <xref:System.Windows.Media.ScaleTransform.CenterY%2A> establece y se establece en el<xref:System.Windows.FrameworkElement.Width%2A>centro del <xref:System.Windows.FrameworkElement.Height%2A>objeto que se escala: ( /2, /2).</span><span class="sxs-lookup"><span data-stu-id="1847c-113">Typically, you set <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A> to the center of the object that is scaled: (<xref:System.Windows.FrameworkElement.Width%2A>/2, <xref:System.Windows.FrameworkElement.Height%2A>/2).</span></span>  
  
 <span data-ttu-id="1847c-114">En el ejemplo <xref:System.Windows.Shapes.Rectangle> siguiente se muestra otro que se duplica en tamaño; sin <xref:System.Windows.Media.ScaleTransform> embargo, esto tiene un <xref:System.Windows.Media.ScaleTransform.CenterX%2A> <xref:System.Windows.Media.ScaleTransform.CenterY%2A>valor de 25 para ambos y , que corresponde al centro del rectángulo.</span><span class="sxs-lookup"><span data-stu-id="1847c-114">The following example shows another <xref:System.Windows.Shapes.Rectangle> that is doubled in size; however, this <xref:System.Windows.Media.ScaleTransform> has a value of 25 for both <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A>, which corresponds to the center of the rectangle.</span></span>  
  
 [!code-xaml[transformsSample#22](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#22)]  
  
 <span data-ttu-id="1847c-115">En la ilustración siguiente <xref:System.Windows.Media.ScaleTransform> se muestra la diferencia entre las dos operaciones.</span><span class="sxs-lookup"><span data-stu-id="1847c-115">The following illustration shows the difference between the two <xref:System.Windows.Media.ScaleTransform> operations.</span></span> <span data-ttu-id="1847c-116">La línea de puntos muestra el tamaño y la posición del rectángulo antes de escalar.</span><span class="sxs-lookup"><span data-stu-id="1847c-116">The dotted line shows the size and position of the rectangle before scaling.</span></span>  
  
 <span data-ttu-id="1847c-117">![Escalas dobles con diferentes centros](./media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")</span><span class="sxs-lookup"><span data-stu-id="1847c-117">![2x scales with different center points](./media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")</span></span>  
<span data-ttu-id="1847c-118">Dos operaciones de ScaleTransform con valores idénticos de ScaleX y ScaleY pero con centros diferentes</span><span class="sxs-lookup"><span data-stu-id="1847c-118">Two ScaleTransform operations with identical ScaleX and ScaleY values but different centers</span></span>  
  
 <span data-ttu-id="1847c-119">Para ver el ejemplo completo, consulte Ejemplo de [transformaciones 2D](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span><span class="sxs-lookup"><span data-stu-id="1847c-119">For the complete sample, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1847c-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1847c-120">See also</span></span>

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.ScaleTransform>
- [<span data-ttu-id="1847c-121">Información general sobre transformaciones</span><span class="sxs-lookup"><span data-stu-id="1847c-121">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="1847c-122">Temas de información</span><span class="sxs-lookup"><span data-stu-id="1847c-122">How-to Topics</span></span>](transformations-how-to-topics.md)
