---
title: Procedimiento Enumerar los descodificadores instalados
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image codecs [Windows Forms], listing
- image decoders [Windows Forms], listing
ms.assetid: 11417191-8c95-40ca-8024-779e61706fb6
ms.openlocfilehash: c40bb79dde4a9baf8b84f3cda5fdabc6e30ad0b5
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57717536"
---
# <a name="how-to-list-installed-decoders"></a>Filtrar Enumerar los descodificadores instalados
Es posible que desee enumerar los descodificadores de imagen disponibles en un equipo, para determinar si la aplicación puede leer un formato de archivo de imagen determinado. El <xref:System.Drawing.Imaging.ImageCodecInfo> clase proporciona el <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> métodos estáticos para que pueda determinar los descodificadores de imagen que están disponibles. <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> Devuelve una matriz de <xref:System.Drawing.Imaging.ImageCodecInfo> objetos.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente genera la lista de los descodificadores instalados y sus valores de propiedad.  
  
 [!code-csharp[UsingImageEncodersDecoders#2](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#2)]
 [!code-vb[UsingImageEncodersDecoders#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#2)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Una aplicación de Windows Forms.  
  
-   Un <xref:System.Windows.Forms.PaintEventArgs>, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vea también
- [Cómo: Enumerar los codificadores instalados](how-to-list-installed-encoders.md)
- [Usar codificadores y descodificadores de imagen en la interfaz GDI+ administrada](using-image-encoders-and-decoders-in-managed-gdi.md)
