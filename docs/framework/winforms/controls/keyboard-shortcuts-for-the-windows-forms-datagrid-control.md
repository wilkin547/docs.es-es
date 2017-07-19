---
title: "M&#233;todos abreviados de teclado para el control DataGrid de formularios Windows Forms | Microsoft Docs"
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
  - "DataGrid (control) [Windows Forms], teclas de desplazamiento"
  - "métodos abreviados de teclado, DataGrid (control)"
ms.assetid: a01780f9-20d5-4f5f-808f-c790c9a007a5
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# M&#233;todos abreviados de teclado para el control DataGrid de formularios Windows Forms
> [!NOTE]
>  Aunque el control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>, este control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y, en su caso, de uso futuro.  Para obtener más información, vea [Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 En la tabla siguiente se muestran los métodos abreviados de teclado que se pueden utilizar para navegar por el control <xref:System.Windows.Forms.DataGrid> de formularios Windows Forms:  
  
|Acción|Acceso directo|  
|------------|--------------------|  
|Completar una entrada en una celda y bajar a la celda siguiente.<br /><br /> Si el foco se encuentra en un vínculo a una tabla secundaria, navegue hasta dicha tabla.|ENTRAR|  
|Cancelar la modificación de la celda, en modo de edición de celdas.<br /><br /> Cancelar la modificación de la fila, en la selección de marquesinas.|ESC|  
|Eliminar el carácter situado delante del punto de inserción al editar una celda.|RETROCESO|  
|Eliminar el carácter situado detrás del punto de inserción al editar una celda.|DELETE|  
|Desplazarse a la primera celda de la fila actual.|INICIO|  
|Desplazarse a la última celda de la fila actual.|FIN|  
|Resaltar los caracteres de la celda actual y colocar el punto de inserción al final de la línea.  El igual que hacer doble clic en una celda.|F2|  
|Si el foco se encuentra en una celda, ir a la celda siguiente de la fila.<br /><br /> Si el foco se encuentra en la última celda de una fila, ir al primer vínculo de tabla secundaria de la fila y expandirlo.<br /><br /> Si el foco se encuentra en un vínculo secundario, desplazarse hasta el siguiente vínculo secundario.<br /><br /> Si el foco se encuentra en el último vínculo secundario, ir a la primera celda de la fila siguiente.|TAB|  
|Si el foco se encuentra en una celda, ir a la celda anterior de la fila.<br /><br /> Si el foco se encuentra en la primera celda de una fila, ir al último vínculo expandido de tabla secundaria de la fila anterior o ir a la última celda de la fila anterior.<br /><br /> Si el foco se encuentra en un vínculo secundario, desplazarse hasta el vínculo secundario anterior.<br /><br /> Si el foco se encuentra en el primer vínculo secundario, ir a la última celda de la fila anterior.|MAYÚS\+TAB|  
|Ir al siguiente control en el orden de tabulación.|CTRL\+TAB|  
|Ir al control anterior en el orden de tabulación.|CTRL\+MAYÚS\+TAB|  
|Subir hasta la tabla principal si está en una tabla secundaria.  Es igual que hacer clic en el botón Atrás.|ALT\+FLECHA IZQUIERDA|  
|Expandir los vínculos de tabla secundaria.  ALT\+FLECHA ABAJO expande todos los vínculos, no sólo los que estén seleccionados.|ALT\+FLECHA ABAJO o CTRL\+SIGNO MÁS|  
|Contraer los vínculos de tabla secundaria.  ALT\+FLECHA ARRIBA contrae todos los vínculos, no sólo los que estén seleccionados.|ALT\+FLECHA ARRIBA o CTRL\+SIGNO MENOS|  
|Ir hasta la última celda que no esté vacía en el sentido de la flecha.|CTRL\+FLECHA|  
|Extender la selección una fila en el sentido de la flecha \(sin incluir los vínculos de tabla secundaria\).|MAYÚS\+FLECHA ARRIBA\/ABAJO|  
|Extender la selección hasta la última fila que no esté vacía en el sentido de la flecha \(sin incluir los vínculos de tabla secundaria\).|CTRL\+MAYÚS\+ FLECHA ARRIBA\/ABAJO|  
|Desplazarse a la celda superior izquierda.|CTRL\+INICIO|  
|Desplazarse a la celda inferior derecha.|CTRL\+FIN|  
|Extender la selección hasta la fila superior.|CTRL\+MAYÚS\+INICIO|  
|Extender la selección hasta la fila inferior.|CTRL\+MAYÚS\+FIN|  
|Seleccionar la fila actual \(sin incluir los vínculos de tabla secundaria\).|MAYÚS\+ESPACIO|  
|Seleccionar la cuadrícula completa \(sin incluir los vínculos de tabla secundaria\).|CTRL\+A|  
|Mostrar la fila principal al encontrarse en una tabla secundaria.|CTRL\+AV PÁG|  
|Ocultar la fila principal al encontrarse en una tabla secundaria.|CTRL\+RE PÁG|  
|Extender la selección hacia abajo una pantalla \(sin incluir los vínculos de tabla secundaria\).|MAYÚS\+AV PÁG|  
|Extender la selección hacia arriba una pantalla \(sin incluir los vínculos de tabla secundaria\).|MAYÚS\+RE PÁG|  
|Llamar al método <xref:System.Windows.Forms.DataGrid.EndEdit%2A> para la fila actual.|CTRL\+ENTRAR|  
|Escribir un valor <xref:System.DBNull.Value?displayProperty=fullName> en una celda, en modo de edición.|CTRL\+0|  
  
## Vea también  
 [Información general del control DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)   
 [Control DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)