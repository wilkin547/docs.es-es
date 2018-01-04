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
ms.workload: dotnet
ms.openlocfilehash: da0171bf4fa056de2dd06c2f7e431ea55a8dab1a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="performance-tuning-in-the-windows-forms-datagridview-control"></a>Ajuste del rendimiento del control DataGridView en formularios Windows Forms
Cuando se trabaja con grandes cantidades de datos, el `DataGridView` control puede consumir una gran cantidad de memoria en sobrecarga, a menos que se use con cuidado. En clientes con memoria limitada, puede evitar parte de esta sobrecarga evitando las características que tienen un alto costo de memoria. También puede administrar algunos o todos de mantenimiento de datos y recuperación de las tareas mediante el modo virtual con el fin de personalizar el uso de memoria para su escenario.  
  
## <a name="in-this-section"></a>En esta sección  
 [Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 Describe cómo utilizar el `DataGridView` control de forma que evite sanciones de rendimiento y uso de memoria innecesario cuando se trabaja con grandes cantidades de datos.  
  
 [Modo virtual del control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)  
 Describe cómo utilizar el modo virtual para complementar o reemplazar el mecanismo de enlace de datos estándar.  
  
 [Tutorial: Implementar el modo virtual en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)  
 Describe cómo implementar controladores para varios eventos de modo virtual. También muestra cómo implementar el nivel de fila rollback y commit para las modificaciones del usuario.  
  
 [Implementar el modo virtual mediante la carga de datos Just-In-Time en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 Describe cómo cargar datos a petición, lo que resulta útil cuando hay más datos para mostrar que puede almacenar la memoria disponible del cliente.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Windows.Forms.DataGridView>  
 Proporciona documentación de referencia para el control <xref:System.Windows.Forms.DataGridView>.  
  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 Proporciona documentación de referencia para el <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> propiedad.  
  
## <a name="see-also"></a>Vea también  
 [DataGridView (control)](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [Modos de presentación de datos en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)
