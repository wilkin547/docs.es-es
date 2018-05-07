---
title: Predeterminado de teclado y mouse (ratón) en el control DataGridView de formularios Windows Forms
ms.date: 02/13/2018
helpviewer_keywords:
- data grids [Windows Forms], mouse handling
- DataGridView control [Windows Forms], navigation keys
- keyboards [Windows Forms], default handling in DataGridView control
- DataGridView control [Windows Forms], keyboard handling
- mouse [Windows Forms], default handling in DataGridView control
- DataGridView control [Windows Forms], mouse handling
- navigation keys [Windows Forms], DataGridView control
ms.assetid: 4519b928-bfc8-4e8b-bb9c-b1e76a0ca552
ms.openlocfilehash: b0ed468fe7d38fbeda90d5347338bce14059b730
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control"></a>Predeterminado de teclado y mouse (ratón) en el control DataGridView de formularios Windows Forms

Las tablas siguientes describen cómo pueden interactuar los usuarios con el <xref:System.Windows.Forms.DataGridView> control a través de un teclado y un mouse.  
  
> [!NOTE]
>  Para personalizar el comportamiento del teclado, puede controlar eventos de teclado estándar como <xref:System.Windows.Forms.Control.KeyDown>. Sin embargo, en modo de edición, el control de edición hospedado recibe la entrada de teclado y no se producen los eventos de teclado para el <xref:System.Windows.Forms.DataGridView> control. Para controlar los eventos de control de edición, asocie los controladores para el control de edición en una <xref:System.Windows.Forms.DataGridView.EditingControlShowing> controlador de eventos. Como alternativa, puede personalizar el comportamiento del teclado en una <xref:System.Windows.Forms.DataGridView> subclase invalidando el <xref:System.Windows.Forms.DataGridView.ProcessDialogKey%2A> y <xref:System.Windows.Forms.DataGridView.ProcessDataGridViewKey%2A> métodos.  
  
## <a name="default-keyboard-handling"></a>Control de teclado predeterminado  
  
### <a name="basic-navigation-and-entry-keys"></a>Teclas de navegación y entrada básicas  
  
