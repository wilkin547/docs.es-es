---
title: "Cómo: Modificar el tamaño o la situación de una imagen en tiempo de ejecución (formularios Windows Forms)"
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
- cpp
helpviewer_keywords:
- images [Windows Forms], controlling placement in PictureBox control [Windows Forms]
- examples [Windows Forms], PictureBox control
- PictureBox control [Windows Forms], picture size and alignment
- pictures [Windows Forms], controlling placement in PictureBox control [Windows Forms]
ms.assetid: d0b332a3-fae2-4891-957c-dc3e17743326
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: df67871b0b133297a6f53ff9e4a42c7630a5f56d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a>Cómo: Modificar el tamaño o la situación de una imagen en tiempo de ejecución (formularios Windows Forms)
Si usa Windows Forms <xref:System.Windows.Forms.PictureBox> control en un formulario, puede establecer el <xref:System.Windows.Forms.PictureBox.SizeMode%2A> propiedad en ella para:  
  
-   Alinear la esquina izquierda superior de la imagen con la esquina superior izquierda del control  
  
-   Centrar la imagen dentro del control  
  
-   Ajustar el tamaño del control para ajustarse a la imagen que muestra  
  
-   Ajustar cualquier imagen que se muestre para que se ajuste al control.  
  
 Ajuste de una imagen (especialmente uno en formato de mapa de bits), puede producir una pérdida de calidad de la imagen. Metarchivos, que son listas de instrucciones gráficas para dibujar imágenes en tiempo de ejecución, son más adecuados para el ajuste de mapas de bits.  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a>Para establecer la propiedad SizeMode en tiempo de ejecución  
  
1.  Establecer <xref:System.Windows.Forms.PictureBox.SizeMode%2A> a <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (valor predeterminado), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>, o <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>. <xref:System.Windows.Forms.PictureBoxSizeMode.Normal>significa que la imagen se coloca en la esquina superior izquierda del control; Si la imagen es mayor que el control, se recortan los bordes inferior y derecho. <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>significa que la imagen se centra dentro del control. Si la imagen es mayor que el control, se recortan los bordes exteriores de la imagen. <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>significa que el tamaño del control se ajusta al tamaño de la imagen. <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>es el inverso al orden y significa que el tamaño de la imagen se ajusta al tamaño del control.  
  
     En el ejemplo siguiente, la ruta de acceso establecida para la ubicación de la imagen es la carpeta Mis documentos. Para ello, porque se puede asumir que la mayoría de los equipos ejecutan el sistema operativo Windows incluirá este directorio. Esto permite también a los usuarios con niveles de acceso mínimos ejecutar la aplicación de forma segura. El ejemplo siguiente supone un formulario con un <xref:System.Windows.Forms.PictureBox> control ya se ha agregado.  
  
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
 <xref:System.Windows.Forms.PictureBox>  
 [Cargar una imagen mediante el Diseñador](../../../../docs/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms.md)  
 [Información general del control PictureBox](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)  
 [Establecer imágenes en tiempo de ejecución](../../../../docs/framework/winforms/controls/how-to-set-pictures-at-run-time-windows-forms.md)  
 [PictureBox (control)](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)
