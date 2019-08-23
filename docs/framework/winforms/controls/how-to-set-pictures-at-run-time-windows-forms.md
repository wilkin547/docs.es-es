---
title: Procedimiento Establecer imágenes en tiempo de ejecución (Windows Forms)
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
ms.openlocfilehash: 99d78a275c8ad8f55d9b0832a794545b65da7e20
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917526"
---
# <a name="how-to-set-pictures-at-run-time-windows-forms"></a>Procedimiento Establecer imágenes en tiempo de ejecución (Windows Forms)
Puede establecer mediante programación la imagen mostrada por un control <xref:System.Windows.Forms.PictureBox> Windows Forms.  
  
### <a name="to-set-a-picture-programmatically"></a>Para establecer una imagen mediante programación  
  
- Establezca la <xref:System.Windows.Forms.PictureBox.Image%2A> propiedad mediante el <xref:System.Drawing.Image.FromFile%2A> método de la <xref:System.Drawing.Image> clase.  
  
     En el ejemplo siguiente, la ruta de acceso establecida para la ubicación de la imagen es la carpeta Mis documentos. Esto se hace porque puede suponer que la mayoría de los equipos que ejecutan el sistema operativo Windows incluirán este directorio. Esto permite también a los usuarios con niveles de acceso mínimos ejecutar la aplicación de forma segura. En el ejemplo siguiente se supone que ya <xref:System.Windows.Forms.PictureBox> se ha agregado un formulario con un control.  
  
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
  
- En primer lugar, libere la memoria que está usando la imagen y, a continuación, borre el gráfico. La recolección de elementos no utilizados liberará la memoria más adelante si la administración de memoria se convierte en un problema.  
  
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
    > Para obtener más información sobre por qué se debe <xref:System.Drawing.Image.Dispose%2A> usar el método de esta manera, vea [limpiar recursos no administrados](../../../standard/garbage-collection/unmanaged.md).  
  
     Este código borrará la imagen incluso si un gráfico se cargó en el control en tiempo de diseño.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.PictureBox>
- <xref:System.Drawing.Image.FromFile%2A?displayProperty=nameWithType>
- [Información general del control PictureBox](picturebox-control-overview-windows-forms.md)
- [Procedimientos: Cargar una imagen mediante el diseñador](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [Procedimientos: Modificar el tamaño o la posición de una imagen en tiempo de ejecución](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [PictureBox (control)](picturebox-control-windows-forms.md)
