---
title: Procedimiento para guardar archivos mediante el componente SaveFileDialog
description: Obtenga información acerca de cómo usar el componente SaveFileDialog para examinar el sistema de archivos y seleccionar los archivos que se van a guardar.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- saving files
- SaveFileDialog component [Windows Forms], saving files
- files [Windows Forms], saving
- OpenFile method [Windows Forms], saving files with SaveFileDialog component
ms.assetid: 02e8f409-b83f-4707-babb-e71f6b223d90
ms.openlocfilehash: cd773c3d4aa2b907eb09dd87c3fdbe138bf533bb
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904408"
---
# <a name="how-to-save-files-using-the-savefiledialog-component"></a>Procedimiento para guardar archivos mediante el componente SaveFileDialog

El <xref:System.Windows.Forms.SaveFileDialog> componente permite a los usuarios examinar el sistema de archivos y seleccionar los archivos que se van a guardar. El cuadro de diálogo devuelve la ruta de acceso y el nombre del archivo que el usuario seleccionó en el cuadro de diálogo. Sin embargo, debe escribir el código para escribir realmente los archivos en el disco.

### <a name="to-save-a-file-using-the-savefiledialog-component"></a>Guardar un archivo mediante el componente SaveFileDialog

- Muestre el cuadro de diálogo **Guardar archivo** y llame a un método para guardar el archivo seleccionado por el usuario.

  Use el <xref:System.Windows.Forms.SaveFileDialog> método del componente <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> para guardar el archivo. Este método proporciona un <xref:System.IO.Stream> objeto en el que se puede escribir.

  En el ejemplo siguiente se usa la <xref:System.Windows.Forms.DialogResult> propiedad para obtener el nombre del archivo y el <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> método para guardar el archivo. El <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> método proporciona una secuencia para escribir el archivo.

  En el ejemplo siguiente, hay un <xref:System.Windows.Forms.Button> control con una imagen asignada. Al hacer clic en el botón, <xref:System.Windows.Forms.SaveFileDialog> se crea una instancia de un componente con un filtro que permite archivos de tipo. gif,. JPEG y. bmp. Si se selecciona un archivo de este tipo en el cuadro de diálogo Guardar archivo, se guarda la imagen del botón.

  > [!IMPORTANT]
  > Para obtener o establecer la <xref:System.Windows.Forms.FileDialog.FileName%2A> propiedad, el ensamblado requiere un nivel de privilegios concedido por la <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> clase. Si ejecuta el proceso en un contexto de confianza parcial, este podría desencadenar una excepción por falta de privilegios. Para obtener más información, vea [Conceptos básicos sobre la seguridad de acceso del código](../../misc/code-access-security-basics.md).

  En el ejemplo se supone que el formulario tiene un <xref:System.Windows.Forms.Button> control con su <xref:System.Windows.Forms.ButtonBase.Image%2A> propiedad establecida en un archivo de tipo. gif,. JPEG o. bmp.

  > [!NOTE]
  > La <xref:System.Windows.Forms.FileDialog> propiedad de la clase <xref:System.Windows.Forms.FileDialog.FilterIndex%2A> (que, debido a la herencia, forma parte de la <xref:System.Windows.Forms.SaveFileDialog> clase) utiliza un índice basado en uno. Esto es importante si escribe código para guardar datos en un formato concreto (por ejemplo, al guardar un archivo de texto sin formato frente al formato binario). Esta propiedad se incluye en el ejemplo siguiente.

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
              safe_cast\<System::IO::FileStream*>(
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

  (Visual C# y Visual C++) Coloque el siguiente código en el constructor del formulario para registrar el controlador de eventos.

  ```csharp
  this.button2.Click += new System.EventHandler(this.button2_Click);
  ```

  ```cpp
  this->button2->Click += gcnew
      System::EventHandler(this, &Form1::button2_Click);
  ```

  Para obtener más información acerca de cómo escribir secuencias de archivos, vea <xref:System.IO.FileStream.BeginWrite%2A> y <xref:System.IO.FileStream.Write%2A> .

  > [!NOTE]
  > Algunos controles, como el <xref:System.Windows.Forms.RichTextBox> control, tienen la capacidad de guardar archivos.

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.SaveFileDialog>
- [Componente SaveFileDialog](savefiledialog-component-windows-forms.md)
