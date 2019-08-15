---
title: Procedimiento para ocultar columnas en el control DataGridView de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], hiding
- DataGridView control [Windows Forms], column hiding
- data [Windows Forms], displaying
ms.assetid: a81c38e6-2527-426a-bcb1-be691403be04
ms.openlocfilehash: d502a89913e108254848151e9058ac6ae83a9638
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039768"
---
# <a name="how-to-hide-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="f22af-102">Procedimiento para ocultar columnas en el control DataGridView de formularios Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="f22af-102">How to: Hide Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="f22af-103">Algunas veces querrá mostrar solo algunas de las columnas que están disponibles en un control <xref:System.Windows.Forms.DataGridView> de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f22af-103">Sometimes you will want to display only some of the columns that are available in a Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="f22af-104">Por ejemplo, puede que desee mostrar una columna de sueldo de empleado a los usuarios con credenciales de administración mientras la ocultan de otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="f22af-104">For example, you may want to show an employee salary column to users with management credentials while hiding it from other users.</span></span> <span data-ttu-id="f22af-105">Como alternativa, puede enlazar el control a un origen de datos que contenga muchas columnas, solo algunas de las cuales desea mostrar.</span><span class="sxs-lookup"><span data-stu-id="f22af-105">Alternately, you may want to bind the control to a data source that contains many columns, only some of which you want to display.</span></span> <span data-ttu-id="f22af-106">En este caso, normalmente se quitarán las columnas que no le interesa Mostrar en lugar de ocultarlas.</span><span class="sxs-lookup"><span data-stu-id="f22af-106">In this case, you will typically remove the columns you are not interested in displaying rather than hiding them.</span></span> <span data-ttu-id="f22af-107">Para obtener más información, vea [Cómo: Agregue y quite columnas en el control DataGridView Windows Forms mediante el diseñador](add-and-remove-columns-in-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="f22af-107">For more information, see [How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer](add-and-remove-columns-in-the-datagrid-using-the-designer.md).</span></span>

 <span data-ttu-id="f22af-108">El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que <xref:System.Windows.Forms.DataGridView> contenga un control.</span><span class="sxs-lookup"><span data-stu-id="f22af-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="f22af-109">Para obtener información acerca de cómo configurar este tipo de [proyecto, consulte Cómo: Cree un proyecto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) de aplicación de [Windows Forms y cómo: Agregue controles a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="f22af-109">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-hide-a-column-using-the-designer"></a><span data-ttu-id="f22af-110">Para ocultar una columna mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="f22af-110">To hide a column using the designer</span></span>

1. <span data-ttu-id="f22af-111">Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) en la <xref:System.Windows.Forms.DataGridView> esquina superior derecha del control y, a continuación, seleccione **Editar columnas**.</span><span class="sxs-lookup"><span data-stu-id="f22af-111">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>

2. <span data-ttu-id="f22af-112">Seleccione una columna de la lista **columnas seleccionadas** .</span><span class="sxs-lookup"><span data-stu-id="f22af-112">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="f22af-113">En la cuadrícula **propiedades de columna** , establezca <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> la propiedad `false`en.</span><span class="sxs-lookup"><span data-stu-id="f22af-113">In the **Column Properties** grid, set the <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> property to `false`.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="f22af-114">También puede ocultar una columna al agregarla desactivando la casilla **visible** en el cuadro de diálogo **Agregar columna** .</span><span class="sxs-lookup"><span data-stu-id="f22af-114">You can also hide a column when adding it by clearing the **Visible** check box in the **Add Column** dialog box.</span></span>

## <a name="see-also"></a><span data-ttu-id="f22af-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="f22af-115">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [<span data-ttu-id="f22af-116">Cómo: Agregar y quitar columnas en el control DataGridView Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="f22af-116">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="f22af-117">Cómo: Crear un proyecto de aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f22af-117">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="f22af-118">Cómo: Agregar controles a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f22af-118">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
