---
title: 'Cómo: Determinar el formulario secundario MDI activo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Clipboard [Windows Forms], copying data to
- MDI [Windows Forms], child windows
- child forms
- MDI [Windows Forms], activating forms
- MDI [Windows Forms], locating focus
ms.assetid: 33880ec3-0207-4c2b-a616-ff140443cc0f
ms.openlocfilehash: 57491faa10c182630d41565ba236d65e393929b3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182544"
---
# <a name="how-to-determine-the-active-mdi-child"></a><span data-ttu-id="0d9f4-102">Cómo: Determinar el formulario secundario MDI activo</span><span class="sxs-lookup"><span data-stu-id="0d9f4-102">How to: Determine the Active MDI Child</span></span>
<span data-ttu-id="0d9f4-103">En ocasiones, querrá proporcionar un comando que funcione en el control que se centra en el formulario secundario activo actualmente.</span><span class="sxs-lookup"><span data-stu-id="0d9f4-103">On occasion, you will want to provide a command that operates on the control that has focus on the currently active child form.</span></span> <span data-ttu-id="0d9f4-104">Por ejemplo, supongamos que desea copiar el texto seleccionado del cuadro de texto del formulario secundario al Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="0d9f4-104">For example, suppose you want to copy selected text from the child form's text box to the Clipboard.</span></span> <span data-ttu-id="0d9f4-105">Crearía un procedimiento que copie el texto <xref:System.Windows.Forms.Control.Click> seleccionado en el Portapapeles utilizando el evento del elemento de menú Copiar del menú Edición estándar.</span><span class="sxs-lookup"><span data-stu-id="0d9f4-105">You would create a procedure that copies selected text to the Clipboard using the <xref:System.Windows.Forms.Control.Click> event of the Copy menu item on the standard Edit menu.</span></span>  
  
 <span data-ttu-id="0d9f4-106">Dado que una aplicación MDI puede tener muchas instancias del mismo formulario secundario, el procedimiento debe saber qué formulario usar.</span><span class="sxs-lookup"><span data-stu-id="0d9f4-106">Because an MDI application can have many instances of the same child form, the procedure needs to know which form to use.</span></span> <span data-ttu-id="0d9f4-107">Para especificar el formulario <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> correcto, utilice la propiedad, que devuelve el formulario secundario que tiene el foco o que se ha activo más recientemente.</span><span class="sxs-lookup"><span data-stu-id="0d9f4-107">To specify the correct form, use the <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> property, which returns the child form that has the focus or that was most recently active.</span></span>  
  
 <span data-ttu-id="0d9f4-108">Cuando tiene varios controles en un formulario, también debe especificar qué control está activo.</span><span class="sxs-lookup"><span data-stu-id="0d9f4-108">When you have several controls on a form, you also need to specify which control is active.</span></span> <span data-ttu-id="0d9f4-109">Al <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> igual que <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> la propiedad, la propiedad devuelve el control con el foco en el formulario secundario activo.</span><span class="sxs-lookup"><span data-stu-id="0d9f4-109">Like the <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> property, the <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> property returns the control with the focus on the active child form.</span></span> <span data-ttu-id="0d9f4-110">El procedimiento siguiente ilustra un procedimiento de copia que se puede llamar desde un menú de formulario secundario, un menú en el formulario MDI o un botón de barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="0d9f4-110">The procedure below illustrates a copy procedure that can be called from a child form menu, a menu on the MDI form, or a toolbar button.</span></span>  
  
### <a name="to-determine-the-active-mdi-child-to-copy-its-text-to-the-clipboard"></a><span data-ttu-id="0d9f4-111">Para determinar el elemento secundario MDI activo (para copiar su texto en el Portapapeles)</span><span class="sxs-lookup"><span data-stu-id="0d9f4-111">To determine the active MDI child (to copy its text to the Clipboard)</span></span>  
  
1. <span data-ttu-id="0d9f4-112">Dentro de un método, copie el texto del control activo del formulario secundario activo en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="0d9f4-112">Within a method, copy the text of the active control of the active child form to the Clipboard.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="0d9f4-113">En este ejemplo se supone que`Form1`hay un formulario primario MDI ( <xref:System.Windows.Forms.RichTextBox> ) que tiene una o varias ventanas secundarias MDI que contienen un control.</span><span class="sxs-lookup"><span data-stu-id="0d9f4-113">This example assumes there is an MDI parent form (`Form1`) that has one or more MDI child windows containing a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="0d9f4-114">Para obtener más información, consulte Creación de [formularios primarios MDI](how-to-create-mdi-parent-forms.md).</span><span class="sxs-lookup"><span data-stu-id="0d9f4-114">For more information, see [Creating MDI Parent Forms](how-to-create-mdi-parent-forms.md).</span></span>  
  
    ```vb  
    Public Sub mniCopy_Click(ByVal sender As Object, _  
       ByVal e As System.EventArgs) Handles mniCopy.Click  
  
       ' Determine the active child form.  
       Dim activeChild As Form = Me.ActiveMDIChild  
  
       ' If there is an active child form, find the active control, which  
       ' in this example should be a RichTextBox.  
       If (Not activeChild Is Nothing) Then  
          Dim theBox As RichTextBox = _  
            TryCast(activeChild.ActiveControl, RichTextBox)  
  
          If (Not theBox Is Nothing) Then  
             'Put selected text on Clipboard.  
             Clipboard.SetDataObject(theBox.SelectedText)  
          Else  
             MessageBox.Show("You need to select a RichTextBox.")  
          End If  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void mniCopy_Click (object sender, System.EventArgs e)  
    {  
       // Determine the active child form.  
       Form activeChild = this.ActiveMdiChild;  
  
       // If there is an active child form, find the active control, which  
       // in this example should be a RichTextBox.  
       if (activeChild != null)  
       {
          try  
          {  
             RichTextBox theBox = (RichTextBox)activeChild.ActiveControl;  
             if (theBox != null)  
             {  
                // Put the selected text on the Clipboard.  
                Clipboard.SetDataObject(theBox.SelectedText);  
  
             }  
          }  
          catch  
          {  
             MessageBox.Show("You need to select a RichTextBox.");  
          }  
       }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0d9f4-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0d9f4-115">See also</span></span>

- [<span data-ttu-id="0d9f4-116">Aplicaciones de interfaz de múltiples documentos (MDI)</span><span class="sxs-lookup"><span data-stu-id="0d9f4-116">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="0d9f4-117">Cómo: Crear formularios principales MDI</span><span class="sxs-lookup"><span data-stu-id="0d9f4-117">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="0d9f4-118">Cómo: Crear formularios MDI secundarios</span><span class="sxs-lookup"><span data-stu-id="0d9f4-118">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="0d9f4-119">Cómo: Enviar datos al formulario secundario MDI activo</span><span class="sxs-lookup"><span data-stu-id="0d9f4-119">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)
- [<span data-ttu-id="0d9f4-120">Cómo: Organizar formularios MDI secundarios</span><span class="sxs-lookup"><span data-stu-id="0d9f4-120">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)
