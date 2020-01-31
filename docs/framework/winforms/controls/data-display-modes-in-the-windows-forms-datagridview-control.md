---
title: Modos de presentación de datos en el control DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], display modes
- data grids [Windows Forms], display modes
- DataGridView control [Windows Forms], display modes
ms.assetid: 9755a030-3f3f-4705-a661-ba5a48a81875
ms.openlocfilehash: ad6be647e3a36904b055fd6771f539df28938fab
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744006"
---
# <a name="data-display-modes-in-the-windows-forms-datagridview-control"></a>Modos de presentación de datos en el control DataGridView de formularios Windows Forms
El control <xref:System.Windows.Forms.DataGridView> puede mostrar datos en tres modos distintos: enlazado, sin enlazar y virtual. Elija el modo más adecuado en función de sus requisitos.  
  
## <a name="unbound"></a>Unbound  
 El modo sin enlazar es adecuado para mostrar cantidades relativamente pequeñas de datos que se administran mediante programación. No adjunte el control <xref:System.Windows.Forms.DataGridView> directamente a un origen de datos como en modo enlazado. En su lugar, debe rellenar el control por su cuenta, normalmente mediante el método <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType>.  
  
 El modo sin enlazar puede ser especialmente útil para datos estáticos de solo lectura o cuando se desea proporcionar su propio código que interactúe con un almacén de datos externo. Sin embargo, si desea que los usuarios interactúen con un origen de datos externo, normalmente usará el modo enlazado.  
  
 Para obtener un ejemplo en el que se usa un <xref:System.Windows.Forms.DataGridView>sin enlazar de solo lectura, vea [Cómo: crear un control DataGridView de Windows Forms independiente](how-to-create-an-unbound-windows-forms-datagridview-control.md).  
  
## <a name="bound"></a>Enlazado  
 El modo de enlace es adecuado para administrar datos mediante la interacción automática con el almacén de datos. Puede adjuntar el control <xref:System.Windows.Forms.DataGridView> directamente a su origen de datos estableciendo la propiedad <xref:System.Windows.Forms.DataGridView.DataSource%2A>. Cuando el control está enlazado a datos, las filas de datos se insertan y extraen sin necesidad de una administración explícita por su parte. Cuando se `true`la propiedad <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A>, cada columna del origen de datos hará que se cree una columna correspondiente en el control. Si prefiere crear sus propias columnas, puede establecer esta propiedad en `false` y usar la propiedad <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A> para enlazar cada columna al configurarla. Esto resulta útil cuando se desea usar un tipo de columna distinto de los tipos que se generan de forma predeterminada. Para obtener más información, vea [tipos de columna en el control DataGridView de Windows Forms](column-types-in-the-windows-forms-datagridview-control.md).  
  
 Para obtener un ejemplo en el que se usa un control de <xref:System.Windows.Forms.DataGridView> enlazado, vea [Tutorial: validar datos en el control DataGridView Windows Forms](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).  
  
 También puede Agregar columnas sin enlazar a un control de <xref:System.Windows.Forms.DataGridView> en modo enlazado. Esto resulta útil cuando se desea mostrar una columna de botones o vínculos que permiten a los usuarios realizar acciones en filas específicas. También es útil para mostrar las columnas con valores calculados a partir de las columnas enlazadas. Puede rellenar los valores de celda de las columnas calculadas en un controlador para el evento <xref:System.Windows.Forms.DataGridView.CellFormatting>. Sin embargo, si utiliza un <xref:System.Data.DataSet> o <xref:System.Data.DataTable> como origen de datos, es posible que desee utilizar la propiedad <xref:System.Data.DataColumn.Expression%2A?displayProperty=nameWithType> para crear una columna calculada en su lugar. En este caso, el control <xref:System.Windows.Forms.DataGridView> tratará la columna calculada igual que cualquier otra columna del origen de datos.  
  
 No se admite la ordenación por columnas sin enlazar en modo enlazado. Si crea una columna sin enlazar en modo de enlace que contenga valores modificables por el usuario, debe implementar el modo virtual para mantener estos valores cuando el control se ordene por una columna enlazada.  
  
## <a name="virtual"></a>Virtual  
 Con el modo virtual, puede implementar sus propias operaciones de administración de datos. Esto es necesario para mantener los valores de las columnas sin enlazar en modo de enlace cuando el control está ordenado por columnas enlazadas. Sin embargo, el uso principal del modo virtual es optimizar el rendimiento al interactuar con grandes cantidades de datos.  
  
 Puede adjuntar el control <xref:System.Windows.Forms.DataGridView> a una memoria caché administrada y el código controla cuándo se insertan y extraen filas de datos. Para mantener la superficie de memoria pequeña, la memoria caché debe tener un tamaño similar al número de filas que se muestran actualmente. Cuando el usuario desplaza nuevas filas a la vista, el código solicita nuevos datos de la memoria caché y, opcionalmente, vacía los datos antiguos de la memoria.  
  
 Al implementar el modo virtual, deberá realizar un seguimiento de Cuándo se necesita una nueva fila en el modelo de datos y cuándo se debe revertir la adición de la nueva fila. La implementación exacta de esta funcionalidad dependerá de la implementación del modelo de datos y de la semántica de la transacción del modelo de datos. indica si el ámbito de confirmación está en el nivel de celda o fila.  
  
 Para obtener más información sobre el modo virtual, vea [modo virtual en el control DataGridView de Windows Forms](virtual-mode-in-the-windows-forms-datagridview-control.md). Para obtener un ejemplo en el que se muestra cómo usar los eventos de modo virtual, vea [Tutorial: implementar el modo virtual en el control DataGridView de Windows Forms](implementing-virtual-mode-wf-datagridview-control.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A?displayProperty=nameWithType>
- [Mostrar datos en el control DataGridView de Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Tipos de columnas en el control DataGridView de Windows Forms](column-types-in-the-windows-forms-datagridview-control.md)
- [Tutorial: Crear un control DataGridView sin enlazar en Windows Forms](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)
- [Enlazar datos al control DataGridView de formularios Windows Forms](how-to-bind-data-to-the-windows-forms-datagridview-control.md)
- [Modo virtual del control DataGridView de Windows Forms](virtual-mode-in-the-windows-forms-datagridview-control.md)
- [Tutorial: Implementar el modo virtual en el control DataGridView de Windows Forms](implementing-virtual-mode-wf-datagridview-control.md)
