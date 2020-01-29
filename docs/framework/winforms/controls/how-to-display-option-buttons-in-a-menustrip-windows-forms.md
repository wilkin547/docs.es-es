---
title: 'Cómo: Mostrar botones de opción en un control MenuStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip [Windows Forms], displaying option buttons
- displaying option buttons [Windows Forms], MenuStrip [Windows Forms]
- option buttons [Windows Forms], displaying in MenuStrip
ms.assetid: 8b596af2-9ff8-4f7b-93d7-cba830e167f4
ms.openlocfilehash: f3010e71396ce562e9dbdefd4b75b36f3a81ffb3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735528"
---
# <a name="how-to-display-option-buttons-in-a-menustrip-windows-forms"></a><span data-ttu-id="7f211-102">Cómo: Mostrar botones de opción en un control MenuStrip (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="7f211-102">How to: Display Option Buttons in a MenuStrip (Windows Forms)</span></span>

<span data-ttu-id="7f211-103">Los botones de opción, también conocidos como botones de radio, son similares a las casillas, salvo que los usuarios solo pueden seleccionar uno cada vez.</span><span class="sxs-lookup"><span data-stu-id="7f211-103">Option buttons, also known as radio buttons, are similar to check boxes except that users can select only one at a time.</span></span> <span data-ttu-id="7f211-104">Aunque de forma predeterminada la clase <xref:System.Windows.Forms.ToolStripMenuItem> no proporciona el comportamiento del botón de opción, la clase proporciona un comportamiento de casilla que se puede personalizar para implementar el comportamiento de los botones de opción para los elementos de menú en un control <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="7f211-104">Although by default the <xref:System.Windows.Forms.ToolStripMenuItem> class does not provide option-button behavior, the class does provide check-box behavior that you can customize to implement option-button behavior for menu items in a <xref:System.Windows.Forms.MenuStrip> control.</span></span>

<span data-ttu-id="7f211-105">Cuando se `true`la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> de un elemento de menú, los usuarios pueden hacer clic en el elemento para alternar la presentación de una marca de verificación.</span><span class="sxs-lookup"><span data-stu-id="7f211-105">When the <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property of a menu item is `true`, users can click the item to toggle the display of a check mark.</span></span> <span data-ttu-id="7f211-106">La propiedad <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> indica el estado actual del elemento.</span><span class="sxs-lookup"><span data-stu-id="7f211-106">The <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property indicates the current state of the item.</span></span> <span data-ttu-id="7f211-107">Para implementar el comportamiento básico de los botones de opción, debe asegurarse de que cuando se selecciona un elemento, establezca la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> del elemento seleccionado anteriormente en `false`.</span><span class="sxs-lookup"><span data-stu-id="7f211-107">To implement basic option-button behavior, you must ensure that when an item is selected, you set the <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property for the previously selected item to `false`.</span></span>

<span data-ttu-id="7f211-108">En los procedimientos siguientes se describe cómo implementar esta y la funcionalidad adicional en una clase que hereda la clase <xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="7f211-108">The following procedures describe how to implement this and additional functionality in a class that inherits the <xref:System.Windows.Forms.ToolStripMenuItem> class.</span></span> <span data-ttu-id="7f211-109">La clase `ToolStripRadioButtonMenuItem` invalida miembros como <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> y <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> para proporcionar el comportamiento de la selección y la apariencia de los botones de opción.</span><span class="sxs-lookup"><span data-stu-id="7f211-109">The `ToolStripRadioButtonMenuItem` class overrides members such as <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> and <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> to provide the selection behavior and appearance of option buttons.</span></span> <span data-ttu-id="7f211-110">Además, esta clase invalida la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> de modo que las opciones de un submenú estén deshabilitadas a menos que se seleccione el elemento primario.</span><span class="sxs-lookup"><span data-stu-id="7f211-110">Additionally, this class overrides the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property so that options on a submenu are disabled unless the parent item is selected.</span></span>

## <a name="to-implement-option-button-selection-behavior"></a><span data-ttu-id="7f211-111">Para implementar el comportamiento de la selección de botones de opción</span><span class="sxs-lookup"><span data-stu-id="7f211-111">To implement option-button selection behavior</span></span>

