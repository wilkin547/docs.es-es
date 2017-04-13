---
title: "Comportamiento predeterminado de teclado y mouse en el control DataGridView | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "DataGrid [WPF], comportamiento del teclado"
  - "DataGrid [WPF], comportamiento del mouse"
  - "comportamiento del teclado [WPF], DataGrid"
  - "comportamiento del mouse [WPF], DataGrid"
ms.assetid: 563b8854-ca39-4d97-8235-17eaa0f93c8d
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Comportamiento predeterminado de teclado y mouse en el control DataGridView
En este tema se describe cómo los usuarios pueden interactuar con el control <xref:System.Windows.Controls.DataGrid> a través del teclado y el mouse.  
  
 Las interacciones típicas con <xref:System.Windows.Controls.DataGrid> incluyen la navegación, selección y edición.  El comportamiento de selección se ve afectado por las propiedades <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> y <xref:System.Windows.Controls.DataGrid.SelectionUnit%2A>.  Los valores predeterminados que causan el comportamiento descrito en este tema son <xref:System.Windows.Controls.DataGridSelectionMode?displayProperty=fullName> y <xref:System.Windows.Controls.DataGridSelectionUnit?displayProperty=fullName>.  El cambio de estos valores podría producir un comportamiento distinto al descrito.  Cuando una celda está en modo de edición, el control de edición puede invalidar el comportamiento estándar del teclado de <xref:System.Windows.Controls.DataGrid>.  
  
## Comportamiento predeterminado del teclado  
 En la tabla siguiente se muestra el comportamiento predeterminado del teclado para el control <xref:System.Windows.Controls.DataGrid>.  
  
|Tecla o combinación de teclas|Descripción|  
|-----------------------------------|-----------------|  
|FLECHA ABAJO|Mueve el foco a la celda que se encuentra directamente debajo de la celda actual.  Si el foco está en la última fila, al presionar la FLECHA ABAJO, no sucede nada.|  
|FLECHA ARRIBA|Mueve el foco a la celda que se encuentra directamente encima de la celda actual.  Si el foco está en la primera fila, al presionar la FLECHA ARRIBA, no sucede nada.|  
|FLECHA IZQUIERDA|Mueve el foco a la celda anterior de la fila.  Si el foco está en la primera celda de la fila, al presionar la FLECHA IZQUIERDA, no sucede nada.|  
|FLECHA DERECHA|Mueve el foco a la siguiente celda de la fila.  Si el foco está en la última celda de la fila, al presionar la FLECHA DERECHA, no sucede nada.|  
|INICIO|Mueve el foco a la primera celda de la fila actual.|  
|FIN|Mueve el foco a la última celda de la fila actual.|  
|AV PÁG|Si las filas no están agrupadas, desplaza el control descendente por el número de filas que se muestran totalmente.  Mueve el foco a la última fila que se muestra totalmente sin cambiar las columnas.<br /><br /> Si se agrupan las filas, mueve el foco a la última fila de <xref:System.Windows.Controls.DataGrid> sin cambiar las columnas.|  
|RE PÁG|Si las filas no están agrupadas, desplaza el control ascendente por el número de filas que se muestran totalmente.  Desplaza el foco a la primera fila mostrada sin cambiar las columnas.<br /><br /> Si se agrupan las filas, mueve el foco a la primera fila de <xref:System.Windows.Controls.DataGrid> sin cambiar las columnas.|  
|TAB|Mueve el foco a la siguiente celda de la fila actual.  Si el foco está en la última celda de la fila, mueve el foco a la primera celda de la siguiente fila.  Si el foco está en la última celda del control, desplaza el foco al siguiente control en el orden de tabulación del contenedor primario.<br /><br /> Si la celda actual está en el modo de edición y presionar TAB  causa que el foco se desplace fuera de la fila actual, cualquier cambio que se hubiera realizado en la fila se confirma antes de que se cambie el foco.|  
|MAYÚS\+TAB|Mueve el foco a la celda anterior de la fila actual.  Si el foco ya está en la primera celda de la fila, desplaza el foco a la primera celda de la fila anterior.  Si el foco está en la primera celda del control, desplaza el foco al control anterior en el orden de tabulación del contenedor primario.<br /><br /> Si la celda actual está en el modo de edición y presionar TAB  causa que el foco se desplace fuera de la fila actual, cualquier cambio que se hubiera realizado en la fila se confirma antes de que se cambie el foco.|  
|CTRL\+FLECHA ABAJO|Mueve el foco a la última celda de la columna actual.|  
|CTRL\+FLECHA ARRIBA|Mueve el foco a la primera celda de la columna actual.|  
|CTRL\+FLECHA DERECHA|Mueve el foco a la última celda de la fila actual.|  
|CTRL\+FLECHA IZQUIERDA|Mueve el foco a la primera celda de la fila actual.|  
|CTRL\+INICIO|Desplaza el foco a la primera celda del control.|  
|CTRL\+FIN|Desplaza el foco a la última celda del control.|  
|CTRL\+AV PÁG|Igual que AV PÁG.|  
|CTRL\+RE PÁG|Igual que RE PÁG.|  
|F2|Si el valor de la propiedad <xref:System.Windows.Controls.DataGrid.IsReadOnly%2A?displayProperty=fullName> es `false` y el valor de la propiedad <xref:System.Windows.Controls.DataGridColumn.IsReadOnly%2A?displayProperty=fullName> es `false` para la columna actual, coloca la celda actual en modo de edición.|  
|ENTRAR|Confirma cualquier cambio en la celda y fila actuales y desplaza el foco a la celda directamente debajo de la celda actual.  Si el foco está en la última fila, confirma cualquier cambio sin mover el foco.|  
|ESC|Si el control está en modo de edición, cancela la edición y revierte todos los cambios realizados en el control.  Si el origen de datos subyacente implementa <xref:System.ComponentModel.IEditableObject>, al presionar ESC por segunda vez, se cancela el modo de edición para toda la fila.|  
|RETROCESO|Elimina el carácter situado delante del cursor al editar una celda.|  
|DELETE|Elimina el carácter situado detrás del cursor al editar una celda.|  
|CTRL\+ENTRAR|Confirma cualquier cambio en la celda actual sin mover el foco.|  
|CTRL\+A|Si <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> se establece en <xref:System.Windows.Controls.DataGridSelectionMode>, se seleccionan todas las filas de <xref:System.Windows.Controls.DataGrid>.|  
  
