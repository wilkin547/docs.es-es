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
# <a name="performance-tuning-in-the-windows-forms-datagridview-control"></a>Ajuste del rendimiento del control DataGridView en Windows Forms
Cuando se trabaja con grandes cantidades de datos, el control de `DataGridView` puede consumir una gran cantidad de memoria en exceso, a menos que se use con cuidado. En los clientes con memoria limitada, puede evitar esta sobrecarga evitando las características que tienen un alto costo de memoria. También puede administrar algunas o todas las tareas de mantenimiento y recuperación de datos mediante el modo virtual con el fin de personalizar el uso de memoria para su escenario.  
  
## <a name="in-this-section"></a>En esta sección  
 [Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 Describe cómo usar el control `DataGridView` de forma que se evite el uso de memoria y las penalizaciones de rendimiento innecesarias al trabajar con grandes cantidades de datos.  
  
 [Modo virtual del control DataGridView de Windows Forms](virtual-mode-in-the-windows-forms-datagridview-control.md)  
 Describe cómo usar el modo virtual para complementar o reemplazar el mecanismo de enlace de datos estándar.  
  
 [Tutorial: Implementar el modo virtual en el control DataGridView de Windows Forms](implementing-virtual-mode-wf-datagridview-control.md)  
 Describe cómo implementar Controladores para varios eventos de modo virtual. También muestra cómo implementar la reversión de nivel de fila y la confirmación para las ediciones de usuario.  
  
 [Implementar el modo virtual mediante la carga de datos Just-In-Time en el control DataGridView de formularios Windows Forms](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 Describe cómo cargar datos a petición, lo que resulta útil cuando se tienen más datos que mostrar que la memoria de cliente disponible que puede almacenar.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Windows.Forms.DataGridView>  
 Proporciona documentación de referencia para el control <xref:System.Windows.Forms.DataGridView>.  
  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 Proporciona documentación de referencia para la propiedad <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>.  
  
## <a name="see-also"></a>Consulte también

- [DataGridView (control)](datagridview-control-windows-forms.md)
- [Modos de presentación de datos en el control DataGridView de Windows Forms](data-display-modes-in-the-windows-forms-datagridview-control.md)
