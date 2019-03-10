---
title: Filtrar Determinar los parámetros admitidos por un codificador
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encoder parameters [Windows Forms], determining supported
ms.assetid: f47ae459-e3ce-4d41-a140-2f6c6aea3f44
ms.openlocfilehash: f5af00833c8d8373444b475673709d902598d9d0
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57719707"
---
# <a name="how-to-determine-the-parameters-supported-by-an-encoder"></a>Filtrar Determinar los parámetros admitidos por un codificador
Puede ajustar los parámetros de imagen, como el nivel de calidad y la compresión, pero debe saber qué parámetros son compatibles con un codificador de imagen determinado. El <xref:System.Drawing.Image> clase proporciona el <xref:System.Drawing.Image.GetEncoderParameterList%2A> método para que pueda determinar qué parámetros de imagen se admiten para un codificador determinado. Especifique el codificador con un GUID. El <xref:System.Drawing.Image.GetEncoderParameterList%2A> método devuelve una matriz de <xref:System.Drawing.Imaging.EncoderParameter> objetos.  
  
## <a name="example"></a>Ejemplo  
 El código de ejemplo siguiente genera los parámetros admitidos para el codificador JPEG. Use la lista de categorías de parámetro y los GUID asociados en el <xref:System.Drawing.Imaging.Encoder> información general de clases para determinar la categoría para cada parámetro.  
  
 [!code-csharp[UsingImageEncodersDecoders#3](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#3)]
 [!code-vb[UsingImageEncodersDecoders#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Una aplicación de Windows Forms.  
  
-   Un <xref:System.Windows.Forms.PaintEventArgs>, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vea también
- [Cómo: Enumerar los codificadores instalados](how-to-list-installed-encoders.md)
- [Tipos de mapas de bits](types-of-bitmaps.md)
- [Usar codificadores y descodificadores de imagen en la interfaz GDI+ administrada](using-image-encoders-and-decoders-in-managed-gdi.md)
