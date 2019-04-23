---
title: Procedimiento para determinar los parámetros que admite un codificador
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encoder parameters [Windows Forms], determining supported
ms.assetid: f47ae459-e3ce-4d41-a140-2f6c6aea3f44
ms.openlocfilehash: 2626eee239d9876125340dd133c5a9b3e45c3d7e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59204580"
---
# <a name="how-to-determine-the-parameters-supported-by-an-encoder"></a><span data-ttu-id="5276c-102">Procedimiento para determinar los parámetros que admite un codificador</span><span class="sxs-lookup"><span data-stu-id="5276c-102">How to: Determine the Parameters Supported by an Encoder</span></span>
<span data-ttu-id="5276c-103">Puede ajustar los parámetros de imagen, como el nivel de calidad y la compresión, pero debe saber qué parámetros son compatibles con un codificador de imagen determinado.</span><span class="sxs-lookup"><span data-stu-id="5276c-103">You can adjust image parameters, such as quality and compression level, but you must know which parameters are supported by a given image encoder.</span></span> <span data-ttu-id="5276c-104">El <xref:System.Drawing.Image> clase proporciona el <xref:System.Drawing.Image.GetEncoderParameterList%2A> método para que pueda determinar qué parámetros de imagen se admiten para un codificador determinado.</span><span class="sxs-lookup"><span data-stu-id="5276c-104">The <xref:System.Drawing.Image> class provides the <xref:System.Drawing.Image.GetEncoderParameterList%2A> method so that you can determine which image parameters are supported for a particular encoder.</span></span> <span data-ttu-id="5276c-105">Especifique el codificador con un GUID.</span><span class="sxs-lookup"><span data-stu-id="5276c-105">You specify the encoder with a GUID.</span></span> <span data-ttu-id="5276c-106">El <xref:System.Drawing.Image.GetEncoderParameterList%2A> método devuelve una matriz de <xref:System.Drawing.Imaging.EncoderParameter> objetos.</span><span class="sxs-lookup"><span data-stu-id="5276c-106">The <xref:System.Drawing.Image.GetEncoderParameterList%2A> method returns an array of <xref:System.Drawing.Imaging.EncoderParameter> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5276c-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5276c-107">Example</span></span>  
 <span data-ttu-id="5276c-108">El código de ejemplo siguiente genera los parámetros admitidos para el codificador JPEG.</span><span class="sxs-lookup"><span data-stu-id="5276c-108">The following example code outputs the supported parameters for the JPEG encoder.</span></span> <span data-ttu-id="5276c-109">Use la lista de categorías de parámetro y los GUID asociados en el <xref:System.Drawing.Imaging.Encoder> información general de clases para determinar la categoría para cada parámetro.</span><span class="sxs-lookup"><span data-stu-id="5276c-109">Use the list of parameter categories and associated GUIDs in the <xref:System.Drawing.Imaging.Encoder> class overview to determine the category for each parameter.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#3](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#3)]
 [!code-vb[UsingImageEncodersDecoders#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5276c-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="5276c-110">Compiling the Code</span></span>  
 <span data-ttu-id="5276c-111">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="5276c-111">This example requires:</span></span>  
  
-   <span data-ttu-id="5276c-112">Una aplicación de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="5276c-112">A Windows Forms application.</span></span>  
  
-   <span data-ttu-id="5276c-113">Un <xref:System.Windows.Forms.PaintEventArgs>, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="5276c-113">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5276c-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="5276c-114">See also</span></span>

- [<span data-ttu-id="5276c-115">Cómo: Enumerar los codificadores instalados</span><span class="sxs-lookup"><span data-stu-id="5276c-115">How to: List Installed Encoders</span></span>](how-to-list-installed-encoders.md)
- [<span data-ttu-id="5276c-116">Tipos de mapas de bits</span><span class="sxs-lookup"><span data-stu-id="5276c-116">Types of Bitmaps</span></span>](types-of-bitmaps.md)
- [<span data-ttu-id="5276c-117">Usar codificadores y descodificadores de imagen en la interfaz GDI+ administrada</span><span class="sxs-lookup"><span data-stu-id="5276c-117">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)
