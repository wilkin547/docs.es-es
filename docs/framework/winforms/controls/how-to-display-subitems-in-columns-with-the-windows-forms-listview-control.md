---
title: Mostrar subelementos en columnas con el control ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items
- Details view
- ListView control [Windows Forms], adding ListSubItems
- subitems
ms.assetid: e465f044-cde7-4fd9-a687-788a73a0f554
ms.openlocfilehash: 5c6d807410ad4ee0198d6334844bd65b148edff4
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745546"
---
# <a name="how-to-display-subitems-in-columns-with-the-windows-forms-listview-control"></a><span data-ttu-id="0436d-102">Cómo: Mostrar subelementos en columnas con el control ListView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0436d-102">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>
<span data-ttu-id="0436d-103">El control Windows Forms <xref:System.Windows.Forms.ListView> puede mostrar texto adicional, o subelementos, para cada elemento en la vista de detalles.</span><span class="sxs-lookup"><span data-stu-id="0436d-103">The Windows Forms <xref:System.Windows.Forms.ListView> control can display additional text, or subitems, for each item in the Details view.</span></span> <span data-ttu-id="0436d-104">La primera columna muestra el texto del elemento, por ejemplo un número de empleado.</span><span class="sxs-lookup"><span data-stu-id="0436d-104">The first column displays the item text, for example an employee number.</span></span> <span data-ttu-id="0436d-105">Las columnas segunda, tercera y subsiguientes muestran el primer, segundo y subelementos asociados posteriores.</span><span class="sxs-lookup"><span data-stu-id="0436d-105">The second, third, and subsequent columns display the first, second, and subsequent associated subitems.</span></span>  
  
### <a name="to-add-subitems-to-a-list-item"></a><span data-ttu-id="0436d-106">Para agregar subelementos a un elemento de lista</span><span class="sxs-lookup"><span data-stu-id="0436d-106">To add subitems to a list item</span></span>  
  
1. <span data-ttu-id="0436d-107">Agregue las columnas necesarias.</span><span class="sxs-lookup"><span data-stu-id="0436d-107">Add any columns needed.</span></span> <span data-ttu-id="0436d-108">Dado que la primera columna mostrará la propiedad <xref:System.Windows.Forms.ListView.Text%2A> del elemento, se necesita una columna más que los subelementos.</span><span class="sxs-lookup"><span data-stu-id="0436d-108">Because the first column will display the item's <xref:System.Windows.Forms.ListView.Text%2A> property, you need one more column than there are subitems.</span></span> <span data-ttu-id="0436d-109">Para obtener más información sobre cómo agregar columnas, vea [Cómo: Agregar columnas al control ListView de Windows Forms](how-to-add-columns-to-the-windows-forms-listview-control.md).</span><span class="sxs-lookup"><span data-stu-id="0436d-109">For more information on adding columns, see [How to: Add Columns to the Windows Forms ListView Control](how-to-add-columns-to-the-windows-forms-listview-control.md).</span></span>  
  
2. <span data-ttu-id="0436d-110">Llame al método <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> de la colección devuelta por la propiedad <xref:System.Windows.Forms.ListViewItem.SubItems%2A> de un elemento.</span><span class="sxs-lookup"><span data-stu-id="0436d-110">Call the <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> method of the collection returned by the <xref:System.Windows.Forms.ListViewItem.SubItems%2A> property of an item.</span></span> <span data-ttu-id="0436d-111">En el ejemplo de código siguiente se establece el nombre del empleado y el Departamento para un elemento de lista.</span><span class="sxs-lookup"><span data-stu-id="0436d-111">The code example below sets the employee name and department for a list item.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#61)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#61)]  
  
## <a name="see-also"></a><span data-ttu-id="0436d-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="0436d-112">See also</span></span>

- [<span data-ttu-id="0436d-113">Información general del control ListView</span><span class="sxs-lookup"><span data-stu-id="0436d-113">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="0436d-114">Agregar y quitar elementos con el control ListView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0436d-114">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="0436d-115">Agregar columnas al control ListView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0436d-115">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [<span data-ttu-id="0436d-116">Mostrar iconos del control ListView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0436d-116">How to: Display Icons for the Windows Forms ListView Control</span></span>](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [<span data-ttu-id="0436d-117">Agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="0436d-117">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
