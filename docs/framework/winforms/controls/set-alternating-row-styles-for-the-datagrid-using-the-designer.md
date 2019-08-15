---
title: Procedimiento para establecer estilos de fila alternos en el control DataGridView de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- ledger-like formats
- DataGridView control [Windows Forms], row style alternation
- Windows Forms, rows
- rows [Windows Forms], alternating
- data [Windows Forms], displaying
ms.assetid: 02373442-bf94-4470-9f8a-e44c4a9d5b88
ms.openlocfilehash: 1be746d4cce36344e034692a0e2e8e6a9e9320d5
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040440"
---
# <a name="how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="fb177-102">Procedimiento para establecer estilos de fila alternos en el control DataGridView de formularios Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="fb177-102">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer</span></span>

<span data-ttu-id="fb177-103">Los datos tabulares se suelen presentar en un formato de libro de contabilidad en el que las filas alternas tienen diferentes colores de fondo.</span><span class="sxs-lookup"><span data-stu-id="fb177-103">Tabular data is often presented in a ledger-like format where alternating rows have different background colors.</span></span> <span data-ttu-id="fb177-104">Este formato permite a los usuarios saber fácilmente qué celdas están en cada fila, especialmente con tablas anchas que tienen muchas columnas.</span><span class="sxs-lookup"><span data-stu-id="fb177-104">This format makes it easier for users to tell which cells are in each row, especially with wide tables that have many columns.</span></span>

<span data-ttu-id="fb177-105">Con el control <xref:System.Windows.Forms.DataGridView>, puede especificar la información de estilo completa para las filas alternas.</span><span class="sxs-lookup"><span data-stu-id="fb177-105">With the <xref:System.Windows.Forms.DataGridView> control, you can specify complete style information for alternating rows.</span></span> <span data-ttu-id="fb177-106">Puede usar características de estilo como el color de primer plano y la fuente, además del color de fondo, para diferenciar las filas alternas.</span><span class="sxs-lookup"><span data-stu-id="fb177-106">You can use style characteristics like foreground color and font, in addition to background color, to differentiate alternating rows.</span></span> <span data-ttu-id="fb177-107">Para obtener más información, vea [estilos de celda en el control DataGridView de Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="fb177-107">For more information, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>

<span data-ttu-id="fb177-108">El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que <xref:System.Windows.Forms.DataGridView> contenga un control.</span><span class="sxs-lookup"><span data-stu-id="fb177-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="fb177-109">Para obtener información acerca de cómo configurar este tipo de [proyecto, consulte Cómo: Cree un proyecto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) de aplicación de [Windows Forms y cómo: Agregue controles a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="fb177-109">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>


### <a name="define-styles-for-alternating-rows"></a><span data-ttu-id="fb177-110">Definir estilos para filas alternas</span><span class="sxs-lookup"><span data-stu-id="fb177-110">Define styles for alternating rows</span></span>

1. <span data-ttu-id="fb177-111">Seleccione el <xref:System.Windows.Forms.DataGridView> control en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="fb177-111">Select the <xref:System.Windows.Forms.DataGridView> control in the designer.</span></span>

2. <span data-ttu-id="fb177-112">En la **ventana Propiedades** , haga clic en el botón![de puntos suspensivos (el botón de puntos suspensivos (...) del](./media/visual-studio-ellipsis-button.png)ventana Propiedades de Visual Studio <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> .) situado junto a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="fb177-112">In the **Properties** window, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> property.</span></span>

3. <span data-ttu-id="fb177-113">En el cuadro de diálogo **generador de CellStyle** , defina el estilo estableciendo las propiedades y use el panel de **vista previa** para confirmar las opciones.</span><span class="sxs-lookup"><span data-stu-id="fb177-113">In the **CellStyle Builder** dialog box, define the style by setting the properties, and use the **Preview** pane to confirm your choices.</span></span> <span data-ttu-id="fb177-114">Los estilos que especifique se usan para todas las demás filas mostradas en el control, comenzando por la segunda.</span><span class="sxs-lookup"><span data-stu-id="fb177-114">The styles you specify are used for every other row displayed in the control, starting with the second one.</span></span>

4. <span data-ttu-id="fb177-115">Para definir estilos para las filas restantes, repita los pasos 2 y 3 con <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> la propiedad.</span><span class="sxs-lookup"><span data-stu-id="fb177-115">To define styles for the remaining rows, repeat steps 2 and 3 using the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> property.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fb177-116">Las celdas se muestran mediante estilos heredados de varias propiedades.</span><span class="sxs-lookup"><span data-stu-id="fb177-116">Cells are displayed using styles inherited from multiple properties.</span></span> <span data-ttu-id="fb177-117">Para obtener más información sobre la herencia de estilos, vea [estilos de celda en el control DataGridView de Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="fb177-117">For more information about style inheritance, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fb177-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb177-118">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="fb177-119">Estilos de celda en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fb177-119">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="fb177-120">Estilo y formato básicos del control DataGridView en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fb177-120">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="fb177-121">Utilizar el Diseñador con el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fb177-121">Using the Designer with the Windows Forms DataGridView Control</span></span>](using-the-designer-with-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="fb177-122">Procedimientos: Crear un proyecto de aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fb177-122">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="fb177-123">Cómo: Agregar controles a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fb177-123">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
