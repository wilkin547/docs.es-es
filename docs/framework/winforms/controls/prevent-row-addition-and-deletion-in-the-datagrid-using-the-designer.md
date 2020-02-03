---
title: Impedir la adición y eliminación de filas en el control DataGridView mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], preventing row addition or deletion
ms.assetid: a17722bd-9400-41e6-8dcc-c9c151f0a749
ms.openlocfilehash: cc9aff0f15d1bd6de5c469ee7069a99f3360837a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728714"
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="2d553-102">Cómo: Impedir la adición y eliminación de filas en el control DataGridView de formularios Windows Forms mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="2d553-102">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="2d553-103">En algunos casos, querrá impedir que los usuarios incluyan nuevas filas de datos o eliminen las filas existentes en el control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="2d553-103">Sometimes you will want to prevent users from entering new rows of data or deleting existing rows in your <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="2d553-104">Las nuevas filas se escriben en la fila especial para los nuevos registros en la parte inferior del control.</span><span class="sxs-lookup"><span data-stu-id="2d553-104">New rows are entered in the special row for new records at the bottom of the control.</span></span> <span data-ttu-id="2d553-105">Al deshabilitar la adición de filas, no se muestra la fila de los nuevos registros.</span><span class="sxs-lookup"><span data-stu-id="2d553-105">When you disable row addition, the row for new records is not displayed.</span></span> <span data-ttu-id="2d553-106">Después, puede hacer que el control sea completamente de solo lectura deshabilitando la eliminación de filas y la edición de celdas.</span><span class="sxs-lookup"><span data-stu-id="2d553-106">You can then make the control entirely read-only by disabling row deletion and cell editing.</span></span>

 <span data-ttu-id="2d553-107">El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que contenga un control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="2d553-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="2d553-108">Para obtener información sobre cómo configurar este tipo de proyecto, vea [Cómo: crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="2d553-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-prevent-row-addition-and-deletion"></a><span data-ttu-id="2d553-109">Para evitar la adición y eliminación de filas</span><span class="sxs-lookup"><span data-stu-id="2d553-109">To prevent row addition and deletion</span></span>

- <span data-ttu-id="2d553-110">Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) en la esquina superior derecha del control <xref:System.Windows.Forms.DataGridView> y, a continuación, desactive las casillas **Habilitar agregar** y **Habilitar eliminación** .</span><span class="sxs-lookup"><span data-stu-id="2d553-110">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then clear the **Enable Adding** and **Enable Deleting** check boxes.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2d553-111">Para que el control sea completamente de solo lectura, desactive también la casilla **Habilitar edición** .</span><span class="sxs-lookup"><span data-stu-id="2d553-111">To make the control entirely read-only, clear the **Enable Editing** check box as well.</span></span>

## <a name="see-also"></a><span data-ttu-id="2d553-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2d553-112">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>
- [<span data-ttu-id="2d553-113">Cómo: crear un proyecto de aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2d553-113">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="2d553-114">Cómo: Agregar controles a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2d553-114">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
