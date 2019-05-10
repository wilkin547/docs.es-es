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
ms.openlocfilehash: 275041372bd5e7da5dd0b32dc0a3d70a38bd0dcd
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063764"
---
# <a name="how-to-create-thumbnail-images"></a>Procedimiento para crear imágenes en miniatura
Una imagen en miniatura es una versión reducida de una imagen. Puede crear una imagen en miniatura mediante una llamada a la <xref:System.Drawing.Image.GetThumbnailImage%2A> método de un <xref:System.Drawing.Image> objeto.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un <xref:System.Drawing.Image> objeto desde un archivo JPG. La imagen original tiene un ancho de 640 píxeles y un alto de 479 píxeles. El código crea una imagen en miniatura que tiene un ancho de 100 píxeles y un alto de 100 píxeles.  
  
 La siguiente ilustración muestra la imagen en miniatura:  
  
 ![Captura de pantalla que muestra la miniatura de salida.](./media/how-to-create-thumbnail-images/construct-thumbnail-image.png)  
  
> [!NOTE]
>  En este ejemplo, un método de devolución de llamada se declara, pero nunca se utiliza. Esto es compatible con todas las versiones de GDI +.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.WorkingWithImages#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de la <xref:System.Windows.Forms.Control.Paint> controlador de eventos. Para ejecutar el ejemplo, siga estos pasos:  
  
1. Cree una nueva aplicación de Windows Forms.  
  
2. Agregue el código de ejemplo al formulario.  
  
3. Cree un controlador para el formulario <xref:System.Windows.Forms.Control.Paint> eventos  
  
4. En el <xref:System.Windows.Forms.Control.Paint> controlador, llamada la `GetThumbnail` método y pase `e` para <xref:System.Windows.Forms.PaintEventArgs>.  
  
5. Buscar un archivo de imagen que desea realizar una miniatura.  
  
6. En el `GetThumbnail` método, especifique la ruta de acceso y nombre de la imagen de archivo.  
  
7. Presione F5 para ejecutar el ejemplo.  
  
     Aparece una imagen en miniatura del 100 por 100 en el formulario.  
  
## <a name="see-also"></a>Vea también

- [Imágenes, mapas de bits y metarchivos](images-bitmaps-and-metafiles.md)
- [Trabajar con imágenes, mapas de bits, iconos y metarchivos](working-with-images-bitmaps-icons-and-metafiles.md)
