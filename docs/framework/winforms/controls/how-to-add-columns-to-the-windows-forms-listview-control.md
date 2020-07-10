---
title: Agregar columnas al control ListView
description: Obtenga información sobre cómo agregar columnas al control Windows Forms ListView para mostrar varios tipos de información sobre cada elemento de lista.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
- list views [Windows Forms], adding columns
ms.assetid: 79174274-12ee-4a5d-80db-6ec02976d010
ms.openlocfilehash: 7ca4e86ca3a9679876f2525c49596534f175096a
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174567"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control"></a><span data-ttu-id="b8262-103">Procedimiento para agregar columnas al control ListView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b8262-103">How to: Add Columns to the Windows Forms ListView Control</span></span>
<span data-ttu-id="b8262-104">En la vista de detalles, el <xref:System.Windows.Forms.ListView> control puede mostrar varias columnas para cada elemento de la lista.</span><span class="sxs-lookup"><span data-stu-id="b8262-104">In the Details view, the <xref:System.Windows.Forms.ListView> control can display multiple columns for each list item.</span></span> <span data-ttu-id="b8262-105">Puede usar las columnas para mostrar al usuario varios tipos de información sobre cada elemento de la lista.</span><span class="sxs-lookup"><span data-stu-id="b8262-105">You can use the columns to display to the user several types of information about each list item.</span></span> <span data-ttu-id="b8262-106">Por ejemplo, una lista de archivos podría mostrar el nombre de archivo, el tipo de archivo, el tamaño y la fecha en que se modificó el archivo por última vez.</span><span class="sxs-lookup"><span data-stu-id="b8262-106">For example, a list of files could display the file name, file type, size, and date the file was last modified.</span></span> <span data-ttu-id="b8262-107">Para obtener información sobre cómo rellenar las columnas una vez creadas, vea [Cómo: Mostrar subelementos en columnas con el control ListView Windows Forms](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).</span><span class="sxs-lookup"><span data-stu-id="b8262-107">For information about populating the columns after they are created, see [How to: Display Subitems in Columns with the Windows Forms ListView Control](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).</span></span>  
  
### <a name="to-add-columns-programmatically"></a><span data-ttu-id="b8262-108">Para agregar columnas mediante programación</span><span class="sxs-lookup"><span data-stu-id="b8262-108">To add columns programmatically</span></span>  
  
1. <span data-ttu-id="b8262-109">Establezca la propiedad del control <xref:System.Windows.Forms.ListView.View%2A> en <xref:System.Windows.Forms.View.Details> .</span><span class="sxs-lookup"><span data-stu-id="b8262-109">Set the control's <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>  
  
2. <span data-ttu-id="b8262-110">Use el <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> método de la propiedad de la vista de lista <xref:System.Windows.Forms.ListView.Columns%2A> .</span><span class="sxs-lookup"><span data-stu-id="b8262-110">Use the <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> method of the list view's <xref:System.Windows.Forms.ListView.Columns%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="b8262-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8262-111">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- [<span data-ttu-id="b8262-112">Control ListView</span><span class="sxs-lookup"><span data-stu-id="b8262-112">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="b8262-113">Información general sobre el control ListView</span><span class="sxs-lookup"><span data-stu-id="b8262-113">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
