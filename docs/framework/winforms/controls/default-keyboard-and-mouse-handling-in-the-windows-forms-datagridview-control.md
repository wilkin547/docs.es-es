---
title: "Control predeterminado de teclado y mouse (rat&#243;n) en el control DataGridView de formularios Windows Forms | Microsoft Docs"
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
  - "cuadrículas de datos, controlar el mouse"
  - "DataGridView (control) [Windows Forms], controlar el teclado"
  - "DataGridView (control) [Windows Forms], controlar el mouse"
  - "DataGridView (control) [Windows Forms], teclas de desplazamiento"
  - "teclados, control predeterminado del control DataGridView"
  - "mouse, control predeterminado del control DataGridView"
  - "teclas de desplazamiento, DataGridView (control)"
ms.assetid: 4519b928-bfc8-4e8b-bb9c-b1e76a0ca552
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Control predeterminado de teclado y mouse (rat&#243;n) en el control DataGridView de formularios Windows Forms
Las siguientes tablas describen cómo pueden interactuar los usuarios con el control <xref:System.Windows.Forms.DataGridView> a través de un teclado y un mouse.  
  
> [!NOTE]
>  Para personalizar el comportamiento del teclado, puede controlar eventos de teclado estándar como <xref:System.Windows.Forms.Control.KeyDown>.  En modo de edición, sin embargo, el control de edición hospedado recibe la entrada del teclado y no se producen eventos de teclado para el control <xref:System.Windows.Forms.DataGridView>.  Para controlar los eventos de control de edición, asocie los controladores al control de edición en un controlador de eventos <xref:System.Windows.Forms.DataGridView.EditingControlShowing>.  Alternativamente, puede personalizar el comportamiento del teclado en una subclase <xref:System.Windows.Forms.DataGridView>, reemplazando los métodos <xref:System.Windows.Forms.DataGridView.ProcessDialogKey%2A> y <xref:System.Windows.Forms.DataGridView.ProcessDataGridViewKey%2A>.  
  
## Controlar el teclado predeterminado  
  
### Navegación básica y teclas de entrada  
  
|Tecla o combinación de teclas|Descripción|  
|-----------------------------------|-----------------|  
|FLECHA ABAJO|Mueve el foco a la celda que se encuentra directamente debajo de la celda actual.  Si el foco está en la última fila, no hace nada.|  
|FLECHA IZQUIERDA|Mueve el foco a la celda anterior de la fila.  Si el foco está en la primera celda de la fila, no hace nada.|  
|FLECHA DERECHA|Mueve el foco a la siguiente celda de la fila.  Si el foco está en la última celda de la fila, no hace nada.|  
|FLECHA ARRIBA|Mueve el foco a la celda que se encuentra directamente encima de la celda actual.  Si el foco está en la primera fila, no hace nada.|  
|INICIO|Mueve el foco a la primera celda de la fila actual.|  
|FIN|Mueve el foco a la última celda de la fila actual.|  
|AV PÁG|Desplaza el control descendente por el número de filas que se muestran totalmente.  Mueve el foco a la última fila que se muestra totalmente sin cambiar las columnas.|  
|RE PÁG|Desplaza el control ascendente por el número de filas que se muestran totalmente.  Desplaza el foco a la primera fila mostrada sin cambiar las columnas.|  
|TAB|Si el valor de propiedad <xref:System.Windows.Forms.DataGridView.StandardTab%2A> es `false`, mueve el foco a la celda siguiente de la fila actual.  Si el foco ya está en la última celda de la fila, mueve el foco a la primera celda de la siguiente fila.  Si el foco está en la última celda del control, desplaza el foco al siguiente control en el orden de tabulación del contenedor primario.<br /><br /> Si el valor de propiedad <xref:System.Windows.Forms.DataGridView.StandardTab%2A> es `true`, desplaza el foco al siguiente control en el orden de tabulación del contenedor primario.|  
|MAYÚS\+TAB|Si el valor de propiedad <xref:System.Windows.Forms.DataGridView.StandardTab%2A> es `false`, desplaza el foco a la celda anterior de la fila actual.  Si el foco ya está en la primera celda de la fila, desplaza el foco a la primera celda de la fila anterior.  Si el foco está en la primera celda del control, desplaza el foco al control anterior en el orden de tabulación del contenedor primario.<br /><br /> Si el valor de propiedad <xref:System.Windows.Forms.DataGridView.StandardTab%2A> es `true`, desplaza el foco al control anterior en el orden de tabulación del contenedor primario.|  
|CTRL\+TAB|Si el valor de propiedad <xref:System.Windows.Forms.DataGridView.StandardTab%2A> es `false`, desplaza el foco al siguiente control en el orden de tabulación del contenedor primario.<br /><br /> Si el valor de propiedad <xref:System.Windows.Forms.DataGridView.StandardTab%2A> es `true`, mueve el foco a la celda siguiente de la fila actual.  Si el foco ya está en la última celda de la fila, mueve el foco a la primera celda de la siguiente fila.  Si el foco está en la última celda del control, desplaza el foco al siguiente control en el orden de tabulación del contenedor primario.|  
|CTRL\+MAYÚS\+TAB|Si el valor de propiedad <xref:System.Windows.Forms.DataGridView.StandardTab%2A> es `false`, desplaza el foco al control anterior en el orden de tabulación del contenedor primario.<br /><br /> Si el valor de propiedad <xref:System.Windows.Forms.DataGridView.StandardTab%2A> es `true`, desplaza el foco a la celda anterior de la fila actual.  Si el foco ya está en la primera celda de la fila, desplaza el foco a la primera celda de la fila anterior.  Si el foco está en la primera celda del control, desplaza el foco al control anterior en el orden de tabulación del contenedor primario.|  
|CTRL\+FLECHA|Desplaza el foco a la última celda en el sentido de la flecha.|  
|CTRL\+INICIO|Desplaza el foco a la primera celda del control.|  
|CTRL\+FIN|Desplaza el foco a la última celda del control.|  
|CTRL\+AV PÁG\/RE PÁG|Igual que AV PÁG o RE PÁG.|  
|F2|Coloca la celda actual en el modo de edición de la celda si el valor de propiedad <xref:System.Windows.Forms.DataGridView.EditMode%2A> es <xref:System.Windows.Forms.DataGridViewEditMode> o <xref:System.Windows.Forms.DataGridViewEditMode>.|  
|F4|Si la celda actual es una <xref:System.Windows.Forms.DataGridViewComboBoxCell>, coloca la celda en el modo de edición y muestra la lista desplegable.|  
|ALT\+FLECHA ARRIBA\/ABAJO|Si la celda actual es una <xref:System.Windows.Forms.DataGridViewComboBoxCell>, coloca la celda en el modo de edición y muestra la lista desplegable.|  
|BARRA ESPACIADORA|Si la celda actual es una <xref:System.Windows.Forms.DataGridViewButtonCell>, <xref:System.Windows.Forms.DataGridViewLinkCell> o <xref:System.Windows.Forms.DataGridViewCheckBoxCell>, provoca los eventos <xref:System.Windows.Forms.DataGridView.CellClick> y <xref:System.Windows.Forms.DataGridView.CellContentClick>.  Si la celda actual es una <xref:System.Windows.Forms.DataGridViewButtonCell>, también presiona el botón.  Si la celda actual es <xref:System.Windows.Forms.DataGridViewCheckBoxCell>, también cambia el estado de activación.|  
|ENTRAR|Confirma cualquier cambio en la celda y fila actuales y desplaza el foco a la celda directamente debajo de la celda actual.  Si el foco está en la última fila, confirma cualquier cambio sin mover el foco.|  
|ESC|Si el control está en modo de edición, cancela la edición.  Si el control no está en modo de edición, revierte todos los cambios realizados en la actual fila si el control está enlazado a un origen de datos que admita la edición o si el modo virtual se ha implementado con un ámbito de confirmación de fila.|  
|RETROCESO|Elimina el carácter situado delante del punto de inserción al editar una celda.|  
|DELETE|Elimina el carácter situado detrás del punto de inserción al editar una celda.|  
|CTRL\+ENTRAR|Confirma cualquier cambio en la celda actual sin mover el foco.  Confirma también los cambios realizados en la actual fila si el control está enlazado a un origen de datos que admita la edición o si el modo virtual se ha implementado con un ámbito de confirmación de fila.|  
|CTRL\+0|Especifica un valor <xref:System.DBNull.Value?displayProperty=fullName> en la celda actual si se puede editar la celda.  De forma predeterminada, el valor mostrado para un valor de celda de la propiedad <xref:System.DBNull> es el valor activo de la propiedad <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> de <xref:System.Windows.Forms.DataGridViewCellStyle> para la celda actual.|  
  
### Teclas de selección  
 Si la propiedad <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> se establece en `false` y la propiedad <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> se establece en <xref:System.Windows.Forms.DataGridViewSelectionMode>, si cambia la celda actual utilizando las teclas de navegación, la selección cambia a la nueva celda.  Las teclas MAYÚS, CTRL y ALT no alteran este comportamiento.  
  
 Si <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> se establece en <xref:System.Windows.Forms.DataGridViewSelectionMode> o en <xref:System.Windows.Forms.DataGridViewSelectionMode>, se produce el mismo comportamiento pero con las siguientes modificaciones.  
  
|Tecla o combinación de teclas|Descripción|  
|-----------------------------------|-----------------|  
|MAYÚS\+ESPACIO|Selecciona la fila o columna completa \(igual que hacer clic en la fila o encabezado de columna\).|  
|Tecla de navegación \(tecla de dirección, RE PÁG\/ABAJO, INICIO, FIN\)|Si selecciona una fila o columna completa, al cambiar la celda actual por la columna o la fila nueva, la selección se desplaza a la fila o la columna nueva \(según el modo de selección\).|  
  
 Si <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> se establece en `false` y <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> en <xref:System.Windows.Forms.DataGridViewSelectionMode> o <xref:System.Windows.Forms.DataGridViewSelectionMode>, al cambiar la celda actual por la celda o la columna nueva utilizando el teclado, la selección se desplaza a la fila o la columna nueva.  Las teclas MAYÚS, CTRL y ALT no alteran este comportamiento.  
  
 Si <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> se establece en `true`, el comportamiento de la navegación no cambia, pero si navega utilizando el teclado y al mismo tiempo presiona MAYÚS \(incluyendo CTRL\+MAYÚS\) modificará la selección múltiple.  Antes de comenzar la navegación, el control marca la celda actual como una celda del delimitador.  Cuando navega presionando MAYÚS, la selección incluye todas las celdas entre la celda del delimitador y la celda actual.  Otras celdas del control permanecerán seleccionadas si ya lo estaban, pero se anulará su selección si la navegación con el teclado las sitúa temporalmente entre la celda del delimitador y la celda actual.  
  
 Si <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> se establece en `true` y <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> en <xref:System.Windows.Forms.DataGridViewSelectionMode> o <xref:System.Windows.Forms.DataGridViewSelectionMode>, el comportamiento de la celda del delimitador es el mismo, pero sólo si se seleccionan o se anula la selección de las filas y las columnas completas.  
  
## Control predeterminado del mouse  
  
### Control básico del mouse  
  
> [!NOTE]
>  Al hacer clic en una celda con el botón primario del mouse, siempre se cambia la celda actual.  Al hacer clic en una celda con el botón secundario del mouse, se abre un menú contextual, cuando uno está disponible.  
  
|Acción del mouse|Descripción|  
|----------------------|-----------------|  
|Botón primario del mouse presionado|Hace que la celda en la que hace clic sea la celda activa y provoca el evento <xref:System.Windows.Forms.DataGridView.CellMouseDown?displayProperty=fullName>.|  
|Botón primario del mouse liberado|Genera el evento <xref:System.Windows.Forms.DataGridView.CellMouseUp?displayProperty=fullName>.|  
|Clic con el botón primario del mouse|Provoca los eventos <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=fullName> y <xref:System.Windows.Forms.DataGridView.CellMouseClick?displayProperty=fullName>.|  
|Botón primario del mouse presionado y arrastrar a la celda del encabezado de columna|Si la propiedad <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=fullName> es `true`, mueva la columna para que se pueda colocar en una nueva posición.|  
  
### Selección del mouse  
 No existe ninguna acción de selección asociada al botón central del mouse o a su rueda.  
  
 Si la propiedad <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> se establece en `false` y la propiedad <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> en <xref:System.Windows.Forms.DataGridViewSelectionMode>, se produce el siguiente comportamiento.  
  
|Acción del mouse|Descripción|  
|----------------------|-----------------|  
|Clic con el botón primario del mouse|Selecciona sólo la celda actual si el usuario hace clic en una celda.  No se realiza ninguna selección si el usuario hace clic en una fila o encabezado de columna.|  
|Clic con el botón secundario del mouse|Muestra un menú contextual si alguno está disponible.|  
  
 Se produce el mismo comportamiento si <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> está establecido en <xref:System.Windows.Forms.DataGridViewSelectionMode> o <xref:System.Windows.Forms.DataGridViewSelectionMode>, excepto que, según el modo de selección, al hacer clic en la fila o el encabezado de la columna seleccionará la fila o la columna completa y establecerá la celda activa en la primera celda de la fila o de la columna.  
  
 Si <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> se establece en <xref:System.Windows.Forms.DataGridViewSelectionMode> o <xref:System.Windows.Forms.DataGridViewSelectionMode>, haciendo clic en cualquier celda de una fila o una columna seleccionará la fila o la columna completa.  
  
 Si <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> se establece en `true`, al hacer clic a la vez que se presiona CTRL o MAYÚS modificará una selección múltiple.  
  
 Cuando se hace clic en una celda al mismo tiempo que se presiona CTRL, la celda cambia su estado de selección mientras que las demás celdas conservan su estado de selección actual.  
  
 Cuando se hace clic en una o varias celdas al mismo tiempo que se presiona MAYÚS, la selección incluye todas las celdas entre la celda activa y la celda del delimitador en la posición de la celda activa antes del primer clic.  Cuando se hace clic y se arrastra el puntero a lo largo de varias celdas, la celda del delimitador es la celda en la que se hizo clic al principio de la operación de arrastre.  Los clics subsiguientes junto con la tecla MAYÚS presionada, cambian la celda activa, pero no la celda del delimitador.  Otras celdas del control permanecerán seleccionadas si ya lo estaban, pero se anulará su selección si la navegación con el mouse las sitúa temporalmente entre la celda del delimitador y la celda activa.  
  
 Si <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> se establece en `true` y <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> en <xref:System.Windows.Forms.DataGridViewSelectionMode> o <xref:System.Windows.Forms.DataGridViewSelectionMode>, al hacer clic en la fila o el encabezado de la columna \(según el modo de selección\) a la vez que se presiona la tecla MAYÚS, modificará la selección existente de las filas o columnas completas si ya estaban seleccionadas.  De lo contrario, anulará la selección e iniciará una nueva selección de filas o columnas completas.  Sin embargo, al hacer clic en una fila o encabezado de columna a la vez que se presiona la tecla CTRL, se agregará o se quitará la fila o columna en la que se hizo clic de la selección activa sin que se modifique esta selección.  
  
 Si <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> se establece en `true` y <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> en <xref:System.Windows.Forms.DataGridViewSelectionMode> o <xref:System.Windows.Forms.DataGridViewSelectionMode>, al hacer clic en una celda a la vez que se presiona la tecla MAYÚS o CTRL el comportamiento es el mismo excepto que sólo afecta a las filas o columnas completas.  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 [Control DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)