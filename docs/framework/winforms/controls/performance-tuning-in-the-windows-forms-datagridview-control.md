---
title: "Ajuste del rendimiento del control DataGridView en formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "DataGridView (control) [Windows Forms], ajuste del rendimiento"
  - "ajuste del rendimiento, cuadrículas de datos"
  - "rendimiento, DataGridView (control)"
ms.assetid: 6ccbff28-a0ff-41e4-b601-61b31b61851d
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Ajuste del rendimiento del control DataGridView en formularios Windows Forms
Al trabajar con grandes volúmenes de datos, el control `DataGridView` puede utilizar una gran cantidad de memoria en sobrecarga, a menos que la utilice cuidadosamente.  En clientes con memoria limitada, puede evitar parte de esta sobrecarga evitando las características que tienen un costo de memoria alto.  También puede administrar varias o todas las tareas de mantenimiento y recuperación de datos utilizando el modo virtual con el fin de personalizar la utilización de memoria para su caso.  
  
## En esta sección  
 [Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 Describe cómo utilizar el control `DataGridView` de un modo que evita el uso innecesario de memoria y las consecuencias en el rendimiento cuando se trabaja con grandes volúmenes de datos  
  
 [Modo virtual del control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)  
 Describe cómo utilizar el modo virtual para complementar o reemplazar el mecanismo de enlace de datos estándar.  
  
 [Tutorial: Implementar el modo virtual en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)  
 Describe cómo implementar los controladores para varios eventos de modo virtual.  También muestra cómo implementar la operación de reversión para filas y confirmar las modificaciones del usuario.  
  
 [Implementar el modo virtual mediante la carga de datos Just\-In\-Time en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 Describe cómo cargar datos a petición, que resulta de utilidad cuando se tienen más datos para mostrar de lo que se puede almacenar en la memoria disponible del cliente.  
  
## Referencia  
 <xref:System.Windows.Forms.DataGridView>  
 Proporciona documentación de referencia para el control <xref:System.Windows.Forms.DataGridView>.  
  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 Proporciona documentación de referencia para la propiedad <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>.  
  
## Vea también  
 [Control DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)   
 [Modos de presentación de datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)