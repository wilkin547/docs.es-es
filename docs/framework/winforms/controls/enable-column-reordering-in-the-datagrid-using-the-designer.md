---
title: Habilitar la reordenación de columnas en el control DataGridView mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- columns [Windows Forms], reordering
- data [Windows Forms], displaying
ms.assetid: d82bd69c-6799-4439-a32c-91139c5901d1
ms.openlocfilehash: 14dc1081a8608c6e6add67f641c4b55825d2fc81
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "77626976"
---
# <a name="how-to-enable-column-reordering-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="c5e17-102">Cómo: Habilitar la reordenación de columnas en el control DataGridView de formularios Windows Forms mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="c5e17-102">How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="c5e17-103">Al ver los datos mostrados en un control de <xref:System.Windows.Forms.DataGridView> de Windows Forms, a veces los usuarios desean comparar los valores de columnas específicas.</span><span class="sxs-lookup"><span data-stu-id="c5e17-103">When viewing data displayed in a Windows Forms <xref:System.Windows.Forms.DataGridView> control, users sometimes want to compare the values in specific columns.</span></span> <span data-ttu-id="c5e17-104">Esto puede ser inconveniente si las columnas están ampliamente separadas en el control, especialmente si los usuarios deben desplazarse horizontalmente para ver todas las columnas en las que están interesados.</span><span class="sxs-lookup"><span data-stu-id="c5e17-104">This can be inconvenient if the columns are widely separated in the control, especially if users must scroll back and forth horizontally in order to see all the columns they are interested in.</span></span> <span data-ttu-id="c5e17-105">Puede facilitar la tarea de comparar los valores de columna si permite que los usuarios reordenen las columnas.</span><span class="sxs-lookup"><span data-stu-id="c5e17-105">You can make the task of comparing column values easier by enabling your users to reorder the columns.</span></span> <span data-ttu-id="c5e17-106">Al habilitar la reordenación de columnas, los usuarios pueden mover una columna a una nueva posición arrastrando el encabezado de columna con el mouse.</span><span class="sxs-lookup"><span data-stu-id="c5e17-106">When you enable column reordering, users can move a column to a new position by dragging the column header with the mouse.</span></span>

 <span data-ttu-id="c5e17-107">El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que contenga un control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="c5e17-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="c5e17-108">Para obtener información sobre cómo configurar este tipo de proyecto, vea [Cómo: crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="c5e17-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-enable-column-reordering"></a><span data-ttu-id="c5e17-109">Para habilitar la reordenación de columnas</span><span class="sxs-lookup"><span data-stu-id="c5e17-109">To enable column reordering</span></span>

- <span data-ttu-id="c5e17-110">Haga clic en el glifo de acciones del diseñador (![flecha negra pequeña](./media/designer-actions-glyph.gif)) en la esquina superior derecha del control <xref:System.Windows.Forms.DataGridView> y, a continuación, seleccione **Habilitar reordenación de columnas**.</span><span class="sxs-lookup"><span data-stu-id="c5e17-110">Click the designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Enable Column Reordering**.</span></span>

## <a name="see-also"></a><span data-ttu-id="c5e17-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c5e17-111">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType>
- [<span data-ttu-id="c5e17-112">Inmovilizar columnas en el control DataGridView de Windows Forms mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="c5e17-112">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](freeze-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="c5e17-113">Cómo: crear un proyecto de aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c5e17-113">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="c5e17-114">Cómo: Agregar controles a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c5e17-114">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
