---
title: "C&#243;mo: Modificar el tama&#241;o o la situaci&#243;n de una imagen en tiempo de ejecuci&#243;n (formularios Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ejemplos [Windows Forms], PictureBox (control)"
  - "imágenes [Windows Forms], controlar colocación en el control PictureBox [Windows Forms]"
  - "PictureBox (control) [Windows Forms], tamaño y alineación de imagen"
  - "imágenes, controlar colocación en el control PictureBox [Windows Forms]"
ms.assetid: d0b332a3-fae2-4891-957c-dc3e17743326
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Modificar el tama&#241;o o la situaci&#243;n de una imagen en tiempo de ejecuci&#243;n (formularios Windows Forms)
Si utiliza el control <xref:System.Windows.Forms.PictureBox> de los formularios Windows Forms en un formulario, puede establecer en él la propiedad <xref:System.Windows.Forms.PictureBox.SizeMode%2A> en:  
  
-   Alinear la esquina superior izquierda de la imagen con la esquina superior izquierda del control.  
  
-   Centrar la imagen dentro del control.  
  
-   Ajustar el tamaño del control a la imagen que muestra.  
  
-   Ajustar cualquier imagen que se muestre para que se ajuste al control.  
  
 Al ajustar una imagen, puede producirse una pérdida de calidad de la misma, sobre todo si ésta tiene formato de mapa de bits.  Los metarchivos, que son listas de instrucciones gráficas para dibujar imágenes en tiempo de ejecución, admiten mejor esta operación de ajuste que los mapas de bits.  
  
### Para establecer la propiedad SizeMode en tiempo de ejecución  
  
1.  Establezca <xref:System.Windows.Forms.PictureBox.SizeMode%2A> en <xref:System.Windows.Forms.PictureBoxSizeMode> \(valor predeterminado\), <xref:System.Windows.Forms.PictureBoxSizeMode>, <xref:System.Windows.Forms.PictureBoxSizeMode> o <xref:System.Windows.Forms.PictureBoxSizeMode>.  <xref:System.Windows.Forms.PictureBoxSizeMode> significa que la imagen se sitúa en la esquina superior izquierda del control; si la imagen es mayor que el control, sus bordes derecho e inferior se recortan.  <xref:System.Windows.Forms.PictureBoxSizeMode> significa que la imagen está centrada dentro del control; si la imagen es mayor que el control, los bordes exteriores de la imagen se recortan.  <xref:System.Windows.Forms.PictureBoxSizeMode> significa que el tamaño del control se ajusta al tamaño de la imagen.  <xref:System.Windows.Forms.PictureBoxSizeMode> es lo contrario, y significa que el tamaño de la imagen se ajusta al tamaño del control.  
  
     En el ejemplo siguiente, la ruta de acceso establecida para la ubicación de la imagen es la carpeta Mis documentos \(My Documents\).  Se utiliza esta ubicación porque se puede asumir que la mayoría de los equipos que ejecuten el sistema operativo Windows tendrán este directorio.  Esto permite también a los usuarios con niveles de acceso mínimos ejecutar la aplicación de un modo seguro.  En el ejemplo siguiente suponemos que ya se ha agregado un control <xref:System.Windows.Forms.PictureBox> al formulario.  
  
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
  
## Vea también  
 <xref:System.Windows.Forms.PictureBox>   
 [Cómo: Cargar una imagen mediante el Diseñador](../../../../docs/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms.md)   
 [Información general del control PictureBox](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)   
 [Cómo: Establecer imágenes en tiempo de ejecución](../../../../docs/framework/winforms/controls/how-to-set-pictures-at-run-time-windows-forms.md)   
 [PictureBox \(Control\)](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)