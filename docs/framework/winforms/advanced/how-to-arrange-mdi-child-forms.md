---
title: Procedimiento para organizar formularios secundarios MDI
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- child forms [Windows Forms], arranging
- MDI [Windows Forms], arranging child forms
ms.assetid: a0786378-3206-4ccc-898e-7d3b38cc5089
ms.openlocfilehash: c7a9d03ef60586e1162f088d662dfe44bbdcb591
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938117"
---
# <a name="how-to-arrange-mdi-child-forms"></a><span data-ttu-id="05e38-102">Procedimiento para organizar formularios secundarios MDI</span><span class="sxs-lookup"><span data-stu-id="05e38-102">How to: Arrange MDI Child Forms</span></span>
<span data-ttu-id="05e38-103">A menudo, las aplicaciones van a tener comandos de menú para acciones (como Mosaico, Cascada y Organizar) que controlan el diseño de los formularios secundarios MDI abiertos.</span><span class="sxs-lookup"><span data-stu-id="05e38-103">Often, applications will have menu commands for actions such as Tile, Cascade, and Arrange, which control the layout of the open MDI child forms.</span></span> <span data-ttu-id="05e38-104">Puede usar el método <xref:System.Windows.Forms.Form.LayoutMdi%2A> con uno de los valores de enumeración de <xref:System.Windows.Forms.MdiLayout> para reorganizar los formularios secundarios en un formulario primario MDI.</span><span class="sxs-lookup"><span data-stu-id="05e38-104">You can use the <xref:System.Windows.Forms.Form.LayoutMdi%2A> method with one of the <xref:System.Windows.Forms.MdiLayout> enumeration values to rearrange the child forms in an MDI parent form.</span></span>  
  
 <span data-ttu-id="05e38-105">Los valores de la enumeración de <xref:System.Windows.Forms.MdiLayout> muestran los formularios secundarios en cascada, en mosaico horizontal o vertical o como iconos de formulario secundario dispuestos a lo largo de la parte inferior del formulario MDI.</span><span class="sxs-lookup"><span data-stu-id="05e38-105">The <xref:System.Windows.Forms.MdiLayout> enumeration values display child forms as cascading, as horizontally or vertically tiled, or as child form icons arranged along the lower portion of the MDI form.</span></span> <span data-ttu-id="05e38-106">Estos valores tienen el mismo efecto que los comandos de Windows **ventanas en cascada**, **mostrar ventanas en paralelo**, **mostrar ventanas apiladas**, y **mostrar el escritorio** , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="05e38-106">These values have the same effect as the Windows commands **Cascade windows**, **Show windows side by side**, **Show windows stacked**, and **Show the desktop**, respectively.</span></span>  
  
 <span data-ttu-id="05e38-107">Con frecuencia, estos métodos se usan como los controladores de eventos a los que llama el evento <xref:System.Windows.Forms.Control.Click> de un elemento de menú.</span><span class="sxs-lookup"><span data-stu-id="05e38-107">Often, these methods are used as the event handlers called by a menu item's <xref:System.Windows.Forms.Control.Click> event.</span></span> <span data-ttu-id="05e38-108">De este modo, un elemento de menú con el texto "Ventanas en cascada" puede tener el efecto deseado en las ventanas secundarias de MDI.</span><span class="sxs-lookup"><span data-stu-id="05e38-108">In this way, a menu item with the text "Cascade Windows" can have the desired effect on the MDI child windows.</span></span>  
  
### <a name="to-arrange-child-forms"></a><span data-ttu-id="05e38-109">Para organizar los formularios secundarios</span><span class="sxs-lookup"><span data-stu-id="05e38-109">To arrange child forms</span></span>  
  
1. <span data-ttu-id="05e38-110">En un método, use el método <xref:System.Windows.Forms.Form.LayoutMdi%2A> para establecer la enumeración <xref:System.Windows.Forms.MdiLayout> para el formulario primario MDI.</span><span class="sxs-lookup"><span data-stu-id="05e38-110">In a method, use the <xref:System.Windows.Forms.Form.LayoutMdi%2A> method to set the <xref:System.Windows.Forms.MdiLayout> enumeration for the MDI parent form.</span></span> <span data-ttu-id="05e38-111">En el siguiente ejemplo se usa el valor de enumeración de <xref:System.Windows.Forms.MdiLayout.Cascade?displayProperty=nameWithType> para las ventanas secundarias del formulario primario MDI (`Form1`).</span><span class="sxs-lookup"><span data-stu-id="05e38-111">The following example uses the <xref:System.Windows.Forms.MdiLayout.Cascade?displayProperty=nameWithType> enumeration value for the child windows of the MDI parent form (`Form1`).</span></span> <span data-ttu-id="05e38-112">La enumeración se utiliza en el código durante el controlador de eventos para el <xref:System.Windows.Forms.Control.Click> eventos de la **Cascade Windows** elemento de menú.</span><span class="sxs-lookup"><span data-stu-id="05e38-112">The enumeration is used in code during the event handler for the <xref:System.Windows.Forms.Control.Click> event of the **Cascade Windows** menu item.</span></span>  
  
    ```vb  
    Protected Sub CascadeWindows_Click(ByVal sender As System.Object, ByVal e As System.EventArgs)  
       Me.LayoutMdi(System.Windows.Forms.MdiLayout.Cascade)  
    End Sub  
    ```  
  
    ```csharp  
    protected void CascadeWindows_Click(object sender, System.EventArgs e){  
       this.LayoutMdi(System.Windows.Forms.MdiLayout.Cascade);  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="05e38-113">Las ventanas también se pueden colocar en mosaico u organizarse como iconos si se cambia el valor de enumeración de <xref:System.Windows.Forms.MdiLayout> utilizado.</span><span class="sxs-lookup"><span data-stu-id="05e38-113">You can also tile windows and arranging windows as icons by changing the <xref:System.Windows.Forms.MdiLayout> enumeration value used.</span></span>  
  
2. <span data-ttu-id="05e38-114">Si usa Visual C#, incluya el siguiente código en el constructor del formulario para registrar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="05e38-114">If you’re using Visual C#, place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="05e38-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="05e38-115">See also</span></span>

- [<span data-ttu-id="05e38-116">Aplicaciones de interfaz de múltiples documentos (MDI)</span><span class="sxs-lookup"><span data-stu-id="05e38-116">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="05e38-117">Cómo: Crear formularios principales MDI</span><span class="sxs-lookup"><span data-stu-id="05e38-117">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="05e38-118">Cómo: Crear formularios MDI secundarios</span><span class="sxs-lookup"><span data-stu-id="05e38-118">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="05e38-119">Cómo: Determinar el formulario secundario MDI activo</span><span class="sxs-lookup"><span data-stu-id="05e38-119">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)
- [<span data-ttu-id="05e38-120">Cómo: Enviar datos al formulario secundario MDI activo</span><span class="sxs-lookup"><span data-stu-id="05e38-120">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)
