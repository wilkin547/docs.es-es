---
title: Procedimiento para enumerar los descodificadores instalados
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image codecs [Windows Forms], listing
- image decoders [Windows Forms], listing
ms.assetid: 11417191-8c95-40ca-8024-779e61706fb6
ms.openlocfilehash: 961862d6212b7e76812fc222d3a99f08528d9a16
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64626908"
---
# <a name="how-to-list-installed-decoders"></a><span data-ttu-id="c59da-102">Procedimiento para enumerar los descodificadores instalados</span><span class="sxs-lookup"><span data-stu-id="c59da-102">How to: List Installed Decoders</span></span>
<span data-ttu-id="c59da-103">Es posible que desee enumerar los descodificadores de imagen disponibles en un equipo, para determinar si la aplicación puede leer un formato de archivo de imagen determinado.</span><span class="sxs-lookup"><span data-stu-id="c59da-103">You may want to list the image decoders available on a computer, to determine whether your application can read a particular image file format.</span></span> <span data-ttu-id="c59da-104">El <xref:System.Drawing.Imaging.ImageCodecInfo> clase proporciona el <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> métodos estáticos para que pueda determinar los descodificadores de imagen que están disponibles.</span><span class="sxs-lookup"><span data-stu-id="c59da-104">The <xref:System.Drawing.Imaging.ImageCodecInfo> class provides the <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> static methods so that you can determine which image decoders are available.</span></span> <span data-ttu-id="c59da-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> Devuelve una matriz de <xref:System.Drawing.Imaging.ImageCodecInfo> objetos.</span><span class="sxs-lookup"><span data-stu-id="c59da-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> returns an array of <xref:System.Drawing.Imaging.ImageCodecInfo> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c59da-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c59da-106">Example</span></span>  
 <span data-ttu-id="c59da-107">El ejemplo de código siguiente genera la lista de los descodificadores instalados y sus valores de propiedad.</span><span class="sxs-lookup"><span data-stu-id="c59da-107">The following code example outputs the list of installed decoders and their property values.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#2](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#2)]
 [!code-vb[UsingImageEncodersDecoders#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c59da-108">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="c59da-108">Compiling the Code</span></span>  
 <span data-ttu-id="c59da-109">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="c59da-109">This example requires:</span></span>  
  
- <span data-ttu-id="c59da-110">Una aplicación de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c59da-110">A Windows Forms application.</span></span>  
  
- <span data-ttu-id="c59da-111">Un <xref:System.Windows.Forms.PaintEventArgs>, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="c59da-111">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c59da-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="c59da-112">See also</span></span>

- [<span data-ttu-id="c59da-113">Cómo: Enumerar los codificadores instalados</span><span class="sxs-lookup"><span data-stu-id="c59da-113">How to: List Installed Encoders</span></span>](how-to-list-installed-encoders.md)
- [<span data-ttu-id="c59da-114">Usar codificadores y descodificadores de imagen en la interfaz GDI+ administrada</span><span class="sxs-lookup"><span data-stu-id="c59da-114">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)
