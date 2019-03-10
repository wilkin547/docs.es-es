---
title: Procedimiento Mostrar los botones de opción en un control MenuStrip (formularios Windows Forms)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip [Windows Forms], displaying option buttons
- displaying option buttons [Windows Forms], MenuStrip [Windows Forms]
- option buttons [Windows Forms], displaying in MenuStrip
ms.assetid: 8b596af2-9ff8-4f7b-93d7-cba830e167f4
ms.openlocfilehash: c64dd88915fdd17deee415b4d6c3fd088fbcfbfd
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718875"
---
# <a name="how-to-display-option-buttons-in-a-menustrip-windows-forms"></a><span data-ttu-id="ab0ea-102">Filtrar Mostrar los botones de opción en un control MenuStrip (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="ab0ea-102">How to: Display Option Buttons in a MenuStrip (Windows Forms)</span></span>
<span data-ttu-id="ab0ea-103">Botones de opción, también conocido como botones de radio, son similares a las casillas excepto en que los usuarios pueden seleccionar solo uno en uno.</span><span class="sxs-lookup"><span data-stu-id="ab0ea-103">Option buttons, also known as radio buttons, are similar to check boxes except that users can select only one at a time.</span></span> <span data-ttu-id="ab0ea-104">Aunque de forma predeterminada el <xref:System.Windows.Forms.ToolStripMenuItem> clase no proporciona el comportamiento del botón de opción, la clase proporciona el comportamiento de la casilla de verificación que se puede personalizar para implementar el comportamiento del botón de opción para los elementos de menú en un <xref:System.Windows.Forms.MenuStrip> control.</span><span class="sxs-lookup"><span data-stu-id="ab0ea-104">Although by default the <xref:System.Windows.Forms.ToolStripMenuItem> class does not provide option-button behavior, the class does provide check-box behavior that you can customize to implement option-button behavior for menu items in a <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="ab0ea-105">Cuando el <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> es propiedad de un elemento de menú `true`, los usuarios hacer clic en el elemento para alternar la presentación de una marca de verificación.</span><span class="sxs-lookup"><span data-stu-id="ab0ea-105">When the <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property of a menu item is `true`, users can click the item to toggle the display of a check mark.</span></span> <span data-ttu-id="ab0ea-106">El <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> propiedad indica el estado actual del elemento.</span><span class="sxs-lookup"><span data-stu-id="ab0ea-106">The <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property indicates the current state of the item.</span></span> <span data-ttu-id="ab0ea-107">Para implementar el comportamiento del botón de opción básico, debe asegurarse de que cuando se selecciona un elemento, establecen el <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> propiedad del elemento seleccionado anteriormente para `false`.</span><span class="sxs-lookup"><span data-stu-id="ab0ea-107">To implement basic option-button behavior, you must ensure that when an item is selected, you set the <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property for the previously selected item to `false`.</span></span>  
  
 <span data-ttu-id="ab0ea-108">Los procedimientos siguientes describen cómo realizar la implementación y funcionalidad adicional en una clase que hereda la <xref:System.Windows.Forms.ToolStripMenuItem> clase.</span><span class="sxs-lookup"><span data-stu-id="ab0ea-108">The following procedures describe how to implement this and additional functionality in a class that inherits the <xref:System.Windows.Forms.ToolStripMenuItem> class.</span></span> <span data-ttu-id="ab0ea-109">El `ToolStripRadioButtonMenuItem` clase reemplaza a los miembros como <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> y <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> para proporcionar el comportamiento de la selección y la apariencia de botones de opción.</span><span class="sxs-lookup"><span data-stu-id="ab0ea-109">The `ToolStripRadioButtonMenuItem` class overrides members such as <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> and <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> to provide the selection behavior and appearance of option buttons.</span></span> <span data-ttu-id="ab0ea-110">Además, esta clase invalida el <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> propiedad, por lo que las opciones de un submenú están deshabilitadas a menos que el elemento primario está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="ab0ea-110">Additionally, this class overrides the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property so that options on a submenu are disabled unless the parent item is selected.</span></span>  
  
### <a name="to-implement-option-button-selection-behavior"></a><span data-ttu-id="ab0ea-111">Para implementar el comportamiento de selección de botón de opción</span><span class="sxs-lookup"><span data-stu-id="ab0ea-111">To implement option-button selection behavior</span></span>  
  
