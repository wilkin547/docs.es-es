---
title: Procedimiento Abrir archivos mediante el componente OpenFileDialog
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
ms.openlocfilehash: 87e7640da76205341b9e95310314800ac9dbfe30
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54678816"
---
# <a name="how-to-open-files-using-the-openfiledialog-component"></a>Procedimiento Abrir archivos mediante el componente OpenFileDialog
El <xref:System.Windows.Forms.OpenFileDialog> componente permite a los usuarios examinar las carpetas de su equipo o en cualquier equipo en la red y seleccionar uno o varios archivos para abrirlos. El cuadro de diálogo devuelve la ruta de acceso y el nombre del archivo que seleccionó el usuario en el cuadro de diálogo.  
  
 Cuando el usuario haya seleccionado el archivo que se abrirá, hay dos enfoques para el mecanismo de apertura del archivo. Si prefiere trabajar con secuencias de archivo, puede crear una instancia de la <xref:System.IO.StreamReader> clase. Como alternativa, puede usar el <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> método para abrir el archivo seleccionado.  
  
 El primer ejemplo siguiente implica una <xref:System.Security.Permissions.FileIOPermission> comprobación del permiso (como se describe en la "Nota de seguridad" más abajo), pero le permite acceder al nombre de archivo. Puede usar esta técnica desde las zonas de máquina local, intranet e Internet. El segundo método también realiza un <xref:System.Security.Permissions.FileIOPermission> comprobación del permiso, pero es más adecuado para las aplicaciones en las zonas Intranet o Internet.  
  
### <a name="to-open-a-file-as-a-stream-using-the-openfiledialog-component"></a>Abrir archivos como secuencia mediante el componente OpenFileDialog  
  
1.  Muestre el cuadro de diálogo **Abrir archivo** y llame a un método para abrir el archivo seleccionado por el usuario.  
  
     Un enfoque consiste en usar el <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> método para mostrar el cuadro de diálogo Abrir archivo y usar una instancia de la <xref:System.IO.StreamReader> clase para abrir el archivo.  
  
     El ejemplo siguiente usa el <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.Control.Click> controlador de eventos para abrir una instancia de la <xref:System.Windows.Forms.OpenFileDialog> componente. Cuando se elige un archivo y el usuario hace clic en **Aceptar**, se abre el archivo seleccionado en el cuadro de diálogo. En este caso, el contenido se muestra en un cuadro de mensaje para mostrar que se leyó la secuencia de archivo.  
  
    > [!IMPORTANT]
    >  Para obtener o establecer el <xref:System.Windows.Forms.FileDialog.FileName%2A> propiedad, el ensamblado requiere un nivel de privilegio concedido por la <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> clase. Si ejecuta el proceso en un contexto de confianza parcial, este podría desencadenar una excepción por falta de privilegios. Para obtener más información, vea [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md) (Aspectos básicos de seguridad de acceso del código).  
  
     En el ejemplo se da por supuesto que el formulario tiene un <xref:System.Windows.Forms.Button> control y un <xref:System.Windows.Forms.OpenFileDialog> componente.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       If OpenFileDialog1.ShowDialog() = System.Windows.Forms.DialogResult.OK Then  
         Dim sr As New System.IO.StreamReader(OpenFileDialog1.FileName)  
         MessageBox.Show(sr.ReadToEnd)  
         sr.Close()  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(openFileDialog1.ShowDialog() == System.Windows.Forms.DialogResult.OK)  
       {  
          System.IO.StreamReader sr = new   
             System.IO.StreamReader(openFileDialog1.FileName);  
          MessageBox.Show(sr.ReadToEnd());  
          sr.Close();  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if(openFileDialog1->ShowDialog() == System::Windows::Forms::DialogResult::OK)  
          {  
             System::IO::StreamReader ^ sr = gcnew  
                System::IO::StreamReader(openFileDialog1->FileName);  
             MessageBox::Show(sr->ReadToEnd());  
             sr->Close();  
          }  
       }  
    ```  
  
     (Visual C# y [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
    > [!NOTE]
    >  Para obtener más información sobre la lectura de secuencias de archivo, consulte <xref:System.IO.FileStream.BeginRead%2A> y <xref:System.IO.FileStream.Read%2A>.  
  
### <a name="to-open-a-file-as-a-file-using-the-openfiledialog-component"></a>Abrir archivos como archivo mediante el componente OpenFileDialog  
  
1.  Use la <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> método para mostrar el cuadro de diálogo y el <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> método para abrir el archivo.  
  
     El <xref:System.Windows.Forms.OpenFileDialog> del componente <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> método devuelve los bytes que componen el archivo. Estos bytes proporcionan una secuencia de la que se puede leer. En el ejemplo siguiente, un <xref:System.Windows.Forms.OpenFileDialog> se crea una instancia de componente con un filtro "cursor", lo que permite al usuario elegir solo los archivos con la extensión de nombre de archivo`.cur`. Si se elige un archivo`.cur`, el cursor del formulario se establece en el cursor seleccionado.  
  
    > [!IMPORTANT]
    >  Para llamar a la <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> método, el ensamblado requiere un nivel de privilegio concedido por la <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> clase. Si ejecuta el proceso en un contexto de confianza parcial, este podría desencadenar una excepción por falta de privilegios. Para obtener más información, vea [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md) (Aspectos básicos de seguridad de acceso del código).  
  
     En el ejemplo se da por supuesto que el formulario tiene un <xref:System.Windows.Forms.Button> control.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       ' Displays an OpenFileDialog so the user can select a Cursor.  
       Dim openFileDialog1 As New OpenFileDialog()  
       openFileDialog1.Filter = "Cursor Files|*.cur"  
       openFileDialog1.Title = "Select a Cursor File"  
  
       ' Show the Dialog.  
       ' If the user clicked OK in the dialog and   
       ' a .CUR file was selected, open it.  
       If openFileDialog1.ShowDialog() = System.Windows.Forms.DialogResult.OK Then  
         ' Assign the cursor in the Stream to the Form's Cursor property.  
         Me.Cursor = New Cursor(openFileDialog1.OpenFile())  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       // Displays an OpenFileDialog so the user can select a Cursor.  
       OpenFileDialog openFileDialog1 = new OpenFileDialog();  
       openFileDialog1.Filter = "Cursor Files|*.cur";  
       openFileDialog1.Title = "Select a Cursor File";  
  
       // Show the Dialog.  
       // If the user clicked OK in the dialog and  
       // a .CUR file was selected, open it.  
        if (openFileDialog1.ShowDialog() == System.Windows.Forms.DialogResult.OK)  
       {  
          // Assign the cursor in the Stream to the Form's Cursor property.  
          this.Cursor = new Cursor(openFileDialog1.OpenFile());  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // Displays an OpenFileDialog so the user can select a Cursor.  
          OpenFileDialog ^ openFileDialog1 = new OpenFileDialog();  
          openFileDialog1->Filter = "Cursor Files|*.cur";  
          openFileDialog1->Title = "Select a Cursor File";  
  
          // Show the Dialog.  
          // If the user clicked OK in the dialog and  
          // a .CUR file was selected, open it.  
          if (openFileDialog1->ShowDialog() == System::Windows::Forms::DialogResult::OK)  
          {  
             // Assign the cursor in the Stream to  
             // the Form's Cursor property.  
             this->Cursor = gcnew  
                System::Windows::Forms::Cursor(  
                openFileDialog1->OpenFile());  
          }  
       }  
    ```  
  
     (Visual C# y [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.OpenFileDialog>
- [OpenFileDialog (componente)](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md)
