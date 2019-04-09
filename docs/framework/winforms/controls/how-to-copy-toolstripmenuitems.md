---
title: Filtrar para copiar ToolStripMenuItems
ms.date: 03/30/2017
helpviewer_keywords:
- menu items [Windows Forms], copying and pasting
- MenuStrip control [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], copying and pasting
ms.assetid: 17ef4207-e92e-4db2-b648-27246e6517ad
ms.openlocfilehash: 94dc1271468661801d07b341214b03bc31bb3099
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59116355"
---
# <a name="how-to-copy-toolstripmenuitems"></a><span data-ttu-id="9652f-102">Filtrar para copiar ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="9652f-102">How to: Copy ToolStripMenuItems</span></span>
<span data-ttu-id="9652f-103">Durante el diseño, puede copiar menús de nivel superior completos y sus elementos de submenú en un lugar diferente en la <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="9652f-103">At design time, you can copy entire top-level menus and their submenu items to a different place on the <xref:System.Windows.Forms.MenuStrip>.</span></span> <span data-ttu-id="9652f-104">También puede copiar elementos de menú individuales entre los menús de nivel superior o cambiar la posición de los elementos de menú dentro de un menú.</span><span class="sxs-lookup"><span data-stu-id="9652f-104">You can also copy individual menu items between top-level menus or change the position of menu items within a menu.</span></span>  
  
### <a name="to-copy-a-top-level-menu-and-its-submenu-items-to-another-top-level-location"></a><span data-ttu-id="9652f-105">Para copiar un menú de nivel superior y sus elementos de submenú en otra ubicación de nivel superior</span><span class="sxs-lookup"><span data-stu-id="9652f-105">To copy a top-level menu and its submenu items to another top-level location</span></span>  
  
1.  <span data-ttu-id="9652f-106">Haga clic en el menú que desea copiar y presione CTRL+C o haga clic con el botón derecho en el menú y seleccione **Copiar** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="9652f-106">Left-click the menu that you want to copy and press CTRL+C, or right-click the menu and select **Copy** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="9652f-107">Haga clic en el menú de nivel superior que está después de la nueva ubicación deseada y presione CTRL+V o haga clic con el botón derecho en el elemento de menú de nivel superior anterior a la nueva ubicación deseada y seleccione **Pegar** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="9652f-107">Left-click the top-level menu that is after the intended new location and press CTRL+V, or right-click the top-level menu item that is before the intended new location and select **Paste** from the shortcut menu.</span></span>  
  
     <span data-ttu-id="9652f-108">El menú copiado se inserta delante del menú de nivel superior seleccionado.</span><span class="sxs-lookup"><span data-stu-id="9652f-108">The menu that you copied is inserted before the selected top-level menu.</span></span>  
  
### <a name="to-copy-a-top-level-menu-and-its-submenu-items-to-a-drop-down-location"></a><span data-ttu-id="9652f-109">Para copiar un menú de nivel superior y sus elementos de submenú en una ubicación desplegable</span><span class="sxs-lookup"><span data-stu-id="9652f-109">To copy a top-level menu and its submenu items to a drop-down location</span></span>  
  
1.  <span data-ttu-id="9652f-110">Haga clic en el menú que desea mover y presione CTRL+C o haga clic con el botón derecho en el menú y seleccione **Copiar** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="9652f-110">Left-click the menu that you want to move and press CTRL+C, or right-click the menu and select **Copy** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="9652f-111">En el menú de nivel superior de destino, haga clic en el elemento de submenú que está encima de la nueva ubicación deseada y presione CTRL+V o haga clic con el botón derecho en el elemento de submenú que está encima de la nueva ubicación deseada y seleccione **Pegar** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="9652f-111">In the destination top-level menu, left-click the submenu item that is above the intended new location and press CTRL+V, or right-click the submenu item that is above the intended new location and select **Paste** from the shortcut menu.</span></span>  
  
     <span data-ttu-id="9652f-112">El menú copiado se inserta delante del elemento de submenú seleccionado.</span><span class="sxs-lookup"><span data-stu-id="9652f-112">The menu that you copied is inserted before the selected submenu item.</span></span>  
  
### <a name="to-copy-a-submenu-item-to-another-menu"></a><span data-ttu-id="9652f-113">Para copiar un elemento de submenú en otro menú</span><span class="sxs-lookup"><span data-stu-id="9652f-113">To copy a submenu item to another menu</span></span>  
  
1.  <span data-ttu-id="9652f-114">Haga clic en el elemento de submenú que desea copiar y presione CTRL+C o haga clic con el botón derecho en el elemento de submenú y seleccione **Copiar** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="9652f-114">Left-click the submenu item that you want to copy and press CTRL+C, or right-click the submenu item and choose **Copy** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="9652f-115">Haga clic en el menú que contendrá el elemento de submenú que ha cortado.</span><span class="sxs-lookup"><span data-stu-id="9652f-115">Left-click the menu that will contain the submenu item that you cut.</span></span>  
  
3.  <span data-ttu-id="9652f-116">Haga clic en el elemento de submenú que está antes de la nueva ubicación deseada y presione CTRL+V o haga clic con el botón derecho en el elemento de submenú anterior a la nueva ubicación deseada y seleccione **Pegar** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="9652f-116">Left-click the submenu item that is before the intended new location and press CTRL+V, or right-click the submenu item that is before the intended new location and select **Paste** from the shortcut menu.</span></span>  
  
     <span data-ttu-id="9652f-117">El elemento de submenú copiado se inserta delante del elemento de submenú seleccionado.</span><span class="sxs-lookup"><span data-stu-id="9652f-117">The submenu item that you copied is inserted before the selected submenu item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9652f-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="9652f-118">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="9652f-119">Información general sobre el control MenuStrip</span><span class="sxs-lookup"><span data-stu-id="9652f-119">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
