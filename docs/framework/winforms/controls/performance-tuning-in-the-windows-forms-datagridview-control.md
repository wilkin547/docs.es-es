---
title: Ajuste del rendimiento del control DataGridView en formularios Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], performance tuning
- performance [Windows Forms], DataGridView control
- performance tuning [Windows Forms], data grids
ms.assetid: 6ccbff28-a0ff-41e4-b601-61b31b61851d
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 452c55d38a896ec96e0992a4b9826f08dc4caa0e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="performance-tuning-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="dd357-102">Ajuste del rendimiento del control DataGridView en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dd357-102">Performance Tuning in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="dd357-103">Cuando se trabaja con grandes cantidades de datos, el `DataGridView` control puede consumir una gran cantidad de memoria en sobrecarga, a menos que se use con cuidado.</span><span class="sxs-lookup"><span data-stu-id="dd357-103">When working with large amounts of data, the `DataGridView` control can consume a large amount of memory in overhead, unless you use it carefully.</span></span> <span data-ttu-id="dd357-104">En clientes con memoria limitada, puede evitar parte de esta sobrecarga evitando las características que tienen un alto costo de memoria.</span><span class="sxs-lookup"><span data-stu-id="dd357-104">On clients with limited memory, you can avoid some of this overhead by avoiding features that have a high memory cost.</span></span> <span data-ttu-id="dd357-105">También puede administrar algunos o todos de mantenimiento de datos y recuperación de las tareas mediante el modo virtual con el fin de personalizar el uso de memoria para su escenario.</span><span class="sxs-lookup"><span data-stu-id="dd357-105">You can also manage some or all of the data maintenance and retrieval tasks yourself using virtual mode in order to customize the memory usage for your scenario.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dd357-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="dd357-106">In This Section</span></span>  
 [<span data-ttu-id="dd357-107">Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dd357-107">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="dd357-108">Describe cómo utilizar el `DataGridView` control de forma que evite sanciones de rendimiento y uso de memoria innecesario cuando se trabaja con grandes cantidades de datos.</span><span class="sxs-lookup"><span data-stu-id="dd357-108">Describes how to use the `DataGridView` control in a way that avoids unnecessary memory usage and performance penalties when working with large amounts of data.</span></span>  
  
 [<span data-ttu-id="dd357-109">Modo virtual del control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dd357-109">Virtual Mode in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="dd357-110">Describe cómo utilizar el modo virtual para complementar o reemplazar el mecanismo de enlace de datos estándar.</span><span class="sxs-lookup"><span data-stu-id="dd357-110">Describes how to use virtual mode to supplement or replace the standard data-binding mechanism.</span></span>  
  
 [<span data-ttu-id="dd357-111">Tutorial: Implementar el modo virtual en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dd357-111">Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)  
 <span data-ttu-id="dd357-112">Describe cómo implementar controladores para varios eventos de modo virtual.</span><span class="sxs-lookup"><span data-stu-id="dd357-112">Describes how to implement handlers for several virtual-mode events.</span></span> <span data-ttu-id="dd357-113">También muestra cómo implementar el nivel de fila rollback y commit para las modificaciones del usuario.</span><span class="sxs-lookup"><span data-stu-id="dd357-113">Also demonstrates how to implement row-level rollback and commit for user edits.</span></span>  
  
 [<span data-ttu-id="dd357-114">Implementar el modo virtual mediante la carga de datos Just-In-Time en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dd357-114">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 <span data-ttu-id="dd357-115">Describe cómo cargar datos a petición, lo que resulta útil cuando hay más datos para mostrar que puede almacenar la memoria disponible del cliente.</span><span class="sxs-lookup"><span data-stu-id="dd357-115">Describes how to load data on demand, which is useful when you have more data to display than the available client memory can store.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="dd357-116">Referencia</span><span class="sxs-lookup"><span data-stu-id="dd357-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="dd357-117">Proporciona documentación de referencia para el control <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="dd357-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 <span data-ttu-id="dd357-118">Proporciona documentación de referencia para el <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="dd357-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd357-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd357-119">See Also</span></span>  
 [<span data-ttu-id="dd357-120">DataGridView (control)</span><span class="sxs-lookup"><span data-stu-id="dd357-120">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [<span data-ttu-id="dd357-121">Modos de presentación de datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dd357-121">Data Display Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)
