---
title: Procedimiento para inmovilizar columnas en el control DataGridView de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], freezing
- DataGridView control [Windows Forms], column freezing
- data [Windows Forms], displaying
ms.assetid: 87412dd2-478f-4751-af87-dafc591fc215
ms.openlocfilehash: d38c8d73bc70e7e521b476ca78c8f102d003c538
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040332"
---
# <a name="how-to-freeze-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="b89e3-102">Procedimiento para inmovilizar columnas en el control DataGridView de formularios Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="b89e3-102">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="b89e3-103">Cuando los usuarios ven los datos mostrados en un control <xref:System.Windows.Forms.DataGridView> de Windows Forms, a veces deben hacer referencia a una sola columna o a un conjunto de columnas con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="b89e3-103">When users view data displayed in a Windows Forms <xref:System.Windows.Forms.DataGridView> control, they sometimes need to refer to a single column or set of columns frequently.</span></span> <span data-ttu-id="b89e3-104">Por ejemplo, cuando se muestra una tabla de información del cliente que contiene muchas columnas, resulta útil mostrar el nombre del cliente en todo momento mientras se habilitan otras columnas para desplazarse fuera del área visible.</span><span class="sxs-lookup"><span data-stu-id="b89e3-104">For example, when you display a table of customer information that contains many columns, it is useful for you to display the customer name at all times while enabling other columns to scroll outside the visible region.</span></span>

 <span data-ttu-id="b89e3-105">Para conseguir este comportamiento, puede inmovilizar las columnas en el control.</span><span class="sxs-lookup"><span data-stu-id="b89e3-105">To achieve this behavior, you can freeze columns in the control.</span></span> <span data-ttu-id="b89e3-106">Al inmovilizar una columna, también se inmovilizan todas las columnas situadas a su izquierda (o a su derecha en los scripts de idioma de derecha a izquierda).</span><span class="sxs-lookup"><span data-stu-id="b89e3-106">When you freeze a column, all the columns to its left (or to its right in right-to-left language scripts) are frozen as well.</span></span> <span data-ttu-id="b89e3-107">Las columnas inmovilizadas permanecen en su lugar mientras que todas las demás columnas se pueden desplazar.</span><span class="sxs-lookup"><span data-stu-id="b89e3-107">Frozen columns remain in place while all other columns can scroll.</span></span> <span data-ttu-id="b89e3-108">Si se habilita la reordenación de columnas, las columnas inmovilizadas se tratan como un grupo distinto de las columnas no inmovilizadas.</span><span class="sxs-lookup"><span data-stu-id="b89e3-108">If column reordering is enabled, the frozen columns are treated as a group distinct from the unfrozen columns.</span></span> <span data-ttu-id="b89e3-109">Los usuarios pueden cambiar la ubicación de las columnas en los grupos, pero no pueden mover una columna de un grupo a otro.</span><span class="sxs-lookup"><span data-stu-id="b89e3-109">Users can reposition columns in either group, but they cannot move a column from one group to the other.</span></span>

 <span data-ttu-id="b89e3-110">El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que <xref:System.Windows.Forms.DataGridView> contenga un control.</span><span class="sxs-lookup"><span data-stu-id="b89e3-110">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="b89e3-111">Para obtener información acerca de cómo configurar este tipo de [proyecto, consulte Cómo: Cree un proyecto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) de aplicación de [Windows Forms y cómo: Agregue controles a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="b89e3-111">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-freeze-a-column-using-the-designer"></a><span data-ttu-id="b89e3-112">Para inmovilizar una columna mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="b89e3-112">To freeze a column using the designer</span></span>

1. <span data-ttu-id="b89e3-113">Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) en la <xref:System.Windows.Forms.DataGridView> esquina superior derecha del control y, a continuación, seleccione **Editar columnas**.</span><span class="sxs-lookup"><span data-stu-id="b89e3-113">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>

2. <span data-ttu-id="b89e3-114">Seleccione una columna de la lista **columnas seleccionadas** .</span><span class="sxs-lookup"><span data-stu-id="b89e3-114">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="b89e3-115">En la cuadrícula **propiedades de columna** , establezca <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> la propiedad `true`en.</span><span class="sxs-lookup"><span data-stu-id="b89e3-115">In the **Column Properties** grid, set the <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> property to `true`.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="b89e3-116">También puede inmovilizar una columna al agregarla seleccionando el cuadro inmovilizado en el cuadro de diálogo **Agregar columna** .</span><span class="sxs-lookup"><span data-stu-id="b89e3-116">You can also freeze a column when adding it by selecting the **Frozen** box in the **Add Column** dialog box.</span></span>

## <a name="see-also"></a><span data-ttu-id="b89e3-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="b89e3-117">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType>
- [<span data-ttu-id="b89e3-118">Cómo: Agregar y quitar columnas en el control DataGridView Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="b89e3-118">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="b89e3-119">Cómo: Habilitar la reordenación de columnas en el control DataGridView Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="b89e3-119">How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer</span></span>](enable-column-reordering-in-the-datagrid-using-the-designer.md)
- <span data-ttu-id="b89e3-120">[Cómo: Mostrar texto de derecha a izquierda en Windows Forms para la globalización](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7d3337xw(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b89e3-120">[How to: Display Right-to-Left Text in Windows Forms for Globalization](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7d3337xw(v=vs.100))</span></span>
- [<span data-ttu-id="b89e3-121">Procedimientos: Crear un proyecto de aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b89e3-121">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="b89e3-122">Cómo: Agregar controles a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b89e3-122">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
