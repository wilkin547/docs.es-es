---
title: Filtrar para cambiar el aspecto del control LinkLabel de formularios Windows Forms
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
ms.openlocfilehash: be2f6e8e10d9f9b23b4f57fa696f1fb88c4726c0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59105032"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-linklabel-control"></a><span data-ttu-id="f68aa-102">Filtrar para cambiar el aspecto del control LinkLabel de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f68aa-102">How to: Change the Appearance of the Windows Forms LinkLabel Control</span></span>
<span data-ttu-id="f68aa-103">Puede cambiar el texto mostrado por el <xref:System.Windows.Forms.LinkLabel> control para adaptarse a una variedad de propósitos.</span><span class="sxs-lookup"><span data-stu-id="f68aa-103">You can change the text displayed by the <xref:System.Windows.Forms.LinkLabel> control to suit a variety of purposes.</span></span> <span data-ttu-id="f68aa-104">Por ejemplo, es una práctica común para indicar al usuario que se puede hacer clic en texto estableciendo el texto que aparezca en un color específico con un carácter de subrayado.</span><span class="sxs-lookup"><span data-stu-id="f68aa-104">For example, it is common practice to indicate to the user that text can be clicked by setting the text to appear in a specific color with an underline.</span></span> <span data-ttu-id="f68aa-105">Después de que el usuario hace clic en el texto, el color cambia a un color diferente.</span><span class="sxs-lookup"><span data-stu-id="f68aa-105">After the user clicks the text, the color changes to a different color.</span></span> <span data-ttu-id="f68aa-106">Para controlar este comportamiento, puede establecer cinco propiedades diferentes: el <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, y <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> propiedades.</span><span class="sxs-lookup"><span data-stu-id="f68aa-106">To control this behavior, you can set five different properties: the <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, and <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> properties.</span></span>  
  
### <a name="to-change-the-appearance-of-a-linklabel-control"></a><span data-ttu-id="f68aa-107">Para cambiar la apariencia de un control LinkLabel</span><span class="sxs-lookup"><span data-stu-id="f68aa-107">To change the appearance of a LinkLabel control</span></span>  
  
1.  <span data-ttu-id="f68aa-108">Establecer el <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> y <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> propiedades a los colores que desee.</span><span class="sxs-lookup"><span data-stu-id="f68aa-108">Set the <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> and <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> properties to the colors you want.</span></span>  
  
     <span data-ttu-id="f68aa-109">Esto puede hacerse ya sea mediante programación o en tiempo de diseño en el **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="f68aa-109">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
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
  
2.  <span data-ttu-id="f68aa-110">Establecer el <xref:System.Windows.Forms.LinkLabel.Text%2A> propiedad título apropiado.</span><span class="sxs-lookup"><span data-stu-id="f68aa-110">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>  
  
     <span data-ttu-id="f68aa-111">Esto puede hacerse ya sea mediante programación o en tiempo de diseño en el **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="f68aa-111">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    LinkLabel1.Text = "Click here to see more."  
    ```  
  
    ```csharp  
    linkLabel1.Text = "Click here to see more.";  
    ```  
  
    ```cpp  
    linkLabel1->Text = "Click here to see more.";  
    ```  
  
3.  <span data-ttu-id="f68aa-112">Establecer el <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> propiedad para determinar qué parte de la leyenda se indicará como un vínculo.</span><span class="sxs-lookup"><span data-stu-id="f68aa-112">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span>  
  
     <span data-ttu-id="f68aa-113">El <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> valor está representado con un <xref:System.Windows.Forms.LinkArea> que contiene dos números, la posición del carácter inicial y el número de caracteres.</span><span class="sxs-lookup"><span data-stu-id="f68aa-113">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> value is represented with a <xref:System.Windows.Forms.LinkArea> containing two numbers, the starting character position and the number of characters.</span></span> <span data-ttu-id="f68aa-114">Esto puede hacerse ya sea mediante programación o en tiempo de diseño en el **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="f68aa-114">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    LinkLabel1.LinkArea = new LinkArea(6,4)  
    ```  
  
    ```csharp  
    linkLabel1.LinkArea = new LinkArea(6,4);  
    ```  
  
    ```cpp  
    linkLabel1->LinkArea = LinkArea(6,4);  
    ```  
  
4.  <span data-ttu-id="f68aa-115">Establecer el <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> propiedad <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>, <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, o <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>.</span><span class="sxs-lookup"><span data-stu-id="f68aa-115">Set the <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> property to <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>, <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, or <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>.</span></span>  
  
     <span data-ttu-id="f68aa-116">Si se establece en <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, la parte del título determinado por <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> sólo se subrayan cuando sitúe el puntero sobre él.</span><span class="sxs-lookup"><span data-stu-id="f68aa-116">If it is set to <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, the part of the caption determined by <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> will only be underlined when the pointer rests on it.</span></span>  
  
5.  <span data-ttu-id="f68aa-117">En el <xref:System.Windows.Forms.LinkLabel.LinkClicked> controlador de eventos, establezca la <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="f68aa-117">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, set the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="f68aa-118">Cuando se ha visitado un vínculo, es una práctica común para cambiar su apariencia de alguna manera, normalmente por color.</span><span class="sxs-lookup"><span data-stu-id="f68aa-118">When a link has been visited, it is common practice to change its appearance in some way, usually by color.</span></span> <span data-ttu-id="f68aa-119">El texto cambiará al color especificado por el <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="f68aa-119">The text will change to the color specified by the <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> property.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f68aa-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="f68aa-120">See also</span></span>

- <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>
- [<span data-ttu-id="f68aa-121">Información general sobre el control LinkLabel</span><span class="sxs-lookup"><span data-stu-id="f68aa-121">LinkLabel Control Overview</span></span>](linklabel-control-overview-windows-forms.md)
- [<span data-ttu-id="f68aa-122">Filtrar para establecer vínculos con un objeto o página web mediante el control LinkLabel de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f68aa-122">How to: Link to an Object or Web Page with the Windows Forms LinkLabel Control</span></span>](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [<span data-ttu-id="f68aa-123">Control LinkLabel</span><span class="sxs-lookup"><span data-stu-id="f68aa-123">LinkLabel Control</span></span>](linklabel-control-windows-forms.md)
