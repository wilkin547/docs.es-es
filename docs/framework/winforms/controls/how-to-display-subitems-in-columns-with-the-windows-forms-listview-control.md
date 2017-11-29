---
title: "Cómo: Mostrar subelementos en columnas con el control ListView de formularios Windows Forms"
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
helpviewer_keywords:
- list items
- Details view
- ListView control [Windows Forms], adding ListSubItems
- subitems
ms.assetid: e465f044-cde7-4fd9-a687-788a73a0f554
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: be1b055c8ea0e7a7c6466033735431a17ecc32f6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-subitems-in-columns-with-the-windows-forms-listview-control"></a><span data-ttu-id="feb10-102">Cómo: Mostrar subelementos en columnas con el control ListView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="feb10-102">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>
<span data-ttu-id="feb10-103">Los formularios Windows Forms <xref:System.Windows.Forms.ListView> control puede mostrar texto adicional o subelementos, para cada elemento de la vista de detalles.</span><span class="sxs-lookup"><span data-stu-id="feb10-103">The Windows Forms <xref:System.Windows.Forms.ListView> control can display additional text, or subitems, for each item in the Details view.</span></span> <span data-ttu-id="feb10-104">La primera columna muestra el texto del elemento, por ejemplo un número de empleado.</span><span class="sxs-lookup"><span data-stu-id="feb10-104">The first column displays the item text, for example an employee number.</span></span> <span data-ttu-id="feb10-105">La segunda, terceros y siguientes columnas muestran el primero, segundo y siguientes subelementos asociados.</span><span class="sxs-lookup"><span data-stu-id="feb10-105">The second, third, and subsequent columns display the first, second, and subsequent associated subitems.</span></span>  
  
### <a name="to-add-subitems-to-a-list-item"></a><span data-ttu-id="feb10-106">Para agregar subelementos a un elemento de lista</span><span class="sxs-lookup"><span data-stu-id="feb10-106">To add subitems to a list item</span></span>  
  
1.  <span data-ttu-id="feb10-107">Agregue las columnas necesarias.</span><span class="sxs-lookup"><span data-stu-id="feb10-107">Add any columns needed.</span></span> <span data-ttu-id="feb10-108">Dado que la primera columna mostrará el elemento <xref:System.Windows.Forms.ListView.Text%2A> propiedad, se necesita una columna más que el número de subelementos.</span><span class="sxs-lookup"><span data-stu-id="feb10-108">Because the first column will display the item's <xref:System.Windows.Forms.ListView.Text%2A> property, you need one more column than there are subitems.</span></span> <span data-ttu-id="feb10-109">Para obtener más información sobre cómo agregar columnas, vea [Cómo: agregar columnas al ListView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md).</span><span class="sxs-lookup"><span data-stu-id="feb10-109">For more information on adding columns, see [How to: Add Columns to the Windows Forms ListView Control](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md).</span></span>  
  
2.  <span data-ttu-id="feb10-110">Llame a la <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> método de la colección devuelta por la <xref:System.Windows.Forms.ListViewItem.SubItems%2A> propiedad de un elemento.</span><span class="sxs-lookup"><span data-stu-id="feb10-110">Call the <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> method of the collection returned by the <xref:System.Windows.Forms.ListViewItem.SubItems%2A> property of an item.</span></span> <span data-ttu-id="feb10-111">El ejemplo de código siguiente establece el nombre de empleado y el departamento para un elemento de lista.</span><span class="sxs-lookup"><span data-stu-id="feb10-111">The code example below sets the employee name and department for a list item.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#61)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#61)]  
  
## <a name="see-also"></a><span data-ttu-id="feb10-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="feb10-112">See Also</span></span>  
 [<span data-ttu-id="feb10-113">Información general del control ListView</span><span class="sxs-lookup"><span data-stu-id="feb10-113">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [<span data-ttu-id="feb10-114">Agregar y quitar elementos con el control ListView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="feb10-114">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="feb10-115">Agregar columnas al control ListView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="feb10-115">How to: Add Columns to the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="feb10-116">Mostrar iconos del control ListView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="feb10-116">How to: Display Icons for the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="feb10-117">Agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="feb10-117">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
