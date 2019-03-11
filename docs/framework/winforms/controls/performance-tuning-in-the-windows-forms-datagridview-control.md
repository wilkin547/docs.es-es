---
title: Ajuste del rendimiento del control DataGridView en formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], performance tuning
- performance [Windows Forms], DataGridView control
- performance tuning [Windows Forms], data grids
ms.assetid: 6ccbff28-a0ff-41e4-b601-61b31b61851d
ms.openlocfilehash: d425488adb8569a48333de4f8c0312143029fbe0
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703181"
---
# <a name="performance-tuning-in-the-windows-forms-datagridview-control"></a>Ajuste del rendimiento del control DataGridView en formularios Windows Forms
Cuando se trabaja con grandes cantidades de datos, el `DataGridView` control puede consumir una gran cantidad de memoria en la sobrecarga, a menos que use con cuidado. En los clientes con memoria limitada, puede evitar algunos de estos gastos evitando las características que tienen un alto costo de memoria. También puede administrar algunos o todos el mantenimiento de datos y tareas de recuperación mediante el modo virtual con el fin de personalizar el uso de memoria para su escenario.  
  
## <a name="in-this-section"></a>En esta sección  
 [Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 Describe cómo utilizar el `DataGridView` control de forma que evita las penalizaciones de rendimiento y uso de memoria innecesario cuando se trabaja con grandes cantidades de datos.  
  
 [Modo virtual del control DataGridView de Windows Forms](virtual-mode-in-the-windows-forms-datagridview-control.md)  
 Describe cómo utilizar el modo virtual para complementar o reemplazar el mecanismo de enlace de datos estándar.  
  
 [Tutorial: Implementar el modo Virtual en el Control DataGridView de formularios de Windows](implementing-virtual-mode-wf-datagridview-control.md)  
 Describe cómo implementar controladores para varios eventos en modo virtual. También muestra cómo implementar el nivel de fila rollback y commit para las modificaciones del usuario.  
  
 [Implementar el modo virtual mediante la carga de datos Just-In-Time en el control DataGridView de formularios Windows Forms](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 Describe cómo cargar datos a petición, lo que resulta útil cuando hay más datos para mostrar que puede almacenar la memoria disponible del cliente.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Windows.Forms.DataGridView>  
 Proporciona documentación de referencia para el control <xref:System.Windows.Forms.DataGridView>.  
  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 Proporciona documentación de referencia para el <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> propiedad.  
  
## <a name="see-also"></a>Vea también
- [DataGridView (control)](datagridview-control-windows-forms.md)
- [Modos de presentación de datos en el control DataGridView de Windows Forms](data-display-modes-in-the-windows-forms-datagridview-control.md)
