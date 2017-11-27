---
title: "Cómo: Convertir una imagen BMP en una imagen PNG"
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
- BMP images [Windows Forms], converting to PNG
- image formats [Windows Forms], converting between
ms.assetid: 9d4a692d-73ac-4ce3-9e05-9ec321e8fbd6
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 542dd132ece543b6a53a9e6d867b49fce4d15a58
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-convert-a-bmp-image-to-a-png-image"></a>Cómo: Convertir una imagen BMP en una imagen PNG
A menudo, deseará convertir de un formato a otro. Puede hacer esta conversión fácilmente llamando al método <xref:System.Drawing.Image.Save%2A> de la clase <xref:System.Drawing.Image> y especificando <xref:System.Drawing.Imaging.ImageFormat> para el formato de archivo de imagen deseado.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, se carga una imagen BMP de un tipo y se guarda la imagen en formato PNG.  
  
 [!code-csharp[UsingImageEncodersDecoders#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#4)]
 [!code-vb[UsingImageEncodersDecoders#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#4)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Una aplicación de Windows Forms.  
  
-   Una referencia al espacio de nombres `System.Drawing.Imaging`.  
  
## <a name="see-also"></a>Vea también  
 [Enumerar los codificadores instalados](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)  
 [Usar codificadores y descodificadores de imagen en la interfaz GDI+ administrada](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)  
 [Tipos de mapas de bits](../../../../docs/framework/winforms/advanced/types-of-bitmaps.md)
