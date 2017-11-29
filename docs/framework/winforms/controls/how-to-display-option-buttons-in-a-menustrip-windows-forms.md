---
title: "Cómo: Mostrar botones de opción en un control MenuStrip (Windows Forms)"
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
- MenuStrip [Windows Forms], displaying option buttons
- displaying option buttons [Windows Forms], MenuStrip [Windows Forms]
- option buttons [Windows Forms], displaying in MenuStrip
ms.assetid: 8b596af2-9ff8-4f7b-93d7-cba830e167f4
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 15f2d1492148a4b00a4b96844f546a4dc968eef6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-option-buttons-in-a-menustrip-windows-forms"></a><span data-ttu-id="99f0f-102">Cómo: Mostrar botones de opción en un control MenuStrip (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="99f0f-102">How to: Display Option Buttons in a MenuStrip (Windows Forms)</span></span>
<span data-ttu-id="99f0f-103">Botones de opción, también conocidos como botones de radio, son similares a las casillas excepto en que los usuarios pueden seleccionar sólo uno en uno.</span><span class="sxs-lookup"><span data-stu-id="99f0f-103">Option buttons, also known as radio buttons, are similar to check boxes except that users can select only one at a time.</span></span> <span data-ttu-id="99f0f-104">Aunque de forma predeterminada el <xref:System.Windows.Forms.ToolStripMenuItem> clase no proporciona el comportamiento de botón de opción, la clase proporcionar un comportamiento de casilla de verificación que se puede personalizar para implementar el comportamiento de botón de opción para elementos de menú en un <xref:System.Windows.Forms.MenuStrip> control.</span><span class="sxs-lookup"><span data-stu-id="99f0f-104">Although by default the <xref:System.Windows.Forms.ToolStripMenuItem> class does not provide option-button behavior, the class does provide check-box behavior that you can customize to implement option-button behavior for menu items in a <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="99f0f-105">Cuando el <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> la propiedad de un elemento de menú es `true`, los usuarios puedan seleccionar el elemento para alternar la presentación de una marca de verificación.</span><span class="sxs-lookup"><span data-stu-id="99f0f-105">When the <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property of a menu item is `true`, users can click the item to toggle the display of a check mark.</span></span> <span data-ttu-id="99f0f-106">El <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> propiedad indica el estado actual del elemento.</span><span class="sxs-lookup"><span data-stu-id="99f0f-106">The <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property indicates the current state of the item.</span></span> <span data-ttu-id="99f0f-107">Para implementar el comportamiento de botón de opción básico, debe asegurarse de que, al que se selecciona un elemento, establezca la <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> propiedad del elemento seleccionado anteriormente para `false`.</span><span class="sxs-lookup"><span data-stu-id="99f0f-107">To implement basic option-button behavior, you must ensure that when an item is selected, you set the <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property for the previously selected item to `false`.</span></span>  
  
 <span data-ttu-id="99f0f-108">Los procedimientos siguientes describen cómo implementar esto y funciones adicionales en una clase que hereda la <xref:System.Windows.Forms.ToolStripMenuItem> clase.</span><span class="sxs-lookup"><span data-stu-id="99f0f-108">The following procedures describe how to implement this and additional functionality in a class that inherits the <xref:System.Windows.Forms.ToolStripMenuItem> class.</span></span> <span data-ttu-id="99f0f-109">El `ToolStripRadioButtonMenuItem` clase reemplaza a los miembros como <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> y <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> para proporcionar el comportamiento de la selección y la apariencia de los botones de opción.</span><span class="sxs-lookup"><span data-stu-id="99f0f-109">The `ToolStripRadioButtonMenuItem` class overrides members such as <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> and <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> to provide the selection behavior and appearance of option buttons.</span></span> <span data-ttu-id="99f0f-110">Además, esta clase reemplaza el <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> propiedad para que las opciones de un submenú están deshabilitados a menos que se selecciona el elemento primario.</span><span class="sxs-lookup"><span data-stu-id="99f0f-110">Additionally, this class overrides the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property so that options on a submenu are disabled unless the parent item is selected.</span></span>  
  
### <a name="to-implement-option-button-selection-behavior"></a><span data-ttu-id="99f0f-111">Para implementar el comportamiento de selección de botón de opción</span><span class="sxs-lookup"><span data-stu-id="99f0f-111">To implement option-button selection behavior</span></span>  
  
