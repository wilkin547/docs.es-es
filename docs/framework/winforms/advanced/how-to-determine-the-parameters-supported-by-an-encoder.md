---
title: "Cómo: Determinar los parámetros admitidos por un codificador"
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
helpviewer_keywords: encoder parameters [Windows Forms], determining supported
ms.assetid: f47ae459-e3ce-4d41-a140-2f6c6aea3f44
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3304adc9ab22d12905bd2a6c3739d909387d82cc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-determine-the-parameters-supported-by-an-encoder"></a><span data-ttu-id="a48ff-102">Cómo: Determinar los parámetros admitidos por un codificador</span><span class="sxs-lookup"><span data-stu-id="a48ff-102">How to: Determine the Parameters Supported by an Encoder</span></span>
<span data-ttu-id="a48ff-103">Puede ajustar los parámetros de imagen, como el nivel de calidad y la compresión, pero debe saber qué parámetros son compatibles con un codificador de imágenes especificado.</span><span class="sxs-lookup"><span data-stu-id="a48ff-103">You can adjust image parameters, such as quality and compression level, but you must know which parameters are supported by a given image encoder.</span></span> <span data-ttu-id="a48ff-104">El <xref:System.Drawing.Image> clase proporciona el <xref:System.Drawing.Image.GetEncoderParameterList%2A> método para que pueda determinar qué parámetros de imagen se admiten para un codificador determinado.</span><span class="sxs-lookup"><span data-stu-id="a48ff-104">The <xref:System.Drawing.Image> class provides the <xref:System.Drawing.Image.GetEncoderParameterList%2A> method so that you can determine which image parameters are supported for a particular encoder.</span></span> <span data-ttu-id="a48ff-105">El codificador se especifica con un GUID.</span><span class="sxs-lookup"><span data-stu-id="a48ff-105">You specify the encoder with a GUID.</span></span> <span data-ttu-id="a48ff-106">El <xref:System.Drawing.Image.GetEncoderParameterList%2A> método devuelve una matriz de <xref:System.Drawing.Imaging.EncoderParameter> objetos.</span><span class="sxs-lookup"><span data-stu-id="a48ff-106">The <xref:System.Drawing.Image.GetEncoderParameterList%2A> method returns an array of <xref:System.Drawing.Imaging.EncoderParameter> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a48ff-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a48ff-107">Example</span></span>  
 <span data-ttu-id="a48ff-108">El código de ejemplo siguiente genera los parámetros compatibles para el codificador JPEG.</span><span class="sxs-lookup"><span data-stu-id="a48ff-108">The following example code outputs the supported parameters for the JPEG encoder.</span></span> <span data-ttu-id="a48ff-109">Utilice la lista de categorías de parámetro y los GUID asociados en la <xref:System.Drawing.Imaging.Encoder> general sobre la clase para determinar la categoría para cada parámetro.</span><span class="sxs-lookup"><span data-stu-id="a48ff-109">Use the list of parameter categories and associated GUIDs in the <xref:System.Drawing.Imaging.Encoder> class overview to determine the category for each parameter.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#3)]
 [!code-vb[UsingImageEncodersDecoders#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a48ff-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="a48ff-110">Compiling the Code</span></span>  
 <span data-ttu-id="a48ff-111">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="a48ff-111">This example requires:</span></span>  
  
-   <span data-ttu-id="a48ff-112">Una aplicación de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a48ff-112">A Windows Forms application.</span></span>  
  
-   <span data-ttu-id="a48ff-113">A <xref:System.Windows.Forms.PaintEventArgs>, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="a48ff-113">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a48ff-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a48ff-114">See Also</span></span>  
 [<span data-ttu-id="a48ff-115">Enumerar los codificadores instalados</span><span class="sxs-lookup"><span data-stu-id="a48ff-115">How to: List Installed Encoders</span></span>](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)  
 [<span data-ttu-id="a48ff-116">Tipos de mapas de bits</span><span class="sxs-lookup"><span data-stu-id="a48ff-116">Types of Bitmaps</span></span>](../../../../docs/framework/winforms/advanced/types-of-bitmaps.md)  
 [<span data-ttu-id="a48ff-117">Usar codificadores y descodificadores de imagen en la interfaz GDI+ administrada</span><span class="sxs-lookup"><span data-stu-id="a48ff-117">Using Image Encoders and Decoders in Managed GDI+</span></span>](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)
