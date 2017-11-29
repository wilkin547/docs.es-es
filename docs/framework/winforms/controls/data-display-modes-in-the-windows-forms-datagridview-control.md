---
title: "Modos de presentación de datos en el control DataGridView de formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data [Windows Forms], display modes
- data grids [Windows Forms], display modes
- DataGridView control [Windows Forms], display modes
ms.assetid: 9755a030-3f3f-4705-a661-ba5a48a81875
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dc7fd3d3012053d8c40edf5fdce8af45c62c98c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="data-display-modes-in-the-windows-forms-datagridview-control"></a>Modos de presentación de datos en el control DataGridView de formularios Windows Forms
El <xref:System.Windows.Forms.DataGridView> control puede mostrar datos en tres modos distintos: dependientes, independientes y virtual. Elija el modo más adecuado según sus requisitos.  
  
## <a name="unbound"></a>Sin enlazar  
 El modo sin enlazar es adecuado para mostrar cantidades relativamente pequeñas de datos que se administran mediante programación. No conecte el <xref:System.Windows.Forms.DataGridView> control directamente a un origen de datos como en modo de enlace. En su lugar, debe rellenar el control usted mismo, normalmente mediante la <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> método.  
  
 El modo sin enlazar puede ser particularmente útil para recopilar datos estáticos y de solo lectura, o cuando desea proporcionar su propio código que interactúa con un almacén de datos externo. Si desea que los usuarios interactuar con un origen de datos externo, sin embargo, normalmente, usará el modo de enlace.  
  
 Para obtener un ejemplo que usa solo lectura sin enlazar <xref:System.Windows.Forms.DataGridView>, consulte [Cómo: crear un DataGridView Control de Windows Forms independientes](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md).  
  
## <a name="bound"></a>Enlazar  
 Modo de enlace es adecuado para la administración de datos mediante la interacción automática con el almacén de datos. Puede adjuntar el <xref:System.Windows.Forms.DataGridView> control directamente a su origen de datos estableciendo el <xref:System.Windows.Forms.DataGridView.DataSource%2A> propiedad. Cuando el control está enlazada a datos, filas de datos se insertan y extraen sin necesidad de una administración explícita por parte del usuario. Cuando el <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> propiedad es `true`, cada columna en el origen de datos producirá una columna correspondiente que se creará en el control. Si prefiere crear sus propias columnas, puede establecer esta propiedad en `false` y usar el <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A> propiedad que se va a enlazar cada columna cuando se configura. Esto es útil cuando desea utilizar un tipo de columna distinto de los tipos que se generan de forma predeterminada. Para obtener más información, consulte [tipos de columna en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md).  
  
 Para obtener un ejemplo que usa un límite <xref:System.Windows.Forms.DataGridView> control, vea [Tutorial: validar datos en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).  
  
 También puede agregar columnas sin enlazar a un <xref:System.Windows.Forms.DataGridView> control en el modo de enlace. Esto es útil cuando desea mostrar una columna de botones o vínculos que permiten a los usuarios realizar acciones en filas específicas. También es útil mostrar las columnas con valores calculados de las columnas enlazadas. Puede rellenar los valores de celda para las columnas calculadas en un controlador para el <xref:System.Windows.Forms.DataGridView.CellFormatting> eventos. Si usas un <xref:System.Data.DataSet> o <xref:System.Data.DataTable> como origen de datos, sin embargo, puede usar el <xref:System.Data.DataColumn.Expression%2A?displayProperty=nameWithType> propiedad que se va a crear una columna calculada en su lugar. En este caso, el <xref:System.Windows.Forms.DataGridView> control tratará la columna calculada como cualquier otra columna del origen de datos.  
  
 No se admite la ordenación por columnas sin enlazar en modo de enlace. Si crea una columna sin enlazar en modo de enlace que contiene valores que puede modificar el usuario, debe implementar el modo virtual para conservar estos valores cuando el control se ordena por una columna enlazada.  
  
## <a name="virtual"></a>Virtual  
 Con el modo virtual, puede implementar sus propias operaciones de administración de datos. Esto es necesario para mantener los valores de columnas sin enlazar en modo de enlace cuando el control se ordena por las columnas enlazadas. Sin embargo, es el uso principal del modo virtual optimizar el rendimiento al interactuar con grandes cantidades de datos.  
  
 Adjuntar el <xref:System.Windows.Forms.DataGridView> control a una memoria caché que administra y el código controla cuando se insertan y extraen filas de datos. Para mantener la superficie de memoria pequeña, la memoria caché debe ser similar en tamaño al número de filas mostradas actualmente. Cuando el usuario desplaza nuevas filas en la vista, el código solicita nuevos datos de la memoria caché y opcionalmente vacía los datos antiguos de la memoria.  
  
 Al implementar el modo virtual, necesitará saber si se necesita una nueva fila en el modelo de datos y si hay que revertir la adición de la nueva fila. La implementación exacta de esta funcionalidad depende de la implementación del modelo de datos y la semántica de transacción del modelo de datos; Si el ámbito de confirmación está en el nivel de celda o fila.  
  
 Para obtener más información sobre el modo virtual, vea [el modo Virtual en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md). Para obtener un ejemplo que muestra cómo utilizar los eventos de modo virtual, vea [Tutorial: implementar el modo Virtual en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A?displayProperty=nameWithType>  
 [Mostrar datos en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [Tipos de columnas en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)  
 [Tutorial: Crear un control DataGridView sin enlazar en Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)  
 [Enlazar datos al control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md)  
 [Modo virtual del control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)  
 [Tutorial: Implementar el modo virtual en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)
