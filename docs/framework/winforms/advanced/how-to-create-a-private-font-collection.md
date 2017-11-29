---
title: "Cómo: Crear una colección de fuentes privada"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- private font collections [Windows Forms], creating
- fonts [Windows Forms], creating private collections
ms.assetid: 6533d5e5-a8dc-4b76-9fc4-3bf75c8b9212
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3016fb9a1b1d8466137bcaddb0b885c02c399baf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-private-font-collection"></a><span data-ttu-id="5f31b-102">Cómo: Crear una colección de fuentes privada</span><span class="sxs-lookup"><span data-stu-id="5f31b-102">How to: Create a Private Font Collection</span></span>
<span data-ttu-id="5f31b-103">El <xref:System.Drawing.Text.PrivateFontCollection> clase hereda de la <xref:System.Drawing.Text.FontCollection> clase base abstracta.</span><span class="sxs-lookup"><span data-stu-id="5f31b-103">The <xref:System.Drawing.Text.PrivateFontCollection> class inherits from the <xref:System.Drawing.Text.FontCollection> abstract base class.</span></span> <span data-ttu-id="5f31b-104">Puede usar un <xref:System.Drawing.Text.PrivateFontCollection> objeto para mantener un conjunto de fuentes específicamente para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5f31b-104">You can use a <xref:System.Drawing.Text.PrivateFontCollection> object to maintain a set of fonts specifically for your application.</span></span> <span data-ttu-id="5f31b-105">Una colección de fuentes privada puede incluir fuentes del sistema instaladas, así como las fuentes que no se hayan instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="5f31b-105">A private font collection can include installed system fonts as well as fonts that have not been installed on the computer.</span></span> <span data-ttu-id="5f31b-106">Para agregar un archivo de fuente a una colección de fuentes privada, llame a la <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile%2A> método de una <xref:System.Drawing.Text.PrivateFontCollection> objeto.</span><span class="sxs-lookup"><span data-stu-id="5f31b-106">To add a font file to a private font collection, call the <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile%2A> method of a <xref:System.Drawing.Text.PrivateFontCollection> object.</span></span>  
  
 <span data-ttu-id="5f31b-107">El <xref:System.Drawing.Text.FontCollection.Families%2A> propiedad de un <xref:System.Drawing.Text.PrivateFontCollection> objeto contiene una matriz de <xref:System.Drawing.FontFamily> objetos.</span><span class="sxs-lookup"><span data-stu-id="5f31b-107">The <xref:System.Drawing.Text.FontCollection.Families%2A> property of a <xref:System.Drawing.Text.PrivateFontCollection> object contains an array of <xref:System.Drawing.FontFamily> objects.</span></span>  
  
 <span data-ttu-id="5f31b-108">El número de familias de fuentes en una colección de fuentes privada no es necesariamente el mismo que el número de archivos de fuente que se han agregado a la colección.</span><span class="sxs-lookup"><span data-stu-id="5f31b-108">The number of font families in a private font collection is not necessarily the same as the number of font files that have been added to the collection.</span></span> <span data-ttu-id="5f31b-109">Por ejemplo, imagine que agrega los archivos ArialBd.tff, Times.tff y TimesBd.tff a una colección.</span><span class="sxs-lookup"><span data-stu-id="5f31b-109">For example, suppose you add the files ArialBd.tff, Times.tff, and TimesBd.tff to a collection.</span></span> <span data-ttu-id="5f31b-110">Habrá tres archivos pero sólo dos familias de la colección porque Times.tff y TimesBd.tff pertenecen a la misma familia.</span><span class="sxs-lookup"><span data-stu-id="5f31b-110">There will be three files but only two families in the collection because Times.tff and TimesBd.tff belong to the same family.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f31b-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5f31b-111">Example</span></span>  
 <span data-ttu-id="5f31b-112">El ejemplo siguiente agrega los siguientes tres archivos de fuente para un <xref:System.Drawing.Text.PrivateFontCollection> objeto:</span><span class="sxs-lookup"><span data-stu-id="5f31b-112">The following example adds the following three font files to a <xref:System.Drawing.Text.PrivateFontCollection> object:</span></span>  
  
-   <span data-ttu-id="5f31b-113">C:\\*systemroot*\Fonts\Arial.tff (Arial, normal)</span><span class="sxs-lookup"><span data-stu-id="5f31b-113">C:\\*systemroot*\Fonts\Arial.tff (Arial, regular)</span></span>  
  
-   <span data-ttu-id="5f31b-114">C:\\*systemroot*\Fonts\CourBI.tff (Courier New, negrita cursiva)</span><span class="sxs-lookup"><span data-stu-id="5f31b-114">C:\\*systemroot*\Fonts\CourBI.tff (Courier New, bold italic)</span></span>  
  
