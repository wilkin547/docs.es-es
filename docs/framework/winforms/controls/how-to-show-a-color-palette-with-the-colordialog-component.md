---
title: Procedimiento Mostrar una paleta de colores con el componente ColorDialog
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- palettes [Windows Forms], showing color
- color dialog box [Windows Forms], showing color palettes
- colors [Windows Forms], allowing users to select
- color palettes [Windows Forms], dialog box
- ColorDialog component [Windows Forms], showing color palettes
- color palettes [Windows Forms], showing in ColorDialog component
- colors [Windows Forms], showing palettes
ms.assetid: ee050f61-dbc8-4436-ba22-51360981ab48
ms.openlocfilehash: 35f6f81c2b13234b23b3b2295e45caf5f16abd9e
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708332"
---
# <a name="how-to-show-a-color-palette-with-the-colordialog-component"></a><span data-ttu-id="f56a2-102">Filtrar Mostrar una paleta de colores con el componente ColorDialog</span><span class="sxs-lookup"><span data-stu-id="f56a2-102">How to: Show a Color Palette with the ColorDialog Component</span></span>
<span data-ttu-id="f56a2-103">El [ColorDialog](colordialog-component-windows-forms.md) componente muestra una paleta de colores y devuelve una propiedad que contiene el color seleccionado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="f56a2-103">The [ColorDialog](colordialog-component-windows-forms.md) component displays a palette of colors and returns a property containing the color the user has selected.</span></span>  
  
### <a name="to-choose-a-color-using-the-colordialog-component"></a><span data-ttu-id="f56a2-104">Para elegir un color mediante el componente ColorDialog</span><span class="sxs-lookup"><span data-stu-id="f56a2-104">To choose a color using the ColorDialog component</span></span>  
  
1.  <span data-ttu-id="f56a2-105">Mostrar el cuadro de diálogo mediante la <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> método.</span><span class="sxs-lookup"><span data-stu-id="f56a2-105">Display the dialog box using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
2.  <span data-ttu-id="f56a2-106">Use el <xref:System.Windows.Forms.DialogResult> propiedad para determinar cómo se cerró el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f56a2-106">Use the <xref:System.Windows.Forms.DialogResult> property to determine how the dialog box was closed.</span></span>  
  
3.  <span data-ttu-id="f56a2-107">Use la <xref:System.Windows.Forms.ColorDialog.Color%2A> propiedad de la <xref:System.Windows.Forms.ColorDialog> componente para establecer el color elegido.</span><span class="sxs-lookup"><span data-stu-id="f56a2-107">Use the <xref:System.Windows.Forms.ColorDialog.Color%2A> property of the <xref:System.Windows.Forms.ColorDialog> component to set the chosen color.</span></span>  
  
     <span data-ttu-id="f56a2-108">En el ejemplo siguiente, la <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.Control.Click> controlador de eventos abre un <xref:System.Windows.Forms.ColorDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="f56a2-108">In the example below, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens a <xref:System.Windows.Forms.ColorDialog> component.</span></span> <span data-ttu-id="f56a2-109">Cuando se es un color elegido y el usuario hace clic en **Aceptar**, <xref:System.Windows.Forms.Button> color de fondo del control se establece en el color elegido.</span><span class="sxs-lookup"><span data-stu-id="f56a2-109">When a color is chosen and the user clicks **OK**, the <xref:System.Windows.Forms.Button> control's background color is set to the chosen color.</span></span> <span data-ttu-id="f56a2-110">En el ejemplo se da por supuesto que el formulario tiene un <xref:System.Windows.Forms.Button> control y un <xref:System.Windows.Forms.ColorDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="f56a2-110">The example assumes your form has a <xref:System.Windows.Forms.Button> control and a <xref:System.Windows.Forms.ColorDialog> component.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles Button1.Click  
       If ColorDialog1.ShowDialog() = DialogResult.OK Then  
          Button1.BackColor = ColorDialog1.Color  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(colorDialog1.ShowDialog() == DialogResult.OK)  
       {  
          button1.BackColor = colorDialog1.Color;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,   
          System::EventArgs ^ e)  
       {  
          if(colorDialog1->ShowDialog() == DialogResult::OK)  
          {  
             button1->BackColor = colorDialog1->Color;  
          }  
       }  
    ```  
  
     <span data-ttu-id="f56a2-111">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="f56a2-111">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=   
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f56a2-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="f56a2-112">See also</span></span>
- <xref:System.Windows.Forms.ColorDialog>
- [<span data-ttu-id="f56a2-113">ColorDialog (componente)</span><span class="sxs-lookup"><span data-stu-id="f56a2-113">ColorDialog Component</span></span>](colordialog-component-windows-forms.md)
