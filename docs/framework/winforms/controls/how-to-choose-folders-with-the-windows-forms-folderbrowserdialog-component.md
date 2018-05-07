---
title: 'Cómo: Elegir carpetas con el componente FolderBrowserDialog de formularios Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- directories [Windows Forms], choosing
- FolderBrowserDialog component [Windows Forms], choosing directories
- folders [Windows Forms], selecting
- folders [Windows Forms], choosing
- directories [Windows Forms], selecting
ms.assetid: 4593670e-7c7d-4661-b46b-4ffb63258adb
ms.openlocfilehash: 657aad6efa195ec3d9741f4f91d4e01af4a54a19
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component"></a>Cómo: Elegir carpetas con el componente FolderBrowserDialog de formularios Windows Forms
A menudo, en las aplicaciones para Windows que cree, tendrá que pedir a los usuarios que seleccionen una carpeta y, con más frecuencia, que guarden un conjunto de archivos. Los formularios de Windows <xref:System.Windows.Forms.FolderBrowserDialog> componente permite realizar fácilmente esta tarea.  
  
### <a name="to-choose-folders-with-the-folderbrowserdialog-component"></a>Elegir carpetas con el componente FolderBrowserDialog  
  
1.  En un procedimiento, compruebe la <xref:System.Windows.Forms.FolderBrowserDialog> del componente <xref:System.Windows.Forms.Form.DialogResult%2A> propiedad para ver cómo se cerró el cuadro de diálogo y obtener el valor de la <xref:System.Windows.Forms.FolderBrowserDialog> del componente <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> propiedad.  
  
2.  Si necesita carpeta de conjunto superior que aparecerá en la vista de árbol del cuadro de diálogo, establezca la <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> propiedad, que toma el miembro de la <xref:System.Environment.SpecialFolder> enumeración.  
  
3.  Además, puede establecer el <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> propiedad, que especifica el texto de cadena que aparece en la parte superior de la vista de árbol del explorador de carpetas.  
  
     En el ejemplo siguiente, la <xref:System.Windows.Forms.FolderBrowserDialog> componente se utiliza para seleccionar una carpeta, similar al crear un proyecto en Visual Studio y le pedirá que seleccione una carpeta para guardarlo. En este ejemplo, a continuación, se muestra el nombre de la carpeta en un <xref:System.Windows.Forms.TextBox> control en el formulario. Es conveniente colocar la ubicación en un área modificable, como un <xref:System.Windows.Forms.TextBox> control, de modo que los usuarios puedan editar su selección en caso de error u otros problemas. En este ejemplo se da por supuesto un formulario con un <xref:System.Windows.Forms.FolderBrowserDialog> componente y una <xref:System.Windows.Forms.TextBox> control.  
  
    ```vb  
    Public Sub ChooseFolder()  
        If FolderBrowserDialog1.ShowDialog() = DialogResult.OK Then  
            TextBox1.Text = FolderBrowserDialog1.SelectedPath  
        End If  
    End Sub  
    ```  
  
    ```csharp  
    public void ChooseFolder()  
    {  
        if (folderBrowserDialog1.ShowDialog() == DialogResult.OK)   
        {  
            textBox1.Text = folderBrowserDialog1.SelectedPath;  
        }  
    }  
    ```  
  
    ```cpp  
    public:  
       void ChooseFolder()  
       {  
          if (folderBrowserDialog1->ShowDialog() == DialogResult::OK)  
          {  
             textBox1->Text = folderBrowserDialog1->SelectedPath;  
          }  
       }  
    ```  
  
    > [!IMPORTANT]
    >  Para utilizar esta clase, el ensamblado requiere un nivel de privilegio concedido por la <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> propiedad, que forma parte de la <xref:System.Security.Permissions.FileIOPermissionAccess> enumeración. Si está en un contexto de confianza parcial, es posible que el proceso produzca una excepción por falta de privilegios. Para obtener más información, vea [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md) (Aspectos básicos de seguridad de acceso del código).  
  
 Para obtener información sobre cómo guardar archivos, consulte [Cómo: Guardar archivos mediante el componente SaveFileDialog](../../../../docs/framework/winforms/controls/how-to-save-files-using-the-savefiledialog-component.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.FolderBrowserDialog>  
 [Información general del componente FolderBrowserDialog (Windows Forms)](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-overview-windows-forms.md)  
 [FolderBrowserDialog (componente)](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-windows-forms.md)
