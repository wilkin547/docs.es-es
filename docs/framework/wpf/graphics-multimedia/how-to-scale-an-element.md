---
title: Procedimiento Ajustar la escala de un elemento
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], elements
- graphics [WPF], scaling elements
ms.assetid: 18158d94-bbe7-4f6a-814e-84d27fa748bf
ms.openlocfilehash: 607b3a11085f746503c1b82552f1740b49d9ef5d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942081"
---
# <a name="how-to-scale-an-element"></a><span data-ttu-id="72540-102">Procedimiento Ajustar la escala de un elemento</span><span class="sxs-lookup"><span data-stu-id="72540-102">How to: Scale an Element</span></span>
<span data-ttu-id="72540-103">En este ejemplo se muestra cómo usar un <xref:System.Windows.Media.ScaleTransform> para escalar un elemento.</span><span class="sxs-lookup"><span data-stu-id="72540-103">This example shows how to use a <xref:System.Windows.Media.ScaleTransform> to scale an element.</span></span>  
  
 <span data-ttu-id="72540-104">Use la <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> y <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> propiedades para cambiar el tamaño del elemento por el factor que especifique.</span><span class="sxs-lookup"><span data-stu-id="72540-104">Use the <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> and <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> properties to resize the element by the factor you specify.</span></span> <span data-ttu-id="72540-105">Por ejemplo, un <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> valor de 1,5 ajusta el elemento al 150 por ciento de su ancho original.</span><span class="sxs-lookup"><span data-stu-id="72540-105">For example, a <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> value of 1.5 stretches the element to 150 percent of its original width.</span></span> <span data-ttu-id="72540-106">Un <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> valor de 0,5 reduce el alto de un elemento en un 50%.</span><span class="sxs-lookup"><span data-stu-id="72540-106">A <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> value of 0.5 shrinks the height of an element by 50 percent.</span></span>  
  
 <span data-ttu-id="72540-107">Use la <xref:System.Windows.Media.ScaleTransform.CenterX%2A> y <xref:System.Windows.Media.ScaleTransform.CenterY%2A> propiedades para especificar el punto que es el centro de la operación de escalado.</span><span class="sxs-lookup"><span data-stu-id="72540-107">Use the <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A> properties to specify the point that is the center of the scale operation.</span></span> <span data-ttu-id="72540-108">De forma predeterminada, un <xref:System.Windows.Media.ScaleTransform> se centra en el punto (0,0), que corresponde a la esquina superior izquierda del rectángulo.</span><span class="sxs-lookup"><span data-stu-id="72540-108">By default, a <xref:System.Windows.Media.ScaleTransform> is centered at the point (0,0), which corresponds to the upper-left corner of the rectangle.</span></span> <span data-ttu-id="72540-109">Esto tiene el efecto de mover el elemento y también de que parezca más grande, ya que al aplicar un <xref:System.Windows.Media.Transform>, cambie el espacio de coordenadas en el que reside el objeto.</span><span class="sxs-lookup"><span data-stu-id="72540-109">This has the effect of moving the element and also of making it appear larger, because when you apply a <xref:System.Windows.Media.Transform>, you change the coordinate space in which the object resides.</span></span>  
  
 <span data-ttu-id="72540-110">En el ejemplo siguiente se usa un <xref:System.Windows.Media.ScaleTransform> duplicar el tamaño de un 50 por 50 <xref:System.Windows.Shapes.Rectangle>.</span><span class="sxs-lookup"><span data-stu-id="72540-110">The following example uses a <xref:System.Windows.Media.ScaleTransform> to double the size of a 50-by-50 <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="72540-111">El <xref:System.Windows.Media.ScaleTransform> tiene un valor de 0 (valor predeterminado) para ambos <xref:System.Windows.Media.ScaleTransform.CenterX%2A> y <xref:System.Windows.Media.ScaleTransform.CenterY%2A>.</span><span class="sxs-lookup"><span data-stu-id="72540-111">The <xref:System.Windows.Media.ScaleTransform> has a value of 0 (the default) for both <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72540-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="72540-112">Example</span></span>  
 [!code-xaml[transformsSample#21](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#21)]  
  
 <span data-ttu-id="72540-113">Normalmente, se establece <xref:System.Windows.Media.ScaleTransform.CenterX%2A> y <xref:System.Windows.Media.ScaleTransform.CenterY%2A> al centro del objeto que se escala: (<xref:System.Windows.FrameworkElement.Width%2A>/2,  <xref:System.Windows.FrameworkElement.Height%2A> /2).</span><span class="sxs-lookup"><span data-stu-id="72540-113">Typically, you set <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A> to the center of the object that is scaled: (<xref:System.Windows.FrameworkElement.Width%2A>/2, <xref:System.Windows.FrameworkElement.Height%2A>/2).</span></span>  
  
 <span data-ttu-id="72540-114">El ejemplo siguiente muestra otro <xref:System.Windows.Shapes.Rectangle> que tiene el doble de tamaño; sin embargo, esto <xref:System.Windows.Media.ScaleTransform> tiene un valor de 25 para ambos <xref:System.Windows.Media.ScaleTransform.CenterX%2A> y <xref:System.Windows.Media.ScaleTransform.CenterY%2A>, que se corresponde con el centro del rectángulo.</span><span class="sxs-lookup"><span data-stu-id="72540-114">The following example shows another <xref:System.Windows.Shapes.Rectangle> that is doubled in size; however, this <xref:System.Windows.Media.ScaleTransform> has a value of 25 for both <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A>, which corresponds to the center of the rectangle.</span></span>  
  
 [!code-xaml[transformsSample#22](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#22)]  
  
 <span data-ttu-id="72540-115">La siguiente ilustración muestra la diferencia entre los dos <xref:System.Windows.Media.ScaleTransform> operaciones.</span><span class="sxs-lookup"><span data-stu-id="72540-115">The following illustration shows the difference between the two <xref:System.Windows.Media.ScaleTransform> operations.</span></span> <span data-ttu-id="72540-116">La línea de puntos muestra el tamaño y la posición del rectángulo antes de escalar.</span><span class="sxs-lookup"><span data-stu-id="72540-116">The dotted line shows the size and position of the rectangle before scaling.</span></span>  
  
 <span data-ttu-id="72540-117">![2 x se puede ampliar con diferentes puntos centrales](./media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")</span><span class="sxs-lookup"><span data-stu-id="72540-117">![2x scales with different center points](./media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")</span></span>  
<span data-ttu-id="72540-118">Dos operaciones de ScaleTransform con valores idénticos de ScaleX y ScaleY pero con centros diferentes</span><span class="sxs-lookup"><span data-stu-id="72540-118">Two ScaleTransform operations with identical ScaleX and ScaleY values but different centers</span></span>  
  
 <span data-ttu-id="72540-119">Para ver el ejemplo completo, consulte [Ejemplo de transformaciones 2D](https://go.microsoft.com/fwlink/?LinkID=158252).</span><span class="sxs-lookup"><span data-stu-id="72540-119">For the complete sample, see [2-D Transforms Sample](https://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72540-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="72540-120">See also</span></span>

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.ScaleTransform>
- [<span data-ttu-id="72540-121">Información general sobre transformaciones</span><span class="sxs-lookup"><span data-stu-id="72540-121">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="72540-122">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="72540-122">How-to Topics</span></span>](transformations-how-to-topics.md)
