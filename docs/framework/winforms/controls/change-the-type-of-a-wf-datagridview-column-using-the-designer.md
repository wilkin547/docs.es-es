---
title: Cambiar el tipo de una columna DataGridView mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], types
- DataGridView control [Windows Forms], changing column type
- data [Windows Forms], displaying
ms.assetid: 7f994d45-600d-4190-a187-35803214b40c
ms.openlocfilehash: 976f257d38dc7be5c904e63da47c61486bd3301c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737134"
---
# <a name="how-to-change-the-type-of-a-windows-forms-datagridview-column-using-the-designer"></a><span data-ttu-id="2f36c-102">Cómo: Cambiar el tipo de una columna DataGridView de formularios Windows Forms mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="2f36c-102">How to: Change the Type of a Windows Forms DataGridView Column Using the Designer</span></span>
<span data-ttu-id="2f36c-103">A veces, querrá cambiar el tipo de una columna que ya se ha agregado a un Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span><span class="sxs-lookup"><span data-stu-id="2f36c-103">Sometimes you will want to change the type of a column that has already been added to a Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="2f36c-104">Por ejemplo, puede que desee modificar los tipos de algunas de las columnas que se generan automáticamente al enlazar el control a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="2f36c-104">For example, you may want to modify the types of some of the columns that are generated automatically when you bind the control to a data source.</span></span> <span data-ttu-id="2f36c-105">Esto resulta útil cuando la tabla que se muestra tiene columnas que contienen claves externas en las filas de una tabla relacionada.</span><span class="sxs-lookup"><span data-stu-id="2f36c-105">This is useful when the table you display has columns containing foreign keys to rows in a related table.</span></span> <span data-ttu-id="2f36c-106">En este caso, puede que desee reemplazar las columnas de cuadro de texto que muestran estas claves externas por columnas de cuadro combinado que muestran valores más significativos de la tabla relacionada.</span><span class="sxs-lookup"><span data-stu-id="2f36c-106">In this case, you may want to replace the text box columns that display these foreign keys with combo box columns that display more meaningful values from the related table.</span></span>

 <span data-ttu-id="2f36c-107">El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que contenga un control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="2f36c-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="2f36c-108">Para obtener información sobre cómo configurar este tipo de proyecto, vea [Cómo: crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="2f36c-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="to-change-the-type-of-a-column-using-the-designer"></a><span data-ttu-id="2f36c-109">Para cambiar el tipo de una columna mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="2f36c-109">To change the type of a column using the designer</span></span>

1. <span data-ttu-id="2f36c-110">Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) en la esquina superior derecha del control <xref:System.Windows.Forms.DataGridView> y, a continuación, seleccione **Editar columnas**.</span><span class="sxs-lookup"><span data-stu-id="2f36c-110">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>

2. <span data-ttu-id="2f36c-111">Seleccione una columna de la lista **columnas seleccionadas** .</span><span class="sxs-lookup"><span data-stu-id="2f36c-111">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="2f36c-112">En la cuadrícula **propiedades de columna** , establezca la propiedad `ColumnType` en el nuevo tipo de columna.</span><span class="sxs-lookup"><span data-stu-id="2f36c-112">In the **Column Properties** grid, set the `ColumnType` property to the new column type.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2f36c-113">La propiedad `ColumnType` es una propiedad de solo tiempo de diseño que indica la clase que representa el tipo de columna.</span><span class="sxs-lookup"><span data-stu-id="2f36c-113">The `ColumnType` property is a design-time-only property that indicates the class representing the column type.</span></span> <span data-ttu-id="2f36c-114">No es una propiedad real definida en una clase de columna.</span><span class="sxs-lookup"><span data-stu-id="2f36c-114">It is not an actual property defined in a column class.</span></span>

## <a name="see-also"></a><span data-ttu-id="2f36c-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2f36c-115">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- [<span data-ttu-id="2f36c-116">Cómo: crear un proyecto de aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2f36c-116">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="2f36c-117">Cómo: Agregar controles a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2f36c-117">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
