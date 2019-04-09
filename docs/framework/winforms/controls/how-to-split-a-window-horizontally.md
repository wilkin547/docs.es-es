---
title: Filtrar para dividir una ventana horizontalmente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SplitContainer control [Windows Forms], horizontal splitter
- splitter windows [Windows Forms], changing splitter orientation
- splitter windows [Windows Forms], horizontal
- windows [Windows Forms], splitting horizontally
ms.assetid: a1f74f29-048c-4723-85fa-b9d375ab8f4b
ms.openlocfilehash: d10616e2f09eabec1209a26aabe501ea0af903cb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59189658"
---
# <a name="how-to-split-a-window-horizontally"></a><span data-ttu-id="4c194-102">Filtrar para dividir una ventana horizontalmente</span><span class="sxs-lookup"><span data-stu-id="4c194-102">How to: Split a Window Horizontally</span></span>
<span data-ttu-id="4c194-103">El ejemplo de código siguiente hace que el divisor que divide el <xref:System.Windows.Forms.SplitContainer> horizontal del control.</span><span class="sxs-lookup"><span data-stu-id="4c194-103">The following code example makes the splitter that divides the <xref:System.Windows.Forms.SplitContainer> control horizontal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4c194-104">El <xref:System.Windows.Forms.SplitContainer.Orientation%2A> propiedad de la <xref:System.Windows.Forms.SplitContainer> control determina la dirección del divisor, no del propio control.</span><span class="sxs-lookup"><span data-stu-id="4c194-104">The <xref:System.Windows.Forms.SplitContainer.Orientation%2A> property of the <xref:System.Windows.Forms.SplitContainer> control determines the direction of the splitter, not of the control itself.</span></span>  
  
### <a name="to-split-a-window-horizontally"></a><span data-ttu-id="4c194-105">Para dividir una ventana horizontalmente</span><span class="sxs-lookup"><span data-stu-id="4c194-105">To split a window horizontally</span></span>  
  
1.  <span data-ttu-id="4c194-106">Dentro de un procedimiento, establecer el <xref:System.Windows.Forms.SplitContainer.Orientation%2A> propiedad de la <xref:System.Windows.Forms.SplitContainer> control <xref:System.Windows.Forms.Orientation.Horizontal>.</span><span class="sxs-lookup"><span data-stu-id="4c194-106">Within a procedure, set the <xref:System.Windows.Forms.SplitContainer.Orientation%2A> property of the <xref:System.Windows.Forms.SplitContainer> control to <xref:System.Windows.Forms.Orientation.Horizontal>.</span></span>  
  
    ```vb  
    Sub ShowSplitContainer()  
        Dim splitContainer1 as new SplitContainer()  
        splitContainer1.BorderStyle = BorderStyle.Fixed3D  
        splitContainer1.Location = New System.Drawing.Point(74, 20)  
        splitContainer1.Name = "DemoSplitContainer"  
        splitContainer1.Size = New System.Drawing.Size(212, 435)  
        splitContainer1.TabIndex = 0  
        splitContainer1.Orientation = Orientation.Horizontal  
        Controls.Add(splitContainer1)  
    End Sub  
    ```  
  
    ```csharp  
    public void showSplitContainer()  
    {  
        SplitContainer splitContainer1 = new SplitContainer ();  
        splitContainer1.BorderStyle = BorderStyle.Fixed3D;  
        splitContainer1.Location = new System.Drawing.Point (74, 20);  
        splitContainer1.Name = "DemoSplitContainer";  
        splitContainer1.Size = new System.Drawing.Size (212, 435);  
        splitContainer1.TabIndex = 0;  
        splitContainer1.Orientation = Orientation.Horizontal;  
        this.Controls.Add (splitContainer1);  
  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4c194-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c194-107">See also</span></span>

- <xref:System.Windows.Forms.SplitContainer>
- [<span data-ttu-id="4c194-108">Control SplitContainer</span><span class="sxs-lookup"><span data-stu-id="4c194-108">SplitContainer Control</span></span>](splitcontainer-control-windows-forms.md)
