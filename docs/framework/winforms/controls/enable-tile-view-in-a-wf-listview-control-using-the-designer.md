---
title: Habilitar la vista en mosaico en el control ListView mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- tile view feature
- ListView control [Windows Forms], tile view
- tiling [Windows Forms], Windows Forms, controls
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
ms.openlocfilehash: a0429efaab14995ab1e3f3b0dfd91db61de72fbf
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745803"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="cfd31-102">Cómo: Habilitar la vista en mosaico en un control ListView de formularios Windows Forms mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="cfd31-102">How to: Enable Tile View in a Windows Forms ListView Control Using the Designer</span></span>
<span data-ttu-id="cfd31-103">La característica de vista en mosaico del control <xref:System.Windows.Forms.ListView> permite proporcionar un equilibrio visual entre la información gráfica y de texto.</span><span class="sxs-lookup"><span data-stu-id="cfd31-103">The tile view feature of the <xref:System.Windows.Forms.ListView> control enables you to provide a visual balance between graphical and textual information.</span></span> <span data-ttu-id="cfd31-104">La información de texto que se muestra para un elemento en la vista de mosaico es igual que la información de columna definida para la vista de detalles.</span><span class="sxs-lookup"><span data-stu-id="cfd31-104">The textual information displayed for an item in tile view is the same as the column information defined for details view.</span></span> <span data-ttu-id="cfd31-105">Las funciones de la vista de mosaico en combinación con las características de agrupación o de marca de inserción del control <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="cfd31-105">Tile view functions in combination with either the grouping or insertion mark features in the <xref:System.Windows.Forms.ListView> control.</span></span>

 <span data-ttu-id="cfd31-106">La vista de mosaico usa un icono 32 x 32 y varias líneas de texto, tal como se muestra en la siguiente imagen.</span><span class="sxs-lookup"><span data-stu-id="cfd31-106">The tile view uses a 32 x 32 icon and several lines of text, as shown in the following image.</span></span>

 <span data-ttu-id="cfd31-107">![Vista en mosaico de un control ListView](./media/enable-tile-view-in-a-wf-listview-control-using-the-designer/tile-view-in-listview-control.gif "Texto e iconos de la vista de mosaico")</span><span class="sxs-lookup"><span data-stu-id="cfd31-107">![Tile View in a ListView Control](./media/enable-tile-view-in-a-wf-listview-control-using-the-designer/tile-view-in-listview-control.gif "Tile view icons and text")</span></span>

 <span data-ttu-id="cfd31-108">Las propiedades y los métodos de la vista de mosaico permiten especificar los campos de columna que se van a mostrar para cada elemento y controlar colectivamente el tamaño y la apariencia de todos los elementos de una ventana de vista de mosaico.</span><span class="sxs-lookup"><span data-stu-id="cfd31-108">Tile view properties and methods enable you to specify which column fields to display for each item, and to collectively control the size and appearance of all items within a tile view window.</span></span> <span data-ttu-id="cfd31-109">Para mayor claridad, la primera línea de texto de un mosaico siempre es el nombre del elemento; no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="cfd31-109">For clarity, the first line of text in a tile is always the item's name; it cannot be changed.</span></span>

 <span data-ttu-id="cfd31-110">El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que contenga un control <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="cfd31-110">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="cfd31-111">Para obtener información sobre cómo configurar este tipo de proyecto, vea [Cómo: crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="cfd31-111">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-set-tile-view-in-the-designer"></a><span data-ttu-id="cfd31-112">Para establecer la vista de mosaico en el diseñador</span><span class="sxs-lookup"><span data-stu-id="cfd31-112">To set tile view in the designer</span></span>

1. <span data-ttu-id="cfd31-113">En Visual Studio, seleccione el control <xref:System.Windows.Forms.ListView> del formulario.</span><span class="sxs-lookup"><span data-stu-id="cfd31-113">In Visual Studio, select the <xref:System.Windows.Forms.ListView> control on your form.</span></span>

2. <span data-ttu-id="cfd31-114">En la ventana **propiedades** , seleccione la propiedad <xref:System.Windows.Forms.ListView.View%2A> y elija **mosaico**.</span><span class="sxs-lookup"><span data-stu-id="cfd31-114">In the **Properties** window, select the <xref:System.Windows.Forms.ListView.View%2A> property and choose **Tile**.</span></span>

## <a name="see-also"></a><span data-ttu-id="cfd31-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="cfd31-115">See also</span></span>

- <xref:System.Windows.Forms.ListView.TileSize%2A>
- [<span data-ttu-id="cfd31-116">Información general del control ListView</span><span class="sxs-lookup"><span data-stu-id="cfd31-116">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
