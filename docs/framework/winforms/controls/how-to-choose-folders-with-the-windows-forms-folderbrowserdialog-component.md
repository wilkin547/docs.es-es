---
title: Filtrar para elegir carpetas con el componente FolderBrowserDialog de formularios Windows Forms
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
ms.openlocfilehash: 2bff105d5c97a8b98d094a1ce3a4f033aa5971be
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59116082"
---
# <a name="how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component"></a>Filtrar para elegir carpetas con el componente FolderBrowserDialog de formularios Windows Forms
A menudo, en las aplicaciones para Windows que cree, tendrá que pedir a los usuarios que seleccionen una carpeta y, con más frecuencia, que guarden un conjunto de archivos. Los formularios de Windows <xref:System.Windows.Forms.FolderBrowserDialog> componente le permite realizar esta tarea con facilidad.  
  
### <a name="to-choose-folders-with-the-folderbrowserdialog-component"></a>Elegir carpetas con el componente FolderBrowserDialog  
  
1.  En un procedimiento, compruebe la <xref:System.Windows.Forms.FolderBrowserDialog> del componente <xref:System.Windows.Forms.Form.DialogResult%2A> propiedad para ver cómo se cerró el cuadro de diálogo y obtener el valor de la <xref:System.Windows.Forms.FolderBrowserDialog> del componente <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> propiedad.  
  
2.  Si necesita a carpeta de la parte superior del conjunto que aparecerá en la vista de árbol del cuadro de diálogo, establezca el <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> propiedad, que toma un miembro de la <xref:System.Environment.SpecialFolder> enumeración.  
  
3.  Además, puede establecer el <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> propiedad, que especifica el texto de cadena que aparece en la parte superior de la vista de árbol del explorador de carpetas.  
  
     En el ejemplo siguiente, la <xref:System.Windows.Forms.FolderBrowserDialog> componente se utiliza para seleccionar una carpeta, similar al crear un proyecto en Visual Studio y se le pedirá que seleccione una carpeta para guardarlo en. En este ejemplo, a continuación, se muestra el nombre de carpeta en un <xref:System.Windows.Forms.TextBox> control en el formulario. Es una buena idea para colocar la ubicación en un área modificable, como un <xref:System.Windows.Forms.TextBox> control, de modo que los usuarios puedan editar su selección en el caso de error u otros problemas. En este ejemplo se supone un formulario con un <xref:System.Windows.Forms.FolderBrowserDialog> componente y un <xref:System.Windows.Forms.TextBox> control.  
  
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
    >  Para usar esta clase, el ensamblado requiere un nivel de privilegio concedido por la <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> propiedad, que forma parte de la <xref:System.Security.Permissions.FileIOPermissionAccess> enumeración. Si está en un contexto de confianza parcial, es posible que el proceso produzca una excepción por falta de privilegios. Para obtener más información, vea [Code Access Security Basics](../../misc/code-access-security-basics.md) (Aspectos básicos de seguridad de acceso del código).  
  
 Para obtener información sobre cómo guardar archivos, vea [Cómo: Guardar archivos mediante el componente SaveFileDialog](how-to-save-files-using-the-savefiledialog-component.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [Información general del componente FolderBrowserDialog (formularios Windows Forms)](folderbrowserdialog-component-overview-windows-forms.md)
- [Componente FolderBrowserDialog](folderbrowserdialog-component-windows-forms.md)
