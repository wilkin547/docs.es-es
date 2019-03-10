---
title: Filtrar Use una matriz de colores para establecer valores alfabéticos en imágenes
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using color matrices for semi-transparent
- transparency [Windows Forms], color matrices
- matrices [Windows Forms], alpha values
- bitmaps [Windows Forms], using color matrices for semi-transparent
ms.assetid: a27121e6-f7e9-4c09-84e2-f05aa9d2a1bb
ms.openlocfilehash: 9e102f51d00953d05ed1d217a345e32178676ffe
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716340"
---
# <a name="how-to-use-a-color-matrix-to-set-alpha-values-in-images"></a><span data-ttu-id="8f5e8-102">Procedimiento Use una matriz de colores para establecer valores alfabéticos en imágenes</span><span class="sxs-lookup"><span data-stu-id="8f5e8-102">How to: Use a Color Matrix to Set Alpha Values in Images</span></span>
<span data-ttu-id="8f5e8-103">El <xref:System.Drawing.Bitmap> clase (que hereda de la <xref:System.Drawing.Image> clase) y la <xref:System.Drawing.Imaging.ImageAttributes> clase proporcionan funcionalidad para obtener y establecer valores de píxel.</span><span class="sxs-lookup"><span data-stu-id="8f5e8-103">The <xref:System.Drawing.Bitmap> class (which inherits from the <xref:System.Drawing.Image> class) and the <xref:System.Drawing.Imaging.ImageAttributes> class provide functionality for getting and setting pixel values.</span></span> <span data-ttu-id="8f5e8-104">Puede usar el <xref:System.Drawing.Imaging.ImageAttributes> clase para modificar la versión alfa de los valores de una imagen completa, o bien puede llamar el <xref:System.Drawing.Bitmap.SetPixel%2A> método de la <xref:System.Drawing.Bitmap> clase para modificar valores de píxeles individuales.</span><span class="sxs-lookup"><span data-stu-id="8f5e8-104">You can use the <xref:System.Drawing.Imaging.ImageAttributes> class to modify the alpha values for an entire image, or you can call the <xref:System.Drawing.Bitmap.SetPixel%2A> method of the <xref:System.Drawing.Bitmap> class to modify individual pixel values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f5e8-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8f5e8-105">Example</span></span>  
 <span data-ttu-id="8f5e8-106">La <xref:System.Drawing.Imaging.ImageAttributes> clase tiene muchas propiedades que puede usar para modificar las imágenes durante la representación.</span><span class="sxs-lookup"><span data-stu-id="8f5e8-106">The <xref:System.Drawing.Imaging.ImageAttributes> class has many properties that you can use to modify images during rendering.</span></span> <span data-ttu-id="8f5e8-107">En el ejemplo siguiente, un <xref:System.Drawing.Imaging.ImageAttributes> objeto se usa para establecer todos los valores alfa en 80 por ciento de su estado original.</span><span class="sxs-lookup"><span data-stu-id="8f5e8-107">In the following example, an <xref:System.Drawing.Imaging.ImageAttributes> object is used to set all the alpha values to 80 percent of what they were.</span></span> <span data-ttu-id="8f5e8-108">Esto se hace al inicializar una matriz de colores y estableciendo el valor de la matriz en 0,8 de escala de alfa.</span><span class="sxs-lookup"><span data-stu-id="8f5e8-108">This is done by initializing a color matrix and setting the alpha scaling value in the matrix to 0.8.</span></span> <span data-ttu-id="8f5e8-109">La dirección de la matriz de colores se pasa a la <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> método de la <xref:System.Drawing.Imaging.ImageAttributes> objeto y el <xref:System.Drawing.Imaging.ImageAttributes> objeto se pasa a la <xref:System.Drawing.Graphics.DrawString%2A> método de la <xref:System.Drawing.Graphics> objeto.</span><span class="sxs-lookup"><span data-stu-id="8f5e8-109">The address of the color matrix is passed to the <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> method of the <xref:System.Drawing.Imaging.ImageAttributes> object, and the <xref:System.Drawing.Imaging.ImageAttributes> object is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> object.</span></span>  
  
 <span data-ttu-id="8f5e8-110">Durante la representación, los valores alfa en el mapa de bits se convierten en 80 por ciento de su estado original.</span><span class="sxs-lookup"><span data-stu-id="8f5e8-110">During rendering, the alpha values in the bitmap are converted to 80 percent of what they were.</span></span> <span data-ttu-id="8f5e8-111">Esto da como resultado una imagen que se mezcla con el fondo.</span><span class="sxs-lookup"><span data-stu-id="8f5e8-111">This results in an image that is blended with the background.</span></span> <span data-ttu-id="8f5e8-112">Como se muestra en la siguiente ilustración, la imagen de mapa de bits es transparente; puede ver la línea negra sólida a través de él.</span><span class="sxs-lookup"><span data-stu-id="8f5e8-112">As the following illustration shows, the bitmap image looks transparent; you can see the solid black line through it.</span></span>  
  
 <span data-ttu-id="8f5e8-113">![Combinación alfa usando una matriz](./media/image2.png "image2")</span><span class="sxs-lookup"><span data-stu-id="8f5e8-113">![Alpha Blending Using a Matrix](./media/image2.png "image2")</span></span>  
  
 <span data-ttu-id="8f5e8-114">Donde es la imagen a través de la parte del fondo en blanco, la imagen se ha mezclado con el color blanco.</span><span class="sxs-lookup"><span data-stu-id="8f5e8-114">Where the image is over the white portion of the background, the image has been blended with the color white.</span></span> <span data-ttu-id="8f5e8-115">Donde la imagen cruza la línea negra, la imagen se mezcla con el color negro.</span><span class="sxs-lookup"><span data-stu-id="8f5e8-115">Where the image crosses the black line, the image is blended with the color black.</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.AlphaBlending#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8f5e8-116">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="8f5e8-116">Compiling the Code</span></span>  
 <span data-ttu-id="8f5e8-117">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs>`e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="8f5e8-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f5e8-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f5e8-118">See also</span></span>
- [<span data-ttu-id="8f5e8-119">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8f5e8-119">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="8f5e8-120">Líneas y rellenos con combinación alfa</span><span class="sxs-lookup"><span data-stu-id="8f5e8-120">Alpha Blending Lines and Fills</span></span>](alpha-blending-lines-and-fills.md)
