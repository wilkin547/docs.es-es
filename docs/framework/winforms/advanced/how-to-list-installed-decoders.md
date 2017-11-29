---
title: "Cómo: Enumerar los descodificadores instalados"
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
- image codecs [Windows Forms], listing
- image decoders [Windows Forms], listing
ms.assetid: 11417191-8c95-40ca-8024-779e61706fb6
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 17cbdebfa6cbb0cacacd923de4bd22125c812938
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-list-installed-decoders"></a><span data-ttu-id="613a9-102">Cómo: Enumerar los descodificadores instalados</span><span class="sxs-lookup"><span data-stu-id="613a9-102">How to: List Installed Decoders</span></span>
<span data-ttu-id="613a9-103">Puede que desee enumerar los descodificadores de imágenes disponibles en un equipo, para determinar si la aplicación puede leer un formato de archivo de imagen determinado.</span><span class="sxs-lookup"><span data-stu-id="613a9-103">You may want to list the image decoders available on a computer, to determine whether your application can read a particular image file format.</span></span> <span data-ttu-id="613a9-104">El <xref:System.Drawing.Imaging.ImageCodecInfo> clase proporciona el <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> métodos estáticos para que pueda determinar qué imagen descodificadores están disponibles.</span><span class="sxs-lookup"><span data-stu-id="613a9-104">The <xref:System.Drawing.Imaging.ImageCodecInfo> class provides the <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> static methods so that you can determine which image decoders are available.</span></span> <span data-ttu-id="613a9-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A>Devuelve una matriz de <xref:System.Drawing.Imaging.ImageCodecInfo> objetos.</span><span class="sxs-lookup"><span data-stu-id="613a9-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> returns an array of <xref:System.Drawing.Imaging.ImageCodecInfo> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="613a9-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="613a9-106">Example</span></span>  
 <span data-ttu-id="613a9-107">En el ejemplo de código siguiente se genera la lista de los descodificadores instalados y sus valores de propiedad.</span><span class="sxs-lookup"><span data-stu-id="613a9-107">The following code example outputs the list of installed decoders and their property values.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#2)]
 [!code-vb[UsingImageEncodersDecoders#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="613a9-108">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="613a9-108">Compiling the Code</span></span>  
 <span data-ttu-id="613a9-109">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="613a9-109">This example requires:</span></span>  
  
-   <span data-ttu-id="613a9-110">Una aplicación de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="613a9-110">A Windows Forms application.</span></span>  
  
-   <span data-ttu-id="613a9-111">A <xref:System.Windows.Forms.PaintEventArgs>, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="613a9-111">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="613a9-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="613a9-112">See Also</span></span>  
 [<span data-ttu-id="613a9-113">Enumerar los codificadores instalados</span><span class="sxs-lookup"><span data-stu-id="613a9-113">How to: List Installed Encoders</span></span>](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)  
 [<span data-ttu-id="613a9-114">Usar codificadores y descodificadores de imagen en la interfaz GDI+ administrada</span><span class="sxs-lookup"><span data-stu-id="613a9-114">Using Image Encoders and Decoders in Managed GDI+</span></span>](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)
