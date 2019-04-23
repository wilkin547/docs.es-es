---
title: Procedimiento para mover elementos ToolStripMenuItems
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], moving
- menus [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], dragging and dropping
- menu items [Windows Forms], moving
- menu items [Windows Forms], cutting and pasting
- menu items [Windows Forms], dragging and dropping
- MenuStrip control [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], cutting and pasting
ms.assetid: cab9e03e-4edd-4c25-b3e3-bd1edc602bd9
ms.openlocfilehash: 2203511e91254c270c59b5d298dd87a5b3737109
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59308365"
---
# <a name="how-to-move-toolstripmenuitems"></a><span data-ttu-id="6d52e-102">Procedimiento para mover elementos ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="6d52e-102">How to: Move ToolStripMenuItems</span></span>
<span data-ttu-id="6d52e-103">En tiempo de diseño, puede mover los menús de nivel superior completos y sus elementos de menú a un lugar diferente el <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="6d52e-103">At design time, you can move entire top-level menus and their menu items to a different place on the <xref:System.Windows.Forms.MenuStrip>.</span></span> <span data-ttu-id="6d52e-104">También puede mover elementos de menú individuales entre los menús de nivel superior o cambiar la posición de los elementos de menú dentro de un menú.</span><span class="sxs-lookup"><span data-stu-id="6d52e-104">You can also move individual menu items between top-level menus or change the position of menu items within a menu.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6d52e-105">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="6d52e-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="6d52e-106">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="6d52e-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="6d52e-107">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="6d52e-107">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-move-a-top-level-menu-and-its-menu-items-to-another-top-level-location"></a><span data-ttu-id="6d52e-108">Para mover un menú de nivel superior y sus elementos de menú a otra ubicación de nivel superior</span><span class="sxs-lookup"><span data-stu-id="6d52e-108">To move a top-level menu and its menu items to another top-level location</span></span>  
  
1. <span data-ttu-id="6d52e-109">Haga clic y mantenga presionado el botón primario del mouse en el menú que desea mover.</span><span class="sxs-lookup"><span data-stu-id="6d52e-109">Click and hold down the left mouse button on the menu that you want to move.</span></span>  
  
2. <span data-ttu-id="6d52e-110">Arrastre el punto de inserción en el menú de nivel superior que está antes de la nueva ubicación deseada y suelte el botón primario del mouse.</span><span class="sxs-lookup"><span data-stu-id="6d52e-110">Drag the insertion point to the top-level menu that is before the intended new location and release the left mouse button.</span></span>  
  
     <span data-ttu-id="6d52e-111">El menú seleccionado se mueve a la derecha del punto de inserción.</span><span class="sxs-lookup"><span data-stu-id="6d52e-111">The selected menu moves to the right of the insertion point.</span></span>  
  
### <a name="to-move-a-top-level-menu-and-its-menu-items-to-a-drop-down-location"></a><span data-ttu-id="6d52e-112">Para mover un menú de nivel superior y sus elementos de menú a una ubicación de la lista desplegable</span><span class="sxs-lookup"><span data-stu-id="6d52e-112">To move a top-level menu and its menu items to a drop-down location</span></span>  
  
1. <span data-ttu-id="6d52e-113">Haga clic en el menú que desea mover y presione CTRL + X, o el menú contextual y seleccione **cortar** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="6d52e-113">Left-click the menu that you want to move and press CTRL+X, or right-click the menu and select **Cut** from the shortcut menu.</span></span>  
  
2. <span data-ttu-id="6d52e-114">En el menú de nivel superior de destino, haga clic en el elemento de menú por encima de la nueva ubicación deseada y presione CTRL+V, o haga clic en el elemento de menú situado encima de la nueva ubicación deseada y seleccione **pegar** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="6d52e-114">In the destination top-level menu, left-click the menu item above the intended new location and press CTRL+V, or right-click the menu item above the intended new location and select **Paste** from the shortcut menu.</span></span>  
  
     <span data-ttu-id="6d52e-115">El menú que ha cortado se inserta después del elemento de menú seleccionado.</span><span class="sxs-lookup"><span data-stu-id="6d52e-115">The menu that you cut is inserted after the selected menu item.</span></span>  
  
