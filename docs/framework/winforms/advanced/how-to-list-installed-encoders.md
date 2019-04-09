---
title: Filtrar para enumerar los codificadores instalados
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image codecs [Windows Forms], listing
- image encoders [Windows Forms], listing
ms.assetid: 49e8e4e9-7a67-42d9-86bf-08821cdc282e
ms.openlocfilehash: ce297cb6d183bc63c8b276e30100aa4e864cd90d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078816"
---
# <a name="how-to-list-installed-encoders"></a>Filtrar para enumerar los codificadores instalados
Es posible que desee enumerar los codificadores de imagen disponibles en un equipo, para determinar si la aplicación puede guardar en un formato de archivo de imagen determinado. El <xref:System.Drawing.Imaging.ImageCodecInfo> clase proporciona el <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> métodos estáticos para que pueda determinar los codificadores de imagen que están disponibles. <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> Devuelve una matriz de <xref:System.Drawing.Imaging.ImageCodecInfo> objetos.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente genera la lista de los codificadores instalados y sus valores de propiedad.  
  
 [!code-csharp[UsingImageEncodersDecoders#1](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#1)]
 [!code-vb[UsingImageEncodersDecoders#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Una aplicación de Windows Forms.  
  
-   Un <xref:System.Windows.Forms.PaintEventArgs>, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vea también

- [Filtrar para enumerar los descodificadores instalados](how-to-list-installed-decoders.md)
- [Usar codificadores y descodificadores de imagen en la interfaz GDI+ administrada](using-image-encoders-and-decoders-in-managed-gdi.md)
