---
title: "C&#243;mo: Guardar archivos mediante el componente SaveFileDialog | Microsoft Docs"
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
  - "archivos, guardar"
  - "OpenFile (método), guardar archivos mediante el componente SaveFileDialog"
  - "SaveFileDialog (componente), guardar archivos"
  - "guardar archivos"
ms.assetid: 02e8f409-b83f-4707-babb-e71f6b223d90
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# C&#243;mo: Guardar archivos mediante el componente SaveFileDialog
El componente <xref:System.Windows.Forms.SaveFileDialog> permite a los usuarios examinar el sistema de archivos y seleccionar los archivos que deseen guardar.  El cuadro de diálogo devuelve la ruta de acceso y el nombre del archivo que seleccionó el usuario en el cuadro de diálogo.  Sin embargo, debe escribir el código para escribir realmente los archivos en el disco.  
  
### Para guardar un archivo utilizando el componente SaveFileDialog  
  
-   Muestre el cuadro de diálogo **Guardar archivo** y llame a un método para guardar el archivo seleccionado por el usuario.  
  
     Utilice el método <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> del componente <xref:System.Windows.Forms.SaveFileDialog> para guardar el archivo.  Este método proporciona un objeto <xref:System.IO.Stream> en el que se puede escribir.  
  
     En el siguiente ejemplo se utiliza la propiedad <xref:System.Windows.Forms.DialogResult> para obtener el nombre del archivo y el método <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> para guardar este archivo.  El método <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> le proporciona una secuencia en la que escribir el archivo.  
  
     En el ejemplo siguiente hay un control <xref:System.Windows.Forms.Button> con una imagen asignada.  Cuando se hace clic en el botón, se crea una instancia del componente <xref:System.Windows.Forms.SaveFileDialog> con un filtro que permite archivos de tipo .gif, .jpeg y .bmp.  Si se selecciona un archivo de este tipo en el cuadro de diálogo Guardar archivo, se guarda la imagen del botón.  
  
    > [!IMPORTANT]
    >  Para obtener o establecer la propiedad <xref:System.Windows.Forms.FileDialog.FileName%2A>, el ensamblado necesita que la clase <xref:System.Security.Permissions.FileIOPermission?displayProperty=fullName> le conceda un nivel de privilegios.  Si ejecuta el proceso en un contexto de confianza parcial, podría desencadenarse una excepción por falta de privilegios.  Para obtener más información, vea [Conceptos básicos sobre la seguridad de acceso del código](../../../../docs/framework/misc/code-access-security-basics.md).  
  
     En el ejemplo se supone que el formulario tiene un control <xref:System.Windows.Forms.Button> con su propiedad <xref:System.Windows.Forms.ButtonBase.Image%2A> definida como un archivo de tipo .gif, .jpeg o .bmp.  
  
    > [!NOTE]
    >  La propiedad <xref:System.Windows.Forms.FileDialog.FilterIndex%2A> de la clase <xref:System.Windows.Forms.FileDialog> \(que, debido a su herencia, forma parte de la clase <xref:System.Windows.Forms.SaveFileDialog>\) utiliza un índice de base uno.  Esto es importante si va a escribir código para guardar datos con un formato específico \(por ejemplo, guardar un archivo con texto sin formato frente al formato binario\).  El ejemplo siguiente muestra el uso de esta propiedad.  
  
    ```vb  
    Private Sub Button2_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles Button2.Click  
       ' Displays a SaveFileDialog so the user can save the Image  
       ' assigned to Button2.  
       Dim saveFileDialog1 As New SaveFileDialog()  
       saveFileDialog1.Filter = "JPeg Image|*.jpg|Bitmap Image|*.bmp|Gif Image|*.gif"  
       saveFileDialog1.Title = "Save an Image File"  
       saveFileDialog1.ShowDialog()  
  
       ' If the file name is not an empty string open it for saving.  
       If saveFileDialog1.FileName <> "" Then  
          ' Saves the Image via a FileStream created by the OpenFile method.  
          Dim fs As System.IO.FileStream = Ctype _  
             (saveFileDialog1.OpenFile(), System.IO.FileStream)  
          ' Saves the Image in the appropriate ImageFormat based upon the  
          ' file type selected in the dialog box.  
          ' NOTE that the FilterIndex property is one-based.  
          Select Case saveFileDialog1.FilterIndex  
             Case 1  
                Me.button2.Image.Save(fs, _  
                   System.Drawing.Imaging.ImageFormat.Jpeg)  
  
             Case 2  
                Me.button2.Image.Save(fs, _  
                   System.Drawing.Imaging.ImageFormat.Bmp)  
  
             Case 3  
                Me.button2.Image.Save(fs, _  
                   System.Drawing.Imaging.ImageFormat.Gif)  
           End Select  
  
           fs.Close()  
        End If  
    End Sub  
  
    ```  
  
    ```csharp  
    private void button2_Click(object sender, System.EventArgs e)  
    {  
       // Displays a SaveFileDialog so the user can save the Image  
       // assigned to Button2.  
       SaveFileDialog saveFileDialog1 = new SaveFileDialog();  
       saveFileDialog1.Filter = "JPeg Image|*.jpg|Bitmap Image|*.bmp|Gif Image|*.gif";  
       saveFileDialog1.Title = "Save an Image File";  
       saveFileDialog1.ShowDialog();  
  
       // If the file name is not an empty string open it for saving.  
       if(saveFileDialog1.FileName != "")  
       {  
          // Saves the Image via a FileStream created by the OpenFile method.  
          System.IO.FileStream fs =   
             (System.IO.FileStream)saveFileDialog1.OpenFile();  
          // Saves the Image in the appropriate ImageFormat based upon the  
          // File type selected in the dialog box.  
          // NOTE that the FilterIndex property is one-based.  
          switch(saveFileDialog1.FilterIndex)  
          {  
             case 1 :   
             this.button2.Image.Save(fs,   
                System.Drawing.Imaging.ImageFormat.Jpeg);  
             break;  
  
             case 2 :   
             this.button2.Image.Save(fs,   
                System.Drawing.Imaging.ImageFormat.Bmp);  
             break;  
  
             case 3 :   
             this.button2.Image.Save(fs,   
                System.Drawing.Imaging.ImageFormat.Gif);  
             break;  
          }  
  
       fs.Close();  
       }  
    }  
  
    ```  
  
    ```cpp  
    private:  
       System::Void button2_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // Displays a SaveFileDialog so the user can save the Image  
          // assigned to Button2.  
          SaveFileDialog ^ saveFileDialog1 = new SaveFileDialog();  
          saveFileDialog1->Filter =   
             "JPeg Image|*.jpg|Bitmap Image|*.bmp|Gif Image|*.gif";  
          saveFileDialog1->Title = "Save an Image File";  
          saveFileDialog1->ShowDialog();  
          // If the file name is not an empty string, open it for saving.  
          if(saveFileDialog1->FileName != "")  
          {  
             // Saves the Image through a FileStream created by  
             // the OpenFile method.  
             System::IO::FileStream ^ fs =   
                safe_cast<System::IO::FileStream*>(  
                saveFileDialog1->OpenFile());  
             // Saves the Image in the appropriate ImageFormat based on  
             // the file type selected in the dialog box.  
             // Note that the FilterIndex property is one based.  
             switch(saveFileDialog1->FilterIndex)  
             {  
                case 1 :  
                   this->button2->Image->Save(fs,  
                      System::Drawing::Imaging::ImageFormat::Jpeg);  
                   break;  
                case 2 :  
                   this->button2->Image->Save(fs,   
                      System::Drawing::Imaging::ImageFormat::Bmp);  
                   break;  
                case 3 :  
                   this->button2->Image->Save(fs,   
                      System::Drawing::Imaging::ImageFormat::Gif);  
                   break;  
             }  
          fs->Close();  
          }  
       }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] y [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.button2.Click += new System.EventHandler(this.button2_Click);  
  
    ```  
  
    ```cpp  
    this->button2->Click += gcnew  
       System::EventHandler(this, &Form1::button2_Click);  
    ```  
  
     Para obtener más información sobre la escritura en secuencias de archivo, vea [FileStream.BeginWrite \(Método\)](frlrfSystemIOFileStreamClassBeginWriteTopic) y [FileStream.Write \(Método\)](https://msdn.microsoft.com/en-us/library/system.io.filestream.write.aspx).  
  
    > [!NOTE]
    >  Algunos controles, como <xref:System.Windows.Forms.RichTextBox>, pueden guardar archivos.  Para obtener más información, vea la sección "SaveFileDialog Component" del artículo técnico de MSDN Online Library, [Essential Code for Windows Forms Dialog Boxes](http://go.microsoft.com/fwlink/?LinkID=102575).  
  
## Vea también  
 <xref:System.Windows.Forms.SaveFileDialog>   
 [SaveFileDialog](../../../../docs/framework/winforms/controls/savefiledialog-component-windows-forms.md)