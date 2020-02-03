---
title: Funcionalidad predeterminada en el control DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], default functionality in DataGridView control
- DataGridView control [Windows Forms], default functionality
ms.assetid: 4405f697-cad1-4839-9bcd-8ddb09d9f00e
ms.openlocfilehash: b695883ac7ec3fb0c459adb66214b0eceab3a128
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746134"
---
# <a name="default-functionality-in-the-windows-forms-datagridview-control"></a>Funcionalidad predeterminada en el control DataGridView de Windows Forms
El control Windows Forms <xref:System.Windows.Forms.DataGridView> proporciona a los usuarios una cantidad significativa de funcionalidad predeterminada.  
  
## <a name="default-functionality"></a>Funcionalidad predeterminada  
 De forma predeterminada, un control <xref:System.Windows.Forms.DataGridView>:  
  
- Muestra automáticamente los encabezados de columna y los encabezados de fila que permanecen visibles cuando la tabla se desplaza verticalmente.  
  
- Tiene un encabezado de fila que contiene un indicador de selección para la fila actual.  
  
- Tiene un rectángulo de selección en la primera celda.  
  
- Tiene columnas a las que se puede cambiar el tamaño automáticamente cuando el usuario hace doble clic en los divisores de columna.  
  
- Admite automáticamente los estilos visuales en Windows XP y la familia de Windows Server 2003 cuando se llama al método <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> desde el método de `Main` de la aplicación.  
  
 Además, el contenido de un control <xref:System.Windows.Forms.DataGridView> se puede editar de forma predeterminada:  
  
- Si el usuario hace doble clic o presiona F2 en una celda, el control coloca automáticamente la celda en modo de edición y actualiza el contenido de la celda a medida que el usuario escribe.  
  
- Si el usuario se desplaza hasta el final de la cuadrícula, el usuario verá que hay una fila para agregar nuevos registros. Cuando el usuario hace clic en esta fila, se agrega una nueva fila al control <xref:System.Windows.Forms.DataGridView>, con los valores predeterminados. Cuando el usuario presiona ESC, esta nueva fila desaparece.  
  
- Si el usuario hace clic en un encabezado de fila, se selecciona toda la fila.  
  
 Al enlazar un control de <xref:System.Windows.Forms.DataGridView> a un origen de datos estableciendo su propiedad <xref:System.Windows.Forms.DataGridView.DataSource%2A>, el control:  
  
- Usa automáticamente los nombres de las columnas del origen de datos como texto de encabezado de columna.  
  
- Se rellena con el contenido del origen de datos. <xref:System.Windows.Forms.DataGridView> columnas se crean automáticamente para cada columna del origen de datos.  
  
- Crea una fila para cada fila visible de la tabla.  
  
- Ordena automáticamente las filas basándose en los datos subyacentes cuando el usuario hace clic en un encabezado de columna.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.DataGridView>
- [DataGridView (control)](datagridview-control-windows-forms.md)
