---
title: Procedimiento para cargar archivos en el control RichTextBox de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- text boxes [Windows Forms], displaying files
- examples [Windows Forms], text boxes
- .rtf files [Windows Forms], opening in RichTextBox control
- RTF files [Windows Forms], opening in RichTextBox control
- text files [Windows Forms], displaying in RichTextBox control
- .rtf files [Windows Forms], displaying in RichTextBox control
- RichTextBox control [Windows Forms], opening files
- RTF files [Windows Forms], displaying in RichTextBox control
ms.assetid: c03451be-f285-4428-a71a-c41e002cc919
ms.openlocfilehash: ffbce7401f068b3d0a7fee4fd8ba04c10cb6f6b7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59340859"
---
# <a name="how-to-load-files-into-the-windows-forms-richtextbox-control"></a>Procedimiento para cargar archivos en el control RichTextBox de formularios Windows Forms
El control <xref:System.Windows.Forms.RichTextBox> de Windows Forms puede mostrar un archivo de texto sin formato, un archivo de texto sin formato Unicode o un archivo de formato de texto enriquecido (RTF). Para ello, llame al método <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> . También puede usar el método <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> para cargar los datos desde una secuencia. Para obtener más información, consulta <xref:System.Windows.Forms.RichTextBox.LoadFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.  
  
### <a name="to-load-a-file-into-the-richtextbox-control"></a>Para cargar un archivo en el control RichTextBox  
  
1. Determine la ruta de acceso del archivo que quiere abrir con el componente <xref:System.Windows.Forms.OpenFileDialog> . Para obtener información general, consulte [general sobre el componente OpenFileDialog](openfiledialog-component-overview-windows-forms.md).  
  
2. Llame al método <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> del control <xref:System.Windows.Forms.RichTextBox> especificando el archivo que se va a cargar y, si quiere, un tipo de archivo. En el siguiente ejemplo, el archivo que se va a cargar se toma de la propiedad <xref:System.Windows.Forms.OpenFileDialog> del componente <xref:System.Windows.Forms.FileDialog.FileName%2A> . Si llama al método con un nombre de archivo como único argumento, se presupondrá que el tipo de archivo es RTF. Para especificar otro tipo de archivo, llame al método con un valor de la enumeración <xref:System.Windows.Forms.RichTextBoxStreamType> como segundo argumento.  
  
     En el siguiente ejemplo, el componente <xref:System.Windows.Forms.OpenFileDialog> aparece cuando se hace clic en un botón. Después, el archivo seleccionado se abre y se muestra en el control <xref:System.Windows.Forms.RichTextBox> . En este ejemplo se presupone que un formulario tiene un botón,`btnOpenFile`.  
  
    ```vb  
    Private Sub btnOpenFile_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles btnOpenFile.Click  
         If OpenFileDialog1.ShowDialog() = DialogResult.OK Then  
           RichTextBox1.LoadFile(OpenFileDialog1.FileName, _  
              RichTextBoxStreamType.RichText)  
          End If  
    End Sub  
    ```  
  
    ```csharp  
    private void btnOpenFile_Click(object sender, System.EventArgs e)  
    {  
       if(openFileDialog1.ShowDialog() == DialogResult.OK)  
       {  
         richTextBox1.LoadFile(openFileDialog1.FileName, RichTextBoxStreamType.RichText);  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void btnOpenFile_Click(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          if(openFileDialog1->ShowDialog() == DialogResult::OK)  
          {  
             richTextBox1->LoadFile(openFileDialog1->FileName,  
                RichTextBoxStreamType::RichText);  
          }  
       }  
    ```  
  
     (Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.btnOpenFile.Click += new System.EventHandler(this. btnOpenFile_Click);  
    ```  
  
    ```cpp  
    this->btnOpenFile->Click += gcnew   
       System::EventHandler(this, &Form1::btnOpenFile_Click);  
    ```  
  
    > [!IMPORTANT]
    >  Para ejecutar este proceso, es posible que el ensamblado necesite un nivel de privilegio concedido por la clase <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> . Si está en un contexto de confianza parcial, es posible que el proceso produzca una excepción por falta de privilegios. Para obtener más información, vea [Code Access Security Basics](../../misc/code-access-security-basics.md) (Aspectos básicos de seguridad de acceso del código).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.RichTextBox.LoadFile%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox (control)](richtextbox-control-windows-forms.md)
- [Controles que se utilizan en formularios Windows Forms](controls-to-use-on-windows-forms.md)
