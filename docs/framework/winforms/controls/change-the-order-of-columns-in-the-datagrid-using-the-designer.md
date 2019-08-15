---
title: Procedimiento para cambiar el orden de las columnas en el control DataGridView de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], order of
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- data [Windows Forms], displaying
ms.assetid: 7fe52a98-75d6-448c-97a5-65ca2c568c1a
ms.openlocfilehash: bf77cf3705a470bbe00be383f6a5cb2d28bda34d
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039630"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="33f96-102">Procedimiento para cambiar el orden de las columnas en el control DataGridView de formularios Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="33f96-102">How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer</span></span>

<span data-ttu-id="33f96-103">Al enlazar un control <xref:System.Windows.Forms.DataGridView> de Windows Forms a un origen de datos, el orden de presentación de las columnas generadas automáticamente viene determinado por el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="33f96-103">When you bind a Windows Forms <xref:System.Windows.Forms.DataGridView> control to a data source, the display order of the automatically generated columns is dictated by the data source.</span></span> <span data-ttu-id="33f96-104">Si este orden no es el preferido, puede cambiar el orden de las columnas mediante el diseñador.</span><span class="sxs-lookup"><span data-stu-id="33f96-104">If this order is not what you prefer, you can change the order of the columns using the designer.</span></span> <span data-ttu-id="33f96-105">También puede que desee agregar columnas sin enlazar al control y cambiar el orden de visualización.</span><span class="sxs-lookup"><span data-stu-id="33f96-105">You may also want to add unbound columns to the control and change their display order.</span></span> <span data-ttu-id="33f96-106">Para obtener información sobre cómo cambiar el orden de las columnas mediante programación [, consulte Cómo: Cambiar el orden de las columnas en el control](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)DataGridView Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="33f96-106">For information about how to change the column order programmatically, see [How to: Change the Order of Columns in the Windows Forms DataGridView Control](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md).</span></span>

<span data-ttu-id="33f96-107">El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que <xref:System.Windows.Forms.DataGridView> contenga un control.</span><span class="sxs-lookup"><span data-stu-id="33f96-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="33f96-108">Para obtener información acerca de cómo configurar este tipo de [proyecto, consulte Cómo: Cree un proyecto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) de aplicación de [Windows Forms y cómo: Agregue controles a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="33f96-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-change-the-column-order-using-the-designer"></a><span data-ttu-id="33f96-109">Para cambiar el orden de las columnas mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="33f96-109">To change the column order using the designer</span></span>

1. <span data-ttu-id="33f96-110">Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) en la <xref:System.Windows.Forms.DataGridView> esquina superior derecha del control y, a continuación, seleccione **Editar columnas**.</span><span class="sxs-lookup"><span data-stu-id="33f96-110">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>

2. <span data-ttu-id="33f96-111">Seleccione una columna de la lista **columnas seleccionadas** .</span><span class="sxs-lookup"><span data-stu-id="33f96-111">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="33f96-112">Haga clic en la flecha arriba o abajo situada a la derecha de la lista **columnas seleccionadas** hasta que la columna seleccionada se encuentra en la posición deseada.</span><span class="sxs-lookup"><span data-stu-id="33f96-112">Click the up or down arrow to the right of the **Selected Columns** list until the selected column is in the position you want.</span></span>

## <a name="see-also"></a><span data-ttu-id="33f96-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="33f96-113">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="33f96-114">Cómo: Agregar y quitar columnas en el control DataGridView Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="33f96-114">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="33f96-115">Cómo: Crear un proyecto de aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="33f96-115">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="33f96-116">Cómo: Agregar controles a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="33f96-116">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