### <a name="to-move-a-menu-item-within-a-menu-using-the-items-collection-editor"></a><span data-ttu-id="6d52e-116">Para mover un elemento de menú dentro de un menú con el Editor de colección de elementos</span><span class="sxs-lookup"><span data-stu-id="6d52e-116">To move a menu item within a menu using the Items Collection Editor</span></span>  
  
1. <span data-ttu-id="6d52e-117">Haga clic en el menú que contiene el elemento de menú que desea mover.</span><span class="sxs-lookup"><span data-stu-id="6d52e-117">Right-click the menu that contains the menu item you want to move.</span></span>  
  
2. <span data-ttu-id="6d52e-118">En el menú contextual, elija **Editar DropDownItems**.</span><span class="sxs-lookup"><span data-stu-id="6d52e-118">From the shortcut menu, choose **Edit DropDownItems**.</span></span>  
  
3. <span data-ttu-id="6d52e-119">En el **Editor de la colección de elementos**, haga clic en el elemento de menú que desea mover.</span><span class="sxs-lookup"><span data-stu-id="6d52e-119">In the **Items Collection Editor**, left-click the menu item you want to move.</span></span>  
  
4. <span data-ttu-id="6d52e-120">Haga clic en las teclas de dirección arriba y abajo para mover el elemento de menú en el menú.</span><span class="sxs-lookup"><span data-stu-id="6d52e-120">Click the UP and DOWN ARROW keys to move the menu item within the menu.</span></span>  
  
5. <span data-ttu-id="6d52e-121">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6d52e-121">Click **OK**.</span></span>  
  
### <a name="to-move-a-menu-item-within-a-menu-using-the-keyboard"></a><span data-ttu-id="6d52e-122">Para mover un elemento de menú dentro de un menú mediante el teclado</span><span class="sxs-lookup"><span data-stu-id="6d52e-122">To move a menu item within a menu using the keyboard</span></span>  
  
1. <span data-ttu-id="6d52e-123">Presione y mantenga presionada la tecla ALT.</span><span class="sxs-lookup"><span data-stu-id="6d52e-123">Press and hold down the ALT key.</span></span>  
  
2. <span data-ttu-id="6d52e-124">Haga clic y mantenga el botón primario del mouse en el elemento de menú que desea mover.</span><span class="sxs-lookup"><span data-stu-id="6d52e-124">Click and hold the left mouse button on the menu item that you want to move.</span></span>  
  
3. <span data-ttu-id="6d52e-125">Arrastre el elemento de menú a la nueva ubicación y suelte el botón primario del mouse.</span><span class="sxs-lookup"><span data-stu-id="6d52e-125">Drag the menu item to the new location and release the left mouse button.</span></span>  
  
### <a name="to-move-a-menu-item-to-another-menu"></a><span data-ttu-id="6d52e-126">Para mover un elemento de menú a otro menú</span><span class="sxs-lookup"><span data-stu-id="6d52e-126">To move a menu item to another menu</span></span>  
  
1. <span data-ttu-id="6d52e-127">Haga clic en el elemento de menú que desea mover y presione CTRL + X, o haga clic en el elemento de menú y elija **cortar** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="6d52e-127">Left-click the menu item that you want to move and press CTRL+X, or right-click the menu item and choose **Cut** from the shortcut menu.</span></span>  
  
2. <span data-ttu-id="6d52e-128">Haga clic en el menú que contendrá el elemento de menú que ha cortado.</span><span class="sxs-lookup"><span data-stu-id="6d52e-128">Left-click the menu that will contain the menu item that you cut.</span></span>  
  
3. <span data-ttu-id="6d52e-129">Haga clic en el elemento de menú que está antes de la nueva ubicación deseada y presione CTRL+V o haga clic en el elemento de menú que es anterior a la nueva ubicación deseada y seleccione **pegar** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="6d52e-129">Left-click the menu item that is before the intended new location and press CTRL+V, or right-click the menu item that is before the intended new location and select **Paste** from the shortcut menu.</span></span>  
  
     <span data-ttu-id="6d52e-130">El elemento de menú que ha cortado se inserta después del elemento de menú seleccionado.</span><span class="sxs-lookup"><span data-stu-id="6d52e-130">The menu item that you cut is inserted after the selected menu item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d52e-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d52e-131">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="6d52e-132">Información general sobre el control MenuStrip</span><span class="sxs-lookup"><span data-stu-id="6d52e-132">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
