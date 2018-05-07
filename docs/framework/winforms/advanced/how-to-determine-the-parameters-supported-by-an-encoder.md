---
title: 'Cómo: Determinar los parámetros admitidos por un codificador'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encoder parameters [Windows Forms], determining supported
ms.assetid: f47ae459-e3ce-4d41-a140-2f6c6aea3f44
ms.openlocfilehash: 7f7c270c4ae590c070103d51f116158869b678c6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-determine-the-parameters-supported-by-an-encoder"></a>Cómo: Determinar los parámetros admitidos por un codificador
Puede ajustar los parámetros de imagen, como el nivel de calidad y la compresión, pero debe saber qué parámetros son compatibles con un codificador de imágenes especificado. El <xref:System.Drawing.Image> clase proporciona el <xref:System.Drawing.Image.GetEncoderParameterList%2A> método para que pueda determinar qué parámetros de imagen se admiten para un codificador determinado. El codificador se especifica con un GUID. El <xref:System.Drawing.Image.GetEncoderParameterList%2A> método devuelve una matriz de <xref:System.Drawing.Imaging.EncoderParameter> objetos.  
  
## <a name="example"></a>Ejemplo  
 El código de ejemplo siguiente genera los parámetros compatibles para el codificador JPEG. Utilice la lista de categorías de parámetro y los GUID asociados en la <xref:System.Drawing.Imaging.Encoder> general sobre la clase para determinar la categoría para cada parámetro.  
  
 [!code-csharp[UsingImageEncodersDecoders#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#3)]
 [!code-vb[UsingImageEncodersDecoders#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Una aplicación de Windows Forms.  
  
-   A <xref:System.Windows.Forms.PaintEventArgs>, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vea también  
 [Enumerar los codificadores instalados](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)  
 [Tipos de mapas de bits](../../../../docs/framework/winforms/advanced/types-of-bitmaps.md)  
 [Usar codificadores y descodificadores de imagen en la interfaz GDI+ administrada](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)
