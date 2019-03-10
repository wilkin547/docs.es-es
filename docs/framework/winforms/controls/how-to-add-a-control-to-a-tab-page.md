---
title: Filtrar Agregar un Control a una página de ficha
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
ms.openlocfilehash: 6eb509fd10a5000a5423d624cec5b6d126990d73
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57723960"
---
# <a name="how-to-add-a-control-to-a-tab-page"></a><span data-ttu-id="5e1d4-102">Procedimiento Agregar un Control a una página de ficha</span><span class="sxs-lookup"><span data-stu-id="5e1d4-102">How to: Add a Control to a Tab Page</span></span>
<span data-ttu-id="5e1d4-103">Puede usar los formularios de Windows <xref:System.Windows.Forms.TabControl> para mostrar otros controles de forma organizada.</span><span class="sxs-lookup"><span data-stu-id="5e1d4-103">You can use the Windows Forms <xref:System.Windows.Forms.TabControl> to display other controls in an organized fashion.</span></span> <span data-ttu-id="5e1d4-104">El procedimiento siguiente muestra cómo agregar un botón a la primera pestaña. Para obtener información sobre cómo agregar un icono a la parte de la etiqueta de una página de ficha, vea [Cómo: Cambiar la apariencia del control TabControl de formularios de Windows](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md).</span><span class="sxs-lookup"><span data-stu-id="5e1d4-104">The following procedure shows how to add a button to the first tab. For information about adding an icon to the label part of a tab page, see [How to: Change the Appearance of the Windows Forms TabControl](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md).</span></span>  
  
### <a name="to-add-a-control-programmatically"></a><span data-ttu-id="5e1d4-105">Para agregar un control mediante programación</span><span class="sxs-lookup"><span data-stu-id="5e1d4-105">To add a control programmatically</span></span>  
  
1.  <span data-ttu-id="5e1d4-106">Use la <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> método de la colección devuelta por la <xref:System.Windows.Forms.Control.Controls%2A> propiedad de <xref:System.Windows.Forms.TabPage>:</span><span class="sxs-lookup"><span data-stu-id="5e1d4-106">Use the <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> method of the collection returned by the <xref:System.Windows.Forms.Control.Controls%2A> property of <xref:System.Windows.Forms.TabPage>:</span></span>  
  
     [!code-cpp[TabPageControlCollectionHowToAdd#1](~/samples/snippets/cpp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cpp/add.cpp#1)]
     [!code-csharp[TabPageControlCollectionHowToAdd#1](~/samples/snippets/csharp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cs/add.cs#1)]
     [!code-vb[TabPageControlCollectionHowToAdd#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/vb/add.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="5e1d4-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e1d4-107">See also</span></span>
- [<span data-ttu-id="5e1d4-108">TabControl (control)</span><span class="sxs-lookup"><span data-stu-id="5e1d4-108">TabControl Control</span></span>](tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="5e1d4-109">Información general del control TabControl</span><span class="sxs-lookup"><span data-stu-id="5e1d4-109">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="5e1d4-110">Cómo: Cambiar la apariencia del control TabControl de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="5e1d4-110">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
- [<span data-ttu-id="5e1d4-111">Cómo: Deshabilitar páginas de fichas</span><span class="sxs-lookup"><span data-stu-id="5e1d4-111">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="5e1d4-112">Cómo: Agregar y quitar fichas con el control TabControl de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="5e1d4-112">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
