---
title: Filtrar para agregar columnas al control ListView de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
ms.assetid: 5b1a8b4d-587e-479a-95c1-f9b90884f13a
ms.openlocfilehash: 10963fcb6d87ed74f73ecf4f1831a56eae5a392d
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658456"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="91700-102">Filtrar para agregar columnas al control ListView de formularios Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="91700-102">How to: Add Columns to the Windows Forms ListView Control Using the Designer</span></span>

<span data-ttu-id="91700-103">El control <xref:System.Windows.Forms.ListView> Windows Forms puede mostrar varias columnas para cada elemento de la lista en la vista de **detalles** .</span><span class="sxs-lookup"><span data-stu-id="91700-103">The Windows Forms <xref:System.Windows.Forms.ListView> control can display multiple columns for each list item when in the **Details** view.</span></span> <span data-ttu-id="91700-104">Puede utilizar las columnas para mostrar varios tipos de información sobre cada elemento de lista.</span><span class="sxs-lookup"><span data-stu-id="91700-104">You can use the columns to display several types of information about each list item.</span></span> <span data-ttu-id="91700-105">Por ejemplo, una lista de archivos podría mostrar el nombre de archivo, el tipo de archivo, el tamaño y la fecha en que se modificó el archivo por última vez.</span><span class="sxs-lookup"><span data-stu-id="91700-105">For example, a list of files could display the file name, file type, size, and date the file was last modified.</span></span> <span data-ttu-id="91700-106">Para obtener información sobre cómo rellenar las columnas una vez [creadas, consulte How to: Mostrar los subelementos en columnas con el control](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)ListView Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="91700-106">For information on populating the columns once they are created, see [How to: Display Subitems in Columns with the Windows Forms ListView Control](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).</span></span>

<span data-ttu-id="91700-107">El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que <xref:System.Windows.Forms.ListView> contenga un control.</span><span class="sxs-lookup"><span data-stu-id="91700-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="91700-108">Para obtener información acerca de cómo configurar este tipo de [proyecto, consulte Cómo: Cree un proyecto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) de aplicación de [Windows Forms y cómo: Agregue controles a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="91700-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="to-add-columns-in-the-designer"></a><span data-ttu-id="91700-109">Para agregar columnas en el diseñador</span><span class="sxs-lookup"><span data-stu-id="91700-109">To add columns in the designer</span></span>

1. <span data-ttu-id="91700-110">En la ventana **propiedades** , establezca la propiedad del <xref:System.Windows.Forms.ListView.View%2A> control en <xref:System.Windows.Forms.View.Details>.</span><span class="sxs-lookup"><span data-stu-id="91700-110">In the **Properties** window, set the control's <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>

2. <span data-ttu-id="91700-111">En la **ventana Propiedades** , haga clic en el botón![de **puntos suspensivos** (el botón de puntos suspensivos (...) del](./media/visual-studio-ellipsis-button.png)ventana Propiedades de Visual Studio <xref:System.Windows.Forms.ListView.Columns%2A> .) situado junto a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="91700-111">In the **Properties** window, click the **Ellipsis** button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.ListView.Columns%2A> property.</span></span>

     <span data-ttu-id="91700-112">Aparece el editor de la **colección ColumnHeader** .</span><span class="sxs-lookup"><span data-stu-id="91700-112">The **ColumnHeader Collection Editor** appears.</span></span>

3. <span data-ttu-id="91700-113">Use el botón **Agregar** para agregar nuevas columnas.</span><span class="sxs-lookup"><span data-stu-id="91700-113">Use the **Add** button to add new columns.</span></span> <span data-ttu-id="91700-114">Después, puede seleccionar el encabezado de columna y establecer su texto (el título de la columna), la alineación del texto y el ancho.</span><span class="sxs-lookup"><span data-stu-id="91700-114">You can then select the column header and set its text (the caption of the column), text alignment, and width.</span></span>

## <a name="see-also"></a><span data-ttu-id="91700-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="91700-115">See also</span></span>

- [<span data-ttu-id="91700-116">Información general del control ListView</span><span class="sxs-lookup"><span data-stu-id="91700-116">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="91700-117">Cómo: Agregar y quitar elementos con el control ListView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="91700-117">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="91700-118">Cómo: Mostrar subelementos en columnas con el control ListView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="91700-118">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="91700-119">Cómo: Mostrar iconos del control ListView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="91700-119">How to: Display Icons for the Windows Forms ListView Control</span></span>](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [<span data-ttu-id="91700-120">Cómo: Agregar información personalizada a un control TreeView o ListView (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="91700-120">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
