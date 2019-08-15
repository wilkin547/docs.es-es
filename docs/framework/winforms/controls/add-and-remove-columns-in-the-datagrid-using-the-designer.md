---
title: Procedimiento para agregar y quitar columnas en el control DataGridView de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
f1_keywords:
- vs.DataGridViewAddColumnDialog
helpviewer_keywords:
- DataGridView control [Windows Forms], adding columns
- DataGridView control [Windows Forms], removing columns
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
ms.openlocfilehash: d88d658b31c87e7ae89bfb4a11fe794bfbb0e848
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040097"
---
# <a name="how-to-add-and-remove-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="19bf3-102">Procedimiento para agregar y quitar columnas en el control DataGridView de formularios Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="19bf3-102">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="19bf3-103">El control <xref:System.Windows.Forms.DataGridView> Windows Forms debe contener columnas para poder mostrar los datos.</span><span class="sxs-lookup"><span data-stu-id="19bf3-103">The Windows Forms <xref:System.Windows.Forms.DataGridView> control must contain columns in order to display data.</span></span> <span data-ttu-id="19bf3-104">Si tiene previsto rellenar el control manualmente, debe agregar las columnas.</span><span class="sxs-lookup"><span data-stu-id="19bf3-104">If you plan to populate the control manually, you must add the columns yourself.</span></span> <span data-ttu-id="19bf3-105">Como alternativa, puede enlazar el control a un origen de datos, que genera y rellena automáticamente las columnas.</span><span class="sxs-lookup"><span data-stu-id="19bf3-105">Alternately, you can bind the control to a data source, which generates and populates the columns automatically.</span></span> <span data-ttu-id="19bf3-106">Si el origen de datos contiene más columnas de las que desea mostrar, puede quitar las columnas no deseadas.</span><span class="sxs-lookup"><span data-stu-id="19bf3-106">If the data source contains more columns than you want to display, you can remove the unwanted columns.</span></span>

 <span data-ttu-id="19bf3-107">Los procedimientos siguientes requieren un proyecto de **aplicación Windows** con un formulario que <xref:System.Windows.Forms.DataGridView> contenga un control.</span><span class="sxs-lookup"><span data-stu-id="19bf3-107">The following procedures require a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="19bf3-108">Para obtener información acerca de cómo configurar este tipo de [proyecto, consulte Cómo: Cree un proyecto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) de aplicación de [Windows Forms y cómo: Agregue controles a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="19bf3-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-add-a-column-using-the-designer"></a><span data-ttu-id="19bf3-109">Para agregar una columna mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="19bf3-109">To add a column using the designer</span></span>

1. <span data-ttu-id="19bf3-110">Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) en la <xref:System.Windows.Forms.DataGridView> esquina superior derecha del control y seleccione **Agregar columna**.</span><span class="sxs-lookup"><span data-stu-id="19bf3-110">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Add Column**.</span></span>

2. <span data-ttu-id="19bf3-111">En el cuadro de diálogo **Agregar columna** , elija la opción de **columna DataBound** y seleccione una columna del origen de datos o elija la opción **columna** sin enlazar y defina la columna con los campos proporcionados.</span><span class="sxs-lookup"><span data-stu-id="19bf3-111">In the **Add Column** dialog box, choose the **Databound Column** option and select a column from the data source, or choose the **Unbound Column** option and define the column using the fields provided.</span></span>

3. <span data-ttu-id="19bf3-112">Haga clic en el botón **Agregar** para agregar la columna, lo que hará que aparezca en el diseñador si las columnas existentes aún no rellenan el área de presentación del control.</span><span class="sxs-lookup"><span data-stu-id="19bf3-112">Click the **Add** button to add the column, causing it to appear in the designer if the existing columns do not already fill the control display area.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="19bf3-113">Puede modificar las propiedades de las columnas en el cuadro de diálogo **Editar columnas** , al que puede tener acceso desde la etiqueta inteligente del control.</span><span class="sxs-lookup"><span data-stu-id="19bf3-113">You can modify column properties in the **Edit Columns** dialog box, which you can access from the control's smart tag.</span></span>

## <a name="to-remove-a-column-using-the-designer"></a><span data-ttu-id="19bf3-114">Para quitar una columna mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="19bf3-114">To remove a column using the designer</span></span>

1. <span data-ttu-id="19bf3-115">Elija **Editar columnas** en la etiqueta inteligente del control.</span><span class="sxs-lookup"><span data-stu-id="19bf3-115">Choose **Edit Columns** from the control's smart tag.</span></span>

2. <span data-ttu-id="19bf3-116">Seleccione una columna de la lista **columnas seleccionadas** .</span><span class="sxs-lookup"><span data-stu-id="19bf3-116">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="19bf3-117">Haga clic en el botón **quitar** para eliminar la columna, lo que hará que desaparezca del diseñador.</span><span class="sxs-lookup"><span data-stu-id="19bf3-117">Click the **Remove** button to delete the column, causing it to disappear from the designer.</span></span>

## <a name="see-also"></a><span data-ttu-id="19bf3-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="19bf3-118">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="19bf3-119">Cómo: Crear un proyecto de aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="19bf3-119">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="19bf3-120">Procedimientos: Agregar controles a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="19bf3-120">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
