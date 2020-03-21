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
# <a name="how-to-change-the-appearance-of-the-windows-forms-linklabel-control"></a><span data-ttu-id="ae281-102">Cómo: Cambiar la apariencia del control LinkLabel de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ae281-102">How to: Change the Appearance of the Windows Forms LinkLabel Control</span></span>
<span data-ttu-id="ae281-103">Puede cambiar el texto mostrado <xref:System.Windows.Forms.LinkLabel> por el control para adaptarse a una variedad de propósitos.</span><span class="sxs-lookup"><span data-stu-id="ae281-103">You can change the text displayed by the <xref:System.Windows.Forms.LinkLabel> control to suit a variety of purposes.</span></span> <span data-ttu-id="ae281-104">Por ejemplo, es una práctica común indicar al usuario que se puede hacer clic en el texto estableciendo el texto para que aparezca en un color específico con un subrayado.</span><span class="sxs-lookup"><span data-stu-id="ae281-104">For example, it is common practice to indicate to the user that text can be clicked by setting the text to appear in a specific color with an underline.</span></span> <span data-ttu-id="ae281-105">Después de que el usuario hace clic en el texto, el color cambia a un color diferente.</span><span class="sxs-lookup"><span data-stu-id="ae281-105">After the user clicks the text, the color changes to a different color.</span></span> <span data-ttu-id="ae281-106">Para controlar este comportamiento, puede establecer <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>cinco <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>propiedades <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>diferentes: las propiedades , , , , y <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> .</span><span class="sxs-lookup"><span data-stu-id="ae281-106">To control this behavior, you can set five different properties: the <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, and <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> properties.</span></span>  
  
### <a name="to-change-the-appearance-of-a-linklabel-control"></a><span data-ttu-id="ae281-107">Para cambiar la apariencia de un linkLabel control</span><span class="sxs-lookup"><span data-stu-id="ae281-107">To change the appearance of a LinkLabel control</span></span>  
  
1. <span data-ttu-id="ae281-108">Establezca <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> las <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> propiedades y las propiedades que desee.</span><span class="sxs-lookup"><span data-stu-id="ae281-108">Set the <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> and <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> properties to the colors you want.</span></span>  
  
     <span data-ttu-id="ae281-109">Esto se puede hacer mediante programación o en tiempo de diseño en la ventana **Propiedades.**</span><span class="sxs-lookup"><span data-stu-id="ae281-109">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
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
  
2. <span data-ttu-id="ae281-110">Establezca <xref:System.Windows.Forms.LinkLabel.Text%2A> la propiedad en un título adecuado.</span><span class="sxs-lookup"><span data-stu-id="ae281-110">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>  
  
     <span data-ttu-id="ae281-111">Esto se puede hacer mediante programación o en tiempo de diseño en la ventana **Propiedades.**</span><span class="sxs-lookup"><span data-stu-id="ae281-111">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    LinkLabel1.Text = "Click here to see more."  
    ```  
  
    ```csharp  
    linkLabel1.Text = "Click here to see more.";  
    ```  
  
    ```cpp  
    linkLabel1->Text = "Click here to see more.";  
    ```  
  
3. <span data-ttu-id="ae281-112">Establezca <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> la propiedad para determinar qué parte del título se indicará como un vínculo.</span><span class="sxs-lookup"><span data-stu-id="ae281-112">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span>  
  
     <span data-ttu-id="ae281-113">El <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> valor se representa <xref:System.Windows.Forms.LinkArea> con un contenedor de dos números, la posición del carácter inicial y el número de caracteres.</span><span class="sxs-lookup"><span data-stu-id="ae281-113">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> value is represented with a <xref:System.Windows.Forms.LinkArea> containing two numbers, the starting character position and the number of characters.</span></span> <span data-ttu-id="ae281-114">Esto se puede hacer mediante programación o en tiempo de diseño en la ventana **Propiedades.**</span><span class="sxs-lookup"><span data-stu-id="ae281-114">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    LinkLabel1.LinkArea = new LinkArea(6,4)  
    ```  
  
    ```csharp  
    linkLabel1.LinkArea = new LinkArea(6,4);  
    ```  
  
    ```cpp  
    linkLabel1->LinkArea = LinkArea(6,4);  
    ```  
  
4. <span data-ttu-id="ae281-115">Establezca <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> la <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>propiedad <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>en <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>, , o .</span><span class="sxs-lookup"><span data-stu-id="ae281-115">Set the <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> property to <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>, <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, or <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>.</span></span>  
  
     <span data-ttu-id="ae281-116">Si se establece <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>en , la parte <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> del título determinada por solo se subrayará cuando el puntero se apoye en él.</span><span class="sxs-lookup"><span data-stu-id="ae281-116">If it is set to <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, the part of the caption determined by <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> will only be underlined when the pointer rests on it.</span></span>  
  
5. <span data-ttu-id="ae281-117">En <xref:System.Windows.Forms.LinkLabel.LinkClicked> el controlador de <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> eventos, establezca la propiedad en `true`.</span><span class="sxs-lookup"><span data-stu-id="ae281-117">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, set the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="ae281-118">Cuando se ha visitado un enlace, es una práctica común cambiar su apariencia de alguna manera, generalmente por color.</span><span class="sxs-lookup"><span data-stu-id="ae281-118">When a link has been visited, it is common practice to change its appearance in some way, usually by color.</span></span> <span data-ttu-id="ae281-119">El texto cambiará al color especificado <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> por la propiedad.</span><span class="sxs-lookup"><span data-stu-id="ae281-119">The text will change to the color specified by the <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> property.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ae281-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ae281-120">See also</span></span>

- <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>
- [<span data-ttu-id="ae281-121">Información general sobre el control LinkLabel</span><span class="sxs-lookup"><span data-stu-id="ae281-121">LinkLabel Control Overview</span></span>](linklabel-control-overview-windows-forms.md)
- [<span data-ttu-id="ae281-122">Cómo: Establecer vínculos con un objeto o página Web mediante el control LinkLabel de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ae281-122">How to: Link to an Object or Web Page with the Windows Forms LinkLabel Control</span></span>](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [<span data-ttu-id="ae281-123">Control LinkLabel</span><span class="sxs-lookup"><span data-stu-id="ae281-123">LinkLabel Control</span></span>](linklabel-control-windows-forms.md)
