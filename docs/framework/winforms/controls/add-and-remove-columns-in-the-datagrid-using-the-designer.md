---
title: 'Cómo: Agregar y quitar columnas en el control DataGridView de formularios Windows Forms mediante el Diseñador'
ms.date: 03/30/2017
f1_keywords:
- vs.DataGridViewAddColumnDialog
helpviewer_keywords:
- DataGridView control [Windows Forms], adding columns
- DataGridView control [Windows Forms], removing columns
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
ms.openlocfilehash: 99fe1b8ffb7ccc2a5bef13ea8fef6ace5d5bdfdc
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43452812"
---
# <a name="how-to-add-and-remove-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="4cda2-102">Cómo: Agregar y quitar columnas en el control DataGridView de formularios Windows Forms mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="4cda2-102">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="4cda2-103">Los formularios de Windows <xref:System.Windows.Forms.DataGridView> control debe contener columnas con el fin de mostrar los datos.</span><span class="sxs-lookup"><span data-stu-id="4cda2-103">The Windows Forms <xref:System.Windows.Forms.DataGridView> control must contain columns in order to display data.</span></span> <span data-ttu-id="4cda2-104">Si va a rellenar el control manualmente, debe agregar las columnas.</span><span class="sxs-lookup"><span data-stu-id="4cda2-104">If you plan to populate the control manually, you must add the columns yourself.</span></span> <span data-ttu-id="4cda2-105">Como alternativa, puede enlazar el control a un origen de datos, que genera y rellena las columnas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="4cda2-105">Alternately, you can bind the control to a data source, which generates and populates the columns automatically.</span></span> <span data-ttu-id="4cda2-106">Si el origen de datos contiene más columnas que desea mostrar, puede quitar las columnas innecesarias.</span><span class="sxs-lookup"><span data-stu-id="4cda2-106">If the data source contains more columns than you want to display, you can remove the unwanted columns.</span></span>  
  
 <span data-ttu-id="4cda2-107">Los procedimientos siguientes requieren un **aplicación Windows** proyecto con un formulario que contenga un <xref:System.Windows.Forms.DataGridView> control.</span><span class="sxs-lookup"><span data-stu-id="4cda2-107">The following procedures require a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="4cda2-108">Para obtener información acerca de cómo configurar un proyecto de este tipo, consulte [Cómo: crear un proyecto de aplicación Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: agregar controles a Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="4cda2-108">For information about setting up such a project, see [How to: Create a Windows Application Project](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4cda2-109">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="4cda2-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="4cda2-110">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="4cda2-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="4cda2-111">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="4cda2-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-a-column-using-the-designer"></a><span data-ttu-id="4cda2-112">Para agregar una columna mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="4cda2-112">To add a column using the designer</span></span>  
  
1.  <span data-ttu-id="4cda2-113">Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) en la esquina superior derecha de la <xref:System.Windows.Forms.DataGridView> control y, a continuación, seleccione **Agregar columna**.</span><span class="sxs-lookup"><span data-stu-id="4cda2-113">Click the smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Add Column**.</span></span>  
  
2.  <span data-ttu-id="4cda2-114">En el **Agregar columna** diálogo cuadro, elija el **columna enlazada a datos** opción y seleccione una columna del origen de datos o elija el **columna sin enlazar** opción y definir la columna uso de los campos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="4cda2-114">In the **Add Column** dialog box, choose the **Databound Column** option and select a column from the data source, or choose the **Unbound Column** option and define the column using the fields provided.</span></span>  
  
3.  <span data-ttu-id="4cda2-115">Haga clic en el **agregar** para agregar la columna, haciendo que aparezca en el diseñador si las columnas existentes no ya rellena el área de presentación del control.</span><span class="sxs-lookup"><span data-stu-id="4cda2-115">Click the **Add** button to add the column, causing it to appear in the designer if the existing columns do not already fill the control display area.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4cda2-116">Puede modificar las propiedades de columna en la **Edit Columns** cuadro de diálogo, que puede tener acceso desde la etiqueta inteligente del control.</span><span class="sxs-lookup"><span data-stu-id="4cda2-116">You can modify column properties in the **Edit Columns** dialog box, which you can access from the control's smart tag.</span></span>  
  
### <a name="to-remove-a-column-using-the-designer"></a><span data-ttu-id="4cda2-117">Para quitar una columna mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="4cda2-117">To remove a column using the designer</span></span>  
  
1.  <span data-ttu-id="4cda2-118">Elija **Editar columnas** de etiqueta inteligente del control.</span><span class="sxs-lookup"><span data-stu-id="4cda2-118">Choose **Edit Columns** from the control's smart tag.</span></span>  
  
2.  <span data-ttu-id="4cda2-119">Seleccione una columna en la **columnas seleccionadas** lista.</span><span class="sxs-lookup"><span data-stu-id="4cda2-119">Select a column from the **Selected Columns** list.</span></span>  
  
3.  <span data-ttu-id="4cda2-120">Haga clic en el **quitar** botón para eliminar la columna, lo que hace que desaparece del diseñador.</span><span class="sxs-lookup"><span data-stu-id="4cda2-120">Click the **Remove** button to delete the column, causing it to disappear from the designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cda2-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="4cda2-121">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 [<span data-ttu-id="4cda2-122">Cómo: crear un proyecto de aplicación de Windows</span><span class="sxs-lookup"><span data-stu-id="4cda2-122">How to: Create a Windows Application Project</span></span>](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [<span data-ttu-id="4cda2-123">Cómo: Agregar controles a Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4cda2-123">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
