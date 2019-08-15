---
title: Procedimiento para habilitar la vista en mosaico en un control ListView de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- tile view feature
- ListView control [Windows Forms], tile view
- tiling [Windows Forms], Windows Forms, controls
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
ms.openlocfilehash: 8a45a8a484bd373f53585b1b113a51e59b30fca2
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040362"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="4a135-102">Procedimiento para habilitar la vista en mosaico en un control ListView de formularios Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="4a135-102">How to: Enable Tile View in a Windows Forms ListView Control Using the Designer</span></span>
<span data-ttu-id="4a135-103">La característica de vista de mosaico <xref:System.Windows.Forms.ListView> del control le permite proporcionar un equilibrio visual entre la información gráfica y de texto.</span><span class="sxs-lookup"><span data-stu-id="4a135-103">The tile view feature of the <xref:System.Windows.Forms.ListView> control enables you to provide a visual balance between graphical and textual information.</span></span> <span data-ttu-id="4a135-104">La información de texto que se muestra para un elemento en la vista de mosaico es igual que la información de columna definida para la vista de detalles.</span><span class="sxs-lookup"><span data-stu-id="4a135-104">The textual information displayed for an item in tile view is the same as the column information defined for details view.</span></span> <span data-ttu-id="4a135-105">La vista de mosaico funciona en combinación con las características de agrupación o de marca <xref:System.Windows.Forms.ListView> de inserción del control.</span><span class="sxs-lookup"><span data-stu-id="4a135-105">Tile view functions in combination with either the grouping or insertion mark features in the <xref:System.Windows.Forms.ListView> control.</span></span>

 <span data-ttu-id="4a135-106">La vista de mosaico usa un icono 32 x 32 y varias líneas de texto, tal como se muestra en la siguiente imagen.</span><span class="sxs-lookup"><span data-stu-id="4a135-106">The tile view uses a 32 x 32 icon and several lines of text, as shown in the following image.</span></span>

 <span data-ttu-id="4a135-107">![Vista en mosaico en un control ListView](./media/enable-tile-view-in-a-wf-listview-control-using-the-designer/tile-view-in-listview-control.gif "Iconos y texto de la vista de mosaico")</span><span class="sxs-lookup"><span data-stu-id="4a135-107">![Tile View in a ListView Control](./media/enable-tile-view-in-a-wf-listview-control-using-the-designer/tile-view-in-listview-control.gif "Tile view icons and text")</span></span>

 <span data-ttu-id="4a135-108">Las propiedades y los métodos de la vista de mosaico permiten especificar los campos de columna que se van a mostrar para cada elemento y controlar colectivamente el tamaño y la apariencia de todos los elementos de una ventana de vista de mosaico.</span><span class="sxs-lookup"><span data-stu-id="4a135-108">Tile view properties and methods enable you to specify which column fields to display for each item, and to collectively control the size and appearance of all items within a tile view window.</span></span> <span data-ttu-id="4a135-109">Para mayor claridad, la primera línea de texto de un mosaico siempre es el nombre del elemento; no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="4a135-109">For clarity, the first line of text in a tile is always the item's name; it cannot be changed.</span></span>

 <span data-ttu-id="4a135-110">El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que <xref:System.Windows.Forms.ListView> contenga un control.</span><span class="sxs-lookup"><span data-stu-id="4a135-110">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="4a135-111">Para obtener información acerca de cómo configurar este tipo de [proyecto, consulte Cómo: Cree un proyecto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) de aplicación de [Windows Forms y cómo: Agregue controles a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="4a135-111">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4a135-112">La vista de mosaico solo está disponible en [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] cuando la aplicación llama al método <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4a135-112">The tile view is available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="4a135-113">En sistemas operativos anteriores, el código relacionado con la vista de mosaico no tiene ningún efecto y el control <xref:System.Windows.Forms.ListView> se muestra en la vista de iconos grandes.</span><span class="sxs-lookup"><span data-stu-id="4a135-113">On earlier operating systems, any code related to the tile view has no effect, and the <xref:System.Windows.Forms.ListView> control displays in the large icon view.</span></span> <span data-ttu-id="4a135-114">Para obtener más información, consulta <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4a135-114">For more information, see <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>.</span></span>

## <a name="to-set-tile-view-in-the-designer"></a><span data-ttu-id="4a135-115">Para establecer la vista de mosaico en el diseñador</span><span class="sxs-lookup"><span data-stu-id="4a135-115">To set tile view in the designer</span></span>

1. <span data-ttu-id="4a135-116">En Visual Studio, seleccione el <xref:System.Windows.Forms.ListView> control en el formulario.</span><span class="sxs-lookup"><span data-stu-id="4a135-116">In Visual Studio, select the <xref:System.Windows.Forms.ListView> control on your form.</span></span>

2. <span data-ttu-id="4a135-117">En la ventana **propiedades** , seleccione la <xref:System.Windows.Forms.ListView.View%2A> propiedad y elija **mosaico**.</span><span class="sxs-lookup"><span data-stu-id="4a135-117">In the **Properties** window, select the <xref:System.Windows.Forms.ListView.View%2A> property and choose **Tile**.</span></span>

## <a name="see-also"></a><span data-ttu-id="4a135-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a135-118">See also</span></span>

- <xref:System.Windows.Forms.ListView.TileSize%2A>
- [<span data-ttu-id="4a135-119">Información general del control ListView</span><span class="sxs-lookup"><span data-stu-id="4a135-119">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
