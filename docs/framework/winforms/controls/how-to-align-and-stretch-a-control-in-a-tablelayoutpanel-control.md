---
title: Filtrar para alinear y expandir un control en un control TableLayoutPanel
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.AlignStretchCtrl
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms], stretching controls
- controls [Windows Forms], stretching
- controls [Windows Forms], aligning
ms.assetid: 7dc1a157-6fee-4995-8ebc-b65bdc0909a8
ms.openlocfilehash: c0bcf91d358d233b5b1d2e300d63112303e87a09
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59095410"
---
# <a name="how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control"></a><span data-ttu-id="a7124-102">Filtrar para alinear y expandir un control en un control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="a7124-102">How to: Align and Stretch a Control in a TableLayoutPanel Control</span></span>
<span data-ttu-id="a7124-103">Puede alinear y expandir controles en un <xref:System.Windows.Forms.TableLayoutPanel> con el <xref:System.Windows.Forms.Control.Anchor%2A> y <xref:System.Windows.Forms.Control.Dock%2A> propiedades.</span><span class="sxs-lookup"><span data-stu-id="a7124-103">You can align and stretch controls in a <xref:System.Windows.Forms.TableLayoutPanel> with the <xref:System.Windows.Forms.Control.Anchor%2A> and <xref:System.Windows.Forms.Control.Dock%2A> properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a7124-104">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="a7124-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="a7124-105">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="a7124-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="a7124-106">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="a7124-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-align-and-stretch-a-control"></a><span data-ttu-id="a7124-107">Para alinear y expandir un control</span><span class="sxs-lookup"><span data-stu-id="a7124-107">To align and stretch a control</span></span>  
  
1.  <span data-ttu-id="a7124-108">Arrastre un control <xref:System.Windows.Forms.TableLayoutPanel> del **cuadro de herramientas** al formulario.</span><span class="sxs-lookup"><span data-stu-id="a7124-108">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
2.  <span data-ttu-id="a7124-109">Arrastre un <xref:System.Windows.Forms.Button> controlar desde la **cuadro de herramientas** en la celda superior izquierda de la <xref:System.Windows.Forms.TableLayoutPanel> control.</span><span class="sxs-lookup"><span data-stu-id="a7124-109">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the upper-left cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="a7124-110">El <xref:System.Windows.Forms.Button> control está centrado en la celda.</span><span class="sxs-lookup"><span data-stu-id="a7124-110">The <xref:System.Windows.Forms.Button> control is centered in the cell.</span></span>  
  
3.  <span data-ttu-id="a7124-111">Establezca el valor de la <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.Control.Anchor%2A> propiedad `Left,Right`.</span><span class="sxs-lookup"><span data-stu-id="a7124-111">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Left,Right`.</span></span> <span data-ttu-id="a7124-112">El <xref:System.Windows.Forms.Button> control se expande para que coincida con el ancho de la celda.</span><span class="sxs-lookup"><span data-stu-id="a7124-112">The <xref:System.Windows.Forms.Button> control stretches to match the width of the cell.</span></span>  
  
4.  <span data-ttu-id="a7124-113">Establezca el valor de la <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.Control.Anchor%2A> propiedad `Top,Bottom`.</span><span class="sxs-lookup"><span data-stu-id="a7124-113">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top,Bottom`.</span></span> <span data-ttu-id="a7124-114">El <xref:System.Windows.Forms.Button> control se expande para ajustarse al alto de la celda.</span><span class="sxs-lookup"><span data-stu-id="a7124-114">The <xref:System.Windows.Forms.Button> control stretches to match the height of the cell.</span></span>  
  
5.  <span data-ttu-id="a7124-115">Establezca el valor de la <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.Control.Dock%2A> propiedad <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="a7124-115">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span> <span data-ttu-id="a7124-116">El <xref:System.Windows.Forms.Button> control se expande para rellenar la celda.</span><span class="sxs-lookup"><span data-stu-id="a7124-116">The <xref:System.Windows.Forms.Button> control expands to fill the cell.</span></span>  
  
6.  <span data-ttu-id="a7124-117">Establezca el valor de la <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.Control.Dock%2A> propiedad <xref:System.Windows.Forms.DockStyle.None>.</span><span class="sxs-lookup"><span data-stu-id="a7124-117">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.None>.</span></span> <span data-ttu-id="a7124-118">El <xref:System.Windows.Forms.Button> control vuelve a su tamaño original y se mueve a la esquina superior izquierda de la celda.</span><span class="sxs-lookup"><span data-stu-id="a7124-118">The <xref:System.Windows.Forms.Button> control returns to its original size and moves to the upper-left corner of the cell.</span></span> <span data-ttu-id="a7124-119">El **Diseñador de Windows Forms** estableció el <xref:System.Windows.Forms.Control.Anchor%2A> propiedad `Top, Left`.</span><span class="sxs-lookup"><span data-stu-id="a7124-119">The **Windows Forms Designer** has set the <xref:System.Windows.Forms.Control.Anchor%2A> property to `Top, Left`.</span></span>  
  
7.  <span data-ttu-id="a7124-120">Establezca el valor de la <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.Control.Anchor%2A> propiedad `Bottom,Right`.</span><span class="sxs-lookup"><span data-stu-id="a7124-120">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to `Bottom,Right`.</span></span> <span data-ttu-id="a7124-121">El <xref:System.Windows.Forms.Button> control se mueve a la esquina inferior derecha de la celda.</span><span class="sxs-lookup"><span data-stu-id="a7124-121">The <xref:System.Windows.Forms.Button> control moves to the lower-right corner of the cell.</span></span>  
  
8.  <span data-ttu-id="a7124-122">Establezca el valor de la <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.Control.Anchor%2A> propiedad <xref:System.Windows.Forms.AnchorStyles.None>.</span><span class="sxs-lookup"><span data-stu-id="a7124-122">Set the value of the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Anchor%2A> property to <xref:System.Windows.Forms.AnchorStyles.None>.</span></span> <span data-ttu-id="a7124-123">El <xref:System.Windows.Forms.Button> control se desplaza hasta el centro de la celda.</span><span class="sxs-lookup"><span data-stu-id="a7124-123">The <xref:System.Windows.Forms.Button> control moves to the center of the cell.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7124-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7124-124">See also</span></span>

- [<span data-ttu-id="a7124-125">Control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="a7124-125">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
