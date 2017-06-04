---
title: "Tutorial: Implementar el modo virtual en el control DataGridView de formularios Windows Forms | Microsoft Docs"
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
  - "datos [Windows Forms], administrar conjuntos de datos grandes"
  - "DataGridView (control) [Windows Forms], conjuntos de datos grandes"
  - "DataGridView (control) [Windows Forms], modo virtual"
  - "modo virtual, tutoriales"
  - "tutoriales [Windows Forms], DataGridView (control)"
ms.assetid: 74eb5276-5ab8-4ce0-8005-dae751d85f7c
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Tutorial: Implementar el modo virtual en el control DataGridView de formularios Windows Forms
Si desea mostrar grandes volúmenes de datos en formato de tabla en un control <xref:System.Windows.Forms.DataGridView>, puede establecer la propiedad <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> en `true` y administrar de forma explícita la interacción del control con el almacén de datos.  Esto le permite ajustar el rendimiento del control en esta situación.  
  
 El control <xref:System.Windows.Forms.DataGridView> proporciona varios eventos que puede controlar para interactuar con un almacén de datos personalizado.  Este tutorial le guía a través del proceso de implementar estos controladores de eventos.  En el ejemplo de código de este tema se utiliza un origen de datos muy sencillo para fines de ilustración.  En una configuración de producción, normalmente cargará sólo las filas que necesite mostrar en caché y controlará eventos <xref:System.Windows.Forms.DataGridView> para interactuar con la caché y actualizarla.  Para obtener más información, vea [Implementar el modo virtual mediante la carga de datos Just\-In\-Time en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md).  
  
 Para copiar el código de este tema como un listado sencillo, vea [Cómo: Implementar el modo virtual en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).  
  
## Crear el formulario  
  
#### Para implementar el modo virtual  
  