1.  <span data-ttu-id="99f0f-112">Inicializar el <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> propiedad `true` para habilitar la selección de elementos.</span><span class="sxs-lookup"><span data-stu-id="99f0f-112">Initialize the <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property to `true` to enable item selection.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#110)]
     [!code-vb[ToolStripRadioButtonMenuItem#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#110)]  
  
2.  <span data-ttu-id="99f0f-113">Invalidar el <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> método para borrar la selección del elemento seleccionado anteriormente cuando se selecciona un nuevo elemento.</span><span class="sxs-lookup"><span data-stu-id="99f0f-113">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> method to clear the selection of the previously selected item when a new item is selected.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#120)]
     [!code-vb[ToolStripRadioButtonMenuItem#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#120)]  
  
3.  <span data-ttu-id="99f0f-114">Invalidar el <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> método para asegurarse de que al hacer clic en un elemento que ya se ha seleccionado no borrará la selección.</span><span class="sxs-lookup"><span data-stu-id="99f0f-114">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> method to ensure that clicking an item that has already been selected will not clear the selection.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#130)]
     [!code-vb[ToolStripRadioButtonMenuItem#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#130)]  
  
### <a name="to-modify-the-appearance-of-the-option-button-items"></a><span data-ttu-id="99f0f-115">Para modificar la apariencia de los elementos de botón de opción</span><span class="sxs-lookup"><span data-stu-id="99f0f-115">To modify the appearance of the option-button items</span></span>  
  
1.  <span data-ttu-id="99f0f-116">Invalidar el <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> método para reemplazar la marca de verificación de forma predeterminada con un botón de opción mediante el <xref:System.Windows.Forms.RadioButtonRenderer> clase.</span><span class="sxs-lookup"><span data-stu-id="99f0f-116">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> method to replace the default check-mark with an option button by using the <xref:System.Windows.Forms.RadioButtonRenderer> class.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#140)]
     [!code-vb[ToolStripRadioButtonMenuItem#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#140)]  
  
2.  <span data-ttu-id="99f0f-117">Invalidar el <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>, y <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> métodos para hacer un seguimiento del estado del mouse y asegúrese de que el <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> método pinta el estado del botón de opción correctos.</span><span class="sxs-lookup"><span data-stu-id="99f0f-117">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>, and <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> methods to track the state of the mouse and ensure that the <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> method paints the correct option-button state.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#150](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#150)]
     [!code-vb[ToolStripRadioButtonMenuItem#150](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#150)]  
  
### <a name="to-disable-options-on-a-submenu-when-the-parent-item-is-not-selected"></a><span data-ttu-id="99f0f-118">Para deshabilitar las opciones en un submenú cuando no se selecciona el elemento primario</span><span class="sxs-lookup"><span data-stu-id="99f0f-118">To disable options on a submenu when the parent item is not selected</span></span>  
  
1.  <span data-ttu-id="99f0f-119">Invalidar el <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> propiedad para que el elemento está deshabilitado cuando tiene un elemento primario con ambos un <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> valo `true` y un <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> valo `false`.</span><span class="sxs-lookup"><span data-stu-id="99f0f-119">Override the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property so that the item is disabled when it has a parent item with both a <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> value of `true` and a <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> value of `false`.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#160](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#160)]
     [!code-vb[ToolStripRadioButtonMenuItem#160](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#160)]  
  
2.  <span data-ttu-id="99f0f-120">Invalidar el <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> método para suscribirse a las <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> eventos del elemento primario.</span><span class="sxs-lookup"><span data-stu-id="99f0f-120">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> method to subscribe to the <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> event of the parent item.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#170](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#170)]
     [!code-vb[ToolStripRadioButtonMenuItem#170](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#170)]  
  
3.  <span data-ttu-id="99f0f-121">En el controlador para el elemento principal <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> eventos, invalide el elemento para actualizar la pantalla con el nuevo estado habilitado.</span><span class="sxs-lookup"><span data-stu-id="99f0f-121">In the handler for the parent-item <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> event, invalidate the item to update the display with the new enabled state.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#180](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#180)]
     [!code-vb[ToolStripRadioButtonMenuItem#180](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#180)]  
  
## <a name="example"></a><span data-ttu-id="99f0f-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="99f0f-122">Example</span></span>  
 <span data-ttu-id="99f0f-123">En el ejemplo de código siguiente se proporciona la sección completa `ToolStripRadioButtonMenuItem` (clase) y un <xref:System.Windows.Forms.Form> clase y `Program` clase para demostrar el comportamiento de botón de opción.</span><span class="sxs-lookup"><span data-stu-id="99f0f-123">The following code example provides the complete `ToolStripRadioButtonMenuItem` class, and a <xref:System.Windows.Forms.Form> class and `Program` class to demonstrate the option-button behavior.</span></span>  
  
 [!code-csharp[ToolStripRadioButtonMenuItem#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#000)]
 [!code-vb[ToolStripRadioButtonMenuItem#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="99f0f-124">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="99f0f-124">Compiling the Code</span></span>  
 <span data-ttu-id="99f0f-125">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="99f0f-125">This example requires:</span></span>  
  
-   <span data-ttu-id="99f0f-126">Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="99f0f-126">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99f0f-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="99f0f-127">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.RadioButtonRenderer>  
 [<span data-ttu-id="99f0f-128">Control MenuStrip</span><span class="sxs-lookup"><span data-stu-id="99f0f-128">MenuStrip Control</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)  
 [<span data-ttu-id="99f0f-129">Implementar un control ToolStripRenderer personalizado</span><span class="sxs-lookup"><span data-stu-id="99f0f-129">How to: Implement a Custom ToolStripRenderer</span></span>](../../../../docs/framework/winforms/controls/how-to-implement-a-custom-toolstriprenderer.md)
