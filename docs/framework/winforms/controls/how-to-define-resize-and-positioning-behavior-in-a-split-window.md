---
title: Procedimiento para definir el comportamiento de cambio de tamaño y colocación de una ventana dividida
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- split windows [Windows Forms], resizing
- splitter windows [Windows Forms], resizing
- SplitContainer control [Windows Forms], resizing
ms.assetid: 9bf73f36-ed2d-4a02-b15a-0770eff4fdfa
ms.openlocfilehash: 8cdcfdfaa135a92ed6a6e96d4a72de2c97f2493d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59328678"
---
# <a name="how-to-define-resize-and-positioning-behavior-in-a-split-window"></a><span data-ttu-id="da274-102">Procedimiento para definir el comportamiento de cambio de tamaño y colocación de una ventana dividida</span><span class="sxs-lookup"><span data-stu-id="da274-102">How to: Define Resize and Positioning Behavior in a Split Window</span></span>
<span data-ttu-id="da274-103">Los paneles de la <xref:System.Windows.Forms.SplitContainer> control se prestan bien a la que se va a cambiar el tamaño y manipulados por usuarios.</span><span class="sxs-lookup"><span data-stu-id="da274-103">The panels of the <xref:System.Windows.Forms.SplitContainer> control lend themselves well to being resized and manipulated by users.</span></span> <span data-ttu-id="da274-104">Sin embargo, habrá veces cuando desee controlar mediante programación el divisor, donde se coloca y hasta qué punto se puede mover.</span><span class="sxs-lookup"><span data-stu-id="da274-104">However, there will be times when you will want to programmatically control the splitter—where it is positioned and to what degree it can be moved.</span></span>  
  
 <span data-ttu-id="da274-105">El <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> propiedad y otras propiedades en el <xref:System.Windows.Forms.SplitContainer> control proporcionan un control preciso sobre el comportamiento de la interfaz de usuario para satisfacer sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="da274-105">The <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property and the other properties on the <xref:System.Windows.Forms.SplitContainer> control give you precise control over the behavior of your user interface to suit your needs.</span></span> <span data-ttu-id="da274-106">Estas propiedades se muestran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="da274-106">These properties are listed in the following table.</span></span>  
  
|<span data-ttu-id="da274-107">Name</span><span class="sxs-lookup"><span data-stu-id="da274-107">Name</span></span>|<span data-ttu-id="da274-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="da274-108">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="da274-109">Propiedad <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A></span><span class="sxs-lookup"><span data-stu-id="da274-109"><xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> property</span></span>|<span data-ttu-id="da274-110">Determina si el divisor es móvil mediante el teclado o mouse.</span><span class="sxs-lookup"><span data-stu-id="da274-110">Determines if the splitter is movable by means of the keyboard or mouse.</span></span>|  
|<span data-ttu-id="da274-111">Propiedad <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A></span><span class="sxs-lookup"><span data-stu-id="da274-111"><xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> property</span></span>|<span data-ttu-id="da274-112">Determina la distancia en píxeles desde el borde izquierdo o superior a la barra de división movible.</span><span class="sxs-lookup"><span data-stu-id="da274-112">Determines the distance in pixels from the left or upper edge to the movable splitter bar.</span></span>|  
|<span data-ttu-id="da274-113">Propiedad <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A></span><span class="sxs-lookup"><span data-stu-id="da274-113"><xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property</span></span>|<span data-ttu-id="da274-114">Determina la distancia mínima en píxeles, que el usuario puede mover el divisor.</span><span class="sxs-lookup"><span data-stu-id="da274-114">Determines the minimum distance, in pixels, that the splitter can be moved by the user.</span></span>|  
  
 <span data-ttu-id="da274-115">El ejemplo siguiente se modifica el <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> propiedad para crear un efecto "divisor con ajuste"; cuando el usuario arrastra el separador, incrementa en unidades de 10 píxeles en lugar de con el valor predeterminado 1.</span><span class="sxs-lookup"><span data-stu-id="da274-115">The example below modifies the <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property to create a "snapping splitter" effect; when the user drags the splitter, it increments in units of 10 pixels rather than the default 1.</span></span>  
  
### <a name="to-define-splitcontainer-resize-behavior"></a><span data-ttu-id="da274-116">Para definir el comportamiento de cambio de tamaño de SplitContainer</span><span class="sxs-lookup"><span data-stu-id="da274-116">To define SplitContainer resize behavior</span></span>  
  
1. <span data-ttu-id="da274-117">En un procedimiento, establezca el <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> propiedad tenga el tamaño deseado, por lo que se consigue el comportamiento 'ajuste' del divisor.</span><span class="sxs-lookup"><span data-stu-id="da274-117">In a procedure, set the <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property to the desired size, so that the 'snapping' behavior of the splitter is achieved.</span></span>  
  
     <span data-ttu-id="da274-118">En el ejemplo de código siguiente dentro del formulario <xref:System.Windows.Forms.Form.Load> evento, el divisor dentro del <xref:System.Windows.Forms.SplitContainer> control se establece para saltar 10 píxeles cuando arrastra.</span><span class="sxs-lookup"><span data-stu-id="da274-118">In the following code example, within the form's <xref:System.Windows.Forms.Form.Load> event, the splitter within the <xref:System.Windows.Forms.SplitContainer> control is set to jump 10 pixels when dragged.</span></span>  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, _  
        ByVal e As System.EventArgs) Handles MyBase.Load  
        Dim splitSnapper as new SplitContainer()  
        splitSnapper.SplitterIncrement = 10  
        splitSnapper.Dock = DockStyle.Fill  
        splitSnapper.Parent = me  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_Load(System.Object sender, System.EventArgs e)  
    {  
        SplitContainer splitSnapper = new SplitContainer();  
        splitSnapper.SplitterIncrement = 10;  
        splitSnapper.Dock = DockStyle.Fill;  
        splitSnapper.Parent = this;  
    }  
    ```  
  
     <span data-ttu-id="da274-119">(Visual C#) Coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="da274-119">(Visual C#) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
     <span data-ttu-id="da274-120">Mover el divisor ligeramente a la izquierda o derecha no tendrá ningún efecto apreciable; Sin embargo, cuando el puntero del mouse deja de 10 píxeles en cualquier dirección, el divisor se ajustará a la nueva posición.</span><span class="sxs-lookup"><span data-stu-id="da274-120">Moving the splitter slightly to the left or right will have no discernible effect; however, when the mouse pointer goes 10 pixels in either direction, the splitter will snap to the new position.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da274-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="da274-121">See also</span></span>

- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>
