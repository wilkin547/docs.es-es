---
title: Filtrar para agregar y quitar columnas en el control DataGridView de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
f1_keywords:
- vs.DataGridViewAddColumnDialog
helpviewer_keywords:
- DataGridView control [Windows Forms], adding columns
- DataGridView control [Windows Forms], removing columns
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
ms.openlocfilehash: 80ede9b7bc5bf667e03dc0a745fbc0b5f6c2663a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59343290"
---
# <a name="how-to-add-and-remove-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="3298d-102">Filtrar para agregar y quitar columnas en el control DataGridView de formularios Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="3298d-102">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="3298d-103">Los formularios de Windows <xref:System.Windows.Forms.DataGridView> control debe contener columnas con el fin de mostrar los datos.</span><span class="sxs-lookup"><span data-stu-id="3298d-103">The Windows Forms <xref:System.Windows.Forms.DataGridView> control must contain columns in order to display data.</span></span> <span data-ttu-id="3298d-104">Si va a rellenar el control manualmente, debe agregar las columnas.</span><span class="sxs-lookup"><span data-stu-id="3298d-104">If you plan to populate the control manually, you must add the columns yourself.</span></span> <span data-ttu-id="3298d-105">Como alternativa, puede enlazar el control a un origen de datos, que genera y rellena las columnas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="3298d-105">Alternately, you can bind the control to a data source, which generates and populates the columns automatically.</span></span> <span data-ttu-id="3298d-106">Si el origen de datos contiene más columnas que desea mostrar, puede quitar las columnas innecesarias.</span><span class="sxs-lookup"><span data-stu-id="3298d-106">If the data source contains more columns than you want to display, you can remove the unwanted columns.</span></span>  
  
 <span data-ttu-id="3298d-107">Los procedimientos siguientes requieren un **aplicación Windows** proyecto con un formulario que contenga un <xref:System.Windows.Forms.DataGridView> control.</span><span class="sxs-lookup"><span data-stu-id="3298d-107">The following procedures require a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="3298d-108">Para obtener información acerca de cómo configurar un proyecto de este tipo, vea [Cómo: Cree un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="3298d-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3298d-109">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="3298d-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="3298d-110">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="3298d-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="3298d-111">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="3298d-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-a-column-using-the-designer"></a><span data-ttu-id="3298d-112">Para agregar una columna mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="3298d-112">To add a column using the designer</span></span>  
  
1. <span data-ttu-id="3298d-113">Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) en la esquina superior derecha de la <xref:System.Windows.Forms.DataGridView> control y, a continuación, seleccione **Agregar columna**.</span><span class="sxs-lookup"><span data-stu-id="3298d-113">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Add Column**.</span></span>  
  
2. <span data-ttu-id="3298d-114">En el **Agregar columna** diálogo cuadro, elija el **columna enlazada a datos** opción y seleccione una columna del origen de datos o elija el **columna sin enlazar** opción y definir la columna uso de los campos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="3298d-114">In the **Add Column** dialog box, choose the **Databound Column** option and select a column from the data source, or choose the **Unbound Column** option and define the column using the fields provided.</span></span>  
  
3. <span data-ttu-id="3298d-115">Haga clic en el **agregar** para agregar la columna, haciendo que aparezca en el diseñador si las columnas existentes no ya rellena el área de presentación del control.</span><span class="sxs-lookup"><span data-stu-id="3298d-115">Click the **Add** button to add the column, causing it to appear in the designer if the existing columns do not already fill the control display area.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3298d-116">Puede modificar las propiedades de columna en la **Edit Columns** cuadro de diálogo, que puede tener acceso desde la etiqueta inteligente del control.</span><span class="sxs-lookup"><span data-stu-id="3298d-116">You can modify column properties in the **Edit Columns** dialog box, which you can access from the control's smart tag.</span></span>  
  
### <a name="to-remove-a-column-using-the-designer"></a><span data-ttu-id="3298d-117">Para quitar una columna mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="3298d-117">To remove a column using the designer</span></span>  
  
1. <span data-ttu-id="3298d-118">Elija **Editar columnas** de etiqueta inteligente del control.</span><span class="sxs-lookup"><span data-stu-id="3298d-118">Choose **Edit Columns** from the control's smart tag.</span></span>  
  
2. <span data-ttu-id="3298d-119">Seleccione una columna en la **columnas seleccionadas** lista.</span><span class="sxs-lookup"><span data-stu-id="3298d-119">Select a column from the **Selected Columns** list.</span></span>  
  
3. <span data-ttu-id="3298d-120">Haga clic en el **quitar** botón para eliminar la columna, lo que hace que desaparece del diseñador.</span><span class="sxs-lookup"><span data-stu-id="3298d-120">Click the **Remove** button to delete the column, causing it to disappear from the designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3298d-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="3298d-121">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="3298d-122">Filtrar Cree un proyecto de aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3298d-122">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="3298d-123">Filtrar para agregar controles a formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3298d-123">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