1.  Cree una clase que deriva de <xref:System.Windows.Forms.Form> y contiene un control <xref:System.Windows.Forms.DataGridView>.  
  
     El código siguiente contiene alguna inicialización básica.  Se declaran algunas variables que se utilizarán en pasos posteriores, se proporciona un método `Main` y un diseño de formulario sencillo del constructor de clase.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#001](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#001)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#001](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#001)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#001](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#001)]  
    [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#002](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#002)]
    [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#002](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#002)]
    [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#002](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#002)]  
  
2.  Implemente un controlador para el evento <xref:System.Windows.Forms.Form.Load> del formulario que inicializa el control <xref:System.Windows.Forms.DataGridView> y rellena el almacén de datos con valores de ejemplo.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#110](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#110)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#110)]  
  
3.  Implemente un controlador para el evento <xref:System.Windows.Forms.DataGridView.CellValueNeeded> que recupera el valor de celda solicitado del almacén de datos o el objeto `Customer` actualmente en edición.  
  
     Este evento aparece cada vez que el control <xref:System.Windows.Forms.DataGridView> tiene que dibujar una celda.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#120](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#120)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#120)]  
  
4.  Implemente un controlador para el evento <xref:System.Windows.Forms.DataGridView.CellValuePushed> que almacena un valor de celda editado en el objeto `Customer` que representa la fila editada.  Este evento se produce cada vez que el usuario confirma un cambio de valor de celda.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#130](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#130)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#130)]  
  
5.  Implemente un controlador para el evento <xref:System.Windows.Forms.DataGridView.NewRowNeeded> que crea un nuevo objeto `Customer` que representa una fila recién creada.  
  
     Este evento aparece cada vez que el usuario especifica la fila de nuevos registros.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#140](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#140)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#140)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#140)]  
  
6.  Implemente un controlador para el evento <xref:System.Windows.Forms.DataGridView.RowValidated> que guarda las filas nuevas o modificadas en el almacén de datos.  
  
     Este evento aparece cada vez que el usuario cambia la fila actual.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#150](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#150)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#150](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#150)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#150](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#150)]  
  
7.  Implemente un controlador para el evento <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> que indica si se producirá el evento <xref:System.Windows.Forms.DataGridView.CancelRowEdit> cuando el usuario señale la inversión de fila presionando dos veces ESC en el modo de edición o una vez fuera del modo de edición.  
  
     De forma predeterminada, se produce el evento <xref:System.Windows.Forms.DataGridView.CancelRowEdit> con la inversión de fila cuando se ha modificado alguna celda de la fila actual, a no ser que la propiedad <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=fullName> esté establecida en `true` en el controlador de eventos <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>.  Este evento resulta de utilidad cuando se determina el ámbito de la confirmación en tiempo de ejecución.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#160](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#160)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#160](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#160)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#160](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#160)]  
  
8.  Implemente un controlador para el evento <xref:System.Windows.Forms.DataGridView.CancelRowEdit> que descarta los valores del objeto `Customer` que representa la fila actual.  
  
     Se produce este evento cuando el usuario señala la reversión de la fila presionando dos veces ESC en modo de edición o una vez fuera del modo de edición.  No se produce este evento si no se ha modificado ninguna celda de la fila actual o si se ha establecido el valor de la propiedad <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=fullName> en `false` en un controlador de eventos <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#170](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#170)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#170](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#170)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#170](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#170)]  
  
9. Implemente un controlador para el evento <xref:System.Windows.Forms.DataGridView.UserDeletingRow> que elimina un objeto `Customer` existente del almacén de datos o descarta un objeto `Customer` no guardado que representa una fila recién creada.  
  
     Se produce este evento siempre que el usuario elimina una fila haciendo clic en un encabezado de fila y presionando la tecla SUPR.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#180](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#180)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#180](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#180)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#180](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#180)]  
  
10. Implemente una clase `Customers` simple para representar los elementos de datos utilizados por este ejemplo de código.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#200](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#200)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#200](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#200)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#200](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#200)]  
  
## Probar la aplicación  
 Puede comprobar el formulario para asegurarse de que se comporta de la forma prevista.  
  
#### Para comprobar el formulario  
  
-   Compile y ejecute la aplicación.  
  
     Aparecerá un control <xref:System.Windows.Forms.DataGridView> rellenado con tres registros del cliente.  Puede modificar los valores de varias celdas de una fila y presionar dos veces ESC en el modo de edición y una vez fuera de éste modo para invertir la fila completa a sus valores originales.  Cuando modifica, agrega o elimina filas del control, se modifican, agregan o eliminan objetos `Customer` del almacén de datos, también.  
  
## Pasos siguientes  
 Esta aplicación proporciona conocimientos básicos de los eventos que debe controlar para implementar el modo virtual en el control <xref:System.Windows.Forms.DataGridView>.  Puede mejorar esta aplicación básica de varios maneras:  
  
-   Implemente un almacén de datos que almacena en memoria caché los valores de una base de datos externa.  La caché recuperará y descartará valores según sea necesario de modo que sólo contenga lo que es necesario para la presentación a la vez que utiliza una pequeña cantidad de memoria en el equipo cliente.  
  
-   Ajuste el rendimiento del almacén de datos en función de sus requisitos.  Por ejemplo, quizá desee compensar las conexiones de red ralentizadas en lugar de las limitaciones de memoria del equipo cliente utilizando un tamaño mayor de caché y minimizando el número de consultas de base de datos.  
  
 Para obtener más información sobre cómo almacenar en memoria caché valores de una base de datos externa, vea [Cómo: Implementar el modo virtual con la carga de datos Just\-In\-Time en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>   
 <xref:System.Windows.Forms.DataGridView.CellValueNeeded>   
 <xref:System.Windows.Forms.DataGridView.CellValuePushed>   
 <xref:System.Windows.Forms.DataGridView.NewRowNeeded>   
 <xref:System.Windows.Forms.DataGridView.RowValidated>   
 <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>   
 <xref:System.Windows.Forms.DataGridView.CancelRowEdit>   
 <xref:System.Windows.Forms.DataGridView.UserDeletingRow>   
 [Ajuste del rendimiento del control DataGridView en formularios Windows Forms](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)   
 [Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)   
 [Implementar el modo virtual mediante la carga de datos Just\-In\-Time en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)   
 [Cómo: Implementar el modo virtual en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)