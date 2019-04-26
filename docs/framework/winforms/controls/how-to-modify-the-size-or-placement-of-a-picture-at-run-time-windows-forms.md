---
title: Procedimiento Modificar el tamaño o la ubicación de una imagen en tiempo de ejecución (formularios Windows Forms)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], controlling placement in PictureBox control [Windows Forms]
- examples [Windows Forms], PictureBox control
- PictureBox control [Windows Forms], picture size and alignment
- pictures [Windows Forms], controlling placement in PictureBox control [Windows Forms]
ms.assetid: d0b332a3-fae2-4891-957c-dc3e17743326
ms.openlocfilehash: d0a86d7fe53dba3da6bd63587561f82877bc2f06
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61913736"
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a>Procedimiento Modificar el tamaño o la ubicación de una imagen en tiempo de ejecución (formularios Windows Forms)
Si utiliza los formularios de Windows <xref:System.Windows.Forms.PictureBox> control en un formulario, puede establecer el <xref:System.Windows.Forms.PictureBox.SizeMode%2A> propiedad en él para:  
  
-   Alinear esquina superior izquierda la imagen en la con la esquina superior izquierda del control  
  
-   Centrar la imagen dentro del control  
  
-   Ajustar el tamaño del control para que quepa la imagen que muestra  
  
-   Estirar cualquier imagen que se muestre para ajustar el control  
  
 Ajuste de una imagen (especialmente uno en formato de mapa de bits) puede producirse una pérdida de calidad de imagen. Los metarchivos, que son listas de instrucciones de gráficos para dibujar imágenes en tiempo de ejecución, son más adecuados para el ajuste de los mapas de bits.  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a>Para establecer la propiedad SizeMode en tiempo de ejecución  
  
1. Establecer <xref:System.Windows.Forms.PictureBox.SizeMode%2A> a <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (valor predeterminado), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>, o <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>. <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> significa que la imagen se coloca en la esquina superior izquierda del control; Si la imagen es mayor que el control, se recortan los bordes derecho e inferiores. <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> significa que la imagen se centra dentro del control. Si la imagen es mayor que el control, se recortan los bordes exteriores de la imagen. <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> significa que el tamaño del control se ajusta al tamaño de la imagen. <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> es el inverso y significa que el tamaño de la imagen se ajusta al tamaño del control.  
  
     En el ejemplo siguiente, la ruta de acceso establecida para la ubicación de la imagen es la carpeta Mis documentos. Hecho esto, ya que puede asumir que la mayoría de los equipos que ejecutan el sistema operativo de Windows tendrán este directorio. Esto permite también a los usuarios con niveles de acceso mínimos ejecutar la aplicación de forma segura. El ejemplo siguiente se da por supuesto un formulario con un <xref:System.Windows.Forms.PictureBox> control ya se ha agregado.  
  
    ```vb  
    Private Sub StretchPic()  
       ' Stretch the picture to fit the control.  
       PictureBox1.SizeMode = PictureBoxSizeMode.StretchImage  
       ' Load the picture into the control.  
       ' You should replace the bold image   
       ' in the sample below with an icon of your own choosing.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
    End Sub  
    ```  
  
    ```csharp  
    private void StretchPic(){  
       // Stretch the picture to fit the control.  
       PictureBox1.SizeMode = PictureBoxSizeMode.StretchImage;  
       // Load the picture into the control.  
       // You should replace the bold image   
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       + @"\Image.gif")  
    }  
    ```  
  
    ```cpp  
    private:  
       void StretchPic()  
       {  
          // Stretch the picture to fit the control.  
          pictureBox1->SizeMode = PictureBoxSizeMode::StretchImage;  
          // Load the picture into the control.  
          // You should replace the bold image   
          // in the sample below with an icon of your own choosing.  
          pictureBox1->Image = Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
       }  
    ```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.PictureBox>
- [Cómo: Cargar una imagen mediante el diseñador](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [Información general del control PictureBox](picturebox-control-overview-windows-forms.md)
- [Cómo: Establecer imágenes en tiempo de ejecución](how-to-set-pictures-at-run-time-windows-forms.md)
- [PictureBox (control)](picturebox-control-windows-forms.md)