1. <span data-ttu-id="7f211-112">Inicialice la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> en `true` para habilitar la selección de elementos.</span><span class="sxs-lookup"><span data-stu-id="7f211-112">Initialize the <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property to `true` to enable item selection.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#110](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#110)]
     [!code-vb[ToolStripRadioButtonMenuItem#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#110)]

2. <span data-ttu-id="7f211-113">Invalide el método <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> para borrar la selección del elemento seleccionado anteriormente cuando se selecciona un nuevo elemento.</span><span class="sxs-lookup"><span data-stu-id="7f211-113">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> method to clear the selection of the previously selected item when a new item is selected.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#120](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#120)]
     [!code-vb[ToolStripRadioButtonMenuItem#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#120)]

3. <span data-ttu-id="7f211-114">Invalide el método <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> para asegurarse de que al hacer clic en un elemento que ya se ha seleccionado no se borrará la selección.</span><span class="sxs-lookup"><span data-stu-id="7f211-114">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> method to ensure that clicking an item that has already been selected will not clear the selection.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#130](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#130)]
     [!code-vb[ToolStripRadioButtonMenuItem#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#130)]

## <a name="to-modify-the-appearance-of-the-option-button-items"></a><span data-ttu-id="7f211-115">Para modificar la apariencia de los elementos de botón de opción</span><span class="sxs-lookup"><span data-stu-id="7f211-115">To modify the appearance of the option-button items</span></span>

1. <span data-ttu-id="7f211-116">Invalide el método <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> para reemplazar la marca de verificación predeterminada por un botón de opción mediante la clase <xref:System.Windows.Forms.RadioButtonRenderer>.</span><span class="sxs-lookup"><span data-stu-id="7f211-116">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> method to replace the default check-mark with an option button by using the <xref:System.Windows.Forms.RadioButtonRenderer> class.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#140](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#140)]
     [!code-vb[ToolStripRadioButtonMenuItem#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#140)]

2. <span data-ttu-id="7f211-117">Invalide los métodos <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>y <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> para realizar el seguimiento del estado del mouse y asegurarse de que el método <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> dibuje el estado correcto del botón de opción.</span><span class="sxs-lookup"><span data-stu-id="7f211-117">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>, and <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> methods to track the state of the mouse and ensure that the <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> method paints the correct option-button state.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#150](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#150)]
     [!code-vb[ToolStripRadioButtonMenuItem#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#150)]

## <a name="to-disable-options-on-a-submenu-when-the-parent-item-is-not-selected"></a><span data-ttu-id="7f211-118">Para deshabilitar las opciones de un submenú cuando no se selecciona el elemento primario</span><span class="sxs-lookup"><span data-stu-id="7f211-118">To disable options on a submenu when the parent item is not selected</span></span>

1. <span data-ttu-id="7f211-119">Invalide la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> de modo que el elemento esté deshabilitado cuando tenga un elemento primario con un valor <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> de `true` y un valor <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> de `false`.</span><span class="sxs-lookup"><span data-stu-id="7f211-119">Override the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property so that the item is disabled when it has a parent item with both a <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> value of `true` and a <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> value of `false`.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#160](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#160)]
     [!code-vb[ToolStripRadioButtonMenuItem#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#160)]

2. <span data-ttu-id="7f211-120">Invalide el método <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> para suscribirse al evento de <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> del elemento primario.</span><span class="sxs-lookup"><span data-stu-id="7f211-120">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> method to subscribe to the <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> event of the parent item.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#170](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#170)]
     [!code-vb[ToolStripRadioButtonMenuItem#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#170)]

3. <span data-ttu-id="7f211-121">En el controlador del evento de <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> de elemento primario, invalide el elemento para actualizar la presentación con el nuevo estado habilitado.</span><span class="sxs-lookup"><span data-stu-id="7f211-121">In the handler for the parent-item <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> event, invalidate the item to update the display with the new enabled state.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#180](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#180)]
     [!code-vb[ToolStripRadioButtonMenuItem#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#180)]

## <a name="example"></a><span data-ttu-id="7f211-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7f211-122">Example</span></span>

<span data-ttu-id="7f211-123">En el ejemplo de código siguiente se proporciona la clase `ToolStripRadioButtonMenuItem` completa y una clase <xref:System.Windows.Forms.Form> y `Program` clase para mostrar el comportamiento del botón de opción.</span><span class="sxs-lookup"><span data-stu-id="7f211-123">The following code example provides the complete `ToolStripRadioButtonMenuItem` class, and a <xref:System.Windows.Forms.Form> class and `Program` class to demonstrate the option-button behavior.</span></span>

[!code-csharp[ToolStripRadioButtonMenuItem#000](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#000)]
[!code-vb[ToolStripRadioButtonMenuItem#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#000)]

## <a name="compiling-the-code"></a><span data-ttu-id="7f211-124">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="7f211-124">Compiling the Code</span></span>

<span data-ttu-id="7f211-125">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="7f211-125">This example requires:</span></span>

- <span data-ttu-id="7f211-126">Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="7f211-126">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>

## <a name="see-also"></a><span data-ttu-id="7f211-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f211-127">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RadioButtonRenderer>
- [<span data-ttu-id="7f211-128">Control MenuStrip</span><span class="sxs-lookup"><span data-stu-id="7f211-128">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
- [<span data-ttu-id="7f211-129">Implementar un control ToolStripRenderer personalizado</span><span class="sxs-lookup"><span data-stu-id="7f211-129">How to: Implement a Custom ToolStripRenderer</span></span>](how-to-implement-a-custom-toolstriprenderer.md)
