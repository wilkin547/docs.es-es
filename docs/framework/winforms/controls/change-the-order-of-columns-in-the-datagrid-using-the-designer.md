---
title: Cambiar el orden de las columnas en el control DataGridView mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], order of
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- data [Windows Forms], displaying
ms.assetid: 7fe52a98-75d6-448c-97a5-65ca2c568c1a
ms.openlocfilehash: 7540203fb1c0465caeb045275734d1a7c6f25ee8
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628753"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="8d4e0-102">Cómo: Cambiar el orden de las columnas en el control DataGridView de formularios Windows Forms mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="8d4e0-102">How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer</span></span>

<span data-ttu-id="8d4e0-103">Al enlazar un Windows Forms <xref:System.Windows.Forms.DataGridView> control a un origen de datos, el orden de presentación de las columnas generadas automáticamente viene determinado por el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="8d4e0-103">When you bind a Windows Forms <xref:System.Windows.Forms.DataGridView> control to a data source, the display order of the automatically generated columns is dictated by the data source.</span></span> <span data-ttu-id="8d4e0-104">Si este orden no es el preferido, puede cambiar el orden de las columnas mediante el diseñador.</span><span class="sxs-lookup"><span data-stu-id="8d4e0-104">If this order is not what you prefer, you can change the order of the columns using the designer.</span></span> <span data-ttu-id="8d4e0-105">También puede que desee agregar columnas sin enlazar al control y cambiar el orden de visualización.</span><span class="sxs-lookup"><span data-stu-id="8d4e0-105">You may also want to add unbound columns to the control and change their display order.</span></span> <span data-ttu-id="8d4e0-106">Para obtener información sobre cómo cambiar el orden de las columnas mediante programación, vea [Cómo: cambiar el orden de las columnas en el control DataGridView Windows Forms](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="8d4e0-106">For information about how to change the column order programmatically, see [How to: Change the Order of Columns in the Windows Forms DataGridView Control](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md).</span></span>

<span data-ttu-id="8d4e0-107">El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que contenga un control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="8d4e0-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="8d4e0-108">Para obtener información sobre cómo configurar este tipo de proyecto, vea [Cómo: crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="8d4e0-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-change-the-column-order-using-the-designer"></a><span data-ttu-id="8d4e0-109">Para cambiar el orden de las columnas mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="8d4e0-109">To change the column order using the designer</span></span>

1. <span data-ttu-id="8d4e0-110">Haga clic en el glifo de acciones del diseñador (![flecha negra pequeña](./media/designer-actions-glyph.gif)) en la esquina superior derecha del control <xref:System.Windows.Forms.DataGridView> y, a continuación, seleccione **Editar columnas**.</span><span class="sxs-lookup"><span data-stu-id="8d4e0-110">Click the designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>

2. <span data-ttu-id="8d4e0-111">Seleccione una columna de la lista **columnas seleccionadas** .</span><span class="sxs-lookup"><span data-stu-id="8d4e0-111">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="8d4e0-112">Haga clic en la flecha arriba o abajo situada a la derecha de la lista **columnas seleccionadas** hasta que la columna seleccionada se encuentra en la posición deseada.</span><span class="sxs-lookup"><span data-stu-id="8d4e0-112">Click the up or down arrow to the right of the **Selected Columns** list until the selected column is in the position you want.</span></span>

## <a name="see-also"></a><span data-ttu-id="8d4e0-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8d4e0-113">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="8d4e0-114">Agregar y quitar columnas en el control DataGridView de Windows Forms mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="8d4e0-114">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="8d4e0-115">Cómo: crear un proyecto de aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8d4e0-115">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="8d4e0-116">Cómo: Agregar controles a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8d4e0-116">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
