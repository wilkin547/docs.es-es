---
title: Agregar columnas al control ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
- list views [Windows Forms], adding columns
ms.assetid: 79174274-12ee-4a5d-80db-6ec02976d010
ms.openlocfilehash: dd438ffbadddfc37ec9eb15e59a908bb58472a45
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744581"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control"></a><span data-ttu-id="fd28f-102">Cómo: Agregar columnas al control ListView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fd28f-102">How to: Add Columns to the Windows Forms ListView Control</span></span>
<span data-ttu-id="fd28f-103">En la vista de detalles, el control <xref:System.Windows.Forms.ListView> puede mostrar varias columnas para cada elemento de la lista.</span><span class="sxs-lookup"><span data-stu-id="fd28f-103">In the Details view, the <xref:System.Windows.Forms.ListView> control can display multiple columns for each list item.</span></span> <span data-ttu-id="fd28f-104">Puede usar las columnas para mostrar al usuario varios tipos de información sobre cada elemento de la lista.</span><span class="sxs-lookup"><span data-stu-id="fd28f-104">You can use the columns to display to the user several types of information about each list item.</span></span> <span data-ttu-id="fd28f-105">Por ejemplo, una lista de archivos podría mostrar el nombre de archivo, el tipo de archivo, el tamaño y la fecha en que se modificó el archivo por última vez.</span><span class="sxs-lookup"><span data-stu-id="fd28f-105">For example, a list of files could display the file name, file type, size, and date the file was last modified.</span></span> <span data-ttu-id="fd28f-106">Para obtener información sobre cómo rellenar las columnas una vez creadas, vea [Cómo: Mostrar subelementos en columnas con el control ListView Windows Forms](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).</span><span class="sxs-lookup"><span data-stu-id="fd28f-106">For information about populating the columns after they are created, see [How to: Display Subitems in Columns with the Windows Forms ListView Control](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).</span></span>  
  
### <a name="to-add-columns-programmatically"></a><span data-ttu-id="fd28f-107">Para agregar columnas mediante programación</span><span class="sxs-lookup"><span data-stu-id="fd28f-107">To add columns programmatically</span></span>  
  
1. <span data-ttu-id="fd28f-108">Establezca la propiedad <xref:System.Windows.Forms.ListView.View%2A> del control en <xref:System.Windows.Forms.View.Details>.</span><span class="sxs-lookup"><span data-stu-id="fd28f-108">Set the control's <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>  
  
2. <span data-ttu-id="fd28f-109">Use el método <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> de la propiedad <xref:System.Windows.Forms.ListView.Columns%2A> de la vista de lista.</span><span class="sxs-lookup"><span data-stu-id="fd28f-109">Use the <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> method of the list view's <xref:System.Windows.Forms.ListView.Columns%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="fd28f-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd28f-110">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- [<span data-ttu-id="fd28f-111">ListView (control)</span><span class="sxs-lookup"><span data-stu-id="fd28f-111">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="fd28f-112">Información general del control ListView</span><span class="sxs-lookup"><span data-stu-id="fd28f-112">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