-   <span data-ttu-id="5f31b-115">C:\\*systemroot*\Fonts\TimesBd.tff (Times New Roman, negrita)</span><span class="sxs-lookup"><span data-stu-id="5f31b-115">C:\\*systemroot*\Fonts\TimesBd.tff (Times New Roman, bold)</span></span>  
  
 <span data-ttu-id="5f31b-116">El código recupera una matriz de <xref:System.Drawing.FontFamily> objetos desde la <xref:System.Drawing.Text.FontCollection.Families%2A> propiedad de la <xref:System.Drawing.Text.PrivateFontCollection> objeto.</span><span class="sxs-lookup"><span data-stu-id="5f31b-116">The code retrieves an array of <xref:System.Drawing.FontFamily> objects from the <xref:System.Drawing.Text.FontCollection.Families%2A> property of the <xref:System.Drawing.Text.PrivateFontCollection> object.</span></span>  
  
 <span data-ttu-id="5f31b-117">Para cada <xref:System.Drawing.FontFamily> objeto de la colección, el código llama el <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> método para determinar si hay disponibles varios estilos (normal, negrita, cursiva, negrita y cursiva, subrayado y tachado).</span><span class="sxs-lookup"><span data-stu-id="5f31b-117">For each <xref:System.Drawing.FontFamily> object in the collection, the code calls the <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> method to determine whether various styles (regular, bold, italic, bold italic, underline, and strikeout) are available.</span></span> <span data-ttu-id="5f31b-118">Los argumentos se pasan a la <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> método son miembros de la <xref:System.Drawing.FontStyle> enumeración.</span><span class="sxs-lookup"><span data-stu-id="5f31b-118">The arguments passed to the <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> method are members of the <xref:System.Drawing.FontStyle> enumeration.</span></span>  
  
 <span data-ttu-id="5f31b-119">Si una combinación de familia y estilo concreta está disponible, un <xref:System.Drawing.Font> objeto se construye utilizando esa familia y ese estilo.</span><span class="sxs-lookup"><span data-stu-id="5f31b-119">If a given family/style combination is available, a <xref:System.Drawing.Font> object is constructed using that family and style.</span></span> <span data-ttu-id="5f31b-120">El primer argumento pasado a la <xref:System.Drawing.Font.%23ctor%2A> constructor es el nombre de familia de fuentes (no un <xref:System.Drawing.FontFamily> objeto tal y como es el caso de otras variaciones de la <xref:System.Drawing.Font.%23ctor%2A> constructor).</span><span class="sxs-lookup"><span data-stu-id="5f31b-120">The first argument passed to the <xref:System.Drawing.Font.%23ctor%2A> constructor is the font family name (not a <xref:System.Drawing.FontFamily> object as is the case for other variations of the <xref:System.Drawing.Font.%23ctor%2A> constructor).</span></span> <span data-ttu-id="5f31b-121">Después de la <xref:System.Drawing.Font> se haya construido, se pasa a la <xref:System.Drawing.Graphics.DrawString%2A> método de la <xref:System.Drawing.Graphics> clase para mostrar el nombre de familia junto con el nombre del estilo.</span><span class="sxs-lookup"><span data-stu-id="5f31b-121">After the <xref:System.Drawing.Font> object is constructed, it is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class to display the family name along with the name of the style.</span></span>  
  
 <span data-ttu-id="5f31b-122">El resultado del código siguiente es similar a la salida que se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="5f31b-122">The output of the following code is similar to the output shown in the following illustration.</span></span>  
  
 <span data-ttu-id="5f31b-123">![Texto de las fuentes](../../../../docs/framework/winforms/advanced/media/csfontstext7.png "csfontstext7")</span><span class="sxs-lookup"><span data-stu-id="5f31b-123">![Fonts Text](../../../../docs/framework/winforms/advanced/media/csfontstext7.png "csfontstext7")</span></span>  
  
 <span data-ttu-id="5f31b-124">Arial.tff (que se agregó a la colección de fuentes privada en el ejemplo de código siguiente) es el archivo de fuente del estilo normal de Arial.</span><span class="sxs-lookup"><span data-stu-id="5f31b-124">Arial.tff (which was added to the private font collection in the following code example) is the font file for the Arial regular style.</span></span> <span data-ttu-id="5f31b-125">Sin embargo, tenga en cuenta que el resultado del programa muestra varios estilos disponibles aparte del normal para la familia de fuentes Arial.</span><span class="sxs-lookup"><span data-stu-id="5f31b-125">Note, however, that the program output shows several available styles other than regular for the Arial font family.</span></span> <span data-ttu-id="5f31b-126">Esto es así porque [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] puede simular los estilos negrita, cursiva y negrita cursiva a partir del estilo normal.</span><span class="sxs-lookup"><span data-stu-id="5f31b-126">That is because [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] can simulate the bold, italic, and bold italic styles from the regular style.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="5f31b-127">También puede generar subrayados y tachados a partir del estilo normal.</span><span class="sxs-lookup"><span data-stu-id="5f31b-127"> can also produce underlines and strikeouts from the regular style.</span></span>  
  
 <span data-ttu-id="5f31b-128">De forma similar, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] puede simular el estilo negrita cursiva a partir del estilo negrita o del estilo cursiva.</span><span class="sxs-lookup"><span data-stu-id="5f31b-128">Similarly, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] can simulate the bold italic style from either the bold style or the italic style.</span></span> <span data-ttu-id="5f31b-129">El resultado del programa muestra que el estilo de negrita cursiva está disponible para la familia Times a pesar de que TimesBd.tff (Times New Roman, negrita) es el único archivo de veces en la colección.</span><span class="sxs-lookup"><span data-stu-id="5f31b-129">The program output shows that the bold italic style is available for the Times family even though TimesBd.tff (Times New Roman, bold) is the only Times file in the collection.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.FontsAndText#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5f31b-130">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="5f31b-130">Compiling the Code</span></span>  
 <span data-ttu-id="5f31b-131">El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="5f31b-131">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f31b-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f31b-132">See Also</span></span>  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 [<span data-ttu-id="5f31b-133">Utilizar fuentes y texto</span><span class="sxs-lookup"><span data-stu-id="5f31b-133">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