1.  <span data-ttu-id="ab0ea-112">Inicializar el <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> propiedad `true` para habilitar la selección de elementos.</span><span class="sxs-lookup"><span data-stu-id="ab0ea-112">Initialize the <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property to `true` to enable item selection.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#110](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#110)]
     [!code-vb[ToolStripRadioButtonMenuItem#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#110)]  
  
2.  <span data-ttu-id="ab0ea-113">Invalidar el <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> método para borrar la selección del elemento seleccionado previamente cuando se selecciona un nuevo elemento.</span><span class="sxs-lookup"><span data-stu-id="ab0ea-113">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> method to clear the selection of the previously selected item when a new item is selected.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#120](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#120)]
     [!code-vb[ToolStripRadioButtonMenuItem#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#120)]  
  
3.  <span data-ttu-id="ab0ea-114">Invalidar el <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> método para asegurarse de que al hacer clic en un elemento que se ha seleccionado ya no borra la selección.</span><span class="sxs-lookup"><span data-stu-id="ab0ea-114">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> method to ensure that clicking an item that has already been selected will not clear the selection.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#130](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#130)]
     [!code-vb[ToolStripRadioButtonMenuItem#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#130)]  
  
### <a name="to-modify-the-appearance-of-the-option-button-items"></a><span data-ttu-id="ab0ea-115">Para modificar la apariencia de los elementos de botón de opción</span><span class="sxs-lookup"><span data-stu-id="ab0ea-115">To modify the appearance of the option-button items</span></span>  
  
1.  <span data-ttu-id="ab0ea-116">Invalidar el <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> método para reemplazar la marca de verificación de forma predeterminada con un botón de opción mediante el <xref:System.Windows.Forms.RadioButtonRenderer> clase.</span><span class="sxs-lookup"><span data-stu-id="ab0ea-116">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> method to replace the default check-mark with an option button by using the <xref:System.Windows.Forms.RadioButtonRenderer> class.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#140](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#140)]
     [!code-vb[ToolStripRadioButtonMenuItem#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#140)]  
  
2.  <span data-ttu-id="ab0ea-117">Invalidar el <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>, y <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> métodos para realizar un seguimiento del estado del mouse y asegúrese de que el <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> método pinta el estado del botón de opción correctos.</span><span class="sxs-lookup"><span data-stu-id="ab0ea-117">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>, and <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> methods to track the state of the mouse and ensure that the <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> method paints the correct option-button state.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#150](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#150)]
     [!code-vb[ToolStripRadioButtonMenuItem#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#150)]  
  
### <a name="to-disable-options-on-a-submenu-when-the-parent-item-is-not-selected"></a><span data-ttu-id="ab0ea-118">Para deshabilitar las opciones de un submenú al elemento primario no está seleccionado</span><span class="sxs-lookup"><span data-stu-id="ab0ea-118">To disable options on a submenu when the parent item is not selected</span></span>  
  
1.  <span data-ttu-id="ab0ea-119">Invalidar el <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> propiedad para que el elemento está deshabilitado cuando tiene un elemento primario con ambos un <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> valor `true` y un <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> valor de `false`.</span><span class="sxs-lookup"><span data-stu-id="ab0ea-119">Override the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property so that the item is disabled when it has a parent item with both a <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> value of `true` and a <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> value of `false`.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#160](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#160)]
     [!code-vb[ToolStripRadioButtonMenuItem#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#160)]  
  
2.  <span data-ttu-id="ab0ea-120">Invalidar el <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> método para suscribirse a la <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> eventos del elemento primario.</span><span class="sxs-lookup"><span data-stu-id="ab0ea-120">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> method to subscribe to the <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> event of the parent item.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#170](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#170)]
     [!code-vb[ToolStripRadioButtonMenuItem#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#170)]  
  
3.  <span data-ttu-id="ab0ea-121">En el controlador para el elemento principal <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> eventos, invalide el elemento para actualizar la pantalla con el nuevo estado habilitado.</span><span class="sxs-lookup"><span data-stu-id="ab0ea-121">In the handler for the parent-item <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> event, invalidate the item to update the display with the new enabled state.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#180](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#180)]
     [!code-vb[ToolStripRadioButtonMenuItem#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#180)]  
  
## <a name="example"></a><span data-ttu-id="ab0ea-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ab0ea-122">Example</span></span>  
 <span data-ttu-id="ab0ea-123">En el ejemplo de código siguiente se proporciona la completa `ToolStripRadioButtonMenuItem` (clase) y un <xref:System.Windows.Forms.Form> clase y `Program` clase para demostrar el comportamiento del botón de opción.</span><span class="sxs-lookup"><span data-stu-id="ab0ea-123">The following code example provides the complete `ToolStripRadioButtonMenuItem` class, and a <xref:System.Windows.Forms.Form> class and `Program` class to demonstrate the option-button behavior.</span></span>  
  
 [!code-csharp[ToolStripRadioButtonMenuItem#000](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#000)]
 [!code-vb[ToolStripRadioButtonMenuItem#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ab0ea-124">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="ab0ea-124">Compiling the Code</span></span>  
 <span data-ttu-id="ab0ea-125">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="ab0ea-125">This example requires:</span></span>  
  
-   <span data-ttu-id="ab0ea-126">Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="ab0ea-126">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab0ea-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab0ea-127">See also</span></span>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RadioButtonRenderer>
- [<span data-ttu-id="ab0ea-128">Control MenuStrip</span><span class="sxs-lookup"><span data-stu-id="ab0ea-128">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
- [<span data-ttu-id="ab0ea-129">Cómo: Implementar un control ToolStripRenderer personalizado</span><span class="sxs-lookup"><span data-stu-id="ab0ea-129">How to: Implement a Custom ToolStripRenderer</span></span>](how-to-implement-a-custom-toolstriprenderer.md)
