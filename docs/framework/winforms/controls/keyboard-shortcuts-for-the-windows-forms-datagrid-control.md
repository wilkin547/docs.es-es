---
title: Métodos abreviados de teclado para el control DataGrid de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- keyboard shortcuts [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], navigation keys
ms.assetid: a01780f9-20d5-4f5f-808f-c790c9a007a5
ms.openlocfilehash: 58e65ee9d95329c3583515b99db47b87b3749c8f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59145982"
---
# <a name="keyboard-shortcuts-for-the-windows-forms-datagrid-control"></a>Métodos abreviados de teclado para el control DataGrid de formularios Windows Forms
> [!NOTE]
>  El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).  
  
 En la tabla siguiente se enumera los métodos abreviados de teclado que pueden usarse para la navegación dentro de los formularios de Windows <xref:System.Windows.Forms.DataGrid> control:  
  
|Acción|Acceso directo|  
|------------|--------------|  
|Completar una entrada de celda y mover hacia abajo hasta la celda siguiente.<br /><br /> Si el foco está en un vínculo de la tabla secundaria, vaya a esa tabla.|ENTRAR|  
|Cancelar la edición de celda si se encuentra en modo de edición de celda.<br /><br /> Si se encuentra en la selección de recuadro, cancelar la modificación de la fila.|ESC|  
|Eliminar el carácter delante del punto de inserción al editar una celda.|RETROCESO|  
|Eliminar el carácter después del punto de inserción al editar una celda.|SUPRIMIR|  
|Mover a la primera celda de la fila actual.|INICIO|  
|Mover a la última celda de la fila actual.|FIN|  
|Resaltar los caracteres de la celda actual y coloque el punto de inserción al final de la línea. Mismo comportamiento que haga doble clic en una celda.|F2|  
|Si el foco está en una celda, mueva a la siguiente celda de la fila.<br /><br /> Si el foco está en la última celda de una fila, mover en el primer vínculo de la tabla secundaria de la fila y expándalo.<br /><br /> Si el foco está en un vínculo secundario, desplazarse hasta el siguiente vínculo secundario.<br /><br /> Si el foco está en el último vínculo secundario, mueva a la primera celda de la fila siguiente.|TAB|  
|Si el foco está en una celda, mueva a la celda en la fila anterior.<br /><br /> Si el foco está en la primera celda de una fila, mover en el último vínculo de la tabla secundaria expandida de la fila anterior o se mueve a la última celda de la fila anterior.<br /><br /> Si el foco está en un vínculo secundario, mueva el vínculo secundario anterior.<br /><br /> Si el foco está en el primer vínculo secundario, mueva a la última celda de la fila anterior.|MAYÚS+TAB|  
|Mover al siguiente control en el orden de tabulación.|CTRL+TAB|  
|Mover al control anterior en el orden de tabulación.|CTRL+MAYÚS+TAB|  
|Mover hacia arriba en la tabla primaria en el caso de una tabla secundaria. Mismo comportamiento que al hacer clic en el botón Atrás.|ALT+FLECHA IZQUIERDA|  
|Expanda los vínculos de tabla secundaria. ALT + FLECHA ABAJO expande todos los vínculos, no solo los seleccionados.|ALT + flecha abajo o CTRL + signo más|  
|Contraer vínculos de tabla secundaria. CTRL+ALT+FLECHA arriba contrae todos los vínculos, no solo los seleccionados.|ALT + flecha arriba o CTRL + signo menos|  
|Mover a la celda en la dirección de la flecha más lejana no vacías.|CTRL+TECLAS DE DIRECCIÓN|  
|Ampliar la selección de una fila en la dirección de la flecha (sin incluir los vínculos de tabla secundaria).|MAYÚS+FLECHA ARRIBA/ABAJO|  
|Ampliar la selección de fila más lejana no vacíos en la dirección de la flecha (sin incluir los vínculos de tabla secundaria).|CTRL + MAYÚS + ARRIBA/FLECHA ABAJO|  
|Mover a la celda superior izquierda.|CTRL + INICIO|  
|Mover a la celda inferior derecha.|CTRL + FIN|  
|Ampliar la selección hasta la fila superior.|CTRL + MAYÚS + INICIO|  
|Ampliar la selección hasta la fila inferior.|CTRL + MAYÚS + FIN|  
|Seleccione la fila actual (excepto los vínculos de tabla secundaria).|MAYÚS + BARRA ESPACIADORA|  
|Seleccione toda la cuadrícula (excepto los vínculos de tabla secundaria).|CTRL+A|  
|Mostrar la fila primaria cuando se encuentra en una tabla secundaria.|CTRL+AV PÁG|  
|Ocultar la fila primaria cuando se encuentra en una tabla secundaria.|CTRL+RE PÁG|  
|Ampliar la selección hacia abajo una pantalla (sin incluir los vínculos de tabla secundaria).|MAYÚS+AV PÁG|  
|Ampliar la selección hacia arriba una pantalla (sin incluir los vínculos de tabla secundaria).|MAYÚS+RE PÁG|  
|Llame a la <xref:System.Windows.Forms.DataGrid.EndEdit%2A> método para la fila actual.|CTRL+ENTRAR|  
|Escriba un <xref:System.DBNull.Value?displayProperty=nameWithType> valor en una celda en modo de edición.|CTRL+0|  
  
## <a name="see-also"></a>Vea también

- [Información general del control DataGrid](datagrid-control-overview-windows-forms.md)
- [DataGrid (control)](datagrid-control-windows-forms.md)
