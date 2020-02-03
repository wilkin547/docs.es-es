---
title: Cambiar la apariencia del control LinkLabel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- LinkLabel properties
- LinkLabel control [Windows Forms], changing appearance of links
- links [Windows Forms], changing appearance
- examples [Windows Forms], LinkLabel control
- LinkLabel control [Windows Forms], examples
ms.assetid: fdc5854f-5162-4457-8cbe-1042feb2d132
ms.openlocfilehash: 0b38722fb1647ea215c3bb8978dd3f54b300a0e0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746621"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-linklabel-control"></a>Cómo: Cambiar la apariencia del control LinkLabel de formularios Windows Forms
Puede cambiar el texto mostrado por el control de <xref:System.Windows.Forms.LinkLabel> para que se ajuste a una variedad de propósitos. Por ejemplo, es una práctica común indicar al usuario que se puede hacer clic en el texto estableciendo el texto para que aparezca en un color específico con un subrayado. Una vez que el usuario hace clic en el texto, el color cambia a un color diferente. Para controlar este comportamiento, puede establecer cinco propiedades diferentes: las propiedades <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>y <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>.  
  
### <a name="to-change-the-appearance-of-a-linklabel-control"></a>Para cambiar la apariencia de un control LinkLabel  
  
1. Establezca las propiedades <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> y <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> en los colores que desee.  
  
     Esto puede hacerse mediante programación o en tiempo de diseño, en la ventana **propiedades** .  
  
    ```vb  
    ' You can set the color using decimal values for red, green, and blue  
    LinkLabel1.LinkColor = Color.FromArgb(0, 0, 255)  
    ' Or you can set the color using defined constants  
    LinkLabel1.VisitedLinkColor = Color.Purple  
    ```  
  
    ```csharp  
    // You can set the color using decimal values for red, green, and blue  
    linkLabel1.LinkColor = Color.FromArgb(0, 0, 255);  
    // Or you can set the color using defined constants  
    linkLabel1.VisitedLinkColor = Color.Purple;  
    ```  
  
    ```cpp  
    // You can set the color using decimal values for red, green, and blue  
    linkLabel1->LinkColor = Color::FromArgb(0, 0, 255);  
    // Or you can set the color using defined constants  
    linkLabel1->VisitedLinkColor = Color::Purple;  
    ```  
  
2. Establezca la propiedad <xref:System.Windows.Forms.LinkLabel.Text%2A> en un título adecuado.  
  
     Esto puede hacerse mediante programación o en tiempo de diseño, en la ventana **propiedades** .  
  
    ```vb  
    LinkLabel1.Text = "Click here to see more."  
    ```  
  
    ```csharp  
    linkLabel1.Text = "Click here to see more.";  
    ```  
  
    ```cpp  
    linkLabel1->Text = "Click here to see more.";  
    ```  
  
3. Establezca la propiedad <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> para determinar qué parte del título se indicará como un vínculo.  
  
     El valor <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> se representa con un <xref:System.Windows.Forms.LinkArea> que contiene dos números, la posición del carácter inicial y el número de caracteres. Esto puede hacerse mediante programación o en tiempo de diseño, en la ventana **propiedades** .  
  
    ```vb  
    LinkLabel1.LinkArea = new LinkArea(6,4)  
    ```  
  
    ```csharp  
    linkLabel1.LinkArea = new LinkArea(6,4);  
    ```  
  
    ```cpp  
    linkLabel1->LinkArea = LinkArea(6,4);  
    ```  
  
4. Establezca la propiedad <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> en <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>, <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>o <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>.  
  
     Si se establece en <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, la parte del título determinada por <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> solo se subrayará cuando el puntero se sitúe sobre ella.  
  
5. En el controlador de eventos <xref:System.Windows.Forms.LinkLabel.LinkClicked>, establezca la propiedad <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> en `true`.  
  
     Cuando se ha visitado un vínculo, es una práctica común cambiar su apariencia de alguna manera, normalmente por color. El texto cambiará al color especificado por la propiedad <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>.  
  
    ```vb  
    Protected Sub LinkLabel1_LinkClicked (ByVal sender As Object, _  
       ByVal e As EventArgs) Handles LinkLabel1.LinkClicked  
       ' Change the color of the link text  
       ' by setting LinkVisited to True.  
       LinkLabel1.LinkVisited = True  
       ' Then do whatever other action is appropriate  
    End Sub  
    ```  
  
    ```csharp  
    protected void LinkLabel1_LinkClicked(object sender, System.EventArgs e)  
    {  
       // Change the color of the link text by setting LinkVisited   
       // to True.  
       linkLabel1.LinkVisited = true;  
       // Then do whatever other action is appropriate  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void linkLabel1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)  
       {  
          // Change the color of the link text by setting LinkVisited   
          // to True.  
          linkLabel1->LinkVisited = true;  
          // Then do whatever other action is appropriate  
       }  
    ```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>
- [Información general sobre el control LinkLabel](linklabel-control-overview-windows-forms.md)
- [Establecer vínculos con un objeto o página Web mediante el control LinkLabel de formularios Windows Forms](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [LinkLabel (control)](linklabel-control-windows-forms.md)
