---
title: Procedimiento para editar columnas y filas en un control TableLayoutPanel
description: Obtenga información sobre cómo usar el cuadro de diálogo estilos de columnas y filas para editar las filas y columnas de los controles de Windows Forms.
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor
helpviewer_keywords:
- columns [Windows Forms], editing
- TableLayoutPanel control [Windows Forms], editing
- rows [Windows Forms], editing
ms.assetid: c367ed43-40dc-49eb-9e0f-ba70e83dfec0
ms.openlocfilehash: cfd2ca4be5d5a2658a9a129d911f1dba9670ccfd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619356"
---
# <a name="how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control"></a><span data-ttu-id="ba818-103">Procedimiento para editar columnas y filas en un control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="ba818-103">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>

<span data-ttu-id="ba818-104">Puede usar el editor de la colección del <xref:System.Windows.Forms.TableLayoutPanel> control, denominado cuadro de diálogo **estilos de columna y fila** , para editar las filas y columnas de los controles.</span><span class="sxs-lookup"><span data-stu-id="ba818-104">You can use the collection editor of the <xref:System.Windows.Forms.TableLayoutPanel> control, called the **Column and Row Styles** dialog box, to edit the rows and columns of your controls.</span></span>

> [!NOTE]
> <span data-ttu-id="ba818-105">Si desea que un control abarque varias filas o columnas, establezca las `RowSpan` propiedades y `ColumnSpan` en el control.</span><span class="sxs-lookup"><span data-stu-id="ba818-105">If you want a control to span multiple rows or columns, set the `RowSpan` and `ColumnSpan` properties on the control.</span></span> <span data-ttu-id="ba818-106">Para obtener más información, consulta [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span><span class="sxs-lookup"><span data-stu-id="ba818-106">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span>
>
> <span data-ttu-id="ba818-107">Si desea alinear un control dentro de una celda, o si desea que un control se estire dentro de una celda, use la propiedad del control <xref:System.Windows.Forms.Control.Anchor%2A> .</span><span class="sxs-lookup"><span data-stu-id="ba818-107">If you want to align a control within a cell, or if you want a control to stretch within a cell, use the control's <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span> <span data-ttu-id="ba818-108">Para obtener más información, consulta [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span><span class="sxs-lookup"><span data-stu-id="ba818-108">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span>

## <a name="to-edit-rows-and-columns"></a><span data-ttu-id="ba818-109">Para editar filas y columnas</span><span class="sxs-lookup"><span data-stu-id="ba818-109">To edit rows and columns</span></span>

1. <span data-ttu-id="ba818-110">Arrastre un control <xref:System.Windows.Forms.TableLayoutPanel> del **cuadro de herramientas** al formulario.</span><span class="sxs-lookup"><span data-stu-id="ba818-110">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="ba818-111">Haga clic en el <xref:System.Windows.Forms.TableLayoutPanel> glifo de acciones del diseñador del control ( ![ flecha negra pequeña ](./media/designer-actions-glyph.gif) ) y seleccione **Editar filas y columnas** para abrir el cuadro de diálogo **estilos de columna y fila** .</span><span class="sxs-lookup"><span data-stu-id="ba818-111">Click the <xref:System.Windows.Forms.TableLayoutPanel> control's designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) and select **Edit Rows and Columns** to open the **Column and Row Styles** dialog box.</span></span> <span data-ttu-id="ba818-112">También puede hacer clic con el botón derecho en el <xref:System.Windows.Forms.TableLayoutPanel> control y seleccionar **Editar filas y columnas** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="ba818-112">You can also right click on the <xref:System.Windows.Forms.TableLayoutPanel> control and select **Edit Rows and Columns** from the shortcut menu.</span></span>

3. <span data-ttu-id="ba818-113">Para agregar o quitar columnas, seleccione **columnas** en el cuadro de lista desplegable **tipo de miembro** .</span><span class="sxs-lookup"><span data-stu-id="ba818-113">To add or remove columns, select **Columns** from the **Member type** drop-down list box.</span></span>

4. <span data-ttu-id="ba818-114">Para agregar o quitar filas, seleccione **filas** en el cuadro de lista desplegable **tipo de miembro** .</span><span class="sxs-lookup"><span data-stu-id="ba818-114">To add or remove rows, select **Rows** from the **Member type** drop-down list box.</span></span>

5. <span data-ttu-id="ba818-115">Haga clic en el botón **Agregar** para agregar una fila o columna al final de la lista de **miembros** .</span><span class="sxs-lookup"><span data-stu-id="ba818-115">Click the **Add** button to add a row or column to the end of the **Member** list.</span></span>

6. <span data-ttu-id="ba818-116">Haga clic en el botón **Insertar** para agregar una fila o columna delante del elemento seleccionado actualmente en la lista.</span><span class="sxs-lookup"><span data-stu-id="ba818-116">Click the **Insert** button to add a row or column before the currently selected item in the list.</span></span>

7. <span data-ttu-id="ba818-117">Si va a agregar una fila o una columna, seleccione el **tipo de tamaño** de la nueva fila o columna.</span><span class="sxs-lookup"><span data-stu-id="ba818-117">If you are adding a row or column, select the **Size Type** for the new row or column.</span></span> <span data-ttu-id="ba818-118">Para obtener más información, vea <xref:System.Windows.Forms.SizeType>.</span><span class="sxs-lookup"><span data-stu-id="ba818-118">For more information, see <xref:System.Windows.Forms.SizeType>.</span></span>

8. <span data-ttu-id="ba818-119">Para quitar una fila o columna, haga clic en el botón **quitar** para eliminar el elemento seleccionado actualmente en la lista de **miembros** .</span><span class="sxs-lookup"><span data-stu-id="ba818-119">To remove a row or column, click the **Remove** button to delete the currently selected item in the **Member** list.</span></span>

## <a name="see-also"></a><span data-ttu-id="ba818-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba818-120">See also</span></span>

- <xref:System.Windows.Forms.SizeType>
- [<span data-ttu-id="ba818-121">Control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="ba818-121">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
