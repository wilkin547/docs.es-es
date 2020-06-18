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
# <a name="how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component"></a><span data-ttu-id="ab737-103">Procedimiento para elegir carpetas con el componente FolderBrowserDialog de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ab737-103">How to: Choose Folders with the Windows Forms FolderBrowserDialog Component</span></span>

<span data-ttu-id="ab737-104">A menudo, en las aplicaciones para Windows que cree, tendrá que pedir a los usuarios que seleccionen una carpeta y, con más frecuencia, que guarden un conjunto de archivos.</span><span class="sxs-lookup"><span data-stu-id="ab737-104">Often, within Windows applications you create, you will have to prompt users to select a folder, most frequently to save a set of files.</span></span> <span data-ttu-id="ab737-105">El <xref:System.Windows.Forms.FolderBrowserDialog> componente Windows Forms permite llevar a cabo esta tarea fácilmente.</span><span class="sxs-lookup"><span data-stu-id="ab737-105">The Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> component allows you to easily accomplish this task.</span></span>

### <a name="to-choose-folders-with-the-folderbrowserdialog-component"></a><span data-ttu-id="ab737-106">Elegir carpetas con el componente FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="ab737-106">To choose folders with the FolderBrowserDialog component</span></span>

1. <span data-ttu-id="ab737-107">En un procedimiento, Compruebe la <xref:System.Windows.Forms.FolderBrowserDialog> propiedad del componente <xref:System.Windows.Forms.Form.DialogResult%2A> para ver cómo se cerró el cuadro de diálogo y obtenga el valor de la <xref:System.Windows.Forms.FolderBrowserDialog> propiedad del componente <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> .</span><span class="sxs-lookup"><span data-stu-id="ab737-107">In a procedure, check the <xref:System.Windows.Forms.FolderBrowserDialog> component's <xref:System.Windows.Forms.Form.DialogResult%2A> property to see how the dialog box was closed and get the value of the <xref:System.Windows.Forms.FolderBrowserDialog> component's <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property.</span></span>

2. <span data-ttu-id="ab737-108">Si tiene que establecer la carpeta de nivel superior que aparecerá en la vista de árbol del cuadro de diálogo, establezca la <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> propiedad, que toma un miembro de la <xref:System.Environment.SpecialFolder> enumeración.</span><span class="sxs-lookup"><span data-stu-id="ab737-108">If you need to set the top-most folder that will appear within the tree view of the dialog box, set the <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> property, which takes a member of the <xref:System.Environment.SpecialFolder> enumeration.</span></span>

3. <span data-ttu-id="ab737-109">Además, puede establecer la <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> propiedad, que especifica la cadena de texto que aparece en la parte superior de la vista de árbol de explorador de carpetas.</span><span class="sxs-lookup"><span data-stu-id="ab737-109">Additionally, you can set the <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> property, which specifies the text string that appears at the top of the folder-browser tree view.</span></span>

    <span data-ttu-id="ab737-110">En el ejemplo siguiente, el <xref:System.Windows.Forms.FolderBrowserDialog> componente se usa para seleccionar una carpeta, similar a cuando se crea un proyecto en Visual Studio y se le pide que seleccione una carpeta en la que guardarla.</span><span class="sxs-lookup"><span data-stu-id="ab737-110">In the example below, the <xref:System.Windows.Forms.FolderBrowserDialog> component is used to select a folder, similar to when you create a project in Visual Studio and are prompted to select a folder to save it in.</span></span> <span data-ttu-id="ab737-111">En este ejemplo, el nombre de la carpeta se muestra en un <xref:System.Windows.Forms.TextBox> control en el formulario.</span><span class="sxs-lookup"><span data-stu-id="ab737-111">In this example, the folder name is then displayed in a <xref:System.Windows.Forms.TextBox> control on the form.</span></span> <span data-ttu-id="ab737-112">Se recomienda colocar la ubicación en un área modificable, como un <xref:System.Windows.Forms.TextBox> control, para que los usuarios puedan editar su selección en caso de que se produzcan errores u otros problemas.</span><span class="sxs-lookup"><span data-stu-id="ab737-112">It is a good idea to place the location in an editable area, such as a <xref:System.Windows.Forms.TextBox> control, so that users may edit their selection in case of error or other issues.</span></span> <span data-ttu-id="ab737-113">En este ejemplo se da por supuesto un formulario con un <xref:System.Windows.Forms.FolderBrowserDialog> componente y un <xref:System.Windows.Forms.TextBox> control.</span><span class="sxs-lookup"><span data-stu-id="ab737-113">This example assumes a form with a <xref:System.Windows.Forms.FolderBrowserDialog> component and a <xref:System.Windows.Forms.TextBox> control.</span></span>

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
    > <span data-ttu-id="ab737-114">Para usar esta clase, el ensamblado requiere un nivel de privilegios concedido por la <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> propiedad, que forma parte de la <xref:System.Security.Permissions.FileIOPermissionAccess> enumeración.</span><span class="sxs-lookup"><span data-stu-id="ab737-114">To use this class, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> property, which is part of the <xref:System.Security.Permissions.FileIOPermissionAccess> enumeration.</span></span> <span data-ttu-id="ab737-115">Si está en un contexto de confianza parcial, es posible que el proceso produzca una excepción por falta de privilegios.</span><span class="sxs-lookup"><span data-stu-id="ab737-115">If you are running in a partial-trust context, the process might throw an exception because of insufficient privileges.</span></span> <span data-ttu-id="ab737-116">Para obtener más información, vea [Conceptos básicos sobre la seguridad de acceso del código](../../misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="ab737-116">For more information, see [Code Access Security Basics](../../misc/code-access-security-basics.md).</span></span>

<span data-ttu-id="ab737-117">Para obtener información sobre cómo guardar archivos, consulte [Cómo: Guardar archivos mediante el componente SaveFileDialog](how-to-save-files-using-the-savefiledialog-component.md).</span><span class="sxs-lookup"><span data-stu-id="ab737-117">For information on how to save files, see [How to: Save Files Using the SaveFileDialog Component](how-to-save-files-using-the-savefiledialog-component.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ab737-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ab737-118">See also</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [<span data-ttu-id="ab737-119">Información general del componente FolderBrowserDialog (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="ab737-119">FolderBrowserDialog Component Overview (Windows Forms)</span></span>](folderbrowserdialog-component-overview-windows-forms.md)
- [<span data-ttu-id="ab737-120">Componente FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="ab737-120">FolderBrowserDialog Component</span></span>](folderbrowserdialog-component-windows-forms.md)
