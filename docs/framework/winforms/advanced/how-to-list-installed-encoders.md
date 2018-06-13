---
title: 'Cómo: Enumerar los codificadores instalados'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image codecs [Windows Forms], listing
- image encoders [Windows Forms], listing
ms.assetid: 49e8e4e9-7a67-42d9-86bf-08821cdc282e
ms.openlocfilehash: 1882ce9a140fb325c29411173ba7bde717bd3f98
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524760"
---
# <a name="how-to-list-installed-encoders"></a><span data-ttu-id="20f7a-102">Cómo: Enumerar los codificadores instalados</span><span class="sxs-lookup"><span data-stu-id="20f7a-102">How to: List Installed Encoders</span></span>
<span data-ttu-id="20f7a-103">Puede enumerar los codificadores de imágenes disponibles en un equipo, para determinar si la aplicación puede guardar en un formato de archivo de imagen determinado.</span><span class="sxs-lookup"><span data-stu-id="20f7a-103">You may want to list the image encoders available on a computer, to determine whether your application can save to a particular image file format.</span></span> <span data-ttu-id="20f7a-104">El <xref:System.Drawing.Imaging.ImageCodecInfo> clase proporciona el <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> métodos estáticos para que pueda determinar qué imagen codificadores están disponibles.</span><span class="sxs-lookup"><span data-stu-id="20f7a-104">The <xref:System.Drawing.Imaging.ImageCodecInfo> class provides the <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> static methods so that you can determine which image encoders are available.</span></span> <span data-ttu-id="20f7a-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> Devuelve una matriz de <xref:System.Drawing.Imaging.ImageCodecInfo> objetos.</span><span class="sxs-lookup"><span data-stu-id="20f7a-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> returns an array of <xref:System.Drawing.Imaging.ImageCodecInfo> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20f7a-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="20f7a-106">Example</span></span>  
 <span data-ttu-id="20f7a-107">En el ejemplo de código siguiente se genera la lista de los codificadores instalados y sus valores de propiedad.</span><span class="sxs-lookup"><span data-stu-id="20f7a-107">The following code example outputs the list of installed encoders and their property values.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#1)]
 [!code-vb[UsingImageEncodersDecoders#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="20f7a-108">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="20f7a-108">Compiling the Code</span></span>  
 <span data-ttu-id="20f7a-109">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="20f7a-109">This example requires:</span></span>  
  
-   <span data-ttu-id="20f7a-110">Una aplicación de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="20f7a-110">A Windows Forms application.</span></span>  
  
-   <span data-ttu-id="20f7a-111">A <xref:System.Windows.Forms.PaintEventArgs>, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="20f7a-111">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20f7a-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="20f7a-112">See Also</span></span>  
 [<span data-ttu-id="20f7a-113">Enumerar los descodificadores instalados</span><span class="sxs-lookup"><span data-stu-id="20f7a-113">How to: List Installed Decoders</span></span>](../../../../docs/framework/winforms/advanced/how-to-list-installed-decoders.md)  
 [<span data-ttu-id="20f7a-114">Usar codificadores y descodificadores de imagen en la interfaz GDI+ administrada</span><span class="sxs-lookup"><span data-stu-id="20f7a-114">Using Image Encoders and Decoders in Managed GDI+</span></span>](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)