## Teclas de selección  
 Si el valor de la propiedad <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> se establece en <xref:System.Windows.Controls.DataGridSelectionMode>, el comportamiento de navegación no cambia, pero si se navega con el teclado y al mismo tiempo se presiona la tecla MAYÚS \(incluida la combinación de teclas CTRL\+MAYÚS\), se modifica una selección de varias filas.  Antes de comenzar la navegación, el control marca la fila actual como fila delimitadora.  Cuando se navega presionando la tecla MAYÚS, la selección incluye todas las filas comprendidas entre la fila delimitadora y la fila actual.  
  
 Las siguientes teclas de selección modifican una selección de varias filas.  
  
-   MAYÚS\+FLECHA ABAJO  
  
-   MAYÚS\+FLECHA ARRIBA  
  
-   MAYÚS\+AV PÁG  
  
-   MAYÚS\+RE PÁG  
  
-   CTRL\+MAYÚS\+FLECHA ABAJO  
  
-   CTRL\+MAYÚS\+FLECHA ARRIBA  
  
-   CTRL\+MAYÚS\+INICIO  
  
-   CTRL\+MAYÚS\+FIN  
  
## Comportamiento predeterminado del mouse  
 En la tabla siguiente se muestra el comportamiento predeterminado del mouse para el control <xref:System.Windows.Controls.DataGrid>.  
  
