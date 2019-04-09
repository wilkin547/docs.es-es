---
title: Filtrar Establecer imágenes en tiempo de ejecución (formularios Windows Forms)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- pictures [Windows Forms], setting display
- examples [Windows Forms], PictureBox control
- bitmaps [Windows Forms], displaying in PictureBox control [Windows Forms]
- PictureBox control [Windows Forms], adding images
- images [Windows Forms], adding with PictureBox control [Windows Forms]
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 18ca41d0-68a5-4660-985e-a6c1fbc01d76
ms.openlocfilehash: 8ed3ba9050a9117a53b5f4f1cccd26381f55ab32
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59073603"
---
# <a name="how-to-set-pictures-at-run-time-windows-forms"></a>Filtrar Establecer imágenes en tiempo de ejecución (formularios Windows Forms)
Puede establecer mediante programación la imagen que muestra un formulario Windows Forms <xref:System.Windows.Forms.PictureBox> control.  
  
### <a name="to-set-a-picture-programmatically"></a>Para establecer una imagen mediante programación  
  
-   Establecer el <xref:System.Windows.Forms.PictureBox.Image%2A> propiedad utilizando el <xref:System.Drawing.Image.FromFile%2A> método de la <xref:System.Drawing.Image> clase.  
  
     En el ejemplo siguiente, la ruta de acceso establecida para la ubicación de la imagen es la carpeta Mis documentos. Hecho esto, ya que puede asumir que la mayoría de los equipos que ejecutan el sistema operativo de Windows tendrán este directorio. Esto permite también a los usuarios con niveles de acceso mínimos ejecutar la aplicación de forma segura. El ejemplo siguiente se da por supuesto un formulario con un <xref:System.Windows.Forms.PictureBox> control ya se ha agregado.  
  
    ```vb  
    Private Sub LoadNewPict()  
       ' You should replace the bold image   
       ' in the sample below with an icon of your own choosing.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
    End Sub  
    ```  
  
    ```csharp  
    private void LoadNewPict(){  
       // You should replace the bold image   
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       pictureBox1.Image = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
    }  
    ```  
  
    ```cpp  
    private:  
       void LoadNewPict()  
       {  
          // You should replace the bold image   
          // in the sample below with an icon of your own choosing.  
          pictureBox1->Image = Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
       }  
    ```  
  
### <a name="to-clear-a-graphic"></a>Para borrar un gráfico  
  
-   En primer lugar, liberar la memoria utilizada por la imagen y, a continuación, desactive el gráfico. Colección de elementos no utilizados liberará la memoria más adelante si la administración de memoria se convierte en un problema.  
  
    ```vb  
    If Not (PictureBox1.Image Is Nothing) Then  
       PictureBox1.Image.Dispose()  
       PictureBox1.Image = Nothing  
    End If  
    ```  
  
    ```csharp  
    if (pictureBox1.Image != null)   
    {  
       pictureBox1.Image.Dispose();  
       pictureBox1.Image = null;  
    }  
    ```  
  
    ```cpp  
    if (pictureBox1->Image != nullptr)  
    {  
       pictureBox1->Image->Dispose();  
       pictureBox1->Image = nullptr;  
    }  
    ```  
  
    > [!NOTE]
    >  Para obtener más información sobre por qué debería usar el <xref:System.Drawing.Image.Dispose%2A> método de este modo, consulte [limpiar recursos no administrados](../../../standard/garbage-collection/unmanaged.md).  
  
     Este código borrará la imagen incluso si se ha cargado un gráfico en el control en tiempo de diseño.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.PictureBox>
- <xref:System.Drawing.Image.FromFile%2A?displayProperty=nameWithType>
- [Información general sobre el control PictureBox](picturebox-control-overview-windows-forms.md)
- [Filtrar para cargar una imagen mediante el diseñador](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [Filtrar para modificar el tamaño o la situación de una imagen en tiempo de ejecución](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [Control PictureBox](picturebox-control-windows-forms.md)
