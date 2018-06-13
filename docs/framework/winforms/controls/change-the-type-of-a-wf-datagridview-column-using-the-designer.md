---
title: 'Cómo: Cambiar el tipo de una columna DataGridView de formularios Windows Forms mediante el Diseñador'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], types
- DataGridView control [Windows Forms], changing column type
- data [Windows Forms], displaying
ms.assetid: 7f994d45-600d-4190-a187-35803214b40c
ms.openlocfilehash: b5d395575ac486307625fbdf2f236b6a588cc3ed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527020"
---
# <a name="how-to-change-the-type-of-a-windows-forms-datagridview-column-using-the-designer"></a><span data-ttu-id="42310-102">Cómo: Cambiar el tipo de una columna DataGridView de formularios Windows Forms mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="42310-102">How to: Change the Type of a Windows Forms DataGridView Column Using the Designer</span></span>
<span data-ttu-id="42310-103">En ocasiones, deseará cambiar el tipo de una columna que ya se agregó a Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span><span class="sxs-lookup"><span data-stu-id="42310-103">Sometimes you will want to change the type of a column that has already been added to a Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="42310-104">Por ejemplo, puede que desee modificar los tipos de algunas de las columnas que se generan automáticamente al enlazar el control a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="42310-104">For example, you may want to modify the types of some of the columns that are generated automatically when you bind the control to a data source.</span></span> <span data-ttu-id="42310-105">Esto es útil cuando la tabla que se muestra tiene columnas que contienen claves externas a las filas de una tabla relacionada.</span><span class="sxs-lookup"><span data-stu-id="42310-105">This is useful when the table you display has columns containing foreign keys to rows in a related table.</span></span> <span data-ttu-id="42310-106">En este caso, puede que desee reemplazar las columnas de cuadro de texto que muestran estas claves externas con columnas de cuadro combinado que muestran valores más significativos de la tabla relacionada.</span><span class="sxs-lookup"><span data-stu-id="42310-106">In this case, you may want to replace the text box columns that display these foreign keys with combo box columns that display more meaningful values from the related table.</span></span>  
  
 <span data-ttu-id="42310-107">El procedimiento siguiente requiere un **aplicación de Windows** proyecto con un formulario que contenga un <xref:System.Windows.Forms.DataGridView> control.</span><span class="sxs-lookup"><span data-stu-id="42310-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="42310-108">Para obtener información acerca de cómo configurar un proyecto de este tipo, consulte [Cómo: crear un proyecto de aplicación de Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="42310-108">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="42310-109">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="42310-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="42310-110">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="42310-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="42310-111">Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="42310-111">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-change-the-type-of-a-column-using-the-designer"></a><span data-ttu-id="42310-112">Para cambiar el tipo de una columna mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="42310-112">To change the type of a column using the designer</span></span>  
  
1.  <span data-ttu-id="42310-113">Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) en la esquina superior derecha de la <xref:System.Windows.Forms.DataGridView> control y, a continuación, seleccione **Editar columnas**.</span><span class="sxs-lookup"><span data-stu-id="42310-113">Click the smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>  
  
2.  <span data-ttu-id="42310-114">Seleccione una columna en la **columnas seleccionadas** lista.</span><span class="sxs-lookup"><span data-stu-id="42310-114">Select a column from the **Selected Columns** list.</span></span>  
  
3.  <span data-ttu-id="42310-115">En el **propiedades de columna** cuadrícula, establecer el `ColumnType` propiedad para el nuevo tipo de columna.</span><span class="sxs-lookup"><span data-stu-id="42310-115">In the **Column Properties** grid, set the `ColumnType` property to the new column type.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="42310-116">El `ColumnType` propiedad es una propiedad de solo tiempo de diseño que indica la clase que representa el tipo de columna.</span><span class="sxs-lookup"><span data-stu-id="42310-116">The `ColumnType` property is a design-time-only property that indicates the class representing the column type.</span></span> <span data-ttu-id="42310-117">No es una propiedad real definida en una clase de columna.</span><span class="sxs-lookup"><span data-stu-id="42310-117">It is not an actual property defined in a column class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42310-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="42310-118">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 [<span data-ttu-id="42310-119">Cómo: crear un proyecto de aplicación de Windows</span><span class="sxs-lookup"><span data-stu-id="42310-119">How to: Create a Windows Application Project</span></span>](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [<span data-ttu-id="42310-120">Cómo: Agregar controles a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="42310-120">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
