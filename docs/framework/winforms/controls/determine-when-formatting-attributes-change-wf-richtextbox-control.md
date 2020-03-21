---
title: Determinar cuándo cambian los atributos de formato en RichTextBox Control
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
ms.openlocfilehash: a190c3479b58464763e0eefdd32d14e88a1f05e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142269"
---
# <a name="how-to-determine-when-formatting-attributes-change-in-the-windows-forms-richtextbox-control"></a><span data-ttu-id="d1be2-102">Cómo: Determinar cuándo cambian los atributos de formato en el control RichTextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d1be2-102">How to: Determine When Formatting Attributes Change in the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="d1be2-103">Un uso común del <xref:System.Windows.Forms.RichTextBox> control de formularios Windows Forms es dar formato al texto con atributos como opciones de fuente o estilos de párrafo.</span><span class="sxs-lookup"><span data-stu-id="d1be2-103">A common use of the Windows Forms <xref:System.Windows.Forms.RichTextBox> control is formatting text with attributes such as font options or paragraph styles.</span></span> <span data-ttu-id="d1be2-104">Es posible que la aplicación deba realizar un seguimiento de cualquier cambio en el formato del texto con el fin de mostrar una barra de herramientas, como en muchas aplicaciones de procesamiento de texto.</span><span class="sxs-lookup"><span data-stu-id="d1be2-104">Your application may need to keep track of any changes in text formatting for the purpose of displaying a toolbar, as in many word-processing applications.</span></span>  
  
### <a name="to-respond-to-changes-in-formatting-attributes"></a><span data-ttu-id="d1be2-105">Para responder a los cambios en los atributos de formato</span><span class="sxs-lookup"><span data-stu-id="d1be2-105">To respond to changes in formatting attributes</span></span>  
  
1. <span data-ttu-id="d1be2-106">Escriba código <xref:System.Windows.Forms.RichTextBox.SelectionChanged> en el controlador de eventos para realizar una acción adecuada en función del valor del atributo.</span><span class="sxs-lookup"><span data-stu-id="d1be2-106">Write code in the <xref:System.Windows.Forms.RichTextBox.SelectionChanged> event handler to perform an appropriate action depending on the value of the attribute.</span></span> <span data-ttu-id="d1be2-107">En el ejemplo siguiente se cambia la apariencia de <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> un botón de barra de herramientas en función del valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="d1be2-107">The following example changes the appearance of a toolbar button depending on the value of the <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> property.</span></span> <span data-ttu-id="d1be2-108">El botón de la barra de herramientas solo se actualizará cuando se mueva el punto de inserción en el control.</span><span class="sxs-lookup"><span data-stu-id="d1be2-108">The toolbar button will only be updated when the insertion point is moved in the control.</span></span>  
  
     <span data-ttu-id="d1be2-109">En el ejemplo siguiente se <xref:System.Windows.Forms.RichTextBox> supone <xref:System.Windows.Forms.ToolBar> un formulario con un control y un control que contiene un botón de barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="d1be2-109">The example below assumes a form with a <xref:System.Windows.Forms.RichTextBox> control and a <xref:System.Windows.Forms.ToolBar> control that contains a toolbar button.</span></span> <span data-ttu-id="d1be2-110">Para obtener más información acerca de las barras de herramientas y los botones de la barra de herramientas, vea [Cómo: Agregar botones a un control de barra](how-to-add-buttons-to-a-toolbar-control.md)de herramientas .</span><span class="sxs-lookup"><span data-stu-id="d1be2-110">For more information about toolbars and toolbar buttons, see [How to: Add Buttons to a ToolBar Control](how-to-add-buttons-to-a-toolbar-control.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d1be2-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d1be2-111">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox.SelectionChanged>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="d1be2-112">Control RichTextBox</span><span class="sxs-lookup"><span data-stu-id="d1be2-112">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="d1be2-113">Controles que se utilizan en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d1be2-113">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
