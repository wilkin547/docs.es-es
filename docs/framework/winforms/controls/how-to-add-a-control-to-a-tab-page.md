---
title: Filtrar para agregar un control a una ficha
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TabPage control
- tab controls [Windows Forms], tab order
- tab pages [Windows Forms], adding controls
ms.assetid: b092532e-7346-469f-b9a1-897f9bea4fb7
ms.openlocfilehash: b42845ab996c0985fe6a48ac588e6d706905faac
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59195857"
---
# <a name="how-to-add-a-control-to-a-tab-page"></a><span data-ttu-id="bab6d-102">Filtrar para agregar un control a una ficha</span><span class="sxs-lookup"><span data-stu-id="bab6d-102">How to: Add a Control to a Tab Page</span></span>
<span data-ttu-id="bab6d-103">Puede usar los formularios de Windows <xref:System.Windows.Forms.TabControl> para mostrar otros controles de forma organizada.</span><span class="sxs-lookup"><span data-stu-id="bab6d-103">You can use the Windows Forms <xref:System.Windows.Forms.TabControl> to display other controls in an organized fashion.</span></span> <span data-ttu-id="bab6d-104">El procedimiento siguiente muestra cómo agregar un botón a la primera pestaña. Para obtener información sobre cómo agregar un icono a la parte de la etiqueta de una página de ficha, vea [Cómo: Cambiar la apariencia del control TabControl de formularios de Windows](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md).</span><span class="sxs-lookup"><span data-stu-id="bab6d-104">The following procedure shows how to add a button to the first tab. For information about adding an icon to the label part of a tab page, see [How to: Change the Appearance of the Windows Forms TabControl](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md).</span></span>  
  
### <a name="to-add-a-control-programmatically"></a><span data-ttu-id="bab6d-105">Para agregar un control mediante programación</span><span class="sxs-lookup"><span data-stu-id="bab6d-105">To add a control programmatically</span></span>  
  
1.  <span data-ttu-id="bab6d-106">Use la <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> método de la colección devuelta por la <xref:System.Windows.Forms.Control.Controls%2A> propiedad de <xref:System.Windows.Forms.TabPage>:</span><span class="sxs-lookup"><span data-stu-id="bab6d-106">Use the <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> method of the collection returned by the <xref:System.Windows.Forms.Control.Controls%2A> property of <xref:System.Windows.Forms.TabPage>:</span></span>  
  
     [!code-cpp[TabPageControlCollectionHowToAdd#1](~/samples/snippets/cpp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cpp/add.cpp#1)]
     [!code-csharp[TabPageControlCollectionHowToAdd#1](~/samples/snippets/csharp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cs/add.cs#1)]
     [!code-vb[TabPageControlCollectionHowToAdd#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/vb/add.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="bab6d-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="bab6d-107">See also</span></span>

- [<span data-ttu-id="bab6d-108">TabControl (Control)</span><span class="sxs-lookup"><span data-stu-id="bab6d-108">TabControl Control</span></span>](tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="bab6d-109">Información general sobre el control TabControl</span><span class="sxs-lookup"><span data-stu-id="bab6d-109">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="bab6d-110">Filtrar para cambiar el aspecto apariencia del control TabControl de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bab6d-110">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
- [<span data-ttu-id="bab6d-111">Filtrar para deshabilitar fichas</span><span class="sxs-lookup"><span data-stu-id="bab6d-111">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="bab6d-112">Filtrar para agregar y quitar fichas con el control TabControl de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bab6d-112">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