|Tecla o combinación de teclas|Descripción|  
|----------------------------|-----------------|  
|FLECHA ABAJO|Mueve el foco a la celda situada directamente debajo de la celda actual. Si el foco está en la última fila, no hace nada.|  
|FLECHA IZQUIERDA|Mueve el foco a la celda anterior de la fila. Si el foco está en la primera celda de la fila, no hace nada.|  
|FLECHA DERECHA|Mueve el foco a la siguiente celda en la fila. Si el foco está en la última celda de la fila, no hace nada.|  
|FLECHA ARRIBA|Mueve el foco a la celda directamente encima de la celda actual. Si el foco está en la primera fila, no hace nada.|  
|INICIO|Mueve el foco a la primera celda de la fila actual.|  
|FIN|Mueve el foco a la última celda de la fila actual.|  
|AV PÁG|Desplaza el control hacia abajo por el número de filas que se muestran completamente. Mueve el foco a la última fila muestra totalmente sin cambiar las columnas.|  
|RE PÁG|Desplaza el control hacia arriba por el número de filas que se muestran completamente. Mover el foco a la primera fila mostrada sin cambiar las columnas.|  
|TAB|Si el <xref:System.Windows.Forms.DataGridView.StandardTab%2A> es el valor de la propiedad `false`, mueve el foco a la siguiente celda en la fila actual. Si el foco está en la última celda de la fila, mueve el foco a la primera celda de la fila siguiente. Si el foco está en la última celda en el control, mueve el foco al siguiente control en el orden de tabulación del contenedor primario.<br /><br /> Si el <xref:System.Windows.Forms.DataGridView.StandardTab%2A> es el valor de la propiedad `true`, mueve el foco al siguiente control en el orden de tabulación del contenedor primario.|  
|MAYÚS+TAB|Si el <xref:System.Windows.Forms.DataGridView.StandardTab%2A> es el valor de la propiedad `false`, mueve el foco a la celda anterior de la fila actual. Si el foco está en la primera celda de la fila, mueve el foco a la última celda de la fila anterior. Si el foco está en la primera celda del control, desplaza el foco al control anterior en el orden de tabulación del contenedor primario.<br /><br /> Si el <xref:System.Windows.Forms.DataGridView.StandardTab%2A> es el valor de la propiedad `true`, mueve el foco al control anterior en el orden de tabulación del contenedor primario.|  
|CTRL+TAB|Si el <xref:System.Windows.Forms.DataGridView.StandardTab%2A> es el valor de la propiedad `false`, mueve el foco al siguiente control en el orden de tabulación del contenedor primario.<br /><br /> Si el <xref:System.Windows.Forms.DataGridView.StandardTab%2A> es el valor de la propiedad `true`, mueve el foco a la siguiente celda en la fila actual. Si el foco está en la última celda de la fila, mueve el foco a la primera celda de la fila siguiente. Si el foco está en la última celda en el control, mueve el foco al siguiente control en el orden de tabulación del contenedor primario.|  
|CTRL+MAYÚS+TAB|Si el <xref:System.Windows.Forms.DataGridView.StandardTab%2A> es el valor de la propiedad `false`, mueve el foco al control anterior en el orden de tabulación del contenedor primario.<br /><br /> Si el <xref:System.Windows.Forms.DataGridView.StandardTab%2A> es el valor de la propiedad `true`, mueve el foco a la celda anterior de la fila actual. Si el foco está en la primera celda de la fila, mueve el foco a la última celda de la fila anterior. Si el foco está en la primera celda del control, desplaza el foco al control anterior en el orden de tabulación del contenedor primario.|  
|CTRL + FLECHA|Mueve el foco a la última celda en la dirección de la flecha.|  
|CTRL + INICIO|Mueve el foco a la primera celda del control.|  
|CTRL + FIN|Mueve el foco a la última celda en el control.|  
|CTRL+AV PÁG ARRIBA/ABAJO|Igual que AV PÁG o AV PÁG.|  
|F2|Pone la celda actual en modo de edición de celda si el <xref:System.Windows.Forms.DataGridView.EditMode%2A> es el valor de la propiedad <xref:System.Windows.Forms.DataGridViewEditMode.EditOnF2> o <xref:System.Windows.Forms.DataGridViewEditMode.EditOnKeystrokeOrF2>.|
|F3|Ordena la columna actual si la <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType> es el valor de la propiedad <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic>. Es el mismo que al hacer clic en el encabezado de columna actual. Disponible desde .NET Framework 4.7.2. Para habilitar esta característica, las aplicaciones deben tener como destino .NET Framework 4.7.2 o versiones posteriores u opte explícitamente por el uso de conmutadores AppContext las mejoras de accesibilidad.|  
|F4|Si la celda actual es un <xref:System.Windows.Forms.DataGridViewComboBoxCell>, coloca la celda en modo de edición y se muestra la lista desplegable.|  
|ALT+FLECHA ARRIBA/ABAJO|Si la celda actual es un <xref:System.Windows.Forms.DataGridViewComboBoxCell>, coloca la celda en modo de edición y se muestra la lista desplegable.|  
|Barra espaciadora|Si la celda actual es un <xref:System.Windows.Forms.DataGridViewButtonCell>, <xref:System.Windows.Forms.DataGridViewLinkCell>, o <xref:System.Windows.Forms.DataGridViewCheckBoxCell>, genera el <xref:System.Windows.Forms.DataGridView.CellClick> y <xref:System.Windows.Forms.DataGridView.CellContentClick> eventos. Si la celda actual es un <xref:System.Windows.Forms.DataGridViewButtonCell>, también presiona el botón. Si la celda actual es un <xref:System.Windows.Forms.DataGridViewCheckBoxCell>, también cambia el estado de activación.|  
|ENTRAR|Confirma los cambios a la celda actual y la fila y mueve el foco a la celda situada directamente debajo de la celda actual. Si el foco está en la última fila, confirma los cambios sin mover el foco.|  
|ESC|Si el control está en modo de edición, cancela la edición. Si el control no está en modo de edición, revierte todos los cambios que se realizaron en la fila actual si el control se enlaza a un origen de datos que admite la edición o el modo virtual se ha implementado con ámbito de confirmación de nivel de fila.|  
|RETROCESO|Elimina el carácter situado delante del punto de inserción al editar una celda.|  
|SUPRIMIR|Elimina el carácter después del punto de inserción al editar una celda.|  
|CTRL+ENTRAR|Confirma los cambios en la celda actual sin mover el foco. También confirma los cambios realizados en la fila actual si el control se enlaza a un origen de datos que admite el modo de edición o virtual se ha implementado con nivel de fila ámbito de confirmación.|  
|CTRL+0|Escribe un <xref:System.DBNull.Value?displayProperty=nameWithType> el valor en la celda actual si se puede editar la celda. De forma predeterminada, la presentación de valor para un <xref:System.DBNull> valor de la celda es el valor de la <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> propiedad de la <xref:System.Windows.Forms.DataGridViewCellStyle> en vigor para la celda actual.|  
  
### <a name="selection-keys"></a>Teclas de selección

 Si el <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> propiedad está establecida en `false` y <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> propiedad está establecida en <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>, la celda actual utilizando las teclas de desplazamiento si se cambia la selección a la nueva celda. La tecla MAYÚS, CTRL y ALT (teclas) no afectan a este comportamiento.  
  
 Si el <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> está establecido en <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, ocurre lo mismo pero con las siguientes adiciones.  
  
