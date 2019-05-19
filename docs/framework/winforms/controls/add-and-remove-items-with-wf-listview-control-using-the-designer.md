---
title: Procedimiento para agregar y quitar elementos con el control ListView de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], populating
- ListView control [Windows Forms], adding list items
ms.assetid: 217611ee-fd11-4d39-9a54-a37c3e781be1
ms.openlocfilehash: 37660061140e38661a27f8f750604ae2609ac57c
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2019
ms.locfileid: "65882293"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="6917f-102">Procedimiento para agregar y quitar elementos con el control ListView de formularios Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="6917f-102">How to: Add and Remove Items with the Windows Forms ListView Control Using the Designer</span></span>
<span data-ttu-id="6917f-103">El proceso de agregar un elemento a un formulario Windows Forms <xref:System.Windows.Forms.ListView> control consta principalmente de especificar el elemento y asignarle propiedades.</span><span class="sxs-lookup"><span data-stu-id="6917f-103">The process of adding an item to a Windows Forms <xref:System.Windows.Forms.ListView> control consists primarily of specifying the item and assigning properties to it.</span></span> <span data-ttu-id="6917f-104">Agregar o quitar elementos de lista puede realizarse en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="6917f-104">Adding or removing list items can be done at any time.</span></span>  
  
 <span data-ttu-id="6917f-105">El procedimiento siguiente requiere una **aplicación Windows** proyecto con un formulario que contenga un <xref:System.Windows.Forms.ListView> control.</span><span class="sxs-lookup"><span data-stu-id="6917f-105">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="6917f-106">Para obtener información acerca de cómo configurar un proyecto de este tipo, vea [Cómo: Cree un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="6917f-106">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6917f-107">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="6917f-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="6917f-108">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="6917f-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="6917f-109">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="6917f-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-or-remove-items-using-the-designer"></a><span data-ttu-id="6917f-110">Para agregar o quitar elementos mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="6917f-110">To add or remove items using the designer</span></span>  
  
1. <span data-ttu-id="6917f-111">Seleccione el control <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="6917f-111">Select the <xref:System.Windows.Forms.ListView> control.</span></span>  
  
2.  <span data-ttu-id="6917f-112">En el **propiedades** ventana, haga clic en el **puntos suspensivos** (![los puntos suspensivos (...) en la ventana Propiedades de Visual Studio.](./media/visual-studio-ellipsis-button.png)) situado junto a la <xref:System.Windows.Forms.ListView.Items%2A> propiedad .</span><span class="sxs-lookup"><span data-stu-id="6917f-112">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>  
  
     <span data-ttu-id="6917f-113">El **Editor de la colección ListViewItem** aparece.</span><span class="sxs-lookup"><span data-stu-id="6917f-113">The **ListViewItem Collection Editor** appears.</span></span>  
  
3. <span data-ttu-id="6917f-114">Para agregar un elemento, haga clic en el **agregar** botón.</span><span class="sxs-lookup"><span data-stu-id="6917f-114">To add an item, click the **Add** button.</span></span> <span data-ttu-id="6917f-115">A continuación, puede establecer las propiedades del nuevo elemento, tales como la <xref:System.Windows.Forms.ListView.Text%2A> y <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> propiedades.</span><span class="sxs-lookup"><span data-stu-id="6917f-115">You can then set properties of the new item, such as the <xref:System.Windows.Forms.ListView.Text%2A> and <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> properties.</span></span>  
  
4. <span data-ttu-id="6917f-116">Para quitar un elemento, selecciónelo y haga clic en el **quitar** botón.</span><span class="sxs-lookup"><span data-stu-id="6917f-116">To remove an item, select it and click the **Remove** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6917f-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="6917f-117">See also</span></span>

- [<span data-ttu-id="6917f-118">Información general del control ListView</span><span class="sxs-lookup"><span data-stu-id="6917f-118">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="6917f-119">Cómo: Agregar columnas al Control de ListView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6917f-119">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [<span data-ttu-id="6917f-120">Cómo: Mostrar subelementos en columnas con el Control ListView de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="6917f-120">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="6917f-121">Cómo: Mostrar iconos para el Control ListView de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="6917f-121">How to: Display Icons for the Windows Forms ListView Control</span></span>](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [<span data-ttu-id="6917f-122">Cómo: Agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="6917f-122">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [<span data-ttu-id="6917f-123">Cómo: Agrupar elementos en un Control ListView de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="6917f-123">How to: Group Items in a Windows Forms ListView Control</span></span>](how-to-group-items-in-a-windows-forms-listview-control.md)
