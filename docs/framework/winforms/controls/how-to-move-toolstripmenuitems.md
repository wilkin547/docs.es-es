---
title: "Cómo: Mover elementos ToolStripMenuItems"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6ffef860118ba20508bba037910d85866055c898
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-move-toolstripmenuitems"></a><span data-ttu-id="f204d-102">Cómo: Mover elementos ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="f204d-102">How to: Move ToolStripMenuItems</span></span>
<span data-ttu-id="f204d-103">En tiempo de diseño, puede mover los menús de nivel superior completos y sus elementos de menú en un lugar diferente el <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="f204d-103">At design time, you can move entire top-level menus and their menu items to a different place on the <xref:System.Windows.Forms.MenuStrip>.</span></span> <span data-ttu-id="f204d-104">También puede mover elementos de menú individuales entre los menús de nivel superior o cambiar la posición de los elementos de menú dentro de un menú.</span><span class="sxs-lookup"><span data-stu-id="f204d-104">You can also move individual menu items between top-level menus or change the position of menu items within a menu.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f204d-105">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="f204d-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="f204d-106">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="f204d-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="f204d-107">Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="f204d-107">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-move-a-top-level-menu-and-its-menu-items-to-another-top-level-location"></a><span data-ttu-id="f204d-108">Para mover un menú de nivel superior y sus elementos de menú a otra ubicación de nivel superior</span><span class="sxs-lookup"><span data-stu-id="f204d-108">To move a top-level menu and its menu items to another top-level location</span></span>  
  
1.  <span data-ttu-id="f204d-109">Haga clic y mantenga presionado el botón primario del mouse en el menú que desea mover.</span><span class="sxs-lookup"><span data-stu-id="f204d-109">Click and hold down the left mouse button on the menu that you want to move.</span></span>  
  
2.  <span data-ttu-id="f204d-110">Arrastre el punto de inserción en el menú de nivel superior que está antes de la nueva ubicación deseada y suelte el botón primario del mouse.</span><span class="sxs-lookup"><span data-stu-id="f204d-110">Drag the insertion point to the top-level menu that is before the intended new location and release the left mouse button.</span></span>  
  
     <span data-ttu-id="f204d-111">El menú seleccionado se mueve a la derecha del punto de inserción.</span><span class="sxs-lookup"><span data-stu-id="f204d-111">The selected menu moves to the right of the insertion point.</span></span>  
  
### <a name="to-move-a-top-level-menu-and-its-menu-items-to-a-drop-down-location"></a><span data-ttu-id="f204d-112">Para mover un menú de nivel superior y sus elementos de menú a una ubicación desplegable</span><span class="sxs-lookup"><span data-stu-id="f204d-112">To move a top-level menu and its menu items to a drop-down location</span></span>  
  
1.  <span data-ttu-id="f204d-113">Haga clic en el menú que desea mover y presione CTRL + X, o haga clic en el menú y seleccione **cortar** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="f204d-113">Left-click the menu that you want to move and press CTRL+X, or right-click the menu and select **Cut** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="f204d-114">En el menú de nivel superior de destino, haga clic en el elemento de menú por encima de la nueva ubicación deseada y presione CTRL+V, o haga clic en el elemento de menú por encima de la nueva ubicación deseada y seleccione **pegar** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="f204d-114">In the destination top-level menu, left-click the menu item above the intended new location and press CTRL+V, or right-click the menu item above the intended new location and select **Paste** from the shortcut menu.</span></span>  
  
     <span data-ttu-id="f204d-115">El menú que ha cortado se inserta después del elemento de menú seleccionado.</span><span class="sxs-lookup"><span data-stu-id="f204d-115">The menu that you cut is inserted after the selected menu item.</span></span>  
  
### <a name="to-move-a-menu-item-within-a-menu-using-the-items-collection-editor"></a><span data-ttu-id="f204d-116">Para mover un elemento de menú dentro de un menú mediante el Editor de la colección de elementos</span><span class="sxs-lookup"><span data-stu-id="f204d-116">To move a menu item within a menu using the Items Collection Editor</span></span>  
  
