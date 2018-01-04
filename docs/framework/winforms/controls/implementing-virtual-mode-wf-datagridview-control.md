---
title: 'Tutorial: Implementar el modo virtual en el control DataGridView de formularios Windows Forms'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- virtual mode [Windows Forms], walkthroughs
- DataGridView control [Windows Forms], large data sets
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 74eb5276-5ab8-4ce0-8005-dae751d85f7c
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3b9a70aaf2643811354cc9d7f6b51ed0805ca916
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-implementing-virtual-mode-in-the-windows-forms-datagridview-control"></a>Tutorial: Implementar el modo virtual en el control DataGridView de formularios Windows Forms
Si desea mostrar grandes cantidades de datos tabulares en una <xref:System.Windows.Forms.DataGridView> control, puede establecer la <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> propiedad `true` y administrar de manera explícita la interacción del control con su almacén de datos. Esto le permite ajustar el rendimiento del control en esta situación.  
  
 El <xref:System.Windows.Forms.DataGridView> control proporciona varios eventos que puede controlar para interactuar con un almacén de datos personalizado. Este tutorial le guía a través del proceso de implementar estos controladores de eventos. El ejemplo de código en este tema usa un origen de datos muy simple con fines meramente ilustrativos. En un entorno de producción, normalmente se cargará solo las filas que se debe mostrar en una memoria caché y controlar <xref:System.Windows.Forms.DataGridView> eventos para interactuar con y actualizar la memoria caché. Para obtener más información, vea [implementar el modo Virtual con la carga de datos Just en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
  
 Para copiar el código de este tema como una sola lista, vea [Cómo: implementar el modo Virtual en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).  
  
## <a name="creating-the-form"></a>Crear el formulario  
  
#### <a name="to-implement-virtual-mode"></a>Para implementar el modo virtual  
  
1.  Cree una clase que deriva de <xref:System.Windows.Forms.Form> y contiene un <xref:System.Windows.Forms.DataGridView> control.  
  
     El siguiente código contiene alguna inicialización básica. Declara algunas de las variables que se utilizarán en pasos posteriores, se proporciona un `Main` (método) y proporciona un diseño de forma simple en el constructor de clase.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#001](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#001)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#001](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#001)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#001](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#001)]  
    [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#002](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#002)]
    [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#002](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#002)]
    [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#002](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#002)]  
  
2.  Implemente un controlador para el formulario <xref:System.Windows.Forms.Form.Load> eventos que inicializan el <xref:System.Windows.Forms.DataGridView> control y rellena el almacén de datos con valores de ejemplo.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#110](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#110)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#110)]  
  
3.  Implemente un controlador para el <xref:System.Windows.Forms.DataGridView.CellValueNeeded> eventos que recupera el valor de celda solicitado desde el almacén de datos o la `Customer` objeto actualmente en Editar.  
  
     Este evento se produce siempre que el <xref:System.Windows.Forms.DataGridView> control necesita pintar una celda.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#120](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#120)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#120)]  
  
4.  Implemente un controlador para el <xref:System.Windows.Forms.DataGridView.CellValuePushed> eventos que almacena un valor de celda editado en el `Customer` objeto que representa la fila editada. Este evento se produce cuando el usuario confirma un cambio del valor de celda.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#130](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#130)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#130)]  
  
5.  Implemente un controlador para el <xref:System.Windows.Forms.DataGridView.NewRowNeeded> eventos que se crea un nuevo `Customer` objeto que representa una fila recién creada.  
  
     Este evento se produce cada vez que el usuario escribe la fila para nuevos registros.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#140](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#140)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#140)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#140)]  
  
6.  Implemente un controlador para el <xref:System.Windows.Forms.DataGridView.RowValidated> evento que guarda filas nuevas o modificadas en el almacén de datos.  
  
     Este evento se produce cuando el usuario cambia la fila actual.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#150](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#150)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#150](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#150)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#150](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#150)]  
  
7.  Implemente un controlador para el <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> evento que indica si la <xref:System.Windows.Forms.DataGridView.CancelRowEdit> evento se producirá cuando el usuario señala la reversión de la fila presionando la tecla ESC dos veces en modo de edición o una vez fuera del modo de edición.  
  
     De forma predeterminada, <xref:System.Windows.Forms.DataGridView.CancelRowEdit> se produce después de crear una nueva versión de fila cuando se han modificado las celdas de la fila actual, a menos que la <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> propiedad está establecida en `true` en el <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> controlador de eventos. Este evento es útil cuando el ámbito de confirmación se determina en tiempo de ejecución.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#160](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#160)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#160](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#160)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#160](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#160)]  
  
8.  Implemente un controlador para el <xref:System.Windows.Forms.DataGridView.CancelRowEdit> eventos que descartan los valores de la `Customer` objeto que representa la fila actual.  
  
     Este evento se produce cuando el usuario señala la reversión de la fila presionando la tecla ESC dos veces en modo de edición o una vez fuera del modo de edición. Este evento no se produce si no se han modificado ninguna celda en la fila actual o si el valor de la <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> propiedad se ha establecido en `false` en un <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> controlador de eventos.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#170](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#170)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#170](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#170)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#170](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#170)]  
  
9. Implemente un controlador para el <xref:System.Windows.Forms.DataGridView.UserDeletingRow> eventos que elimine una existente `Customer` objeto desde el almacén de datos o descarta una que no haya guardado `Customer` objeto que representa una fila recién creada.  
  
     Este evento se produce cuando el usuario elimina una fila haciendo clic en un encabezado de fila y presionando la tecla SUPR.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#180](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#180)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#180](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#180)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#180](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#180)]  
  
10. Implementar un simple `Customers` clase para representar los elementos de datos utilizados por este ejemplo de código.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#200](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#200)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#200](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#200)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#200](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#200)]  
  
## <a name="testing-the-application"></a>Probar la aplicación  
 Puede comprobar el formulario para asegurarse de que se comporta de la forma prevista.  
  
#### <a name="to-test-the-form"></a>Para comprobar el formulario  
  
-   Compile y ejecute la aplicación.  
  
     Verá un <xref:System.Windows.Forms.DataGridView> control rellenado con tres registros del cliente. Puede modificar los valores de varias celdas de una fila y presione ESC dos veces en modo de edición y una vez fuera del modo de edición para revertir toda la fila a sus valores originales. Al modificar, agregar o eliminar filas en el control, `Customer` se modifica, se agregan o se eliminan también los objetos del almacén de datos.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Esta aplicación proporciona una descripción básica de los eventos que debe controlar para implementar el modo virtual en el <xref:System.Windows.Forms.DataGridView> control. Puede mejorar esta aplicación básica de varias maneras:  
  
-   Implementar un almacén de datos que almacena en caché los valores de una base de datos externo. La memoria caché debe recuperar y descartar los valores según sea necesario para que sólo contenga lo que es necesario para su presentación y consume una pequeña cantidad de memoria en el equipo cliente.  
  
-   Ajustar el rendimiento del almacén de datos dependiendo de los requisitos. Por ejemplo, puede compensar para conexiones de red lentas, en lugar de las limitaciones de memoria del equipo cliente utilizando un tamaño de caché y minimizando el número de consultas de base de datos.  
  
 Para obtener más información sobre el almacenamiento en caché de los valores de una base de datos externo, vea [Cómo: implementar el modo Virtual con la carga de datos Just en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 <xref:System.Windows.Forms.DataGridView.CellValueNeeded>  
 <xref:System.Windows.Forms.DataGridView.CellValuePushed>  
 <xref:System.Windows.Forms.DataGridView.NewRowNeeded>  
 <xref:System.Windows.Forms.DataGridView.RowValidated>  
 <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>  
 <xref:System.Windows.Forms.DataGridView.CancelRowEdit>  
 <xref:System.Windows.Forms.DataGridView.UserDeletingRow>  
 [Ajuste del rendimiento del control DataGridView en Windows Forms](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 [Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 [Implementar el modo virtual mediante la carga de datos Just-In-Time en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 [Implementar el modo virtual en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)
