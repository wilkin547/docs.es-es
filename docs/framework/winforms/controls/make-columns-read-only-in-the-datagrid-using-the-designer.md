---
title: Procedimiento para crear columnas de solo lectura en el control DataGridView de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- DataGridView control [Windows Forms], read-only columns
- data [Windows Forms], displaying
- columns [Windows Forms], read-only
ms.assetid: b4ef7a75-ab33-4ee3-b2cf-201530e454e9
ms.openlocfilehash: 6bdd561c863a461f43a5a7aac025fead1f971bb0
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039816"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="6dbf4-102">Procedimiento para crear columnas de solo lectura en el control DataGridView de formularios Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="6dbf4-102">How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="6dbf4-103">De forma predeterminada, los usuarios pueden modificar los datos numéricos y de <xref:System.Windows.Forms.DataGridView> texto que se muestran en el control Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6dbf4-103">By default, users can modify text and numerical data displayed in the Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="6dbf4-104">Si desea mostrar datos que no están diseñados para su modificación, debe hacer que las columnas que contienen los datos sean de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="6dbf4-104">If you want to display data that is not meant for modification, you must make the columns that contain the data read-only.</span></span> <span data-ttu-id="6dbf4-105">Para obtener información sobre cómo hacer que el control sea completamente de solo lectura [, consulte Cómo: Evite la adición y eliminación de filas en el control Windows Forms DataGridView mediante](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)el diseñador.</span><span class="sxs-lookup"><span data-stu-id="6dbf4-105">For information about how to make the control entirely read-only, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md).</span></span>

 <span data-ttu-id="6dbf4-106">El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que <xref:System.Windows.Forms.DataGridView> contenga un control.</span><span class="sxs-lookup"><span data-stu-id="6dbf4-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="6dbf4-107">Para obtener información acerca de cómo configurar este tipo de [proyecto, consulte Cómo: Cree un proyecto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) de aplicación de [Windows Forms y cómo: Agregue controles a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="6dbf4-107">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-make-a-column-read-only-by-using-the-designer"></a><span data-ttu-id="6dbf4-108">Para hacer que una columna sea de solo lectura mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="6dbf4-108">To make a column read-only by using the designer</span></span>

1. <span data-ttu-id="6dbf4-109">Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) en la <xref:System.Windows.Forms.DataGridView> esquina superior derecha del control y, a continuación, seleccione **Editar columnas**.</span><span class="sxs-lookup"><span data-stu-id="6dbf4-109">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>

2. <span data-ttu-id="6dbf4-110">Seleccione una columna de la lista **columnas seleccionadas** .</span><span class="sxs-lookup"><span data-stu-id="6dbf4-110">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="6dbf4-111">En la cuadrícula **propiedades de columna** , establezca <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> la propiedad `true`en.</span><span class="sxs-lookup"><span data-stu-id="6dbf4-111">In the **Column Properties** grid, set the <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> property to `true`.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="6dbf4-112">También puede hacer que una columna sea de solo lectura al agregarla activando la casilla **solo lectura** en el cuadro de diálogo **Agregar columna** .</span><span class="sxs-lookup"><span data-stu-id="6dbf4-112">You can also make a column read-only when you add it by selecting the **Read Only** check box in the **Add Column** dialog box.</span></span>

## <a name="see-also"></a><span data-ttu-id="6dbf4-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="6dbf4-113">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="6dbf4-114">Cómo: Agregar y quitar columnas en el control DataGridView Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="6dbf4-114">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="6dbf4-115">Cómo: Impedir la adición y eliminación de filas en el control Windows Forms DataGridView mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="6dbf4-115">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="6dbf4-116">Cómo: Crear un proyecto de aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6dbf4-116">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="6dbf4-117">Procedimientos: Agregar controles a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6dbf4-117">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
