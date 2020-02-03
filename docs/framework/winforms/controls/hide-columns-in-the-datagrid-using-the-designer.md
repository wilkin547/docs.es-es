---
title: Ocultar columnas en el control DataGridView mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], hiding
- DataGridView control [Windows Forms], column hiding
- data [Windows Forms], displaying
ms.assetid: a81c38e6-2527-426a-bcb1-be691403be04
ms.openlocfilehash: 3c9a6bdeacbeb5929488e6af0054403db73c4239
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738657"
---
# <a name="how-to-hide-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="b9be5-102">Cómo: Ocultar columnas en el control DataGridView de formularios Windows Forms mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="b9be5-102">How to: Hide Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="b9be5-103">Algunas veces querrá mostrar solo algunas de las columnas que están disponibles en un control <xref:System.Windows.Forms.DataGridView> de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="b9be5-103">Sometimes you will want to display only some of the columns that are available in a Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="b9be5-104">Por ejemplo, puede que desee mostrar una columna de sueldo de empleado a los usuarios con credenciales de administración mientras la ocultan de otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="b9be5-104">For example, you may want to show an employee salary column to users with management credentials while hiding it from other users.</span></span> <span data-ttu-id="b9be5-105">Como alternativa, puede enlazar el control a un origen de datos que contenga muchas columnas, solo algunas de las cuales desea mostrar.</span><span class="sxs-lookup"><span data-stu-id="b9be5-105">Alternately, you may want to bind the control to a data source that contains many columns, only some of which you want to display.</span></span> <span data-ttu-id="b9be5-106">En este caso, normalmente se quitarán las columnas que no le interesa Mostrar en lugar de ocultarlas.</span><span class="sxs-lookup"><span data-stu-id="b9be5-106">In this case, you will typically remove the columns you are not interested in displaying rather than hiding them.</span></span> <span data-ttu-id="b9be5-107">Para obtener más información, vea [Cómo: agregar y quitar columnas en el control DataGridView Windows Forms mediante el diseñador](add-and-remove-columns-in-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="b9be5-107">For more information, see [How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer](add-and-remove-columns-in-the-datagrid-using-the-designer.md).</span></span>

 <span data-ttu-id="b9be5-108">El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que contenga un control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="b9be5-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="b9be5-109">Para obtener información sobre cómo configurar este tipo de proyecto, vea [Cómo: crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="b9be5-109">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-hide-a-column-using-the-designer"></a><span data-ttu-id="b9be5-110">Para ocultar una columna mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="b9be5-110">To hide a column using the designer</span></span>

1. <span data-ttu-id="b9be5-111">Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) en la esquina superior derecha del control <xref:System.Windows.Forms.DataGridView> y, a continuación, seleccione **Editar columnas**.</span><span class="sxs-lookup"><span data-stu-id="b9be5-111">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>

2. <span data-ttu-id="b9be5-112">Seleccione una columna de la lista **columnas seleccionadas** .</span><span class="sxs-lookup"><span data-stu-id="b9be5-112">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="b9be5-113">En la cuadrícula **propiedades de columna** , establezca la propiedad <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> en `false`.</span><span class="sxs-lookup"><span data-stu-id="b9be5-113">In the **Column Properties** grid, set the <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> property to `false`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b9be5-114">También puede ocultar una columna al agregarla desactivando la casilla **visible** en el cuadro de diálogo **Agregar columna** .</span><span class="sxs-lookup"><span data-stu-id="b9be5-114">You can also hide a column when adding it by clearing the **Visible** check box in the **Add Column** dialog box.</span></span>

## <a name="see-also"></a><span data-ttu-id="b9be5-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b9be5-115">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [<span data-ttu-id="b9be5-116">Agregar y quitar columnas en el control DataGridView de Windows Forms mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="b9be5-116">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="b9be5-117">Cómo: crear un proyecto de aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b9be5-117">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="b9be5-118">Cómo: Agregar controles a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b9be5-118">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
