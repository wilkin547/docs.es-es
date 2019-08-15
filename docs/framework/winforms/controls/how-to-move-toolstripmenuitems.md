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
ms.openlocfilehash: adf25973fde790937461007bd0106cca02dd83be
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039795"
---
# <a name="how-to-move-toolstripmenuitems"></a><span data-ttu-id="61496-102">Procedimiento para mover elementos ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="61496-102">How to: Move ToolStripMenuItems</span></span>
<span data-ttu-id="61496-103">En tiempo de diseño, puede desplazar los menús de nivel superior completos y sus elementos de menú a un <xref:System.Windows.Forms.MenuStrip>lugar diferente en el.</span><span class="sxs-lookup"><span data-stu-id="61496-103">At design time, you can move entire top-level menus and their menu items to a different place on the <xref:System.Windows.Forms.MenuStrip>.</span></span> <span data-ttu-id="61496-104">También puede mover elementos de menú individuales entre los menús de nivel superior o cambiar la posición de los elementos de menú dentro de un menú.</span><span class="sxs-lookup"><span data-stu-id="61496-104">You can also move individual menu items between top-level menus or change the position of menu items within a menu.</span></span>

## <a name="to-move-a-top-level-menu-and-its-menu-items-to-another-top-level-location"></a><span data-ttu-id="61496-105">Para desplace un menú de nivel superior y sus elementos de menú a otra ubicación de nivel superior</span><span class="sxs-lookup"><span data-stu-id="61496-105">To move a top-level menu and its menu items to another top-level location</span></span>

1. <span data-ttu-id="61496-106">Haga clic y mantenga presionado el botón primario del mouse en el menú que desea desplace.</span><span class="sxs-lookup"><span data-stu-id="61496-106">Click and hold down the left mouse button on the menu that you want to move.</span></span>

2. <span data-ttu-id="61496-107">Arrastre el punto de inserción hasta el menú de nivel superior que está antes de la nueva ubicación deseada y suelte el botón primario del mouse.</span><span class="sxs-lookup"><span data-stu-id="61496-107">Drag the insertion point to the top-level menu that is before the intended new location and release the left mouse button.</span></span>

     <span data-ttu-id="61496-108">El menú seleccionado se mueve a la derecha del punto de inserción.</span><span class="sxs-lookup"><span data-stu-id="61496-108">The selected menu moves to the right of the insertion point.</span></span>

## <a name="to-move-a-top-level-menu-and-its-menu-items-to-a-drop-down-location"></a><span data-ttu-id="61496-109">Para trasladar un menú de nivel superior y sus elementos de menú a una ubicación desplegable</span><span class="sxs-lookup"><span data-stu-id="61496-109">To move a top-level menu and its menu items to a drop-down location</span></span>

1. <span data-ttu-id="61496-110">Haga clic en el menú que desea desplace y presione CTRL + X o haga clic con el botón derecho en el menú y seleccione **cortar** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="61496-110">Left-click the menu that you want to move and press CTRL+X, or right-click the menu and select **Cut** from the shortcut menu.</span></span>

2. <span data-ttu-id="61496-111">En el menú de nivel superior de destino, haga clic con el botón primario en el elemento de menú situado encima de la nueva ubicación deseada y presione CTRL + V, o haga clic con el botón derecho en el elemento de menú situado encima de la nueva ubicación deseada y seleccione **pegar** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="61496-111">In the destination top-level menu, left-click the menu item above the intended new location and press CTRL+V, or right-click the menu item above the intended new location and select **Paste** from the shortcut menu.</span></span>

     <span data-ttu-id="61496-112">El menú que corte se insertará después del elemento de menú seleccionado.</span><span class="sxs-lookup"><span data-stu-id="61496-112">The menu that you cut is inserted after the selected menu item.</span></span>

## <a name="to-move-a-menu-item-within-a-menu-using-the-items-collection-editor"></a><span data-ttu-id="61496-113">Para desplace un elemento de menú dentro de un menú mediante el editor de la colección de elementos</span><span class="sxs-lookup"><span data-stu-id="61496-113">To move a menu item within a menu using the Items Collection Editor</span></span>

