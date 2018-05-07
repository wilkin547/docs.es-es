---
title: Funcionalidad predeterminada en el control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], default functionality in DataGridView control
- DataGridView control [Windows Forms], default functionality
ms.assetid: 4405f697-cad1-4839-9bcd-8ddb09d9f00e
ms.openlocfilehash: a475d8bce388860c88571fbf638d206bfe01223d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="default-functionality-in-the-windows-forms-datagridview-control"></a>Funcionalidad predeterminada en el control DataGridView de formularios Windows Forms
Los formularios Windows Forms <xref:System.Windows.Forms.DataGridView> control proporciona a los usuarios con una cantidad significativa de funcionalidad predeterminada.  
  
## <a name="default-functionality"></a>Funcionalidad predeterminada  
 De forma predeterminada, un <xref:System.Windows.Forms.DataGridView> control:  
  
-   Muestra automáticamente encabezados de columna y encabezados de fila que permanecen visibles cuando la tabla se desplaza verticalmente.  
  
-   Tiene un encabezado de fila que contiene un indicador de selección de la fila actual.  
  
-   Tiene un rectángulo de selección en la primera celda.  
  
-   Tiene columnas que pueden cambiarse automáticamente cuando el usuario hace doble clic en los divisores de columna.  
  
-   Admite automáticamente los estilos visuales en Windows XP y la familia Windows Server 2003 cuando la <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> método se llama desde la aplicación `Main` método.  
  
 Además, el contenido de un <xref:System.Windows.Forms.DataGridView> control puede modificarse de forma predeterminada:  
  
-   Si el usuario hace doble clic o presiona F2 en una celda, el control pone la celda en modo de edición y actualiza el contenido de la celda cuando el usuario escribe automáticamente.  
  
-   Si el usuario se desplaza hasta el final de la cuadrícula, el usuario verá que una fila para agregar nuevos registros está presente. Cuando el usuario hace clic en esta fila, se agrega una nueva fila a la <xref:System.Windows.Forms.DataGridView> control, con los valores predeterminados. Cuando el usuario presiona ESC, esta nueva fila desaparece.  
  
-   Si el usuario hace clic en un encabezado de fila, se selecciona la fila completa.  
  
 Al enlazar un <xref:System.Windows.Forms.DataGridView> control a un origen de datos estableciendo su <xref:System.Windows.Forms.DataGridView.DataSource%2A> propiedad, el control:  
  
-   Usa automáticamente los nombres de columnas del origen de datos como el texto del encabezado de columna.  
  
-   Se rellena con el contenido del origen de datos. <xref:System.Windows.Forms.DataGridView> las columnas se crean automáticamente para cada columna del origen de datos.  
  
-   Crea una fila para cada fila visible en la tabla.  
  
-   Se ordena automáticamente las filas basándose en los datos subyacentes cuando el usuario hace clic en un encabezado de columna.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.DataGridView>  
 [DataGridView (control)](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
