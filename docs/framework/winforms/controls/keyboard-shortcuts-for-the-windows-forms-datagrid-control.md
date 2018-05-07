---
title: Métodos abreviados de teclado para el control DataGrid de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- keyboard shortcuts [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], navigation keys
ms.assetid: a01780f9-20d5-4f5f-808f-c790c9a007a5
ms.openlocfilehash: c05ddd68beeffe70e048a439929fb31454812612
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="keyboard-shortcuts-for-the-windows-forms-datagrid-control"></a>Métodos abreviados de teclado para el control DataGrid de formularios Windows Forms
> [!NOTE]
>  El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).  
  
 En la tabla siguiente se enumera los métodos abreviados de teclado que pueden usarse para la navegación en Windows Forms <xref:System.Windows.Forms.DataGrid> control:  
  
|Acción|Acceso directo|  
|------------|--------------|  
|Completar una entrada de celda y desplazarse hacia abajo a la celda siguiente.<br /><br /> Si el foco está en un vínculo de la tabla secundaria, navegue a esa tabla.|ENTRAR|  
|Cancela la edición de celda si se encuentra en modo de edición de la celda.<br /><br /> Si se encuentra en la selección de recuadro, cancelar la modificación de la fila.|ESC|  
|Eliminar el carácter situado delante del punto de inserción al editar una celda.|RETROCESO|  
|Eliminar el carácter después del punto de inserción al editar una celda.|SUPRIMIR|  
|Mover a la primera celda de la fila actual.|INICIO|  
|Se mueve a la última celda de la fila actual.|FIN|  
|Resaltar los caracteres de la celda actual y coloque el punto de inserción al final de la línea. Mismo comportamiento que haga doble clic en una celda.|F2|  
|Si el foco está en una celda, mueva a la celda siguiente en la fila.<br /><br /> Si el foco está en la última celda de una fila, desplácese al primer vínculo de la tabla secundaria de la fila y expandirlo.<br /><br /> Si el foco está en un vínculo secundario, desplazarse hasta el siguiente vínculo secundario.<br /><br /> Si el foco está en el último vínculo secundario, mueva a la primera celda de la fila siguiente.|TAB|  
|Si el foco está en una celda, mueva a la celda anterior de la fila.<br /><br /> Si el foco está en la primera celda de una fila, desplazarse hasta el último vínculo de tabla expandida secundarios de la fila anterior o se mueve a la última celda de la fila anterior.<br /><br /> Si el foco está en un vínculo secundario, mueva el vínculo secundario anterior.<br /><br /> Si el foco está en el primer vínculo secundario, se mueve a la última celda de la fila anterior.|MAYÚS+TAB|  
|Mover al siguiente control en el orden de tabulación.|CTRL+TAB|  
|Mover al control anterior en el orden de tabulación.|CTRL+MAYÚS+TAB|  
|Mover hacia arriba a la tabla primaria en el caso de una tabla secundaria. Mismo comportamiento que al hacer clic en el botón Atrás.|ALT+FLECHA IZQUIERDA|  
|Expanda los vínculos de tabla secundaria. ALT+FLECHA abajo expande todos los vínculos, no solo los seleccionados.|ALT + flecha abajo o CTRL + signo|  
|Contraer los vínculos de tabla secundaria. ALT+FLECHA arriba contrae todos los vínculos, no solo los seleccionados.|ALT + flecha arriba o CTRL + signo menos|  
|Desplazarse a la celda más lejano no vacías en la dirección de la flecha.|CTRL + FLECHA|  
|Ampliar la selección de una fila en la dirección de la flecha (sin incluir los vínculos de tabla secundaria).|MAYÚS+FLECHA ARRIBA/ABAJO|  
|Ampliar la selección de fila más lejano no vacíos en la dirección de la flecha (sin incluir los vínculos de tabla secundaria).|CTRL + MAYÚS + ARRIBA/FLECHA ABAJO|  
|Mover a la celda superior izquierda.|CTRL + INICIO|  
|Mover a la celda inferior derecha.|CTRL + FIN|  
|Ampliar la selección de la fila superior.|CTRL + MAYÚS + INICIO|  
|Ampliar la selección de la fila inferior.|CTRL + MAYÚS + FIN|  
|Seleccione la fila actual (sin incluir los vínculos de tabla secundaria).|CTRL+MAYÚS+BARRA ESPACIADORA|  
|Seleccione la cuadrícula completa (sin incluir los vínculos de tabla secundaria).|CTRL+A|  
|Mostrar la fila primaria cuando se encuentra en una tabla secundaria.|CTRL+AV PÁG|  
|Ocultar la fila primaria cuando se encuentra en una tabla secundaria.|CTRL+RE PÁG|  
|Ampliar la selección hacia abajo una pantalla (sin incluir los vínculos de tabla secundaria).|MAYÚS+AV PÁG|  
|Ampliar la selección hacia arriba una pantalla (sin incluir los vínculos de tabla secundaria).|MAYÚS+RE PÁG|  
|Llame a la <xref:System.Windows.Forms.DataGrid.EndEdit%2A> método para la fila actual.|CTRL+ENTRAR|  
|Escriba un <xref:System.DBNull.Value?displayProperty=nameWithType> valor en una celda en modo de edición.|CTRL+0|  
  
## <a name="see-also"></a>Vea también  
 [Información general del control DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [DataGrid (control)](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)