1. <span data-ttu-id="61496-114">Haga clic con el botón secundario en el menú que contiene el elemento de menú que desea desplace.</span><span class="sxs-lookup"><span data-stu-id="61496-114">Right-click the menu that contains the menu item you want to move.</span></span>

2. <span data-ttu-id="61496-115">En el menú contextual, elija **Editar DropDownItems**.</span><span class="sxs-lookup"><span data-stu-id="61496-115">From the shortcut menu, choose **Edit DropDownItems**.</span></span>

3. <span data-ttu-id="61496-116">En el **Editor**de la colección de elementos, haga clic con el botón primario en el elemento de menú que desea desplace.</span><span class="sxs-lookup"><span data-stu-id="61496-116">In the **Items Collection Editor**, left-click the menu item you want to move.</span></span>

4. <span data-ttu-id="61496-117">Haga clic en las teclas de flecha arriba y abajo para colocar el elemento de menú en el menú.</span><span class="sxs-lookup"><span data-stu-id="61496-117">Click the UP and DOWN ARROW keys to move the menu item within the menu.</span></span>

5. <span data-ttu-id="61496-118">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="61496-118">Click **OK**.</span></span>

## <a name="to-move-a-menu-item-within-a-menu-using-the-keyboard"></a><span data-ttu-id="61496-119">Para desplace un elemento de menú dentro de un menú mediante el teclado</span><span class="sxs-lookup"><span data-stu-id="61496-119">To move a menu item within a menu using the keyboard</span></span>

1. <span data-ttu-id="61496-120">Presione y mantenga presionada la tecla ALT.</span><span class="sxs-lookup"><span data-stu-id="61496-120">Press and hold down the ALT key.</span></span>

2. <span data-ttu-id="61496-121">Haga clic y mantenga presionado el botón primario del mouse en el elemento de menú que desea desplace.</span><span class="sxs-lookup"><span data-stu-id="61496-121">Click and hold the left mouse button on the menu item that you want to move.</span></span>

3. <span data-ttu-id="61496-122">Arrastre el elemento de menú a la nueva ubicación y suelte el botón primario del mouse.</span><span class="sxs-lookup"><span data-stu-id="61496-122">Drag the menu item to the new location and release the left mouse button.</span></span>

## <a name="to-move-a-menu-item-to-another-menu"></a><span data-ttu-id="61496-123">Para colocar un elemento de menú en otro menú</span><span class="sxs-lookup"><span data-stu-id="61496-123">To move a menu item to another menu</span></span>

1. <span data-ttu-id="61496-124">Haga clic con el botón primario en el elemento de menú que desea desplace y presione CTRL + X o haga clic con el botón derecho en el elemento de menú y elija **cortar** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="61496-124">Left-click the menu item that you want to move and press CTRL+X, or right-click the menu item and choose **Cut** from the shortcut menu.</span></span>

2. <span data-ttu-id="61496-125">Haga clic con el botón primario en el menú que contendrá el elemento de menú que ha cortado.</span><span class="sxs-lookup"><span data-stu-id="61496-125">Left-click the menu that will contain the menu item that you cut.</span></span>

3. <span data-ttu-id="61496-126">Haga clic con el botón primario en el elemento de menú que está antes de la nueva ubicación deseada y presione CTRL + V, o haga clic con el botón derecho en el elemento de menú que se encuentra antes de la nueva ubicación deseada y seleccione **pegar** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="61496-126">Left-click the menu item that is before the intended new location and press CTRL+V, or right-click the menu item that is before the intended new location and select **Paste** from the shortcut menu.</span></span>

     <span data-ttu-id="61496-127">El elemento de menú que corte se insertará después del elemento de menú seleccionado.</span><span class="sxs-lookup"><span data-stu-id="61496-127">The menu item that you cut is inserted after the selected menu item.</span></span>

## <a name="see-also"></a><span data-ttu-id="61496-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="61496-128">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="61496-129">Información general sobre el control MenuStrip</span><span class="sxs-lookup"><span data-stu-id="61496-129">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
