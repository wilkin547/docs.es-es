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
ms.openlocfilehash: 9bb094ce0b7945f23a2e9b8614e56c9492d5f832
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736026"
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a>Cómo: Modificar el tamaño o la situación de una imagen en tiempo de ejecución (formularios Windows Forms)
Si usa el control Windows Forms <xref:System.Windows.Forms.PictureBox> en un formulario, puede establecer la propiedad <xref:System.Windows.Forms.PictureBox.SizeMode%2A> en él en:  
  
- Alinea la esquina superior izquierda de la imagen con la esquina superior izquierda del control  
  
- Centrar la imagen dentro del control  
  
- Ajustar el tamaño del control para que se ajuste a la imagen que se muestra  
  
- Ajustar cualquier imagen que se muestre para ajustarla al control  
  
 La ampliación de una imagen (especialmente una en formato de mapa de bits) puede producir una pérdida en la calidad de la imagen. Los metaarchivos, que son listas de instrucciones de gráficos para dibujar imágenes en tiempo de ejecución, son más adecuados para la ampliación que los mapas de bits.  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a>Para establecer la propiedad SizeMode en tiempo de ejecución  
  
1. Establezca <xref:System.Windows.Forms.PictureBox.SizeMode%2A> en <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (valor predeterminado), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>o <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>. <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> significa que la imagen se coloca en la esquina superior izquierda del control. Si la imagen es mayor que el control, se recortan los bordes inferior y derecho. <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> significa que la imagen se centra dentro del control; Si la imagen es mayor que el control, se recortan los bordes exteriores de la imagen. <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> significa que el tamaño del control se ajusta al tamaño de la imagen. <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> es el inverso y significa que el tamaño de la imagen se ajusta al tamaño del control.  
  
     En el ejemplo siguiente, la ruta de acceso establecida para la ubicación de la imagen es la carpeta Mis documentos. Esto se hace porque puede suponer que la mayoría de los equipos que ejecutan el sistema operativo Windows incluirán este directorio. Esto permite también a los usuarios con niveles de acceso mínimos ejecutar la aplicación de forma segura. En el ejemplo siguiente se supone que ya se ha agregado un formulario con un control <xref:System.Windows.Forms.PictureBox>.  
  
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
- [Cargar una imagen mediante el Diseñador](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [Información general del control PictureBox](picturebox-control-overview-windows-forms.md)
- [Establecer imágenes en tiempo de ejecución](how-to-set-pictures-at-run-time-windows-forms.md)
- [PictureBox (control)](picturebox-control-windows-forms.md)
