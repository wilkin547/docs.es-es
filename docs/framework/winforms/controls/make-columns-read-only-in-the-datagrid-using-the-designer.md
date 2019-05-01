---
title: Procedimiento para crear columnas de solo lectura en el control DataGridView de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- DataGridView control [Windows Forms], read-only columns
- data [Windows Forms], displaying
- columns [Windows Forms], read-only
ms.assetid: b4ef7a75-ab33-4ee3-b2cf-201530e454e9
ms.openlocfilehash: a735b9bef9f9e3488941e05b2aa9444e6ecdc4b8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012885"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="824aa-102">Procedimiento para crear columnas de solo lectura en el control DataGridView de formularios Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="824aa-102">How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="824aa-103">De forma predeterminada, los usuarios pueden modificar texto y datos numéricos que se muestra en los formularios de Windows <xref:System.Windows.Forms.DataGridView> control.</span><span class="sxs-lookup"><span data-stu-id="824aa-103">By default, users can modify text and numerical data displayed in the Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="824aa-104">Si desea mostrar los datos que no está diseñados para su modificación, debe realizar las columnas que contienen los datos de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="824aa-104">If you want to display data that is not meant for modification, you must make the columns that contain the data read-only.</span></span> <span data-ttu-id="824aa-105">Para obtener información acerca de cómo hacer que el control sea de sólo lectura, vea [Cómo: Impedir la adición de la fila y la eliminación en la Windows Forms Control DataGridView de formularios mediante el diseñador](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="824aa-105">For information about how to make the control entirely read-only, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md).</span></span>  
  
 <span data-ttu-id="824aa-106">El procedimiento siguiente requiere una **aplicación Windows** proyecto con un formulario que contenga un <xref:System.Windows.Forms.DataGridView> control.</span><span class="sxs-lookup"><span data-stu-id="824aa-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="824aa-107">Para obtener información acerca de cómo configurar un proyecto de este tipo, vea [Cómo: Cree un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="824aa-107">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="824aa-108">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="824aa-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="824aa-109">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="824aa-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="824aa-110">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="824aa-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-make-a-column-read-only-by-using-the-designer"></a><span data-ttu-id="824aa-111">Convertir una columna de solo lectura mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="824aa-111">To make a column read-only by using the designer</span></span>  
  
1. <span data-ttu-id="824aa-112">Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) en la esquina superior derecha de la <xref:System.Windows.Forms.DataGridView> control y, a continuación, seleccione **Editar columnas**.</span><span class="sxs-lookup"><span data-stu-id="824aa-112">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>  
  
2. <span data-ttu-id="824aa-113">Seleccione una columna en la **columnas seleccionadas** lista.</span><span class="sxs-lookup"><span data-stu-id="824aa-113">Select a column from the **Selected Columns** list.</span></span>  
  
3. <span data-ttu-id="824aa-114">En el **propiedades de columna** cuadrícula, establecer el <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="824aa-114">In the **Column Properties** grid, set the <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> property to `true`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="824aa-115">Puede hacer también una columna de sólo lectura cuando se agrega al seleccionar el **de sólo lectura** casilla de verificación en la **Agregar columna** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="824aa-115">You can also make a column read-only when you add it by selecting the **Read Only** check box in the **Add Column** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="824aa-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="824aa-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="824aa-117">Cómo: Agregar y quitar columnas en el Control de DataGridView de Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="824aa-117">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="824aa-118">Cómo: Impedir la adición de fila y eliminación en el Control de DataGridView de Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="824aa-118">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="824aa-119">Cómo: Crear un proyecto de aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="824aa-119">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="824aa-120">Cómo: Agregar controles a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="824aa-120">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
