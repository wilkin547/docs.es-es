---
title: "Cómo: Mostrar controles no enlazados en un control DataRepeater (Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- DataRepeater, adding unbound controls
- DataRepeater
- displaying unbound data
ms.assetid: f234fa40-5a13-4209-930e-7c5f81e86e66
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3e96219f0ea8b8198967e9fa3c6e5afb824352db
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="8b264-102">Cómo: Mostrar controles no enlazados en un control DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="8b264-102">How to: Display Unbound Controls in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="8b264-103">Además de los controles enlazados, puede que desee agregar otros controles a un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, como una etiqueta estática o una imagen que se repite en cada elemento de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span><span class="sxs-lookup"><span data-stu-id="8b264-103">In addition to bound controls, you may want to add other controls to a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, such as a static label or an image that is repeated on each item in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8b264-104">También debe tener al menos un control enlazado en la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> o nada se mostrará en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8b264-104">You must also have at least one bound control on the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> or nothing will be displayed at run time.</span></span>  
  
### <a name="to-add-unbound-controls-to-a-datarepeater"></a><span data-ttu-id="8b264-105">Para agregar controles independientes a DataRepeater</span><span class="sxs-lookup"><span data-stu-id="8b264-105">To add unbound controls to a DataRepeater</span></span>  
  
1.  <span data-ttu-id="8b264-106">Arrastre un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> controlar desde la **Visual Basic PowerPacks** pestaña en el **cuadro de herramientas** a un control de formulario o contenedor.</span><span class="sxs-lookup"><span data-stu-id="8b264-106">Drag a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="8b264-107">Arrastre las asas de ajuste de tamaño y posición a tamaño y colocar el control.</span><span class="sxs-lookup"><span data-stu-id="8b264-107">Drag the sizing and position handles to size and position the control.</span></span>  
  
     <span data-ttu-id="8b264-108">También puede cambiar el tamaño y colocar el control cambiando la **tamaño** y **posición** propiedades en la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="8b264-108">You can also size and position the control by changing the **Size** and **Position** properties in the Properties window.</span></span>  
  
3.  <span data-ttu-id="8b264-109">Agregue al menos un control enlazado a datos a la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span><span class="sxs-lookup"><span data-stu-id="8b264-109">Add at least one data-bound control to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="8b264-110">Para obtener más información, consulte [Cómo: mostrar datos enlazados en un DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="8b264-110">For more information, see [How to: Display Bound Data in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md).</span></span>  
  
4.  <span data-ttu-id="8b264-111">Arrastre un control desde el **cuadro de herramientas** a la región de la plantilla de elemento de la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span><span class="sxs-lookup"><span data-stu-id="8b264-111">Drag a control from the **Toolbox** onto the item template region of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="8b264-112">Tenga en cuenta que el control tiene dos regiones rectangulares.</span><span class="sxs-lookup"><span data-stu-id="8b264-112">Note that the control has two rectangular regions.</span></span> <span data-ttu-id="8b264-113">La región interna es la *plantilla de elemento*; los controles agregados a la plantilla se repetirá en cada elemento en el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8b264-113">The inner region is the *item template*; controls added to the template will be repeated in each item in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control at run time.</span></span> <span data-ttu-id="8b264-114">La región exterior es el *ventanilla*, donde los elementos se mostrarán; controles que se agregan a esta región no se mostrará en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8b264-114">The outer region is the *viewport*, where the items will be displayed; controls that are added to this region will not be displayed at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b264-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="8b264-115">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [<span data-ttu-id="8b264-116">Introducción al control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="8b264-116">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="8b264-117">Solución de problemas del control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="8b264-117">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="8b264-118">Mostrar los datos enlazados en un control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="8b264-118">How to: Display Bound Data in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="8b264-119">Cómo: crear un formulario principal-detalle mediante dos controles DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="8b264-119">How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)  
 [<span data-ttu-id="8b264-120">Cambiar la apariencia de un control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="8b264-120">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
