---
title: Filtrar para editar columnas y filas en un control TableLayoutPanel
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor
helpviewer_keywords:
- columns [Windows Forms], editing
- TableLayoutPanel control [Windows Forms], editing
- rows [Windows Forms], editing
ms.assetid: c367ed43-40dc-49eb-9e0f-ba70e83dfec0
ms.openlocfilehash: eb194052ecd78d585f251789730a1f9855c509d9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59201967"
---
# <a name="how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control"></a><span data-ttu-id="b2c74-102">Filtrar para editar columnas y filas en un control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="b2c74-102">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>
<span data-ttu-id="b2c74-103">Puede usar el editor de colecciones de la <xref:System.Windows.Forms.TableLayoutPanel> control, denominado el **estilos de columna y fila** cuadro de diálogo, para editar las filas y columnas de los controles.</span><span class="sxs-lookup"><span data-stu-id="b2c74-103">You can use the collection editor of the <xref:System.Windows.Forms.TableLayoutPanel> control, called the **Column and Row Styles** dialog box, to edit the rows and columns of your controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b2c74-104">Si desea un control para abarcar varias filas o columnas, establezca el `RowSpan` y `ColumnSpan` las propiedades del control.</span><span class="sxs-lookup"><span data-stu-id="b2c74-104">If you want a control to span multiple rows or columns, set the `RowSpan` and `ColumnSpan` properties on the control.</span></span> <span data-ttu-id="b2c74-105">Para obtener más información, vea [Tutorial: Organizar controles en formularios de Windows Forms mediante TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span><span class="sxs-lookup"><span data-stu-id="b2c74-105">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span>  
>   
>  <span data-ttu-id="b2c74-106">Si desea alinear un control dentro de una celda, o si desea que un control se ajuste dentro de una celda, use el control <xref:System.Windows.Forms.Control.Anchor%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="b2c74-106">If you want to align a control within a cell, or if you want a control to stretch within a cell, use the control's <xref:System.Windows.Forms.Control.Anchor%2A> property.</span></span> <span data-ttu-id="b2c74-107">Para obtener más información, vea [Tutorial: Organizar controles en formularios de Windows Forms mediante TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span><span class="sxs-lookup"><span data-stu-id="b2c74-107">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).</span></span>  
>   
>  <span data-ttu-id="b2c74-108">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="b2c74-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="b2c74-109">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="b2c74-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="b2c74-110">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="b2c74-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-edit-rows-and-columns"></a><span data-ttu-id="b2c74-111">Para editar filas y columnas</span><span class="sxs-lookup"><span data-stu-id="b2c74-111">To edit rows and columns</span></span>  
  
1.  <span data-ttu-id="b2c74-112">Arrastre un control <xref:System.Windows.Forms.TableLayoutPanel> del **cuadro de herramientas** al formulario.</span><span class="sxs-lookup"><span data-stu-id="b2c74-112">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
2.  <span data-ttu-id="b2c74-113">Haga clic en el <xref:System.Windows.Forms.TableLayoutPanel> glifo de etiqueta inteligente del control (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) y seleccione **Editar filas y columnas** para abrir el  **Estilos de columna y fila** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b2c74-113">Click the <xref:System.Windows.Forms.TableLayoutPanel> control's smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) and select **Edit Rows and Columns** to open the **Column and Row Styles** dialog box.</span></span> <span data-ttu-id="b2c74-114">También puede hacer a la derecha clic en el <xref:System.Windows.Forms.TableLayoutPanel> control y seleccione **Editar filas y columnas** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="b2c74-114">You can also right click on the <xref:System.Windows.Forms.TableLayoutPanel> control and select **Edit Rows and Columns** from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="b2c74-115">Para agregar o quitar columnas, seleccione **columnas** desde el **tipo de miembro** cuadro de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="b2c74-115">To add or remove columns, select **Columns** from the **Member type** drop-down list box.</span></span>  
  
4.  <span data-ttu-id="b2c74-116">Para agregar o quitar filas, seleccione **filas** desde el **tipo de miembro** cuadro de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="b2c74-116">To add or remove rows, select **Rows** from the **Member type** drop-down list box.</span></span>  
  
5.  <span data-ttu-id="b2c74-117">Haga clic en el **agregar** para agregar una fila o columna al final de la **miembro** lista.</span><span class="sxs-lookup"><span data-stu-id="b2c74-117">Click the **Add** button to add a row or column to the end of the **Member** list.</span></span>  
  
6.  <span data-ttu-id="b2c74-118">Haga clic en el **insertar** para agregar una fila o columna delante del elemento actualmente seleccionado en la lista.</span><span class="sxs-lookup"><span data-stu-id="b2c74-118">Click the **Insert** button to add a row or column before the currently selected item in the list.</span></span>  
  
7.  <span data-ttu-id="b2c74-119">Si va a agregar una fila o columna, seleccione el **tipo tamaño** para la nueva fila o columna.</span><span class="sxs-lookup"><span data-stu-id="b2c74-119">If you are adding a row or column, select the **Size Type** for the new row or column.</span></span> <span data-ttu-id="b2c74-120">Para obtener más información, consulta <xref:System.Windows.Forms.SizeType>.</span><span class="sxs-lookup"><span data-stu-id="b2c74-120">For more information, see <xref:System.Windows.Forms.SizeType>.</span></span>  
  
8.  <span data-ttu-id="b2c74-121">Para quitar una fila o columna, haga clic en el **quitar** botón para eliminar el elemento actualmente seleccionado en el **miembro** lista.</span><span class="sxs-lookup"><span data-stu-id="b2c74-121">To remove a row or column, click the **Remove** button to delete the currently selected item in the **Member** list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2c74-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2c74-122">See also</span></span>

- <xref:System.Windows.Forms.SizeType>
- [<span data-ttu-id="b2c74-123">Control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="b2c74-123">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
