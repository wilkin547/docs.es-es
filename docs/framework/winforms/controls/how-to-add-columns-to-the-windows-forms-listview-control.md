---
title: Filtrar para agregar columnas al control ListView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
- list views [Windows Forms], adding columns
ms.assetid: 79174274-12ee-4a5d-80db-6ec02976d010
ms.openlocfilehash: 5c87d43513f2125945145445c61f689cdd9d2aaf
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59345747"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control"></a><span data-ttu-id="8dc2e-102">Filtrar para agregar columnas al control ListView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8dc2e-102">How to: Add Columns to the Windows Forms ListView Control</span></span>
<span data-ttu-id="8dc2e-103">En la vista de detalles, el <xref:System.Windows.Forms.ListView> control puede mostrar varias columnas para cada elemento de lista.</span><span class="sxs-lookup"><span data-stu-id="8dc2e-103">In the Details view, the <xref:System.Windows.Forms.ListView> control can display multiple columns for each list item.</span></span> <span data-ttu-id="8dc2e-104">Puede usar las columnas para mostrar al usuario a varios tipos de información sobre cada elemento de lista.</span><span class="sxs-lookup"><span data-stu-id="8dc2e-104">You can use the columns to display to the user several types of information about each list item.</span></span> <span data-ttu-id="8dc2e-105">Por ejemplo, una lista de archivos podría mostrar el nombre de archivo, tipo de archivo, tamaño y fecha de que última modificación del archivo.</span><span class="sxs-lookup"><span data-stu-id="8dc2e-105">For example, a list of files could display the file name, file type, size, and date the file was last modified.</span></span> <span data-ttu-id="8dc2e-106">Para obtener información acerca de cómo rellenar las columnas después de crearlos, vea [Cómo: Mostrar subelementos en columnas con el Windows Forms Control ListView](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).</span><span class="sxs-lookup"><span data-stu-id="8dc2e-106">For information about populating the columns after they are created, see [How to: Display Subitems in Columns with the Windows Forms ListView Control](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).</span></span>  
  
### <a name="to-add-columns-programmatically"></a><span data-ttu-id="8dc2e-107">Para agregar columnas mediante programación</span><span class="sxs-lookup"><span data-stu-id="8dc2e-107">To add columns programmatically</span></span>  
  
1. <span data-ttu-id="8dc2e-108">Establecer el control <xref:System.Windows.Forms.ListView.View%2A> propiedad <xref:System.Windows.Forms.View.Details>.</span><span class="sxs-lookup"><span data-stu-id="8dc2e-108">Set the control's <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>  
  
2. <span data-ttu-id="8dc2e-109">Use la <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> método de la vista de lista <xref:System.Windows.Forms.ListView.Columns%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="8dc2e-109">Use the <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> method of the list view's <xref:System.Windows.Forms.ListView.Columns%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="8dc2e-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="8dc2e-110">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- [<span data-ttu-id="8dc2e-111">Control ListView</span><span class="sxs-lookup"><span data-stu-id="8dc2e-111">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="8dc2e-112">Información general sobre el control ListView</span><span class="sxs-lookup"><span data-stu-id="8dc2e-112">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
