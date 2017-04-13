---
title: "C&#243;mo: Cambiar la apariencia del control LinkLabel de formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ejemplos [Windows Forms], LinkLabel (control)"
  - "LinkLabel (control) [Windows Forms], cambiar la apariencia de vínculos"
  - "LinkLabel (control) [Windows Forms], ejemplos"
  - "LinkLabel (propiedades)"
  - "vínculos, cambiar apariencia"
ms.assetid: fdc5854f-5162-4457-8cbe-1042feb2d132
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Cambiar la apariencia del control LinkLabel de formularios Windows Forms
Se puede cambiar el texto que muestra el control <xref:System.Windows.Forms.LinkLabel> para adaptarlo a distintos propósitos.  Por ejemplo, es habitual indicar al usuario que puede hacer clic en un texto mediante la asignación de un color específico con un subrayado.  Después de que el usuario haga clic en el texto, el color cambia a un color diferente.  Para controlar este comportamiento, se pueden establecer cinco propiedades diferentes: las propiedades <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> y <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>.  
  
### Para cambiar la apariencia de un control LinkLabel  
  
1.  Establezca las propiedades <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> y <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> en los colores que desea.  
  
     Esto puede hacerse mediante programación o en tiempo de diseño, en la ventana **Propiedades**.  
  
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
  
2.  Establezca la leyenda adecuada en la propiedad <xref:System.Windows.Forms.LinkLabel.Text%2A>.  
  
     Esto puede hacerse mediante programación o en tiempo de diseño, en la ventana **Propiedades**.  
  
    ```vb  
    LinkLabel1.Text = "Click here to see more."  
  
    ```  
  
    ```csharp  
    linkLabel1.Text = "Click here to see more.";  
  
    ```  
  
    ```cpp  
    linkLabel1->Text = "Click here to see more.";  
    ```  
  
3.  Establezca la propiedad <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> para determinar qué parte de la leyenda se indicará como vínculo.  
  
     El valor de <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> se representa con un objeto <xref:System.Windows.Forms.LinkArea> que contiene dos números: la posición del carácter inicial y el número de caracteres.  Esto puede hacerse mediante programación o en tiempo de diseño, en la ventana **Propiedades**.  
  
    ```vb  
    LinkLabel1.LinkArea = new LinkArea(6,4)  
  
    ```  
  
    ```csharp  
    linkLabel1.LinkArea = new LinkArea(6,4);  
  
    ```  
  
    ```cpp  
    linkLabel1->LinkArea = LinkArea(6,4);  
    ```  
  
4.  Establezca la propiedad <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> en <xref:System.Windows.Forms.LinkBehavior>, <xref:System.Windows.Forms.LinkBehavior> o <xref:System.Windows.Forms.LinkBehavior>.  
  
     Si se establece en <xref:System.Windows.Forms.LinkBehavior>, la parte de la leyenda determinada por <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> sólo aparecerá subrayada cuando el puntero esté sobre ella.  
  
5.  En el controlador de eventos <xref:System.Windows.Forms.LinkLabel.LinkClicked>, establezca la propiedad <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> en `true`.  
  
     Cuando se ha visitado un vínculo, lo habitual es cambiar su aspecto de alguna manera, normalmente cambiando su color.  El texto cambiará al color especificado por la propiedad <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>.  
  
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
  
## Vea también  
 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>   
 <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>   
 <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>   
 <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>   
 [Información general sobre el control LinkLabel](../../../../docs/framework/winforms/controls/linklabel-control-overview-windows-forms.md)   
 [Cómo: Establecer vínculos con un objeto o página Web mediante el control LinkLabel de formularios Windows Forms](../../../../docs/framework/winforms/controls/link-to-an-object-or-web-page-with-wf-linklabel-control.md)   
 [LinkLabel \(Control\)](../../../../docs/framework/winforms/controls/linklabel-control-windows-forms.md)