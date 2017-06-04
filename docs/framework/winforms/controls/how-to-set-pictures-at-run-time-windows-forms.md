---
title: "C&#243;mo: Establecer im&#225;genes en tiempo de ejecuci&#243;n (formularios Windows Forms) | Microsoft Docs"
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
  - "mapas de bits [Windows Forms], mostrar en el control PictureBox [Windows Forms]"
  - "ejemplos [Windows Forms], PictureBox (control)"
  - "imágenes [Windows Forms], agregar con el control PictureBox [Windows Forms]"
  - "PictureBox (control) [Windows Forms], agregar imágenes"
  - "PictureBox (control) [Windows Forms], agregar imágenes"
  - "imágenes, configurar pantalla"
ms.assetid: 18ca41d0-68a5-4660-985e-a6c1fbc01d76
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Establecer im&#225;genes en tiempo de ejecuci&#243;n (formularios Windows Forms)
Puede establecer, mediante programación, la imagen que muestra un control <xref:System.Windows.Forms.PictureBox> de un formulario Windows Forms.  
  
### Para establecer una imagen mediante programación  
  
-   Establezca la propiedad <xref:System.Windows.Forms.PictureBox.Image%2A> mediante el método <xref:System.Drawing.Image.FromFile%2A> de la clase <xref:System.Drawing.Image>.  
  
     En el ejemplo siguiente, la ruta de acceso establecida para la ubicación de la imagen es la carpeta Mis documentos \(My Documents\).  Se utiliza esta ubicación porque se puede asumir que la mayoría de los equipos que ejecuten el sistema operativo Windows tendrán este directorio.  Esto permite también a los usuarios con niveles de acceso mínimos ejecutar la aplicación de un modo seguro.  En el ejemplo siguiente suponemos que ya se ha agregado un control <xref:System.Windows.Forms.PictureBox> al formulario.  
  
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
  
### Para borrar un gráfico  
  
-   En primer lugar, libere la memoria que utiliza la imagen y borre el gráfico.  La recolección de elementos no utilizados liberará la memoria más adelante si la administración de la memoria se convierte en un problema.  
  
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
    >  Para obtener más información sobre por qué debe utilizar el método <xref:System.Drawing.Image.Dispose%2A> de esta manera, vea [Cleaning Up Unmanaged Resources](../../../../docs/standard/garbage-collection/unmanaged.md).  
  
     Este código borrará la imagen aunque se haya cargado un gráfico en el control en tiempo de diseño.  
  
## Vea también  
 <xref:System.Windows.Forms.PictureBox>   
 <xref:System.Drawing.Image.FromFile%2A?displayProperty=fullName>   
 [Información general del control PictureBox](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)   
 [Cómo: Cargar una imagen mediante el Diseñador](../../../../docs/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms.md)   
 [Cómo: Modificar el tamaño o la situación de una imagen en tiempo de ejecución](../../../../docs/framework/winforms/controls/how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)   
 [PictureBox \(Control\)](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)