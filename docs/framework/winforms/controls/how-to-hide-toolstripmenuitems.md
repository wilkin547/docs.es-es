---
title: "Cómo: Ocultar ToolStripMenuItems"
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
- cpp
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding
- MenuStrip control [Windows Forms], hiding menu items
- menus [Windows Forms], hiding menu items
- menu items [Windows Forms], hiding
- hiding menu items
ms.assetid: 418a768f-808a-44cd-8cef-f4e161883621
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7cb24fd36bdee76fa80a87d48f41b72f01c8f263
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-hide-toolstripmenuitems"></a><span data-ttu-id="90677-102">Cómo: Ocultar ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="90677-102">How to: Hide ToolStripMenuItems</span></span>
<span data-ttu-id="90677-103">Ocultar elementos de menú es una manera de controlar la interfaz de usuario de la aplicación y restringir los comandos de usuario.</span><span class="sxs-lookup"><span data-stu-id="90677-103">Hiding menu items is a way to control the user interface of your application and restrict user commands.</span></span> <span data-ttu-id="90677-104">A menudo, deseará ocultar un menú completo cuando todos los elementos de menú en el no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="90677-104">Often, you will want to hide an entire menu when all of the menu items on it are unavailable.</span></span> <span data-ttu-id="90677-105">Esto supone menos distracciones para el usuario.</span><span class="sxs-lookup"><span data-stu-id="90677-105">This presents fewer distractions for the user.</span></span> <span data-ttu-id="90677-106">Además, puede ocultar y deshabilitar el menú o el elemento de menú, como si sólo se oculta no impide que el usuario obtener acceso a un comando de menú mediante una tecla de método abreviado.</span><span class="sxs-lookup"><span data-stu-id="90677-106">Furthermore, you might want to both hide and disable the menu or menu item, as hiding alone does not prevent the user from accessing a menu command by using a shortcut key.</span></span>  
  
### <a name="to-hide-any-menu-item-programmatically"></a><span data-ttu-id="90677-107">Para ocultar cualquier elemento de menú mediante programación</span><span class="sxs-lookup"><span data-stu-id="90677-107">To hide any menu item programmatically</span></span>  
  
-   <span data-ttu-id="90677-108">Dentro del método donde estableció las propiedades del elemento de menú, agregue código para establecer el <xref:System.Windows.Forms.ToolStripItem.Visible%2A> propiedad `false`.</span><span class="sxs-lookup"><span data-stu-id="90677-108">Within the method where you set the properties of the menu item, add code to set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property to `false`.</span></span>  
  
    ```vb  
    MenuItem3.Visible = False  
    ```  
  
    ```csharp  
    menuItem3.Visible = false;  
    ```  
  
    ```cpp  
    menuItem3->Visible = false;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="90677-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="90677-109">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripItem.Visible%2A>  
 <xref:System.Windows.Forms.MenuStrip>  
 [<span data-ttu-id="90677-110">Información general sobre el control MenuStrip</span><span class="sxs-lookup"><span data-stu-id="90677-110">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)  
 [<span data-ttu-id="90677-111">Deshabilitar ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="90677-111">How to: Disable ToolStripMenuItems</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems.md)
