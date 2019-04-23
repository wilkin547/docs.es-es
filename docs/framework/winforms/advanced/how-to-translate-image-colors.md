---
title: Procedimiento para convertir colores de imágenes
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], changing colors
- images [Windows Forms], changing colors
- image colors [Windows Forms]
ms.assetid: 2106fb9a-4d60-4dcf-9220-9f189a6c4d19
ms.openlocfilehash: 04e61383ef79b17ea6e1523588cd9593ec9b082c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59132644"
---
# <a name="how-to-translate-image-colors"></a><span data-ttu-id="4372e-102">Procedimiento para convertir colores de imágenes</span><span class="sxs-lookup"><span data-stu-id="4372e-102">How to: Translate Image Colors</span></span>
<span data-ttu-id="4372e-103">Una traducción, agrega un valor a uno o varios de los cuatro componentes de color.</span><span class="sxs-lookup"><span data-stu-id="4372e-103">A translation adds a value to one or more of the four color components.</span></span> <span data-ttu-id="4372e-104">En la siguiente tabla figuran las entradas de la matriz de color que representan las traducciones.</span><span class="sxs-lookup"><span data-stu-id="4372e-104">The color matrix entries that represent translations are given in the following table.</span></span>  
  
|<span data-ttu-id="4372e-105">Componente que se deben traducir</span><span class="sxs-lookup"><span data-stu-id="4372e-105">Component to be translated</span></span>|<span data-ttu-id="4372e-106">Entrada de matriz</span><span class="sxs-lookup"><span data-stu-id="4372e-106">Matrix entry</span></span>|  
|--------------------------------|------------------|  
|<span data-ttu-id="4372e-107">Rojo</span><span class="sxs-lookup"><span data-stu-id="4372e-107">Red</span></span>|<span data-ttu-id="4372e-108">[4][0]</span><span class="sxs-lookup"><span data-stu-id="4372e-108">[4][0]</span></span>|  
|<span data-ttu-id="4372e-109">Verde</span><span class="sxs-lookup"><span data-stu-id="4372e-109">Green</span></span>|<span data-ttu-id="4372e-110">[4][1]</span><span class="sxs-lookup"><span data-stu-id="4372e-110">[4][1]</span></span>|  
|<span data-ttu-id="4372e-111">Azul</span><span class="sxs-lookup"><span data-stu-id="4372e-111">Blue</span></span>|<span data-ttu-id="4372e-112">[4][2]</span><span class="sxs-lookup"><span data-stu-id="4372e-112">[4][2]</span></span>|  
|<span data-ttu-id="4372e-113">Alpha</span><span class="sxs-lookup"><span data-stu-id="4372e-113">Alpha</span></span>|<span data-ttu-id="4372e-114">[4][3]</span><span class="sxs-lookup"><span data-stu-id="4372e-114">[4][3]</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4372e-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4372e-115">Example</span></span>  
 <span data-ttu-id="4372e-116">En el ejemplo siguiente se crea un <xref:System.Drawing.Image> objeto a partir del archivo ColorBars.bmp.</span><span class="sxs-lookup"><span data-stu-id="4372e-116">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars.bmp.</span></span> <span data-ttu-id="4372e-117">A continuación, el código agrega 0,75 al componente rojo de cada píxel de la imagen.</span><span class="sxs-lookup"><span data-stu-id="4372e-117">Then the code adds 0.75 to the red component of each pixel in the image.</span></span> <span data-ttu-id="4372e-118">Se dibuja la imagen original junto con la imagen transformada.</span><span class="sxs-lookup"><span data-stu-id="4372e-118">The original image is drawn alongside the transformed image.</span></span>  
  
 <span data-ttu-id="4372e-119">La siguiente ilustración muestra la imagen original a la izquierda y la imagen transformada de la derecha:</span><span class="sxs-lookup"><span data-stu-id="4372e-119">The following illustration shows the original image on the left and the transformed image on the right:</span></span>  
  
 ![Captura de pantalla de la imagen original y transformada.](./media/how-to-translate-image-colors/original-image-translate-colors.png)  
  
 <span data-ttu-id="4372e-121">En la tabla siguiente se enumera los vectores de color de las cuatro barras antes y después de la traducción de color rojo.</span><span class="sxs-lookup"><span data-stu-id="4372e-121">The following table lists the color vectors for the four bars before and after the red translation.</span></span> <span data-ttu-id="4372e-122">Tenga en cuenta que dado que el valor máximo para un componente de color es 1, el componente rojo de la segunda fila no cambia.</span><span class="sxs-lookup"><span data-stu-id="4372e-122">Note that because the maximum value for a color component is 1, the red component in the second row does not change.</span></span> <span data-ttu-id="4372e-123">(De forma similar, el valor mínimo de un componente de color es 0).</span><span class="sxs-lookup"><span data-stu-id="4372e-123">(Similarly, the minimum value for a color component is 0.)</span></span>  
  
|<span data-ttu-id="4372e-124">Original</span><span class="sxs-lookup"><span data-stu-id="4372e-124">Original</span></span>|<span data-ttu-id="4372e-125">Texto traducido al</span><span class="sxs-lookup"><span data-stu-id="4372e-125">Translated</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="4372e-126">Negro (0, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="4372e-126">Black (0, 0, 0, 1)</span></span>|<span data-ttu-id="4372e-127">(0.75, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="4372e-127">(0.75, 0, 0, 1)</span></span>|  
|<span data-ttu-id="4372e-128">Rojo (1, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="4372e-128">Red (1, 0, 0, 1)</span></span>|<span data-ttu-id="4372e-129">(1, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="4372e-129">(1, 0, 0, 1)</span></span>|  
|<span data-ttu-id="4372e-130">Verde (0, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="4372e-130">Green (0, 1, 0, 1)</span></span>|<span data-ttu-id="4372e-131">(0.75, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="4372e-131">(0.75, 1, 0, 1)</span></span>|  
|<span data-ttu-id="4372e-132">Azul (0, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="4372e-132">Blue (0, 0, 1, 1)</span></span>|<span data-ttu-id="4372e-133">(0.75, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="4372e-133">(0.75, 0, 1, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.RecoloringImages#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.RecoloringImages#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4372e-134">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="4372e-134">Compiling the Code</span></span>  
 <span data-ttu-id="4372e-135">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs>`e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="4372e-135">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="4372e-136">Reemplace `ColorBars.bmp` con un nombre de archivo de imagen y la ruta de acceso que son válidos en el sistema.</span><span class="sxs-lookup"><span data-stu-id="4372e-136">Replace `ColorBars.bmp` with an image file name and path that are valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4372e-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="4372e-137">See also</span></span>

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="4372e-138">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4372e-138">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="4372e-139">Cambiar el color de las imágenes</span><span class="sxs-lookup"><span data-stu-id="4372e-139">Recoloring Images</span></span>](recoloring-images.md)
