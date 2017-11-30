---
title: "Cómo: Mostrar los datos enlazados en un control DataRepeater (Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- DataRepeater, data-binding
- DataRepeater, displaying bound controls
ms.assetid: 56a15326-1334-4275-af4e-075cad79e6f7
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 770003c8879661bfc1ce683f5b6ed84483cf47ea
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-bound-data-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="0ec50-102">Cómo: Mostrar los datos enlazados en un control DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="0ec50-102">How to: Display Bound Data in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="0ec50-103">El uso más común de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control consiste en Mostrar datos enlazados desde una base de datos u otro origen de datos.</span><span class="sxs-lookup"><span data-stu-id="0ec50-103">The most common use of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control is to display bound data from a database or other data source.</span></span>  
  
 <span data-ttu-id="0ec50-104">Además de los controles enlazados, puede que desee agregar otros controles, como una etiqueta estática o una imagen que se repite en cada elemento de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span><span class="sxs-lookup"><span data-stu-id="0ec50-104">In addition to bound controls, you may want to add other controls, such as a static label or an image that is repeated on each item in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="0ec50-105">Para obtener más información, consulte [Cómo: mostrar controles no enlazados en un DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="0ec50-105">For more information, see [How to: Display Unbound Controls in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).</span></span>  
  
 <span data-ttu-id="0ec50-106">También puede enlazar a un origen de datos en tiempo de ejecución estableciendo la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> propiedad `True` y la asignación de un origen de datos a la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="0ec50-106">You can also bind to a data source at run time by setting the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> property to `True` and assigning a data source to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A> property.</span></span> <span data-ttu-id="0ec50-107">En este caso, deberá administrar todas las interacciones con el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="0ec50-107">In this case, you will need to manage all interaction with the data source.</span></span> <span data-ttu-id="0ec50-108">Para obtener más información, consulte [modo Virtual del control DataRepeater](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="0ec50-108">For more information, see [Virtual Mode in the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-data-bound-datarepeater"></a><span data-ttu-id="0ec50-109">Para crear un DataRepeater enlazado a datos</span><span class="sxs-lookup"><span data-stu-id="0ec50-109">To create a data-bound DataRepeater</span></span>  
  
1.  <span data-ttu-id="0ec50-110">Arrastre un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controlar desde la **Visual Basic PowerPacks** pestaña en el **cuadro de herramientas** a un control de formulario o contenedor.</span><span class="sxs-lookup"><span data-stu-id="0ec50-110">Drag a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="0ec50-111">Arrastre las asas de ajuste de tamaño y posición a tamaño y colocar el control.</span><span class="sxs-lookup"><span data-stu-id="0ec50-111">Drag the sizing and position handles to size and position the control.</span></span>  
  
     <span data-ttu-id="0ec50-112">Tenga en cuenta que el control tiene dos regiones rectangulares.</span><span class="sxs-lookup"><span data-stu-id="0ec50-112">Note that the control has two rectangular regions.</span></span> <span data-ttu-id="0ec50-113">La región superior es el *plantilla de elemento*; los controles agregados a la plantilla se repetirá en cada elemento en el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0ec50-113">The upper region is the *item template*; controls added to the template will be repeated in each item in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control at run time.</span></span> <span data-ttu-id="0ec50-114">La región inferior es el *ventanilla*, donde se mostrarán los elementos.</span><span class="sxs-lookup"><span data-stu-id="0ec50-114">The lower region is the *viewport*, where the items will be displayed.</span></span>  
  
     <span data-ttu-id="0ec50-115">También puede cambiar el tamaño y colocar el control o la plantilla de elemento cambiando el **tamaño** y **posición** propiedades en la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="0ec50-115">You can also size and position the control or the item template by changing the **Size** and **Position** properties in the Properties window.</span></span>  
  
3.  <span data-ttu-id="0ec50-116">En el menú **Datos** , haga clic en **Mostrar orígenes de datos**.</span><span class="sxs-lookup"><span data-stu-id="0ec50-116">On the **Data** menu, click **Show Data Sources**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0ec50-117">Si el **orígenes de datos** ventana está vacía, agregue un origen de datos a él.</span><span class="sxs-lookup"><span data-stu-id="0ec50-117">If the **Data Sources** window is empty, add a data source to it.</span></span> <span data-ttu-id="0ec50-118">Para obtener más información, vea [Agregar nuevos orígenes de datos](/visualstudio/data-tools/add-new-data-sources).</span><span class="sxs-lookup"><span data-stu-id="0ec50-118">For more information, see [Add new data sources](/visualstudio/data-tools/add-new-data-sources).</span></span>  
  
4.  <span data-ttu-id="0ec50-119">En el **orígenes de datos** ventana, seleccione el nodo de nivel superior de la tabla que contiene los datos que desea enlazar.</span><span class="sxs-lookup"><span data-stu-id="0ec50-119">In the **Data Sources** window, select the top-level node for the table that contains the data that you want to bind.</span></span>  
  
5.  <span data-ttu-id="0ec50-120">Cambie el tipo drop de la tabla a `Details` haciendo clic en `Details` en la lista desplegable en el nodo de tabla.</span><span class="sxs-lookup"><span data-stu-id="0ec50-120">Change the drop type of the table to `Details` by clicking `Details` in the drop-down list on the table node.</span></span>  
  
6.  <span data-ttu-id="0ec50-121">Seleccione el nodo de tabla y arrástrelo a la región de la plantilla de elemento de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span><span class="sxs-lookup"><span data-stu-id="0ec50-121">Select the table node and drag it onto the item template region of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="0ec50-122">Puede especificar qué tipos de controles que se muestran para cada campo.</span><span class="sxs-lookup"><span data-stu-id="0ec50-122">You can specify which types of controls are displayed for each field.</span></span> <span data-ttu-id="0ec50-123">Para obtener más información, consulte [establecer el control que se creará al arrastrar desde la ventana de orígenes de datos](/visualstudio/data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window).</span><span class="sxs-lookup"><span data-stu-id="0ec50-123">For more information, see [Set the control to be created when dragging from the Data Sources window](/visualstudio/data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ec50-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ec50-124">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [<span data-ttu-id="0ec50-125">Introducción al control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="0ec50-125">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="0ec50-126">Mostrar controles no enlazados en un control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="0ec50-126">How to: Display Unbound Controls in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="0ec50-127">Cómo: crear un formulario principal-detalle mediante dos controles DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="0ec50-127">How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)  
 [<span data-ttu-id="0ec50-128">Cambiar la apariencia de un control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="0ec50-128">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="0ec50-129">Solución de problemas del control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="0ec50-129">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
