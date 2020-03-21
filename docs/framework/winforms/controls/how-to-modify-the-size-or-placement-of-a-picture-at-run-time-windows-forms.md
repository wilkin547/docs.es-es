---
title: 'Cómo: Modificar el tamaño o la situación de una imagen en tiempo de ejecución'
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
ms.openlocfilehash: fea813d7b9fe585e35b729b8b64e3a5f414ef76d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141971"
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a>Cómo: Modificar el tamaño o la situación de una imagen en tiempo de ejecución (formularios Windows Forms)
Si usa el <xref:System.Windows.Forms.PictureBox> control de formularios Windows Forms <xref:System.Windows.Forms.PictureBox.SizeMode%2A> en un formulario, puede establecer la propiedad en él en:  
  
- Alinee la esquina superior izquierda de la imagen con la esquina superior izquierda del control  
  
- Centrar la imagen dentro del control  
  
- Ajuste el tamaño del control para que se ajuste a la imagen que muestra  
  
- Estirar cualquier imagen que muestre para ajustarse al control  
  
 Estirar una imagen (especialmente una en formato de mapa de bits) puede producir una pérdida en la calidad de imagen. Los metarchivos, que son listas de instrucciones gráficas para dibujar imágenes en tiempo de ejecución, son más adecuados para el estiramiento que los mapas de bits.  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a>Para establecer la propiedad SizeMode en tiempo de ejecución  
  
1. Establézalo <xref:System.Windows.Forms.PictureBox.SizeMode%2A> en <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (valor predeterminado), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>o <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>. <xref:System.Windows.Forms.PictureBoxSizeMode.Normal>significa que la imagen se coloca en la esquina superior izquierda del control; si la imagen es más grande que el control, sus bordes inferior y derecho se recortan. <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>significa que la imagen está centrada dentro del control; si la imagen es más grande que el control, los bordes exteriores de la imagen se recortan. <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>significa que el tamaño del control se ajusta al tamaño de la imagen. <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>es lo contrario, y significa que el tamaño de la imagen se ajusta al tamaño del control.  
  
     En el ejemplo siguiente, la ruta establecida para la ubicación de la imagen es la carpeta Mis documentos. Esto se hace, porque puede suponer que la mayoría de los equipos que ejecutan el sistema operativo Windows incluirán este directorio. Esto permite también a los usuarios con niveles de acceso mínimos ejecutar la aplicación de forma segura. En el ejemplo siguiente se <xref:System.Windows.Forms.PictureBox> supone un formulario con un control ya agregado.  
  
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
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.PictureBox>
- [Cómo: Cargar una imagen mediante el Diseñador](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [Información general del control PictureBox](picturebox-control-overview-windows-forms.md)
- [Cómo: Establecer imágenes en tiempo de ejecución](how-to-set-pictures-at-run-time-windows-forms.md)
- [PictureBox (Control)](picturebox-control-windows-forms.md)
