---
title: 'Cómo: Reasignar controles existentes en un elemento primario diferente'
ms.date: 03/30/2017
helpviewer_keywords:
- container controls [Windows Forms], Windows Forms
- layout [Windows Forms], resizing
- layout [Windows Forms], child controls
ms.assetid: 5a5723ff-34e0-4b6f-a57b-be4ebe35cb34
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 1767fcff1742f4ad630b4b996c709b7ded53a129
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459202"
---
# <a name="how-to-reassign-existing-controls-to-a-different-parent"></a><span data-ttu-id="0eb7a-102">Cómo: reasignar controles existentes a un elemento primario diferente</span><span class="sxs-lookup"><span data-stu-id="0eb7a-102">How to: Reassign existing controls to a different parent</span></span>

<span data-ttu-id="0eb7a-103">Puede asignar controles que existen en el formulario a un nuevo control contenedor.</span><span class="sxs-lookup"><span data-stu-id="0eb7a-103">You can assign controls that exist on your form to a new container control.</span></span>

1. <span data-ttu-id="0eb7a-104">En Visual Studio, arrastre tres controles <xref:System.Windows.Forms.Button> desde el **cuadro de herramientas** hasta el formulario.</span><span class="sxs-lookup"><span data-stu-id="0eb7a-104">In Visual Studio, drag three <xref:System.Windows.Forms.Button> controls from the **Toolbox** onto the form.</span></span> <span data-ttu-id="0eb7a-105">Colóquelos cerca entre sí, pero sin alinearlos.</span><span class="sxs-lookup"><span data-stu-id="0eb7a-105">Position them near to each other, but leave them unaligned.</span></span>

2. <span data-ttu-id="0eb7a-106">En el **cuadro de herramientas**, haga clic en el icono del control <xref:System.Windows.Forms.FlowLayoutPanel> .</span><span class="sxs-lookup"><span data-stu-id="0eb7a-106">In the **Toolbox**, click the <xref:System.Windows.Forms.FlowLayoutPanel> control icon.</span></span> <span data-ttu-id="0eb7a-107">(No arrastre el icono hasta el formulario).</span><span class="sxs-lookup"><span data-stu-id="0eb7a-107">(Do not drag the icon onto the form.)</span></span>

3. <span data-ttu-id="0eb7a-108">Mueva el puntero del mouse cerca de los tres controles <xref:System.Windows.Forms.Button> .</span><span class="sxs-lookup"><span data-stu-id="0eb7a-108">Move the mouse pointer close to the three <xref:System.Windows.Forms.Button> controls.</span></span>

   <span data-ttu-id="0eb7a-109">Observe que el puntero cambia a una cruz con el icono del control <xref:System.Windows.Forms.FlowLayoutPanel> agregado.</span><span class="sxs-lookup"><span data-stu-id="0eb7a-109">The pointer changes to a crosshair with the <xref:System.Windows.Forms.FlowLayoutPanel> control icon attached.</span></span>

4. <span data-ttu-id="0eb7a-110">Haga clic y mantenga presionado el botón del mouse.</span><span class="sxs-lookup"><span data-stu-id="0eb7a-110">Click and hold the mouse button.</span></span>

5. <span data-ttu-id="0eb7a-111">Arrastre el puntero del mouse para dibujar el contorno del control <xref:System.Windows.Forms.FlowLayoutPanel> .</span><span class="sxs-lookup"><span data-stu-id="0eb7a-111">Drag the mouse pointer to draw the outline of the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

6. <span data-ttu-id="0eb7a-112">Dibuje el contorno alrededor de los tres controles <xref:System.Windows.Forms.Button> .</span><span class="sxs-lookup"><span data-stu-id="0eb7a-112">Draw the outline around the three <xref:System.Windows.Forms.Button> controls.</span></span>

7. <span data-ttu-id="0eb7a-113">Suelte el botón del mouse.</span><span class="sxs-lookup"><span data-stu-id="0eb7a-113">Release the mouse button.</span></span>

   <span data-ttu-id="0eb7a-114">Observe que los tres controles <xref:System.Windows.Forms.Button> se insertan en el control <xref:System.Windows.Forms.FlowLayoutPanel> .</span><span class="sxs-lookup"><span data-stu-id="0eb7a-114">The three <xref:System.Windows.Forms.Button> controls are now inserted into the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

## <a name="see-also"></a><span data-ttu-id="0eb7a-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="0eb7a-115">See also</span></span>

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="0eb7a-116">Tutorial: Organizar controles en Windows Forms mediante TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="0eb7a-116">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="0eb7a-117">Tutorial: Organizar controles en formularios Windows Forms mediante líneas de ajuste</span><span class="sxs-lookup"><span data-stu-id="0eb7a-117">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