|Tecla o combinación de teclas|Descripción|  
|----------------------------|-----------------|  
|CTRL+MAYÚS+BARRA ESPACIADORA|Selecciona la fila o columna completa (igual que al hacer clic en el encabezado de fila o columna).|  
|tecla de navegación (tecla de flecha, PÁG, inicio, fin)|Si se selecciona una fila o columna completa, al cambiar la celda actual a una nueva fila o columna mueve la selección a la nueva fila o columna (según el modo de selección).|  
  
 Si <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> está establecido en `false` y <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> está establecido en <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, cambiar la celda actual a una nueva fila o columna mediante el teclado mueve la selección a la nueva fila o columna. La tecla MAYÚS, CTRL y ALT (teclas) no afectan a este comportamiento.  
  
 Si <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> se establece en `true`, el comportamiento de navegación no cambia, pero navega con el teclado mientras se presiona MAYÚS (incluyendo CTRL+MAYÚS) modificará una selección de varias celda. Antes de comenzar la navegación, el control marca la celda actual como una celda del delimitador. Si mientras navega mientras presiona la tecla MAYÚS, la selección incluye todas las celdas entre la celda del delimitador y la celda actual. Otras celdas del control permanecerán seleccionadas si ya se han seleccionado, pero se anulará su selección si la navegación con el teclado las sitúa temporalmente entre la celda del delimitador y la celda actual.  
  
 Si <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> está establecido en `true` y <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> está establecido en <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, el comportamiento de la celda del delimitador y la celda actual es el mismo, pero solo filas o columnas completas estén seleccionadas o anular la selección.  
  
## <a name="default-mouse-handling"></a>Control predeterminado del mouse
  
### <a name="basic-mouse-handling"></a>Control básico del mouse
  
> [!NOTE]
>  Haga clic en una celda con el botón primario del mouse siempre cambia la celda actual. Haga clic en una celda con el botón secundario del mouse, se abre un menú contextual, cuando está disponible.  
  
|Acción del mouse|Descripción|  
|------------------|-----------------|  
|Presionar el botón primario del mouse|Hace que la celda que se hace clic en la celda actual y genera el <xref:System.Windows.Forms.DataGridView.CellMouseDown?displayProperty=nameWithType> eventos.|  
|Botón primario del mouse|Genera el evento <xref:System.Windows.Forms.DataGridView.CellMouseUp?displayProperty=nameWithType>.|  
|Haga clic en botón primario del mouse|Genera el <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> y <xref:System.Windows.Forms.DataGridView.CellMouseClick?displayProperty=nameWithType> eventos|  
|Presionar el botón primario del mouse y arrastre en una celda de encabezado de columna|Si el <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> propiedad es `true`, mueve la columna para que se pueda colocar en una nueva posición.|  
  
### <a name="mouse-selection"></a>Selección del mouse

 Ningún comportamiento de la selección está asociado con el botón central del mouse o la rueda del mouse.  
  
 Si el <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> propiedad está establecida en `false` y <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> propiedad está establecida en <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>, ocurre lo siguiente.  
  
|Acción del mouse|Descripción|  
|------------------|-----------------|  
|Haga clic en el botón primario del mouse|Selecciona solo la celda actual si el usuario hace clic en una celda. Ningún comportamiento de la selección, si el usuario hace clic en un encabezado de fila o columna.|  
|Haga clic en el botón secundario del mouse|Muestra un menú contextual si está disponible.|  
  
 El mismo comportamiento se produce cuando el <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> está establecido en <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, excepto que, según el modo de selección, haga clic en un encabezado de fila o columna se seleccione la fila o columna completa y establece la celda actual en la primera celda de la fila o columna.  
  
 Si <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> está establecido en <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, haga clic en cualquier celda de una fila o columna seleccionará la fila o columna completa.  
  
 Si <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> se establece en `true`, haga clic en una celda mientras se presiona la tecla CTRL o MAYÚS modificará una selección de varias celda.  
  
 Al hacer clic en una celda mientras se presiona CTRL, la celda cambiará su estado de selección mientras todas las demás celdas conservan su estado de selección actual.  
  
 Al hacer clic en una celda o una serie de celdas mientras presiona la tecla MAYÚS, la selección incluye todas las celdas entre la celda actual y una celda de anclaje ubicado en la posición de la celda actual antes del primer clic. Al hacer clic y arrastre el puntero por varias celdas, la celda del delimitador es la celda que se ha hecho clic al principio de la operación de arrastre. Los clics sucesivos mientras presiona la tecla MAYÚS cambian la celda actual, pero no la celda del delimitador. Otras celdas del control permanecerán seleccionadas si ya se han seleccionado, pero se anulará su selección si la navegación con el mouse las sitúa temporalmente entre la celda del delimitador y la celda actual.  
  
 Si <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> está establecido en `true` y <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> está establecido en <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, haga clic en un encabezado de fila o columna (según el modo de selección) mientras se presiona MAYÚS modificará una selección existente de filas o columnas completas si tales un existe la selección. En caso contrario, borrará la selección e iniciar una nueva selección de filas o columnas completas. Mientras presiona la tecla CTRL, haga clic en un encabezado de fila o columna, sin embargo, agregará o quitará la fila donde ha hecho clic o columna de la selección actual sin modificar de otra manera la selección actual.  
  
 Si <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> está establecido en `true` y <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> está establecido en <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, haga clic en una celda mientras se presiona la tecla MAYÚS o CTRL se comporta del mismo modo, excepto que solo completa las filas y columnas se ven afectadas.  
  
## <a name="see-also"></a>Vea también

<xref:System.Windows.Forms.DataGridView>  
 [DataGridView (control)](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
