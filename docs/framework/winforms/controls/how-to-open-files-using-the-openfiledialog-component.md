---
title: "C&#243;mo: Abrir archivos mediante el componente OpenFileDialog | Microsoft Docs"
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
  - "archivos, abrir con el componente OpenFileDialog"
  - "OpenFile (método)"
  - "OpenFile (método), OpenFileDialog (componente)"
  - "OpenFileDialog (componente), abrir archivos"
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# C&#243;mo: Abrir archivos mediante el componente OpenFileDialog
El componente <xref:System.Windows.Forms.OpenFileDialog> permite a los usuarios examinar las carpetas de su equipo o de cualquier equipo de la red y seleccionar uno o más archivos para abrirlos.  El cuadro de diálogo devuelve la ruta de acceso y el nombre del archivo que seleccionó el usuario en el cuadro de diálogo.  
  
 Una vez que el usuario ha seleccionado el archivo que desea abrir, hay dos maneras de abrirlo.  Si prefiere trabajar con secuencias de archivo, puede crear una instancia de la clase <xref:System.IO.StreamReader>.  Como alternativa, puede utilizar el método <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> para abrir el archivo seleccionado.  
  
 El primero de los siguientes ejemplos implica una comprobación de permisos de <xref:System.Security.Permissions.FileIOPermission> \(como se describe en la "Nota de seguridad" siguiente\), pero da acceso al nombre del archivo.  Puede utilizar esta técnica desde el equipo local, una intranet o Internet.  El segundo método realiza también una comprobación de permisos de <xref:System.Security.Permissions.FileIOPermission>, pero es más apropiado para aplicaciones de una intranet o de Internet.  
  
### Para abrir un archivo como una secuencia utilizando el componente OpenFileDialog  
  
1.  Muestre el cuadro de diálogo **Abrir archivo** y llame a un método para abrir el archivo seleccionado por el usuario.  
  
     Una posibilidad es utilizar el método <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> para mostrar el cuadro de diálogo Abrir archivo y utilizar una instancia de la clase <xref:System.IO.StreamReader> para abrir el archivo.  
  
     En el ejemplo siguiente, el controlador de eventos <xref:System.Windows.Forms.Control.Click> del control <xref:System.Windows.Forms.Button> abre una instancia del componente <xref:System.Windows.Forms.OpenFileDialog>.  Cuando se elige un archivo y el usuario hace clic en **Aceptar**, se abre el archivo seleccionado en el cuadro de diálogo.  En este caso, el contenido se muestra en un cuadro de mensaje, sólo para mostrar que se ha leído la secuencia de archivo.  
  
    > [!IMPORTANT]
    >  Para obtener o establecer la propiedad <xref:System.Windows.Forms.FileDialog.FileName%2A>, el ensamblado necesita que la clase <xref:System.Security.Permissions.FileIOPermission?displayProperty=fullName> le conceda un nivel de privilegios.  Si ejecuta el proceso en un contexto de confianza parcial, podría desencadenarse una excepción por falta de privilegios.  Para obtener más información, vea [Conceptos básicos sobre la seguridad de acceso del código](../../../../docs/framework/misc/code-access-security-basics.md).  
  
     En el ejemplo se supone que el formulario tiene un control <xref:System.Windows.Forms.Button> y un componente <xref:System.Windows.Forms.OpenFileDialog>.  
  
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
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] y [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
    > [!NOTE]
    >  Para obtener más información sobre la lectura de secuencias de archivo, vea [FileStream.BeginRead \(Método\)](frlrfSystemIOFileStreamClassBeginReadTopic) y [FileStream.Read \(Método\)](https://msdn.microsoft.com/en-us/library/system.io.filestream.read.aspx).  
  
### Para abrir un archivo como archivo utilizando el componente OpenFileDialog  
  
1.  Utilice el método <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> para mostrar el cuadro de diálogo y el método <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> para abrir el archivo.  
  
     El método <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> del componente <xref:System.Windows.Forms.OpenFileDialog> devuelve los bytes que componen el archivo.  Estos bytes proporcionan una secuencia para que la lea.  En el ejemplo siguiente se crea una instancia de un componente <xref:System.Windows.Forms.OpenFileDialog> con un filtro "cursor", lo que permite al usuario elegir sólo archivos que tengan la extensión `.cur`.  Si se elige un archivo `.cur` , el cursor del formulario se establece en el cursor seleccionado.  
  
    > [!IMPORTANT]
    >  Para llamar al método <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A>, el ensamblado requiere un nivel de privilegios concedido por la clase <xref:System.Security.Permissions.FileIOPermission?displayProperty=fullName>.  Si ejecuta el proceso en un contexto de confianza parcial, podría desencadenarse una excepción por falta de privilegios.  Para obtener más información, vea [Conceptos básicos sobre la seguridad de acceso del código](../../../../docs/framework/misc/code-access-security-basics.md).  
  
     En el ejemplo se supone que el formulario tiene un control <xref:System.Windows.Forms.Button>.  
  
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
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] y [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## Vea también  
 <xref:System.Windows.Forms.OpenFileDialog>   
 [OpenFileDialog](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md)