|Acción del mouse|Descripción|  
|----------------------|-----------------|  
|Hacer clic en una fila no seleccionada|Hace que la fila en la que se hace clic se convierta en la fila actual y que la celda en la que hace clic sea la celda activa.|  
|Haga clic en la celda actual|Pone la celda actual en modo de edición.|  
|Arrastrar una celda de encabezado de columna|Si el valor de la propiedad <xref:System.Windows.Controls.DataGrid.CanUserReorderColumns%2A?displayProperty=fullName> es `true` y el valor de la propiedad <xref:System.Windows.Controls.DataGridColumn.CanUserReorder%2A?displayProperty=fullName> es `true` para la columna actual, mueve la columna de modo que se pueda colocar en la nueva posición.|  
|Arrastrar una línea de separación de encabezados de columna|Si el valor de la propiedad <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=fullName> es `true` y el valor de la propiedad <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=fullName> es `true` para la columna actual, cambia el tamaño de la columna.|  
|Haga doble clic en un separador de encabezados de columna|Si la propiedad <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=fullName> es `true` y la propiedad <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=fullName> es `true` para la columna actual, dicha columna se redimensiona automáticamente con el modo de ajuste del tamaño <xref:System.Windows.Controls.DataGridLength.Auto%2A>.|  
|Hacer clic en una celda de encabezado de columna|Si el valor de la propiedad <xref:System.Windows.Controls.DataGrid.CanUserSortColumns%2A?displayProperty=fullName> es `true` y el valor de la propiedad <xref:System.Windows.Controls.DataGridColumn.CanUserSort%2A?displayProperty=fullName> es `true` para la columna actual, ordena la columna.<br /><br /> Al hacer clic en el encabezado de una columna que ya está ordenada, se invertirá la dirección de ordenación de esa columna.<br /><br /> Cuando se presiona la tecla MAYÚS y al mismo tiempo se hace clic en varios encabezados de columna, la ordenación se realiza por varias columnas en el orden en que se ha hecho clic en sus encabezados.|  
|CTRL\+hacer clic en una fila|Si el valor de propiedad <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> se establece en <xref:System.Windows.Controls.DataGridSelectionMode>, modifica una selección de varias filas no contiguas.<br /><br /> Si la fila ya está seleccionada, anula la selección de la fila.|  
|MAYÚS\+hacer clic en una fila|Si el valor de propiedad <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> se establece en <xref:System.Windows.Controls.DataGridSelectionMode>, modifica una selección de varias filas contiguas.|  
|Hacer clic en un encabezado de grupo de filas|Se expande o contrae el grupo.|  
|Haga clic en el botón Seleccionar todo en la esquina superior izquierda de <xref:System.Windows.Controls.DataGrid>|Si <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> se establece en <xref:System.Windows.Controls.DataGridSelectionMode>, se seleccionan todas las filas de <xref:System.Windows.Controls.DataGrid>.|  
  
## Selección del mouse  
 Si el valor de la propiedad <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> se establece en <xref:System.Windows.Controls.DataGridSelectionMode>, al hacer clic en una fila y presionar al mismo tiempo la tecla CTRL o MAYÚS, se modificará una selección de varias filas.  
  
 Cuando se hace clic en una fila al mismo tiempo que se presiona la tecla CTRL, la fila cambia su estado de selección mientras que las demás filas conservan su estado de selección actual.  Realice esta acción para seleccionar filas no adyacentes.  
  
 Cuando se hace clic en una fila al mismo tiempo que se presiona la tecla MAYÚS, la selección incluye todas las filas comprendidas entre la fila actual y la fila delimitadora ubicada en la posición de la fila actual antes del clic.  Si posteriormente se hace clic mientras se presiona la tecla MAYÚS, cambiará la fila actual pero no la fila delimitadora.  Realice esta acción para seleccionar un rango de filas adyacentes.  
  
 CTRL\+MAYÚS se puede combinar para seleccionar intervalos no adyacentes de filas adyacentes.  Para ello, seleccione el primer intervalo usando MAYÚS\+clic, como se describió anteriormente.  Después de seleccionar el primer intervalo de filas, use CTRL\+clic para seleccionar la primera fila del intervalo siguiente y, a continuación, haga clic en la última fila de dicho intervalo a la vez que presiona CTRL\+MAYÚS.  
  
## Vea también  
 <xref:System.Windows.Controls.DataGrid>   
 <xref:System.Windows.Controls.DataGrid.SelectionMode%2A>