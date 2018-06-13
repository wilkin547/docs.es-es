---
title: 'Cómo: Construir fuentes y familias de fuentes'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- font families [Windows Forms], constructing
- fonts [Windows Forms], constructing
ms.assetid: d3a4a223-9492-4b54-9afd-db1c31c3cefd
ms.openlocfilehash: ceace5950ec135ea4d52081da7d1de7a820583ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33520895"
---
# <a name="how-to-construct-font-families-and-fonts"></a><span data-ttu-id="2f052-102">Cómo: Construir fuentes y familias de fuentes</span><span class="sxs-lookup"><span data-stu-id="2f052-102">How to: Construct Font Families and Fonts</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="2f052-103"> agrupa las fuentes con el mismo tipo de letra pero distintos estilos en familias de fuentes.</span><span class="sxs-lookup"><span data-stu-id="2f052-103"> groups fonts with the same typeface but different styles into font families.</span></span> <span data-ttu-id="2f052-104">Por ejemplo, la familia de fuentes Arial contiene las siguientes fuentes:</span><span class="sxs-lookup"><span data-stu-id="2f052-104">For example, the Arial font family contains the following fonts:</span></span>  
  
-   <span data-ttu-id="2f052-105">Arial normal</span><span class="sxs-lookup"><span data-stu-id="2f052-105">Arial Regular</span></span>  
  
-   <span data-ttu-id="2f052-106">Arial negrita</span><span class="sxs-lookup"><span data-stu-id="2f052-106">Arial Bold</span></span>  
  
-   <span data-ttu-id="2f052-107">Arial cursiva</span><span class="sxs-lookup"><span data-stu-id="2f052-107">Arial Italic</span></span>  
  
-   <span data-ttu-id="2f052-108">Arial negrita cursiva</span><span class="sxs-lookup"><span data-stu-id="2f052-108">Arial Bold Italic</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="2f052-109"> utiliza cuatro estilos para formar familias: normal, negrita, cursiva y negrita cursiva.</span><span class="sxs-lookup"><span data-stu-id="2f052-109"> uses four styles to form families: regular, bold, italic, and bold italic.</span></span> <span data-ttu-id="2f052-110">Adjetivos como *restringir* y *redondea* no se consideran estilos; en su lugar forman parte del nombre de familia.</span><span class="sxs-lookup"><span data-stu-id="2f052-110">Adjectives such as *narrow* and *rounded* are not considered styles; rather they are part of the family name.</span></span> <span data-ttu-id="2f052-111">Por ejemplo, Arial Narrow es una familia de fuentes con los miembros siguientes:</span><span class="sxs-lookup"><span data-stu-id="2f052-111">For example, Arial Narrow is a font family with the following members:</span></span>  
  
-   <span data-ttu-id="2f052-112">Arial Narrow Normal</span><span class="sxs-lookup"><span data-stu-id="2f052-112">Arial Narrow Regular</span></span>  
  
-   <span data-ttu-id="2f052-113">Arial Narrow negrita</span><span class="sxs-lookup"><span data-stu-id="2f052-113">Arial Narrow Bold</span></span>  
  
-   <span data-ttu-id="2f052-114">Arial Narrow Cursiva</span><span class="sxs-lookup"><span data-stu-id="2f052-114">Arial Narrow Italic</span></span>  
  
-   <span data-ttu-id="2f052-115">Arial Narrow negrita cursiva</span><span class="sxs-lookup"><span data-stu-id="2f052-115">Arial Narrow Bold Italic</span></span>  
  
 <span data-ttu-id="2f052-116">Antes de poder dibujar texto con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], deberá construir un <xref:System.Drawing.FontFamily> objeto y un <xref:System.Drawing.Font> objeto.</span><span class="sxs-lookup"><span data-stu-id="2f052-116">Before you can draw text with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you need to construct a <xref:System.Drawing.FontFamily> object and a <xref:System.Drawing.Font> object.</span></span> <span data-ttu-id="2f052-117">El <xref:System.Drawing.FontFamily> objeto especifica el tipo de letra (por ejemplo, Arial) y el <xref:System.Drawing.Font> objeto especifica el tamaño, estilo y las unidades.</span><span class="sxs-lookup"><span data-stu-id="2f052-117">The <xref:System.Drawing.FontFamily> object specifies the typeface (for example, Arial), and the <xref:System.Drawing.Font> object specifies the size, style, and units.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f052-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2f052-118">Example</span></span>  
 <span data-ttu-id="2f052-119">En el ejemplo siguiente se crea un estilo normal fuente Arial con un tamaño de 16 píxeles.</span><span class="sxs-lookup"><span data-stu-id="2f052-119">The following example constructs a regular style Arial font with a size of 16 pixels.</span></span> <span data-ttu-id="2f052-120">En el código siguiente, el primer argumento pasado a la <xref:System.Drawing.Font.%23ctor%2A> constructor es el <xref:System.Drawing.FontFamily> objeto.</span><span class="sxs-lookup"><span data-stu-id="2f052-120">In the following code, the first argument passed to the <xref:System.Drawing.Font.%23ctor%2A> constructor is the <xref:System.Drawing.FontFamily> object.</span></span> <span data-ttu-id="2f052-121">El segundo argumento especifica el tamaño de la fuente medido en unidades identificadas por el cuarto argumento.</span><span class="sxs-lookup"><span data-stu-id="2f052-121">The second argument specifies the size of the font measured in units identified by the fourth argument.</span></span> <span data-ttu-id="2f052-122">El tercer argumento identifica el estilo.</span><span class="sxs-lookup"><span data-stu-id="2f052-122">The third argument identifies the style.</span></span>  
  
 <span data-ttu-id="2f052-123"><xref:System.Drawing.GraphicsUnit.Pixel> es un miembro de la <xref:System.Drawing.GraphicsUnit> enumeración, y <xref:System.Drawing.FontStyle.Regular> es un miembro de la <xref:System.Drawing.FontStyle> enumeración.</span><span class="sxs-lookup"><span data-stu-id="2f052-123"><xref:System.Drawing.GraphicsUnit.Pixel> is a member of the <xref:System.Drawing.GraphicsUnit> enumeration, and <xref:System.Drawing.FontStyle.Regular> is a member of the <xref:System.Drawing.FontStyle> enumeration.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.FontsAndText#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2f052-124">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="2f052-124">Compiling the Code</span></span>  
 <span data-ttu-id="2f052-125">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="2f052-125">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f052-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f052-126">See Also</span></span>  
 [<span data-ttu-id="2f052-127">Utilizar fuentes y texto</span><span class="sxs-lookup"><span data-stu-id="2f052-127">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [<span data-ttu-id="2f052-128">Gráficos y dibujos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2f052-128">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
