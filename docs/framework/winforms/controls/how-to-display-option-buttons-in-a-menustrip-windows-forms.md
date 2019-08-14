---
title: Procedimiento Mostrar botones de opción en un MenuStrip (Windows Forms)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip [Windows Forms], displaying option buttons
- displaying option buttons [Windows Forms], MenuStrip [Windows Forms]
- option buttons [Windows Forms], displaying in MenuStrip
ms.assetid: 8b596af2-9ff8-4f7b-93d7-cba830e167f4
ms.openlocfilehash: 94d683369edd6583ad8b01c2ce3f393567a5ed75
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "68971935"
---
# <a name="how-to-display-option-buttons-in-a-menustrip-windows-forms"></a><span data-ttu-id="37d72-102">Procedimiento Mostrar botones de opción en un MenuStrip (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="37d72-102">How to: Display Option Buttons in a MenuStrip (Windows Forms)</span></span>

<span data-ttu-id="37d72-103">Los botones de opción, también conocidos como botones de radio, son similares a las casillas, salvo que los usuarios solo pueden seleccionar uno cada vez.</span><span class="sxs-lookup"><span data-stu-id="37d72-103">Option buttons, also known as radio buttons, are similar to check boxes except that users can select only one at a time.</span></span> <span data-ttu-id="37d72-104">Aunque de forma predeterminada <xref:System.Windows.Forms.ToolStripMenuItem> , la clase no proporciona el comportamiento del botón de opción, la clase proporciona un comportamiento de casilla que se puede personalizar para implementar el comportamiento del botón de opción para <xref:System.Windows.Forms.MenuStrip> los elementos de menú en un control.</span><span class="sxs-lookup"><span data-stu-id="37d72-104">Although by default the <xref:System.Windows.Forms.ToolStripMenuItem> class does not provide option-button behavior, the class does provide check-box behavior that you can customize to implement option-button behavior for menu items in a <xref:System.Windows.Forms.MenuStrip> control.</span></span>

<span data-ttu-id="37d72-105">Cuando la <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> propiedad de un elemento de menú `true`es, los usuarios pueden hacer clic en el elemento para alternar la presentación de una marca de verificación.</span><span class="sxs-lookup"><span data-stu-id="37d72-105">When the <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property of a menu item is `true`, users can click the item to toggle the display of a check mark.</span></span> <span data-ttu-id="37d72-106">La <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> propiedad indica el estado actual del elemento.</span><span class="sxs-lookup"><span data-stu-id="37d72-106">The <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property indicates the current state of the item.</span></span> <span data-ttu-id="37d72-107">Para implementar el comportamiento básico de los botones de opción, debe asegurarse de que cuando se selecciona un elemento, <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> establezca la propiedad del elemento seleccionado anteriormente `false`en.</span><span class="sxs-lookup"><span data-stu-id="37d72-107">To implement basic option-button behavior, you must ensure that when an item is selected, you set the <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property for the previously selected item to `false`.</span></span>

<span data-ttu-id="37d72-108">En los procedimientos siguientes se describe cómo implementar esta y la funcionalidad adicional en una clase que hereda <xref:System.Windows.Forms.ToolStripMenuItem> la clase.</span><span class="sxs-lookup"><span data-stu-id="37d72-108">The following procedures describe how to implement this and additional functionality in a class that inherits the <xref:System.Windows.Forms.ToolStripMenuItem> class.</span></span> <span data-ttu-id="37d72-109">La `ToolStripRadioButtonMenuItem` clase invalida miembros <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> como y <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> para proporcionar el comportamiento de selección y la apariencia de los botones de opción.</span><span class="sxs-lookup"><span data-stu-id="37d72-109">The `ToolStripRadioButtonMenuItem` class overrides members such as <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> and <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> to provide the selection behavior and appearance of option buttons.</span></span> <span data-ttu-id="37d72-110">Además, esta clase invalida la <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> propiedad para que las opciones de un submenú estén deshabilitadas a menos que se seleccione el elemento primario.</span><span class="sxs-lookup"><span data-stu-id="37d72-110">Additionally, this class overrides the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property so that options on a submenu are disabled unless the parent item is selected.</span></span>

## <a name="to-implement-option-button-selection-behavior"></a><span data-ttu-id="37d72-111">Para implementar el comportamiento de la selección de botones de opción</span><span class="sxs-lookup"><span data-stu-id="37d72-111">To implement option-button selection behavior</span></span>

