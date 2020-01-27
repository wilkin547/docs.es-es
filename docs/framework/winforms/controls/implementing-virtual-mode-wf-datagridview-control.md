---
title: 'Tutorial: implementar el modo virtual en el control DataGridView'
ms.date: 03/30/2017
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
ms.openlocfilehash: 5db97b321238bc371c94e627a387bd83ca31b58a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746517"
---
# <a name="walkthrough-implementing-virtual-mode-in-the-windows-forms-datagridview-control"></a>Tutorial: Implementar el modo virtual en el control DataGridView de formularios Windows Forms
Si desea mostrar grandes cantidades de datos tabulares en un control <xref:System.Windows.Forms.DataGridView>, puede establecer la propiedad <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> en `true` y administrar explícitamente la interacción del control con su almacén de datos. Esto le permite ajustar el rendimiento del control en esta situación.  
  
 El control <xref:System.Windows.Forms.DataGridView> proporciona varios eventos que se pueden controlar para interactuar con un almacén de datos personalizado. Este tutorial le guía a través del proceso de implementación de estos controladores de eventos. En el ejemplo de código de este tema se usa un origen de datos muy simple con fines ilustrativos. En una configuración de producción, normalmente solo se cargan las filas que se deben mostrar en una memoria caché y se controla <xref:System.Windows.Forms.DataGridView> eventos para interactuar con la memoria caché y actualizarla. Para obtener más información, vea [implementar el modo virtual con la carga de datos Just-in-Time en el control DataGridView Windows Forms](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
  
 Para copiar el código de este tema como una sola lista, vea [Cómo: implementar el modo virtual en el control DataGridView Windows Forms](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).  
  
## <a name="creating-the-form"></a>Crear el formulario  
  
#### <a name="to-implement-virtual-mode"></a>Para implementar el modo virtual  
  
1. Cree una clase que derive de <xref:System.Windows.Forms.Form> y contenga un control <xref:System.Windows.Forms.DataGridView>.  
  
     El código siguiente contiene alguna inicialización básica. Declara algunas variables que se usarán en pasos posteriores, proporciona un método `Main` y proporciona un diseño de formulario simple en el constructor de clase.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#001)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#001)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#001)]  
    [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#002)]
    [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#002)]
    [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#002)]  
  
2. Implemente un controlador para el evento de <xref:System.Windows.Forms.Form.Load> del formulario que inicializa el control <xref:System.Windows.Forms.DataGridView> y rellena el almacén de datos con valores de ejemplo.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#110)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#110)]  
  
3. Implemente un controlador para el evento <xref:System.Windows.Forms.DataGridView.CellValueNeeded> que recupera el valor de la celda solicitada del almacén de datos o el objeto `Customer` actualmente en edición.  
  
     Este evento se produce siempre que el control de <xref:System.Windows.Forms.DataGridView> necesita pintar una celda.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#120)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#120)]  
  
4. Implemente un controlador para el evento <xref:System.Windows.Forms.DataGridView.CellValuePushed> que almacena un valor de celda editado en el objeto `Customer` que representa la fila modificada. Este evento se produce siempre que el usuario confirma un cambio en el valor de una celda.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#130)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#130)]  
  
5. Implemente un controlador para el evento <xref:System.Windows.Forms.DataGridView.NewRowNeeded> que crea un nuevo objeto `Customer` que representa una fila recién creada.  
  
     Este evento se produce siempre que el usuario escribe la fila de nuevos registros.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#140)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#140)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#140)]  
  
6. Implemente un controlador para el evento <xref:System.Windows.Forms.DataGridView.RowValidated> que guarde las filas nuevas o modificadas en el almacén de datos.  
  
     Este evento se produce siempre que el usuario cambia la fila actual.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#150)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#150)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#150)]  
  
7. Implemente un controlador para el evento <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> que indica si el evento de <xref:System.Windows.Forms.DataGridView.CancelRowEdit> se producirá cuando el usuario señale la reversión de la fila presionando ESC dos veces en modo de edición o una vez fuera del modo de edición.  
  
     De forma predeterminada, <xref:System.Windows.Forms.DataGridView.CancelRowEdit> se produce tras la reversión de las filas cuando se modifican las celdas de la fila actual, a menos que la propiedad <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> esté establecida en `true` en el controlador de eventos <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>. Este evento es útil cuando el ámbito de confirmación se determina en tiempo de ejecución.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#160)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#160)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#160)]  
  
8. Implemente un controlador para el evento <xref:System.Windows.Forms.DataGridView.CancelRowEdit> que descarte los valores del objeto `Customer` que representa la fila actual.  
  
     Este evento se produce cuando el usuario señala la reversión de la fila presionando ESC dos veces en modo de edición o una vez fuera del modo de edición. Este evento no se produce si no se ha modificado ninguna celda de la fila actual o si se ha establecido el valor de la propiedad <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> en `false` en un controlador de eventos <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#170)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#170)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#170)]  
  
9. Implemente un controlador para el evento <xref:System.Windows.Forms.DataGridView.UserDeletingRow> que elimina un objeto `Customer` existente del almacén de datos o descarta un objeto `Customer` no guardado que representa una fila recién creada.  
  
     Este evento se produce cuando el usuario elimina una fila haciendo clic en un encabezado de fila y presionando la tecla Supr.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#180)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#180)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#180)]  
  
10. Implemente una clase de `Customers` simple para representar los elementos de datos utilizados en este ejemplo de código.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#200)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#200)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#200)]  
  
## <a name="testing-the-application"></a>Probar la aplicación  
 Puede comprobar el formulario para asegurarse de que se comporta de la forma prevista.  
  
#### <a name="to-test-the-form"></a>Para comprobar el formulario  
  
- Compile y ejecute la aplicación.  
  
     Verá un control de <xref:System.Windows.Forms.DataGridView> rellenado con tres registros de cliente. Puede modificar los valores de varias celdas de una fila y presionar ESC dos veces en modo de edición y una vez fuera del modo de edición para revertir toda la fila a sus valores originales. Cuando se modifican, agregan o eliminan filas en el control, `Customer` objetos del almacén de datos también se modifican, agregan o eliminan.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Esta aplicación le proporciona una descripción básica de los eventos que debe controlar para implementar el modo virtual en el control de <xref:System.Windows.Forms.DataGridView>. Puede mejorar esta aplicación básica de varias maneras:  
  
- Implemente un almacén de datos que almacene en memoria caché los valores de una base de datos externa. La memoria caché debe recuperar y descartar los valores según sea necesario para que solo contengan lo necesario para la presentación y consumir una pequeña cantidad de memoria en el equipo cliente.  
  
- Ajuste el rendimiento del almacén de datos en función de sus requisitos. Por ejemplo, puede que desee compensar las conexiones de red lentas en lugar de las limitaciones de memoria del equipo cliente con un tamaño de caché mayor y minimizar el número de consultas de base de datos.  
  
 Para obtener más información acerca de los valores de almacenamiento en caché de una base de datos externa, consulte [Cómo: implementar el modo virtual con la carga de datos Just-in-Time en el control DataGridView Windows Forms](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- <xref:System.Windows.Forms.DataGridView.CellValueNeeded>
- <xref:System.Windows.Forms.DataGridView.CellValuePushed>
- <xref:System.Windows.Forms.DataGridView.NewRowNeeded>
- <xref:System.Windows.Forms.DataGridView.RowValidated>
- <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>
- <xref:System.Windows.Forms.DataGridView.CancelRowEdit>
- <xref:System.Windows.Forms.DataGridView.UserDeletingRow>
- [Ajuste del rendimiento del control DataGridView en Windows Forms](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [Implementar el modo virtual mediante la carga de datos Just-In-Time en el control DataGridView de formularios Windows Forms](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
- [Implementar el modo virtual en el control DataGridView de formularios Windows Forms](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)
