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
ms.openlocfilehash: df66991289373a05fc7c27b7768a96643e3bbae0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142135"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-linklabel-control"></a>Cómo: Cambiar la apariencia del control LinkLabel de formularios Windows Forms
Puede cambiar el texto mostrado <xref:System.Windows.Forms.LinkLabel> por el control para adaptarse a una variedad de propósitos. Por ejemplo, es una práctica común indicar al usuario que se puede hacer clic en el texto estableciendo el texto para que aparezca en un color específico con un subrayado. Después de que el usuario hace clic en el texto, el color cambia a un color diferente. Para controlar este comportamiento, puede establecer <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>cinco <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>propiedades <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>diferentes: las propiedades , , , , y <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> .  
  
### <a name="to-change-the-appearance-of-a-linklabel-control"></a>Para cambiar la apariencia de un linkLabel control  
  
1. Establezca <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> las <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> propiedades y las propiedades que desee.  
  
     Esto se puede hacer mediante programación o en tiempo de diseño en la ventana **Propiedades.**  
  
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
  
2. Establezca <xref:System.Windows.Forms.LinkLabel.Text%2A> la propiedad en un título adecuado.  
  
     Esto se puede hacer mediante programación o en tiempo de diseño en la ventana **Propiedades.**  
  
    ```vb  
    LinkLabel1.Text = "Click here to see more."  
    ```  
  
    ```csharp  
    linkLabel1.Text = "Click here to see more.";  
    ```  
  
    ```cpp  
    linkLabel1->Text = "Click here to see more.";  
    ```  
  
3. Establezca <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> la propiedad para determinar qué parte del título se indicará como un vínculo.  
  
     El <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> valor se representa <xref:System.Windows.Forms.LinkArea> con un contenedor de dos números, la posición del carácter inicial y el número de caracteres. Esto se puede hacer mediante programación o en tiempo de diseño en la ventana **Propiedades.**  
  
    ```vb  
    LinkLabel1.LinkArea = new LinkArea(6,4)  
    ```  
  
    ```csharp  
    linkLabel1.LinkArea = new LinkArea(6,4);  
    ```  
  
    ```cpp  
    linkLabel1->LinkArea = LinkArea(6,4);  
    ```  
  
4. Establezca <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> la <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>propiedad <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>en <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>, , o .  
  
     Si se establece <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>en , la parte <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> del título determinada por solo se subrayará cuando el puntero se apoye en él.  
  
5. En <xref:System.Windows.Forms.LinkLabel.LinkClicked> el controlador de <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> eventos, establezca la propiedad en `true`.  
  
     Cuando se ha visitado un enlace, es una práctica común cambiar su apariencia de alguna manera, generalmente por color. El texto cambiará al color especificado <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> por la propiedad.  
  
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
- [Cómo: Establecer vínculos con un objeto o página Web mediante el control LinkLabel de formularios Windows Forms](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [Control LinkLabel](linklabel-control-windows-forms.md)