1. <span data-ttu-id="37d72-112">Inicialice la <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> propiedad en `true` para habilitar la selección de elementos.</span><span class="sxs-lookup"><span data-stu-id="37d72-112">Initialize the <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property to `true` to enable item selection.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#110](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#110)]
     [!code-vb[ToolStripRadioButtonMenuItem#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#110)]

2. <span data-ttu-id="37d72-113">Invalide el <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> método para borrar la selección del elemento seleccionado anteriormente cuando se selecciona un nuevo elemento.</span><span class="sxs-lookup"><span data-stu-id="37d72-113">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> method to clear the selection of the previously selected item when a new item is selected.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#120](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#120)]
     [!code-vb[ToolStripRadioButtonMenuItem#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#120)]

3. <span data-ttu-id="37d72-114">Invalide el <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> método para asegurarse de que al hacer clic en un elemento que ya se ha seleccionado no se borrará la selección.</span><span class="sxs-lookup"><span data-stu-id="37d72-114">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> method to ensure that clicking an item that has already been selected will not clear the selection.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#130](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#130)]
     [!code-vb[ToolStripRadioButtonMenuItem#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#130)]

## <a name="to-modify-the-appearance-of-the-option-button-items"></a><span data-ttu-id="37d72-115">Para modificar la apariencia de los elementos de botón de opción</span><span class="sxs-lookup"><span data-stu-id="37d72-115">To modify the appearance of the option-button items</span></span>

1. <span data-ttu-id="37d72-116">Invalide el <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> método para reemplazar la marca de verificación predeterminada por un botón de opción <xref:System.Windows.Forms.RadioButtonRenderer> mediante la clase.</span><span class="sxs-lookup"><span data-stu-id="37d72-116">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> method to replace the default check-mark with an option button by using the <xref:System.Windows.Forms.RadioButtonRenderer> class.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#140](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#140)]
     [!code-vb[ToolStripRadioButtonMenuItem#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#140)]

2. <span data-ttu-id="37d72-117"><xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>Invalide los <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>métodos, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, y <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> para realizar un seguimiento del estado del mouse y asegurarse <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> de que el método pinta el estado correcto del botón de opción.</span><span class="sxs-lookup"><span data-stu-id="37d72-117">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>, and <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> methods to track the state of the mouse and ensure that the <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> method paints the correct option-button state.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#150](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#150)]
     [!code-vb[ToolStripRadioButtonMenuItem#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#150)]

## <a name="to-disable-options-on-a-submenu-when-the-parent-item-is-not-selected"></a><span data-ttu-id="37d72-118">Para deshabilitar las opciones de un submenú cuando no se selecciona el elemento primario</span><span class="sxs-lookup"><span data-stu-id="37d72-118">To disable options on a submenu when the parent item is not selected</span></span>

1. <span data-ttu-id="37d72-119">Invalide la <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> propiedad para que el elemento se deshabilite cuando tenga un elemento primario con <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> un valor `true` de y <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> un valor `false`de.</span><span class="sxs-lookup"><span data-stu-id="37d72-119">Override the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property so that the item is disabled when it has a parent item with both a <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> value of `true` and a <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> value of `false`.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#160](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#160)]
     [!code-vb[ToolStripRadioButtonMenuItem#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#160)]

2. <span data-ttu-id="37d72-120">Invalide el <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> método para suscribirse <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> al evento del elemento primario.</span><span class="sxs-lookup"><span data-stu-id="37d72-120">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> method to subscribe to the <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> event of the parent item.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#170](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#170)]
     [!code-vb[ToolStripRadioButtonMenuItem#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#170)]

3. <span data-ttu-id="37d72-121">En el controlador del evento de elemento <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> primario, invalide el elemento para actualizar la presentación con el nuevo estado habilitado.</span><span class="sxs-lookup"><span data-stu-id="37d72-121">In the handler for the parent-item <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> event, invalidate the item to update the display with the new enabled state.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#180](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#180)]
     [!code-vb[ToolStripRadioButtonMenuItem#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#180)]

## <a name="example"></a><span data-ttu-id="37d72-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="37d72-122">Example</span></span>

<span data-ttu-id="37d72-123">En el ejemplo de código siguiente se `ToolStripRadioButtonMenuItem` proporciona la clase completa <xref:System.Windows.Forms.Form> y una `Program` clase y clase para mostrar el comportamiento del botón de opción.</span><span class="sxs-lookup"><span data-stu-id="37d72-123">The following code example provides the complete `ToolStripRadioButtonMenuItem` class, and a <xref:System.Windows.Forms.Form> class and `Program` class to demonstrate the option-button behavior.</span></span>

[!code-csharp[ToolStripRadioButtonMenuItem#000](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#000)]
[!code-vb[ToolStripRadioButtonMenuItem#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#000)]

## <a name="compiling-the-code"></a><span data-ttu-id="37d72-124">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="37d72-124">Compiling the Code</span></span>

<span data-ttu-id="37d72-125">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="37d72-125">This example requires:</span></span>

- <span data-ttu-id="37d72-126">Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="37d72-126">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>

## <a name="see-also"></a><span data-ttu-id="37d72-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="37d72-127">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RadioButtonRenderer>
- [<span data-ttu-id="37d72-128">Control MenuStrip</span><span class="sxs-lookup"><span data-stu-id="37d72-128">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
- [<span data-ttu-id="37d72-129">Procedimientos: Implementar un ToolStripRenderer personalizado</span><span class="sxs-lookup"><span data-stu-id="37d72-129">How to: Implement a Custom ToolStripRenderer</span></span>](how-to-implement-a-custom-toolstriprenderer.md)
