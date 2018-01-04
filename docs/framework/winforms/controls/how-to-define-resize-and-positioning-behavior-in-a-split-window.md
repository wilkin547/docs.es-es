---
title: "Cómo: Definir el comportamiento de cambio de tamaño y colocación de una ventana dividida"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- split windows [Windows Forms], resizing
- splitter windows [Windows Forms], resizing
- SplitContainer control [Windows Forms], resizing
ms.assetid: 9bf73f36-ed2d-4a02-b15a-0770eff4fdfa
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ed78a49119c87c52a07cc2ade030e66087d3f420
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-resize-and-positioning-behavior-in-a-split-window"></a><span data-ttu-id="a7bba-102">Cómo: Definir el comportamiento de cambio de tamaño y colocación de una ventana dividida</span><span class="sxs-lookup"><span data-stu-id="a7bba-102">How to: Define Resize and Positioning Behavior in a Split Window</span></span>
<span data-ttu-id="a7bba-103">Los paneles de la <xref:System.Windows.Forms.SplitContainer> control prestan apropiado para la que se va a cambiar de tamaño y manipulados por los usuarios.</span><span class="sxs-lookup"><span data-stu-id="a7bba-103">The panels of the <xref:System.Windows.Forms.SplitContainer> control lend themselves well to being resized and manipulated by users.</span></span> <span data-ttu-id="a7bba-104">Sin embargo, habrá veces cuando desea controlar mediante programación el divisor, donde se coloca y hasta qué punto se puede mover.</span><span class="sxs-lookup"><span data-stu-id="a7bba-104">However, there will be times when you will want to programmatically control the splitter—where it is positioned and to what degree it can be moved.</span></span>  
  
 <span data-ttu-id="a7bba-105">El <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> propiedad y las demás propiedades en el <xref:System.Windows.Forms.SplitContainer> control ofrecen un control preciso sobre el comportamiento de la interfaz de usuario para satisfacer sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="a7bba-105">The <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property and the other properties on the <xref:System.Windows.Forms.SplitContainer> control give you precise control over the behavior of your user interface to suit your needs.</span></span> <span data-ttu-id="a7bba-106">Estas propiedades se muestran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="a7bba-106">These properties are listed in the following table.</span></span>  
  
|<span data-ttu-id="a7bba-107">nombre</span><span class="sxs-lookup"><span data-stu-id="a7bba-107">Name</span></span>|<span data-ttu-id="a7bba-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="a7bba-108">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="a7bba-109">Propiedad <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A></span><span class="sxs-lookup"><span data-stu-id="a7bba-109"><xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> property</span></span>|<span data-ttu-id="a7bba-110">Determina si el divisor se puede mover mediante el teclado o mouse (ratón).</span><span class="sxs-lookup"><span data-stu-id="a7bba-110">Determines if the splitter is movable by means of the keyboard or mouse.</span></span>|  
|<span data-ttu-id="a7bba-111">Propiedad <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A></span><span class="sxs-lookup"><span data-stu-id="a7bba-111"><xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> property</span></span>|<span data-ttu-id="a7bba-112">Determina la distancia en píxeles desde el borde izquierdo o superior de la barra de división puede mover.</span><span class="sxs-lookup"><span data-stu-id="a7bba-112">Determines the distance in pixels from the left or upper edge to the movable splitter bar.</span></span>|  
|<span data-ttu-id="a7bba-113">Propiedad <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A></span><span class="sxs-lookup"><span data-stu-id="a7bba-113"><xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property</span></span>|<span data-ttu-id="a7bba-114">Determina la distancia mínima, en píxeles, que se puede mover el divisor por el usuario.</span><span class="sxs-lookup"><span data-stu-id="a7bba-114">Determines the minimum distance, in pixels, that the splitter can be moved by the user.</span></span>|  
  
 <span data-ttu-id="a7bba-115">El ejemplo siguiente se modifica el <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> propiedad que se va a crear un efecto de "divisor con ajuste"; cuando el usuario arrastra el divisor, avanza en bloques de 10 píxeles en lugar de con el valor predeterminado 1.</span><span class="sxs-lookup"><span data-stu-id="a7bba-115">The example below modifies the <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property to create a "snapping splitter" effect; when the user drags the splitter, it increments in units of 10 pixels rather than the default 1.</span></span>  
  
### <a name="to-define-splitcontainer-resize-behavior"></a><span data-ttu-id="a7bba-116">Para definir el comportamiento de cambio de tamaño de SplitContainer</span><span class="sxs-lookup"><span data-stu-id="a7bba-116">To define SplitContainer resize behavior</span></span>  
  
1.  <span data-ttu-id="a7bba-117">En un procedimiento, establezca la <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> propiedad tenga el tamaño deseado, por lo que se consigue el comportamiento de 'ajuste' del divisor.</span><span class="sxs-lookup"><span data-stu-id="a7bba-117">In a procedure, set the <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property to the desired size, so that the 'snapping' behavior of the splitter is achieved.</span></span>  
  
     <span data-ttu-id="a7bba-118">En el ejemplo de código siguiente dentro del formulario <xref:System.Windows.Forms.Form.Load> evento, el divisor dentro del <xref:System.Windows.Forms.SplitContainer> control se establece en 10 píxeles cuando arrastra de salto.</span><span class="sxs-lookup"><span data-stu-id="a7bba-118">In the following code example, within the form's <xref:System.Windows.Forms.Form.Load> event, the splitter within the <xref:System.Windows.Forms.SplitContainer> control is set to jump 10 pixels when dragged.</span></span>  
  
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
  
     <span data-ttu-id="a7bba-119">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]) Coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="a7bba-119">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
     <span data-ttu-id="a7bba-120">Mover el divisor ligeramente hacia la izquierda o derecha no tendrá ningún efecto visible; Sin embargo, cuando el puntero del mouse desplace 10 píxeles en cualquier dirección, el divisor se ajustará a la nueva posición.</span><span class="sxs-lookup"><span data-stu-id="a7bba-120">Moving the splitter slightly to the left or right will have no discernible effect; however, when the mouse pointer goes 10 pixels in either direction, the splitter will snap to the new position.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7bba-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7bba-121">See Also</span></span>  
 <xref:System.Windows.Forms.SplitContainer>  
 <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>
