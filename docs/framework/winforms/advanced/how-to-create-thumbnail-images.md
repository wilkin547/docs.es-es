---
title: "Cómo: Crear imágenes en miniatura"
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
- thumbnail images [Windows Forms], creating
- images [Windows Forms], creating thumbnails
ms.assetid: e956242a-1e5b-4217-a3cf-5f3fb45d00ba
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2a3866274340932819a419c622c10072dd67c439
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-thumbnail-images"></a>Cómo: Crear imágenes en miniatura
Una imagen en miniatura es una versión reducida de una imagen. Puede crear una imagen en miniatura mediante una llamada a la <xref:System.Drawing.Image.GetThumbnailImage%2A> método de una <xref:System.Drawing.Image> objeto.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un <xref:System.Drawing.Image> objeto desde un archivo JPG. La imagen original tiene un ancho de 640 píxeles y un alto de 479 píxeles. El código crea una imagen en miniatura que tiene un ancho de 100 píxeles y un alto de 100 píxeles.  
  
 En la siguiente ilustración muestra la imagen en miniatura.  
  
 ![Imagen en miniatura](../../../../docs/framework/winforms/advanced/media/thumbnail1.png "Thumbnail1")  
  
> [!NOTE]
>  En este ejemplo, un método de devolución de llamada se declara, pero nunca se utiliza. Esto es compatible con todas las versiones de GDI +.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.WorkingWithImages#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>. Para ejecutar el ejemplo, siga estos pasos:  
  
1.  Cree una nueva aplicación de Windows Forms.  
  
2.  Agregue el código de ejemplo al formulario.  
  
3.  Crear un controlador para el formulario <xref:System.Windows.Forms.Control.Paint> eventos  
  
4.  En el <xref:System.Windows.Forms.Control.Paint> controlador, llame a la `GetThumbnail` método y pase `e` para <xref:System.Windows.Forms.PaintEventArgs>.  
  
5.  Buscar un archivo de imagen que desea realizar una miniatura.  
  
6.  En el `GetThumbnail` (método), especifique la ruta de acceso y el nombre a la imagen de archivo.  
  
7.  Presione F5 para ejecutar el ejemplo.  
  
     Una imagen en miniatura de 100 por 100 aparece en el formulario.  
  
## <a name="see-also"></a>Vea también  
 [Imágenes, mapas de bits y metarchivos](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [Trabajar con imágenes, mapas de bits, iconos y metarchivos](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
