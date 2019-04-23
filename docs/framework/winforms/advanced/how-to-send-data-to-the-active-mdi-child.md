---
title: Procedimiento para enviar datos al formulario secundario MDI activo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- child forms
- MDI [Windows Forms], sending data to forms
- Clipboard [Windows Forms], pasting
- Clipboard [Windows Forms], getting data from
ms.assetid: 1047d2fe-1235-46db-aad9-563aea1d743b
ms.openlocfilehash: f4399d8548eff76aaa4effae6da7239cd3b0284b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59343719"
---
# <a name="how-to-send-data-to-the-active-mdi-child"></a><span data-ttu-id="05f43-102">Procedimiento para enviar datos al formulario secundario MDI activo</span><span class="sxs-lookup"><span data-stu-id="05f43-102">How to: Send Data to the Active MDI Child</span></span>
<span data-ttu-id="05f43-103">A menudo, en el contexto de [aplicaciones de interfaz de múltiples documentos (MDI)](multiple-document-interface-mdi-applications.md), deberá enviar datos a la ventana secundaria activa, por ejemplo, cuando el usuario pega datos desde el Portapapeles en una aplicación MDI.</span><span class="sxs-lookup"><span data-stu-id="05f43-103">Often, within the context of [Multiple-Document Interface (MDI) Applications](multiple-document-interface-mdi-applications.md), you will need to send data to the active child window, such as when the user pastes data from the Clipboard into an MDI application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="05f43-104">Para obtener información sobre cómo comprobar qué ventana secundaria tiene el foco y enviar su contenido en el Portapapeles, consulte [determinar el formulario secundario MDI activo](how-to-determine-the-active-mdi-child.md).</span><span class="sxs-lookup"><span data-stu-id="05f43-104">For information about verifying which child window has focus and sending its contents to the Clipboard, see [Determining the Active MDI Child](how-to-determine-the-active-mdi-child.md).</span></span>  
  
### <a name="to-send-data-to-the-active-mdi-child-window-from-the-clipboard"></a><span data-ttu-id="05f43-105">Para enviar datos a la ventana secundaria MDI activa desde el Portapapeles</span><span class="sxs-lookup"><span data-stu-id="05f43-105">To send data to the active MDI child window from the Clipboard</span></span>  
  
1. <span data-ttu-id="05f43-106">Dentro de un método, copie el texto del Portapapeles en el control activo del formulario secundario activo.</span><span class="sxs-lookup"><span data-stu-id="05f43-106">Within a method, copy the text on the Clipboard to the active control of the active child form.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="05f43-107">En este ejemplo se da por supuesto que hay un formulario primario MDI (`Form1`) que tiene una o varias ventanas secundarias MDI que contiene un <xref:System.Windows.Forms.RichTextBox> control.</span><span class="sxs-lookup"><span data-stu-id="05f43-107">This example assumes there is an MDI parent form (`Form1`) that has one or more MDI child windows containing a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="05f43-108">Para obtener más información, consulte [crear los formularios MDI primario](how-to-create-mdi-parent-forms.md).</span><span class="sxs-lookup"><span data-stu-id="05f43-108">For more information, see [Creating MDI Parent Forms](how-to-create-mdi-parent-forms.md).</span></span>  
  
    ```vb  
    Public Sub mniPaste_Click(ByVal sender As Object, _  
       ByVal e As System.EventArgs) Handles mniPaste.Click  
  
       ' Determine the active child form.  
       Dim activeChild As Form = Me.ParentForm.ActiveMDIChild  
  
       ' If there is an active child form, find the active control, which  
       ' in this example should be a RichTextBox.  
       If (Not activeChild Is Nothing) Then  
          Try  
             Dim theBox As RichTextBox = Ctype(activeChild.ActiveControl, RichTextBox)  
             If (Not theBox Is Nothing) Then  
                ' Create a new instance of the DataObject interface.  
                Dim data As IDataObject = Clipboard.GetDataObject()  
                ' If the data is text, then set the text of the   
                ' RichTextBox to the text in the clipboard.  
                If (data.GetDataPresent(DataFormats.Text)) Then  
                   theBox.SelectedText = data.GetData(DataFormats.Text).ToString()  
                End If  
             End If  
          Catch  
             MessageBox.Show("You need to select a RichTextBox.")  
          End Try  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void mniPaste_Click (object sender, System.EventArgs e)  
    {  
      // Determine the active child form.  
       Form activeChild = this.ParentForm.ActiveMdiChild;  
  
       // If there is an active child form, find the active control, which  
       // in this example should be a RichTextBox.  
       if (activeChild != null)  
       {  
          try   
          {  
             RichTextBox theBox = (RichTextBox)activeChild.ActiveControl;  
             if (theBox != null)  
             {  
                // Create a new instance of the DataObject interface.  
                IDataObject data = Clipboard.GetDataObject();  
                // If the data is text, then set the text of the   
                // RichTextBox to the text in the clipboard.  
                if (data.GetDataPresent(DataFormats.Text))  
                {  
                   theBox.SelectedText = data.GetData(DataFormats.Text).ToString();                 
                }  
             }  
          }  
          catch   
          {  
             MessageBox.Show("You need to select a RichTextBox.");  
          }  
       }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="05f43-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="05f43-109">See also</span></span>

- [<span data-ttu-id="05f43-110">Aplicaciones de interfaz de múltiples documentos (MDI)</span><span class="sxs-lookup"><span data-stu-id="05f43-110">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="05f43-111">Cómo: Crear formularios principales MDI</span><span class="sxs-lookup"><span data-stu-id="05f43-111">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="05f43-112">Cómo: Crear formularios MDI secundarios</span><span class="sxs-lookup"><span data-stu-id="05f43-112">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="05f43-113">Cómo: Determinar el formulario secundario MDI activo</span><span class="sxs-lookup"><span data-stu-id="05f43-113">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)
- [<span data-ttu-id="05f43-114">Cómo: Organizar formularios MDI secundarios</span><span class="sxs-lookup"><span data-stu-id="05f43-114">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)
