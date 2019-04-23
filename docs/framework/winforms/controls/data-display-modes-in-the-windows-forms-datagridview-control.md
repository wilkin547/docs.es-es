---
title: Modos de presentación de datos en el control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], display modes
- data grids [Windows Forms], display modes
- DataGridView control [Windows Forms], display modes
ms.assetid: 9755a030-3f3f-4705-a661-ba5a48a81875
ms.openlocfilehash: 673780909f6d66168548893e99d79bbfec70a0e0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59079700"
---
# <a name="data-display-modes-in-the-windows-forms-datagridview-control"></a>Modos de presentación de datos en el control DataGridView de formularios Windows Forms
El <xref:System.Windows.Forms.DataGridView> control puede mostrar datos en tres modos distintos: dependientes, independientes y virtual. Elija el modo más apropiado según sus requisitos.  
  
## <a name="unbound"></a>Sin enlazar  
 El modo sin enlazar es adecuado para mostrar las cantidades relativamente pequeñas de datos que se administran mediante programación. No adjuntar el <xref:System.Windows.Forms.DataGridView> control directamente a un origen de datos como se muestra en el modo de enlace. En su lugar, debe rellenar el control, normalmente mediante el uso de la <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> método.  
  
 Modo independiente puede ser especialmente útil para datos estáticos de sólo lectura, o cuando desea proporcionar su propio código que interactúa con un almacén de datos externo. Cuando desee que los usuarios interactuar con un origen de datos externos, sin embargo, normalmente usará el modo de enlace.  
  
 Para obtener un ejemplo que usa solo lectura sin enlazar <xref:System.Windows.Forms.DataGridView>, vea [Cómo: Crear un Control DataGridView de formularios de Windows independiente](how-to-create-an-unbound-windows-forms-datagridview-control.md).  
  
## <a name="bound"></a>Enlazado  
 Modo de enlace es adecuado para la administración de datos mediante la interacción con el almacén de datos automática. Puede adjuntar el <xref:System.Windows.Forms.DataGridView> control directamente a su origen de datos estableciendo el <xref:System.Windows.Forms.DataGridView.DataSource%2A> propiedad. Cuando el control está enlazado a datos, las filas de datos se insertan y se extraen sin necesidad de una administración explícita por parte del usuario. Cuando el <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> propiedad es `true`, cada columna del origen de datos provocará una columna correspondiente que se creará en el control. Si prefiere crear sus propias columnas, puede establecer esta propiedad en `false` y usar el <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A> propiedad para enlazar cada columna cuando se configura. Esto es útil cuando desea utilizar un tipo de columna distinto de los tipos que se generan de forma predeterminada. Para obtener más información, consulte [tipos de columna en el DataGridView Control de Windows Forms](column-types-in-the-windows-forms-datagridview-control.md).  
  
 Para obtener un ejemplo que usa un límite <xref:System.Windows.Forms.DataGridView> control, vea [Tutorial: Validar datos en el Windows Forms DataGridView Control](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).  
  
 También puede agregar columnas sin enlazar a un <xref:System.Windows.Forms.DataGridView> control en modo de enlace. Esto es útil cuando desea mostrar una columna de botones o vínculos que los usuarios puedan realizar acciones en filas específicas. También es útil mostrar las columnas con valores calculados de las columnas enlazadas. Puede rellenar los valores de celda para columnas calculadas en un controlador para el <xref:System.Windows.Forms.DataGridView.CellFormatting> eventos. Si usas un <xref:System.Data.DataSet> o <xref:System.Data.DataTable> como origen de datos, sin embargo, puede usar el <xref:System.Data.DataColumn.Expression%2A?displayProperty=nameWithType> propiedad para crear una columna calculada en su lugar. En este caso, el <xref:System.Windows.Forms.DataGridView> control tratará la columna calculada como cualquier otra columna del origen de datos.  
  
 No se admite la ordenación por columnas sin enlazar en modo de enlace. Si crea una columna independiente en el modo de enlace que contiene valores editables de usuario, debe implementar el modo virtual para mantener estos valores cuando el control está ordenado por una columna enlazada.  
  
## <a name="virtual"></a>Virtual  
 Con el modo virtual, puede implementar sus propias operaciones de administración de datos. Esto es necesario para mantener los valores de columnas sin enlazar en modo de enlace cuando el control está ordenado por las columnas enlazadas. Sin embargo, es el uso principal de modo virtual optimizar el rendimiento al interactuar con grandes cantidades de datos.  
  
 Adjunte el <xref:System.Windows.Forms.DataGridView> control a una memoria caché que administra y los controles de código cuando se insertan y extraen las filas de datos. Para mantener la superficie de memoria pequeña, la memoria caché debe ser similar en tamaño al número de filas mostradas actualmente. Cuando el usuario desplaza las nuevas filas en la vista, el código solicita nuevos datos de la memoria caché y, opcionalmente, vacía los datos antiguos de la memoria.  
  
 Al implementar el modo virtual, deberá realizar un seguimiento cuando se necesita una nueva fila en el modelo de datos y si hay que deshacer la adición de la nueva fila. La implementación exacta de esta funcionalidad depende de la implementación del modelo de datos y la semántica de transacción del modelo de datos; Si el ámbito de confirmación está en el nivel de celda o fila.  
  
 Para obtener más información sobre el modo virtual, consulte [el modo Virtual en el DataGridView Control de Windows Forms](virtual-mode-in-the-windows-forms-datagridview-control.md). Para obtener un ejemplo que muestra cómo utilizar el modo virtual eventos, consulte [Tutorial: Implementar el modo Virtual en el Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A?displayProperty=nameWithType>
- [Mostrar datos en el control DataGridView de Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Tipos de columnas en el control DataGridView de Windows Forms](column-types-in-the-windows-forms-datagridview-control.md)
- [Tutorial: Crear una independiente de Windows Forms DataGridView Control](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)
- [Cómo: Enlazar datos al Control DataGridView de formularios Windows Forms](how-to-bind-data-to-the-windows-forms-datagridview-control.md)
- [Modo virtual del control DataGridView de Windows Forms](virtual-mode-in-the-windows-forms-datagridview-control.md)
- [Tutorial: Implementar el modo Virtual en el Control DataGridView de formularios de Windows](implementing-virtual-mode-wf-datagridview-control.md)