1.  <span data-ttu-id="f204d-117">Haga clic en el menú que contiene el elemento de menú que desea mover.</span><span class="sxs-lookup"><span data-stu-id="f204d-117">Right-click the menu that contains the menu item you want to move.</span></span>  
  
2.  <span data-ttu-id="f204d-118">En el menú contextual, elija **Editar DropDownItems**.</span><span class="sxs-lookup"><span data-stu-id="f204d-118">From the shortcut menu, choose **Edit DropDownItems**.</span></span>  
  
3.  <span data-ttu-id="f204d-119">En el **Editor de la colección de elementos**, haga clic en el elemento de menú que desea mover.</span><span class="sxs-lookup"><span data-stu-id="f204d-119">In the **Items Collection Editor**, left-click the menu item you want to move.</span></span>  
  
4.  <span data-ttu-id="f204d-120">Haga clic en las teclas de dirección arriba y abajo para mover el elemento de menú en el menú.</span><span class="sxs-lookup"><span data-stu-id="f204d-120">Click the UP and DOWN ARROW keys to move the menu item within the menu.</span></span>  
  
5.  <span data-ttu-id="f204d-121">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f204d-121">Click **OK**.</span></span>  
  
### <a name="to-move-a-menu-item-within-a-menu-using-the-keyboard"></a><span data-ttu-id="f204d-122">Para mover un elemento de menú dentro de un menú mediante el teclado</span><span class="sxs-lookup"><span data-stu-id="f204d-122">To move a menu item within a menu using the keyboard</span></span>  
  
1.  <span data-ttu-id="f204d-123">Presione y mantenga presionada la tecla ALT.</span><span class="sxs-lookup"><span data-stu-id="f204d-123">Press and hold down the ALT key.</span></span>  
  
2.  <span data-ttu-id="f204d-124">Mantenga presionado el botón primario del mouse en el elemento de menú que desea mover.</span><span class="sxs-lookup"><span data-stu-id="f204d-124">Click and hold the left mouse button on the menu item that you want to move.</span></span>  
  
3.  <span data-ttu-id="f204d-125">Arrastre el elemento de menú a la nueva ubicación y suelte el botón primario del mouse.</span><span class="sxs-lookup"><span data-stu-id="f204d-125">Drag the menu item to the new location and release the left mouse button.</span></span>  
  
### <a name="to-move-a-menu-item-to-another-menu"></a><span data-ttu-id="f204d-126">Para mover un elemento de menú a otro menú</span><span class="sxs-lookup"><span data-stu-id="f204d-126">To move a menu item to another menu</span></span>  
  
1.  <span data-ttu-id="f204d-127">Haga clic en el elemento de menú que desea mover y presione CTRL + X, o haga clic en el elemento de menú y elija **cortar** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="f204d-127">Left-click the menu item that you want to move and press CTRL+X, or right-click the menu item and choose **Cut** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="f204d-128">Haga clic en el menú que contendrá el elemento de menú que ha cortado.</span><span class="sxs-lookup"><span data-stu-id="f204d-128">Left-click the menu that will contain the menu item that you cut.</span></span>  
  
3.  <span data-ttu-id="f204d-129">Haga clic en el elemento de menú que está antes de la nueva ubicación deseada y presione CTRL+V o haga clic en el elemento de menú que es anterior a la nueva ubicación deseada y seleccione **pegar** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="f204d-129">Left-click the menu item that is before the intended new location and press CTRL+V, or right-click the menu item that is before the intended new location and select **Paste** from the shortcut menu.</span></span>  
  
     <span data-ttu-id="f204d-130">El elemento de menú que ha cortado se inserta después del elemento de menú seleccionado.</span><span class="sxs-lookup"><span data-stu-id="f204d-130">The menu item that you cut is inserted after the selected menu item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f204d-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="f204d-131">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [<span data-ttu-id="f204d-132">Información general sobre el control MenuStrip</span><span class="sxs-lookup"><span data-stu-id="f204d-132">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
