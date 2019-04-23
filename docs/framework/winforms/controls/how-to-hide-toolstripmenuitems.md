---
title: Procedimiento para ocultar ToolStripMenuItems
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding
- MenuStrip control [Windows Forms], hiding menu items
- menus [Windows Forms], hiding menu items
- menu items [Windows Forms], hiding
- hiding menu items
ms.assetid: 418a768f-808a-44cd-8cef-f4e161883621
ms.openlocfilehash: dc9daa945f2a546548f2cc6ea033378bd9ceff93
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59127431"
---
# <a name="how-to-hide-toolstripmenuitems"></a><span data-ttu-id="eebe1-102">Procedimiento para ocultar ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="eebe1-102">How to: Hide ToolStripMenuItems</span></span>
<span data-ttu-id="eebe1-103">Ocultar elementos de menú es una manera de controlar la interfaz de usuario de la aplicación y restringir los comandos de usuario.</span><span class="sxs-lookup"><span data-stu-id="eebe1-103">Hiding menu items is a way to control the user interface of your application and restrict user commands.</span></span> <span data-ttu-id="eebe1-104">A menudo, deseará ocultar un menú completo cuando no están disponibles todos los elementos de menú en él.</span><span class="sxs-lookup"><span data-stu-id="eebe1-104">Often, you will want to hide an entire menu when all of the menu items on it are unavailable.</span></span> <span data-ttu-id="eebe1-105">Esto supone menos distracciones para el usuario.</span><span class="sxs-lookup"><span data-stu-id="eebe1-105">This presents fewer distractions for the user.</span></span> <span data-ttu-id="eebe1-106">Además, es posible que desea ocultar y deshabilitar el menú o elemento de menú, como ocultar por sí solo no impide que el usuario acceso a un comando de menú mediante una tecla de método abreviado.</span><span class="sxs-lookup"><span data-stu-id="eebe1-106">Furthermore, you might want to both hide and disable the menu or menu item, as hiding alone does not prevent the user from accessing a menu command by using a shortcut key.</span></span>  
  
### <a name="to-hide-any-menu-item-programmatically"></a><span data-ttu-id="eebe1-107">Para ocultar cualquier elemento de menú mediante programación</span><span class="sxs-lookup"><span data-stu-id="eebe1-107">To hide any menu item programmatically</span></span>  
  
-   <span data-ttu-id="eebe1-108">Dentro del método donde estableció las propiedades del elemento de menú, agregue código para establecer el <xref:System.Windows.Forms.ToolStripItem.Visible%2A> propiedad `false`.</span><span class="sxs-lookup"><span data-stu-id="eebe1-108">Within the method where you set the properties of the menu item, add code to set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property to `false`.</span></span>  
  
    ```vb  
    MenuItem3.Visible = False  
    ```  
  
    ```csharp  
    menuItem3.Visible = false;  
    ```  
  
    ```cpp  
    menuItem3->Visible = false;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="eebe1-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="eebe1-109">See also</span></span>

- <xref:System.Windows.Forms.ToolStripItem.Visible%2A>
- <xref:System.Windows.Forms.MenuStrip>
- [<span data-ttu-id="eebe1-110">Información general sobre el control MenuStrip</span><span class="sxs-lookup"><span data-stu-id="eebe1-110">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
- [<span data-ttu-id="eebe1-111">Cómo: Deshabilitar ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="eebe1-111">How to: Disable ToolStripMenuItems</span></span>](how-to-disable-toolstripmenuitems.md)
