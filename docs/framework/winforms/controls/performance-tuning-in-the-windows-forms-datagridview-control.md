---
title: Optimizar el rendimiento en el control DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], performance tuning
- performance [Windows Forms], DataGridView control
- performance tuning [Windows Forms], data grids
ms.assetid: 6ccbff28-a0ff-41e4-b601-61b31b61851d
ms.openlocfilehash: 77ad86c4cd606bcf074473c97371ec27bcc5605b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744272"
---
# <a name="performance-tuning-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="f3de9-102">Ajuste del rendimiento del control DataGridView en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f3de9-102">Performance Tuning in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="f3de9-103">Cuando se trabaja con grandes cantidades de datos, el control de `DataGridView` puede consumir una gran cantidad de memoria en exceso, a menos que se use con cuidado.</span><span class="sxs-lookup"><span data-stu-id="f3de9-103">When working with large amounts of data, the `DataGridView` control can consume a large amount of memory in overhead, unless you use it carefully.</span></span> <span data-ttu-id="f3de9-104">En los clientes con memoria limitada, puede evitar esta sobrecarga evitando las características que tienen un alto costo de memoria.</span><span class="sxs-lookup"><span data-stu-id="f3de9-104">On clients with limited memory, you can avoid some of this overhead by avoiding features that have a high memory cost.</span></span> <span data-ttu-id="f3de9-105">También puede administrar algunas o todas las tareas de mantenimiento y recuperación de datos mediante el modo virtual con el fin de personalizar el uso de memoria para su escenario.</span><span class="sxs-lookup"><span data-stu-id="f3de9-105">You can also manage some or all of the data maintenance and retrieval tasks yourself using virtual mode in order to customize the memory usage for your scenario.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f3de9-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f3de9-106">In This Section</span></span>  
 [<span data-ttu-id="f3de9-107">Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f3de9-107">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="f3de9-108">Describe cómo usar el control `DataGridView` de forma que se evite el uso de memoria y las penalizaciones de rendimiento innecesarias al trabajar con grandes cantidades de datos.</span><span class="sxs-lookup"><span data-stu-id="f3de9-108">Describes how to use the `DataGridView` control in a way that avoids unnecessary memory usage and performance penalties when working with large amounts of data.</span></span>  
  
 [<span data-ttu-id="f3de9-109">Modo virtual del control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f3de9-109">Virtual Mode in the Windows Forms DataGridView Control</span></span>](virtual-mode-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="f3de9-110">Describe cómo usar el modo virtual para complementar o reemplazar el mecanismo de enlace de datos estándar.</span><span class="sxs-lookup"><span data-stu-id="f3de9-110">Describes how to use virtual mode to supplement or replace the standard data-binding mechanism.</span></span>  
  
 [<span data-ttu-id="f3de9-111">Tutorial: Implementar el modo virtual en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f3de9-111">Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-wf-datagridview-control.md)  
 <span data-ttu-id="f3de9-112">Describe cómo implementar Controladores para varios eventos de modo virtual.</span><span class="sxs-lookup"><span data-stu-id="f3de9-112">Describes how to implement handlers for several virtual-mode events.</span></span> <span data-ttu-id="f3de9-113">También muestra cómo implementar la reversión de nivel de fila y la confirmación para las ediciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="f3de9-113">Also demonstrates how to implement row-level rollback and commit for user edits.</span></span>  
  
 [<span data-ttu-id="f3de9-114">Implementar el modo virtual mediante la carga de datos Just-In-Time en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f3de9-114">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 <span data-ttu-id="f3de9-115">Describe cómo cargar datos a petición, lo que resulta útil cuando se tienen más datos que mostrar que la memoria de cliente disponible que puede almacenar.</span><span class="sxs-lookup"><span data-stu-id="f3de9-115">Describes how to load data on demand, which is useful when you have more data to display than the available client memory can store.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="f3de9-116">Referencia</span><span class="sxs-lookup"><span data-stu-id="f3de9-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="f3de9-117">Proporciona documentación de referencia para el control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="f3de9-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 <span data-ttu-id="f3de9-118">Proporciona documentación de referencia para la propiedad <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="f3de9-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3de9-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f3de9-119">See also</span></span>

- [<span data-ttu-id="f3de9-120">DataGridView (control)</span><span class="sxs-lookup"><span data-stu-id="f3de9-120">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="f3de9-121">Modos de presentación de datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f3de9-121">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)
