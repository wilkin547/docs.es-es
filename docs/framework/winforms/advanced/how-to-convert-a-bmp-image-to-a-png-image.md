---
title: Procedimiento para convertir una imagen BMP en una imagen PNG
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BMP images [Windows Forms], converting to PNG
- image formats [Windows Forms], converting between
ms.assetid: 9d4a692d-73ac-4ce3-9e05-9ec321e8fbd6
ms.openlocfilehash: 3072c07781a8e8e57b64b48e5b4c304c2a0a0efb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937766"
---
# <a name="how-to-convert-a-bmp-image-to-a-png-image"></a>Procedimiento para convertir una imagen BMP en una imagen PNG
A menudo, deseará convertir de un formato a otro. Puede hacer esta conversión fácilmente llamando al método <xref:System.Drawing.Image.Save%2A> de la clase <xref:System.Drawing.Image> y especificando <xref:System.Drawing.Imaging.ImageFormat> para el formato de archivo de imagen deseado.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, se carga una imagen BMP de un tipo y se guarda la imagen en formato PNG.  
  
 [!code-csharp[UsingImageEncodersDecoders#4](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#4)]
 [!code-vb[UsingImageEncodersDecoders#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#4)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Una aplicación de Windows Forms.  
  
- Una referencia al espacio de nombres `System.Drawing.Imaging`.  
  
## <a name="see-also"></a>Vea también

- [Cómo: Enumerar los codificadores instalados](how-to-list-installed-encoders.md)
- [Usar codificadores y descodificadores de imagen en la interfaz GDI+ administrada](using-image-encoders-and-decoders-in-managed-gdi.md)
- [Tipos de mapas de bits](types-of-bitmaps.md)
