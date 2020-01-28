---
title: 'Cómo: Establecer imágenes en tiempo de ejecución'
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
ms.openlocfilehash: bd0509c05fd9c1cfc0c631fcd613c64d20296f6b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746738"
---
# <a name="how-to-set-pictures-at-run-time-windows-forms"></a>Cómo: Establecer imágenes en tiempo de ejecución (formularios Windows Forms)
Puede establecer mediante programación la imagen mostrada por un Windows Forms <xref:System.Windows.Forms.PictureBox> control.  
  
### <a name="to-set-a-picture-programmatically"></a>Para establecer una imagen mediante programación  
  
- Establezca la propiedad <xref:System.Windows.Forms.PictureBox.Image%2A> mediante el método <xref:System.Drawing.Image.FromFile%2A> de la clase <xref:System.Drawing.Image>.  
  
     En el ejemplo siguiente, la ruta de acceso establecida para la ubicación de la imagen es la carpeta Mis documentos. Esto se hace porque puede suponer que la mayoría de los equipos que ejecutan el sistema operativo Windows incluirán este directorio. Esto permite también a los usuarios con niveles de acceso mínimos ejecutar la aplicación de forma segura. En el ejemplo siguiente se supone que ya se ha agregado un formulario con un control <xref:System.Windows.Forms.PictureBox>.  
  
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
    > Para obtener más información sobre por qué se debe usar el método <xref:System.Drawing.Image.Dispose%2A> de esta manera, vea [limpiar recursos no administrados](../../../standard/garbage-collection/unmanaged.md).  
  
     Este código borrará la imagen incluso si un gráfico se cargó en el control en tiempo de diseño.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.PictureBox>
- <xref:System.Drawing.Image.FromFile%2A?displayProperty=nameWithType>
- [Información general del control PictureBox](picturebox-control-overview-windows-forms.md)
- [Cargar una imagen mediante el Diseñador](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [Modificar el tamaño o la situación de una imagen en tiempo de ejecución](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [PictureBox (control)](picturebox-control-windows-forms.md)
