---
title: Elegir carpetas con el componente FolderBrowserDialog
description: Obtenga información acerca de cómo usar el componente FolderBrowserDialog de Windows Forms dentro de las aplicaciones de Windows que cree para solicitar a los usuarios que seleccionen una carpeta.
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
ms.openlocfilehash: 11d01bbaec3b82bc221960ebab5e33ca1aa302db
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903680"
---
# <a name="how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component"></a>Procedimiento para elegir carpetas con el componente FolderBrowserDialog de formularios Windows Forms

A menudo, en las aplicaciones para Windows que cree, tendrá que pedir a los usuarios que seleccionen una carpeta y, con más frecuencia, que guarden un conjunto de archivos. El <xref:System.Windows.Forms.FolderBrowserDialog> componente Windows Forms permite llevar a cabo esta tarea fácilmente.

### <a name="to-choose-folders-with-the-folderbrowserdialog-component"></a>Elegir carpetas con el componente FolderBrowserDialog

1. En un procedimiento, Compruebe la <xref:System.Windows.Forms.FolderBrowserDialog> propiedad del componente <xref:System.Windows.Forms.Form.DialogResult%2A> para ver cómo se cerró el cuadro de diálogo y obtenga el valor de la <xref:System.Windows.Forms.FolderBrowserDialog> propiedad del componente <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> .

2. Si tiene que establecer la carpeta de nivel superior que aparecerá en la vista de árbol del cuadro de diálogo, establezca la <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> propiedad, que toma un miembro de la <xref:System.Environment.SpecialFolder> enumeración.

3. Además, puede establecer la <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> propiedad, que especifica la cadena de texto que aparece en la parte superior de la vista de árbol de explorador de carpetas.

    En el ejemplo siguiente, el <xref:System.Windows.Forms.FolderBrowserDialog> componente se usa para seleccionar una carpeta, similar a cuando se crea un proyecto en Visual Studio y se le pide que seleccione una carpeta en la que guardarla. En este ejemplo, el nombre de la carpeta se muestra en un <xref:System.Windows.Forms.TextBox> control en el formulario. Se recomienda colocar la ubicación en un área modificable, como un <xref:System.Windows.Forms.TextBox> control, para que los usuarios puedan editar su selección en caso de que se produzcan errores u otros problemas. En este ejemplo se da por supuesto un formulario con un <xref:System.Windows.Forms.FolderBrowserDialog> componente y un <xref:System.Windows.Forms.TextBox> control.

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
    > Para usar esta clase, el ensamblado requiere un nivel de privilegios concedido por la <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> propiedad, que forma parte de la <xref:System.Security.Permissions.FileIOPermissionAccess> enumeración. Si está en un contexto de confianza parcial, es posible que el proceso produzca una excepción por falta de privilegios. Para obtener más información, vea [Conceptos básicos sobre la seguridad de acceso del código](../../misc/code-access-security-basics.md).

Para obtener información sobre cómo guardar archivos, consulte [Cómo: Guardar archivos mediante el componente SaveFileDialog](how-to-save-files-using-the-savefiledialog-component.md).

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [Información general del componente FolderBrowserDialog (formularios Windows Forms)](folderbrowserdialog-component-overview-windows-forms.md)
- [Componente FolderBrowserDialog](folderbrowserdialog-component-windows-forms.md)
