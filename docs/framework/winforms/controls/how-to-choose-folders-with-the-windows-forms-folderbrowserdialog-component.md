---
title: "Cómo: Elegir carpetas con el componente FolderBrowserDialog de formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: de41d5664c2481032dffe213a52779834338ca2c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component"></a><span data-ttu-id="211ef-102">Cómo: Elegir carpetas con el componente FolderBrowserDialog de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="211ef-102">How to: Choose Folders with the Windows Forms FolderBrowserDialog Component</span></span>
<span data-ttu-id="211ef-103">A menudo, en las aplicaciones para Windows que cree, tendrá que pedir a los usuarios que seleccionen una carpeta y, con más frecuencia, que guarden un conjunto de archivos.</span><span class="sxs-lookup"><span data-stu-id="211ef-103">Often, within Windows applications you create, you will have to prompt users to select a folder, most frequently to save a set of files.</span></span> <span data-ttu-id="211ef-104">Los formularios de Windows <xref:System.Windows.Forms.FolderBrowserDialog> componente permite realizar fácilmente esta tarea.</span><span class="sxs-lookup"><span data-stu-id="211ef-104">The Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> component allows you to easily accomplish this task.</span></span>  
  
### <a name="to-choose-folders-with-the-folderbrowserdialog-component"></a><span data-ttu-id="211ef-105">Elegir carpetas con el componente FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="211ef-105">To choose folders with the FolderBrowserDialog component</span></span>  
  
1.  <span data-ttu-id="211ef-106">En un procedimiento, compruebe la <xref:System.Windows.Forms.FolderBrowserDialog> del componente <xref:System.Windows.Forms.Form.DialogResult%2A> propiedad para ver cómo se cerró el cuadro de diálogo y obtener el valor de la <xref:System.Windows.Forms.FolderBrowserDialog> del componente <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="211ef-106">In a procedure, check the <xref:System.Windows.Forms.FolderBrowserDialog> component's <xref:System.Windows.Forms.Form.DialogResult%2A> property to see how the dialog box was closed and get the value of the <xref:System.Windows.Forms.FolderBrowserDialog> component's <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property.</span></span>  
  
2.  <span data-ttu-id="211ef-107">Si necesita carpeta de conjunto superior que aparecerá en la vista de árbol del cuadro de diálogo, establezca la <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> propiedad, que toma el miembro de la <xref:System.Environment.SpecialFolder> enumeración.</span><span class="sxs-lookup"><span data-stu-id="211ef-107">If you need to set the top-most folder that will appear within the tree view of the dialog box, set the <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> property, which takes a member of the <xref:System.Environment.SpecialFolder> enumeration.</span></span>  
  
3.  <span data-ttu-id="211ef-108">Además, puede establecer el <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> propiedad, que especifica el texto de cadena que aparece en la parte superior de la vista de árbol del explorador de carpetas.</span><span class="sxs-lookup"><span data-stu-id="211ef-108">Additionally, you can set the <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> property, which specifies the text string that appears at the top of the folder-browser tree view.</span></span>  
  
     <span data-ttu-id="211ef-109">En el ejemplo siguiente, la <xref:System.Windows.Forms.FolderBrowserDialog> componente se utiliza para seleccionar una carpeta, similar al crear un proyecto en Visual Studio y le pedirá que seleccione una carpeta para guardarlo.</span><span class="sxs-lookup"><span data-stu-id="211ef-109">In the example below, the <xref:System.Windows.Forms.FolderBrowserDialog> component is used to select a folder, similar to when you create a project in Visual Studio and are prompted to select a folder to save it in.</span></span> <span data-ttu-id="211ef-110">En este ejemplo, a continuación, se muestra el nombre de la carpeta en un <xref:System.Windows.Forms.TextBox> control en el formulario.</span><span class="sxs-lookup"><span data-stu-id="211ef-110">In this example, the folder name is then displayed in a <xref:System.Windows.Forms.TextBox> control on the form.</span></span> <span data-ttu-id="211ef-111">Es conveniente colocar la ubicación en un área modificable, como un <xref:System.Windows.Forms.TextBox> control, de modo que los usuarios puedan editar su selección en caso de error u otros problemas.</span><span class="sxs-lookup"><span data-stu-id="211ef-111">It is a good idea to place the location in an editable area, such as a <xref:System.Windows.Forms.TextBox> control, so that users may edit their selection in case of error or other issues.</span></span> <span data-ttu-id="211ef-112">En este ejemplo se da por supuesto un formulario con un <xref:System.Windows.Forms.FolderBrowserDialog> componente y una <xref:System.Windows.Forms.TextBox> control.</span><span class="sxs-lookup"><span data-stu-id="211ef-112">This example assumes a form with a <xref:System.Windows.Forms.FolderBrowserDialog> component and a <xref:System.Windows.Forms.TextBox> control.</span></span>  
  
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
    >  <span data-ttu-id="211ef-113">Para utilizar esta clase, el ensamblado requiere un nivel de privilegio concedido por la <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> propiedad, que forma parte de la <xref:System.Security.Permissions.FileIOPermissionAccess> enumeración.</span><span class="sxs-lookup"><span data-stu-id="211ef-113">To use this class, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> property, which is part of the <xref:System.Security.Permissions.FileIOPermissionAccess> enumeration.</span></span> <span data-ttu-id="211ef-114">Si está en un contexto de confianza parcial, es posible que el proceso produzca una excepción por falta de privilegios.</span><span class="sxs-lookup"><span data-stu-id="211ef-114">If you are running in a partial-trust context, the process might throw an exception because of insufficient privileges.</span></span> <span data-ttu-id="211ef-115">Para obtener más información, vea [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md) (Aspectos básicos de seguridad de acceso del código).</span><span class="sxs-lookup"><span data-stu-id="211ef-115">For more information, see [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md).</span></span>  
  
 <span data-ttu-id="211ef-116">Para obtener información sobre cómo guardar archivos, consulte [Cómo: Guardar archivos mediante el componente SaveFileDialog](../../../../docs/framework/winforms/controls/how-to-save-files-using-the-savefiledialog-component.md).</span><span class="sxs-lookup"><span data-stu-id="211ef-116">For information on how to save files, see [How to: Save Files Using the SaveFileDialog Component](../../../../docs/framework/winforms/controls/how-to-save-files-using-the-savefiledialog-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="211ef-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="211ef-117">See Also</span></span>  
 <xref:System.Windows.Forms.FolderBrowserDialog>  
 [<span data-ttu-id="211ef-118">Información general del componente FolderBrowserDialog (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="211ef-118">FolderBrowserDialog Component Overview (Windows Forms)</span></span>](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-overview-windows-forms.md)  
 [<span data-ttu-id="211ef-119">FolderBrowserDialog (componente)</span><span class="sxs-lookup"><span data-stu-id="211ef-119">FolderBrowserDialog Component</span></span>](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-windows-forms.md)
