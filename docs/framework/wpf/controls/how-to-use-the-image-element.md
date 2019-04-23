---
title: Procedimiento Usar el elemento de imagen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Image
- Image control [WPF]
- rendering images [WPF]
ms.assetid: 5b92e74b-1b56-4756-ac64-d5e9e08d9854
ms.openlocfilehash: 967159894e25721bdf380f851712e91d76088f87
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59205308"
---
# <a name="how-to-use-the-image-element"></a><span data-ttu-id="9008a-102">Procedimiento Usar el elemento de imagen</span><span class="sxs-lookup"><span data-stu-id="9008a-102">How to: Use the Image Element</span></span>
<span data-ttu-id="9008a-103">En este ejemplo se muestra cómo incluir imágenes en una aplicación mediante el <xref:System.Windows.Controls.Image> elemento.</span><span class="sxs-lookup"><span data-stu-id="9008a-103">This example shows how to include images in an application by using the <xref:System.Windows.Controls.Image> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9008a-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9008a-104">Example</span></span>  
 <span data-ttu-id="9008a-105">En el siguiente ejemplo se muestra cómo representar una imagen de 200 píxeles de ancho.</span><span class="sxs-lookup"><span data-stu-id="9008a-105">The following example shows how to render an image 200 pixels wide.</span></span> <span data-ttu-id="9008a-106">En este ejemplo de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], tanto la sintaxis de atributo como la sintaxis de etiquetas de propiedad se usan para definir la imagen.</span><span class="sxs-lookup"><span data-stu-id="9008a-106">In this [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example, both attribute syntax and property tag syntax are used to define the image.</span></span> <span data-ttu-id="9008a-107">Para más información sobre la sintaxis de atributo y la sintaxis de propiedad, consulte [Información general sobre las propiedades de dependencia](../advanced/dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9008a-107">For more information on attribute syntax and property syntax, see [Dependency Properties Overview](../advanced/dependency-properties-overview.md).</span></span> <span data-ttu-id="9008a-108">Un <xref:System.Windows.Media.Imaging.BitmapImage> se utiliza para definir los datos de origen de la imagen y se define explícitamente para el ejemplo de sintaxis de la etiqueta de propiedad.</span><span class="sxs-lookup"><span data-stu-id="9008a-108">A <xref:System.Windows.Media.Imaging.BitmapImage> is used to define the image's source data and is explicitly defined for the property tag syntax example.</span></span> <span data-ttu-id="9008a-109">Además, el <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> de la <xref:System.Windows.Media.Imaging.BitmapImage> se establece en el mismo ancho que el <xref:System.Windows.FrameworkElement.Width%2A> de la <xref:System.Windows.Controls.Image>.</span><span class="sxs-lookup"><span data-stu-id="9008a-109">In addition, the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> of the <xref:System.Windows.Media.Imaging.BitmapImage> is set to the same width as the <xref:System.Windows.FrameworkElement.Width%2A> of the <xref:System.Windows.Controls.Image>.</span></span> <span data-ttu-id="9008a-110">Esto se hace para garantizar que la cantidad mínima de memoria se use para representar la imagen.</span><span class="sxs-lookup"><span data-stu-id="9008a-110">This is done to ensure that the minimum amount of memory is used rendering the image.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9008a-111">En general, si desea especificar el tamaño de una imagen representada, especifique solo el <xref:System.Windows.FrameworkElement.Width%2A> o <xref:System.Windows.FrameworkElement.Height%2A> , pero no ambos.</span><span class="sxs-lookup"><span data-stu-id="9008a-111">In general, if you want to specify the size of a rendered image, specify only the <xref:System.Windows.FrameworkElement.Width%2A> or the <xref:System.Windows.FrameworkElement.Height%2A> but not both.</span></span> <span data-ttu-id="9008a-112">Si solo especifica uno, se conserva la relación de aspecto de la imagen.</span><span class="sxs-lookup"><span data-stu-id="9008a-112">If you only specify one, the image's aspect ratio is preserved.</span></span> <span data-ttu-id="9008a-113">De lo contrario, la imagen puede aparecer ajustada o distorsionada de forma inesperada.</span><span class="sxs-lookup"><span data-stu-id="9008a-113">Otherwise, the image may unexpectedly appear stretched or warped.</span></span> <span data-ttu-id="9008a-114">Para controlar la imagen del comportamiento de ajuste de, use la <xref:System.Windows.Controls.Image.Stretch%2A> y <xref:System.Windows.Controls.Image.StretchDirection%2A> propiedades.</span><span class="sxs-lookup"><span data-stu-id="9008a-114">To control the image's stretching behavior, use the <xref:System.Windows.Controls.Image.Stretch%2A> and <xref:System.Windows.Controls.Image.StretchDirection%2A> properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9008a-115">Al especificar el tamaño de una imagen con <xref:System.Windows.FrameworkElement.Width%2A> o <xref:System.Windows.FrameworkElement.Height%2A>, también se debe establecer <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> o <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelHeight%2A> con el mismo tamaño respectivo.</span><span class="sxs-lookup"><span data-stu-id="9008a-115">When you specify the size of an image with either <xref:System.Windows.FrameworkElement.Width%2A> or <xref:System.Windows.FrameworkElement.Height%2A>, you should also set either <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> or <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelHeight%2A> to the same respective size.</span></span>  
  
 <span data-ttu-id="9008a-116">El <xref:System.Windows.Controls.Image.Stretch%2A> propiedad determina cómo el origen de la imagen se ajusta para rellenar el elemento de imagen.</span><span class="sxs-lookup"><span data-stu-id="9008a-116">The <xref:System.Windows.Controls.Image.Stretch%2A> property determines how the image source is stretched to fill the image element.</span></span> <span data-ttu-id="9008a-117">Para obtener más información, vea la enumeración <xref:System.Windows.Media.Stretch>.</span><span class="sxs-lookup"><span data-stu-id="9008a-117">For more information, see the <xref:System.Windows.Media.Stretch> enumeration.</span></span>  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a><span data-ttu-id="9008a-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9008a-118">Example</span></span>  
 <span data-ttu-id="9008a-119">En el siguiente ejemplo se muestra cómo representar una imagen de 200 píxeles de ancho mediante código.</span><span class="sxs-lookup"><span data-stu-id="9008a-119">The following example shows how to render an image 200 pixels wide using code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9008a-120">Establecer <xref:System.Windows.Media.Imaging.BitmapImage> propiedades deben realizarse dentro de un <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> y <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> bloque.</span><span class="sxs-lookup"><span data-stu-id="9008a-120">Setting <xref:System.Windows.Media.Imaging.BitmapImage> properties must be done within a <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> and <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> block.</span></span>  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a><span data-ttu-id="9008a-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="9008a-121">See also</span></span>

- [<span data-ttu-id="9008a-122">Información general sobre imágenes</span><span class="sxs-lookup"><span data-stu-id="9008a-122">Imaging Overview</span></span>](../graphics-multimedia/imaging-overview.md)
