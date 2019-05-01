---
title: Procedimiento para determinar cuándo cambian los atributos de formato en el control RichTextBox de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], text boxes
- RichTextBox control [Windows Forms], determining font changes
- text boxes [Windows Forms], determining font changes
- SelChange event
ms.assetid: bdfed015-f77a-41e5-b38f-f8629b2fa166
ms.openlocfilehash: a90affde9de36f1c83d5b7c21b40580cdf53402e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61972294"
---
# <a name="how-to-determine-when-formatting-attributes-change-in-the-windows-forms-richtextbox-control"></a><span data-ttu-id="655d1-102">Procedimiento para determinar cuándo cambian los atributos de formato en el control RichTextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="655d1-102">How to: Determine When Formatting Attributes Change in the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="655d1-103">Un uso común de los formularios de Windows <xref:System.Windows.Forms.RichTextBox> control es dar formato al texto con atributos tales como las opciones de fuente o estilos de párrafo.</span><span class="sxs-lookup"><span data-stu-id="655d1-103">A common use of the Windows Forms <xref:System.Windows.Forms.RichTextBox> control is formatting text with attributes such as font options or paragraph styles.</span></span> <span data-ttu-id="655d1-104">La aplicación puede necesitar realizar un seguimiento de los cambios en el formato del texto para mostrar una barra de herramientas, como en muchas aplicaciones de procesamiento de texto.</span><span class="sxs-lookup"><span data-stu-id="655d1-104">Your application may need to keep track of any changes in text formatting for the purpose of displaying a toolbar, as in many word-processing applications.</span></span>  
  
### <a name="to-respond-to-changes-in-formatting-attributes"></a><span data-ttu-id="655d1-105">Para responder a cambios en atributos de formato</span><span class="sxs-lookup"><span data-stu-id="655d1-105">To respond to changes in formatting attributes</span></span>  
  
1. <span data-ttu-id="655d1-106">Escribir código en el <xref:System.Windows.Forms.RichTextBox.SelectionChanged> controlador de eventos para realizar las acciones adecuadas según el valor del atributo.</span><span class="sxs-lookup"><span data-stu-id="655d1-106">Write code in the <xref:System.Windows.Forms.RichTextBox.SelectionChanged> event handler to perform an appropriate action depending on the value of the attribute.</span></span> <span data-ttu-id="655d1-107">En el ejemplo siguiente se cambia la apariencia de un botón de barra de herramientas, dependiendo del valor de la <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="655d1-107">The following example changes the appearance of a toolbar button depending on the value of the <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> property.</span></span> <span data-ttu-id="655d1-108">El botón de barra de herramientas sólo se actualizará cuando se mueve el punto de inserción en el control.</span><span class="sxs-lookup"><span data-stu-id="655d1-108">The toolbar button will only be updated when the insertion point is moved in the control.</span></span>  
  
     <span data-ttu-id="655d1-109">El ejemplo siguiente se da por supuesto un formulario con un <xref:System.Windows.Forms.RichTextBox> control y un <xref:System.Windows.Forms.ToolBar> control que contiene un botón de barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="655d1-109">The example below assumes a form with a <xref:System.Windows.Forms.RichTextBox> control and a <xref:System.Windows.Forms.ToolBar> control that contains a toolbar button.</span></span> <span data-ttu-id="655d1-110">Para obtener más información acerca de las barras de herramientas y botones de barra de herramientas, vea [Cómo: Agregar botones a un Control de barra de herramientas](how-to-add-buttons-to-a-toolbar-control.md).</span><span class="sxs-lookup"><span data-stu-id="655d1-110">For more information about toolbars and toolbar buttons, see [How to: Add Buttons to a ToolBar Control](how-to-add-buttons-to-a-toolbar-control.md).</span></span>  
  
    ```vb  
    ' The following code assumes the existence of a toolbar control  
    ' with at least one toolbar button.  
    Private Sub RichTextBox1_SelectionChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles RichTextBox1.SelectionChanged  
       If RichTextBox1.SelectionBullet = True Then  
          ' Bullet button on toolbar should appear pressed  
          ToolBarButton1.Pushed = True  
       Else  
           ' Bullet button on toolbar should appear unpressed  
           ToolBarButton1.Pushed = False  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    // The following code assumes the existence of a toolbar control  
    // with at least one toolbar button.  
    private void richTextBox1_SelectionChanged(object sender,  
    System.EventArgs e)  
    {  
       if (richTextBox1.SelectionBullet == true)   
       {  
          // Bullet button on toolbar should appear pressed  
          toolBarButton1.Pushed = true;  
       }  
       else   
       {  
          // Bullet button on toolbar should appear unpressed  
          toolBarButton1.Pushed = false;  
       }  
    }  
    ```  
  
    ```cpp  
    // The following code assumes the existence of a toolbar control  
    // with at least one toolbar button.  
    private:  
       System::Void richTextBox1_SelectionChanged(  
          System::Object ^  sender, System::EventArgs ^  e)  
       {  
          if (richTextBox1->SelectionBullet == true)  
          {  
             // Bullet button on toolbar should appear pressed  
             toolBarButton1->Pushed = true;  
          }  
          else  
          {  
             // Bullet button on toolbar should appear unpressed  
             toolBarButton1->Pushed = false;  
          }  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="655d1-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="655d1-111">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox.SelectionChanged>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="655d1-112">RichTextBox (control)</span><span class="sxs-lookup"><span data-stu-id="655d1-112">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="655d1-113">Controles que se utilizan en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="655d1-113">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
