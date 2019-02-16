---
title: Filtrar Cambiar el tipo de una columna DataGridView de Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], types
- DataGridView control [Windows Forms], changing column type
- data [Windows Forms], displaying
ms.assetid: 7f994d45-600d-4190-a187-35803214b40c
ms.openlocfilehash: 189dd6d3e7eae7f4d9305bed97711da150198335
ms.sourcegitcommit: 0069cb3de8eed4e92b2195d29e5769a76111acdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/16/2019
ms.locfileid: "56333045"
---
# <a name="how-to-change-the-type-of-a-windows-forms-datagridview-column-using-the-designer"></a><span data-ttu-id="23bc9-102">Filtrar Cambiar el tipo de una columna DataGridView de Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="23bc9-102">How to: Change the Type of a Windows Forms DataGridView Column Using the Designer</span></span>
<span data-ttu-id="23bc9-103">A veces desea cambiar el tipo de una columna que ya se ha agregado a un formulario Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span><span class="sxs-lookup"><span data-stu-id="23bc9-103">Sometimes you will want to change the type of a column that has already been added to a Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="23bc9-104">Por ejemplo, es posible que desee modificar los tipos de algunas de las columnas que se generan automáticamente al enlazar el control a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="23bc9-104">For example, you may want to modify the types of some of the columns that are generated automatically when you bind the control to a data source.</span></span> <span data-ttu-id="23bc9-105">Esto es útil cuando la tabla que se muestra tiene las columnas que contienen claves externas a las filas de una tabla relacionada.</span><span class="sxs-lookup"><span data-stu-id="23bc9-105">This is useful when the table you display has columns containing foreign keys to rows in a related table.</span></span> <span data-ttu-id="23bc9-106">En este caso, es posible que desee reemplazar las columnas del cuadro de texto que se muestran estas claves externas con columnas de cuadro combinado que se muestran los valores más significativos de la tabla relacionada.</span><span class="sxs-lookup"><span data-stu-id="23bc9-106">In this case, you may want to replace the text box columns that display these foreign keys with combo box columns that display more meaningful values from the related table.</span></span>  
  
 <span data-ttu-id="23bc9-107">El procedimiento siguiente requiere una **aplicación Windows** proyecto con un formulario que contenga un <xref:System.Windows.Forms.DataGridView> control.</span><span class="sxs-lookup"><span data-stu-id="23bc9-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="23bc9-108">Para obtener información acerca de cómo configurar un proyecto de este tipo, vea [Cómo: Cree un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: Agregar controles a Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="23bc9-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="23bc9-109">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="23bc9-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="23bc9-110">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="23bc9-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="23bc9-111">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="23bc9-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-change-the-type-of-a-column-using-the-designer"></a><span data-ttu-id="23bc9-112">Para cambiar el tipo de una columna mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="23bc9-112">To change the type of a column using the designer</span></span>  
  
1.  <span data-ttu-id="23bc9-113">Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) en la esquina superior derecha de la <xref:System.Windows.Forms.DataGridView> control y, a continuación, seleccione **Editar columnas**.</span><span class="sxs-lookup"><span data-stu-id="23bc9-113">Click the smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>  
  
2.  <span data-ttu-id="23bc9-114">Seleccione una columna en la **columnas seleccionadas** lista.</span><span class="sxs-lookup"><span data-stu-id="23bc9-114">Select a column from the **Selected Columns** list.</span></span>  
  
3.  <span data-ttu-id="23bc9-115">En el **propiedades de columna** cuadrícula, establecer el `ColumnType` propiedad para el nuevo tipo de columna.</span><span class="sxs-lookup"><span data-stu-id="23bc9-115">In the **Column Properties** grid, set the `ColumnType` property to the new column type.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="23bc9-116">El `ColumnType` propiedad es una propiedad de solo tiempo de diseño que indica la clase que representa el tipo de columna.</span><span class="sxs-lookup"><span data-stu-id="23bc9-116">The `ColumnType` property is a design-time-only property that indicates the class representing the column type.</span></span> <span data-ttu-id="23bc9-117">No es una propiedad real definida en una clase de columna.</span><span class="sxs-lookup"><span data-stu-id="23bc9-117">It is not an actual property defined in a column class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23bc9-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="23bc9-118">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- [<span data-ttu-id="23bc9-119">Cómo: Crear un proyecto de aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="23bc9-119">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="23bc9-120">Cómo: Agregar controles a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="23bc9-120">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
