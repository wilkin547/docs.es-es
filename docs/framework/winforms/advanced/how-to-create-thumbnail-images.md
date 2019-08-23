---
title: Procedimiento para crear imágenes en miniatura
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thumbnail images [Windows Forms], creating
- images [Windows Forms], creating thumbnails
ms.assetid: e956242a-1e5b-4217-a3cf-5f3fb45d00ba
ms.openlocfilehash: 786a92d99f5e7a0c27f502efa9a5fe617ac4d4d6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923751"
---
# <a name="how-to-create-thumbnail-images"></a>Procedimiento para crear imágenes en miniatura
Una imagen en miniatura es una versión pequeña de una imagen. Puede crear una imagen en miniatura llamando al <xref:System.Drawing.Image.GetThumbnailImage%2A> método de un <xref:System.Drawing.Image> objeto.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea <xref:System.Drawing.Image> un objeto a partir de un archivo jpg. La imagen original tiene un ancho de 640 píxeles y un alto de 479 píxeles. El código crea una imagen en miniatura con un ancho de 100 píxeles y un alto de 100 píxeles.  
  
 En la ilustración siguiente se muestra la imagen en miniatura:  
  
 ![Captura de pantalla que muestra la miniatura de salida.](./media/how-to-create-thumbnail-images/construct-thumbnail-image.png)  
  
> [!NOTE]
> En este ejemplo, se declara un método de devolución de llamada, pero nunca se usa. Es compatible con todas las versiones de GDI+.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.WorkingWithImages#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que <xref:System.Windows.Forms.Control.Paint> es un parámetro del controlador de eventos. Para ejecutar el ejemplo, siga estos pasos:  
  
1. Cree una nueva aplicación de Windows Forms.  
  
2. Agregue el código de ejemplo al formulario.  
  
3. Crear un controlador para el evento del <xref:System.Windows.Forms.Control.Paint> formulario  
  
4. En el <xref:System.Windows.Forms.Control.Paint> controlador, llame al `GetThumbnail` método y pase `e` para <xref:System.Windows.Forms.PaintEventArgs>.  
  
5. Busque un archivo de imagen para el que desee crear una miniatura.  
  
6. En el `GetThumbnail` método, especifique la ruta de acceso y el nombre de archivo de la imagen.  
  
7. Presione F5 para ejecutar el ejemplo.  
  
     Aparece una imagen en miniatura 100 por 100 en el formulario.  
  
## <a name="see-also"></a>Vea también

- [Imágenes, mapas de bits y metarchivos](images-bitmaps-and-metafiles.md)
- [Trabajar con imágenes, mapas de bits, iconos y metarchivos](working-with-images-bitmaps-icons-and-metafiles.md)
