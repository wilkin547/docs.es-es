---
title: 'Tutorial: Implementar el modo virtual en el control DataGridView de formularios Windows Forms'
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
ms.openlocfilehash: 7f6bf1703a6536f4d22b3a2fbe412579c59d39dd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59344330"
---
# <a name="walkthrough-implementing-virtual-mode-in-the-windows-forms-datagridview-control"></a>Tutorial: Implementar el modo virtual en el control DataGridView de formularios Windows Forms
Cuando desea mostrar grandes cantidades de datos tabulares en una <xref:System.Windows.Forms.DataGridView> control, puede establecer el <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> propiedad `true` y administrar explícitamente la interacción del control con su almacén de datos. Esto le permite ajustar el rendimiento del control en esta situación.  
  
 El <xref:System.Windows.Forms.DataGridView> control proporciona varios eventos que puede controlar para interactuar con un almacén de datos personalizado. En este tutorial le guiará a través del proceso de implementación de estos controladores de eventos. El ejemplo de código en este tema usa un origen de datos muy sencillo con fines meramente ilustrativos. En una configuración de producción, normalmente se cargará solo las filas que se debe mostrar en una memoria caché y controlar <xref:System.Windows.Forms.DataGridView> eventos e interactuar con actualizar la memoria caché. Para obtener más información, consulte [implementar el modo Virtual con la carga de datos Just In Time en el DataGridView Control de formularios de Windows](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
  
 Para copiar el código de este tema como una sola lista, vea [Cómo: Implementar el modo Virtual en el Windows Forms DataGridView Control](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).  
  
## <a name="creating-the-form"></a>Crear el formulario  
  
#### <a name="to-implement-virtual-mode"></a>Para implementar el modo virtual  
  
1. Cree una clase que deriva de <xref:System.Windows.Forms.Form> y contiene un <xref:System.Windows.Forms.DataGridView> control.  
  
     El siguiente código contiene alguna inicialización básica. Declara algunas variables que se usará en pasos posteriores, se proporciona un `Main` método y proporciona un diseño de forma sencilla en el constructor de clase.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#001)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#001)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#001)]  
    [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#002)]
    [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#002)]
    [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#002)]  
  
2. Implementar un controlador para el formulario <xref:System.Windows.Forms.Form.Load> eventos que inicializa el <xref:System.Windows.Forms.DataGridView> controlar y rellena el almacén de datos con valores de ejemplo.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#110)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#110)]  
  
3. Implementar un controlador para el <xref:System.Windows.Forms.DataGridView.CellValueNeeded> eventos que recupera el valor de celda solicitado desde el almacén de datos o el `Customer` objeto actualmente en la edición.  
  
     Este evento se produce siempre que el <xref:System.Windows.Forms.DataGridView> control necesita dibujar una celda.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#120)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#120)]  
  
4. Implementar un controlador para el <xref:System.Windows.Forms.DataGridView.CellValuePushed> eventos que almacena un valor de celda modificada en el `Customer` objeto que representa la fila editada. Este evento se produce cada vez que el usuario confirma un cambio del valor de celda.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#130)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#130)]  
  
5. Implementar un controlador para el <xref:System.Windows.Forms.DataGridView.NewRowNeeded> eventos que crea un nuevo `Customer` objeto que representa una fila recién creada.  
  
     Este evento se produce cada vez que el usuario escribe la fila para los nuevos registros.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#140)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#140)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#140)]  
  
6. Implementar un controlador para el <xref:System.Windows.Forms.DataGridView.RowValidated> eventos que guarda filas nuevas o modificadas en el almacén de datos.  
  
     Este evento se produce cuando el usuario cambia la fila actual.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#150)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#150)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#150)]  
  
7. Implementar un controlador para el <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> evento que indica si el <xref:System.Windows.Forms.DataGridView.CancelRowEdit> se producirá un evento cuando el usuario señala la reversión de la fila, presione ESC dos veces en modo de edición o una vez fuera del modo de edición.  
  
     De forma predeterminada, <xref:System.Windows.Forms.DataGridView.CancelRowEdit> se produce al crear una nueva versión de fila cuando se han modificado las celdas de la fila actual a menos que el <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> propiedad está establecida en `true` en el <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> controlador de eventos. Este evento es útil cuando el ámbito de confirmación se determina en tiempo de ejecución.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#160)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#160)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#160)]  
  
8. Implementar un controlador para el <xref:System.Windows.Forms.DataGridView.CancelRowEdit> eventos que descartan los valores de la `Customer` objeto que representa la fila actual.  
  
     Este evento se produce cuando el usuario señala la reversión de la fila, presione ESC dos veces en modo de edición o una vez fuera del modo de edición. Este evento no se produce si no hay ninguna celda en la fila actual se han modificado o si el valor de la <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> se ha establecido la propiedad en `false` en un <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> controlador de eventos.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#170)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#170)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#170)]  
  
9. Implementar un controlador para el <xref:System.Windows.Forms.DataGridView.UserDeletingRow> eventos que se eliminan una existente `Customer` objeto desde el almacén de datos o un no guardados se perderán `Customer` objeto que representa una fila recién creada.  
  
     Este evento se produce cada vez que el usuario elimina una fila haciendo clic en un encabezado de fila y presione la tecla SUPR.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#180)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#180)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#180)]  
  
10. Implementar una sencilla `Customers` clase para representar los elementos de datos utilizados en este ejemplo de código.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#200)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#200)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#200)]  
  
## <a name="testing-the-application"></a>Probar la aplicación  
 Puede comprobar el formulario para asegurarse de que se comporta de la forma prevista.  
  
#### <a name="to-test-the-form"></a>Para comprobar el formulario  
  
-   Compile y ejecute la aplicación.  
  
     Verá un <xref:System.Windows.Forms.DataGridView> rellenado con tres registros de cliente del control. Puede modificar los valores de varias celdas en una fila y presione ESC dos veces en modo de edición y una vez fuera del modo de edición para revertir toda la fila a sus valores originales. Al modificar, agregar o eliminar filas en el control, `Customer` objetos en el almacén de datos se puede modificar, se agregan o se eliminan también.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Esta aplicación le ofrece un conocimiento básico de los eventos que se debe controlar para implementar el modo virtual en el <xref:System.Windows.Forms.DataGridView> control. Puede mejorar esta aplicación básica de varias maneras:  
  
-   Implementar un almacén de datos que almacena en caché los valores de una base de datos externo. La memoria caché debe recuperar y descartar los valores según sea necesario para que solo contiene lo que es necesario para su presentación y consume una pequeña cantidad de memoria en el equipo cliente.  
  
-   Ajustar el rendimiento del almacén de datos según sus requisitos. Por ejemplo, podría desea compensar para conexiones de red lentas, en lugar de las limitaciones de memoria del equipo cliente utilizando un tamaño de caché mayor y minimizar el número de consultas de base de datos.  
  
 Para obtener más información sobre almacenamiento en caché los valores de una base de datos externo, vea [Cómo: Implementar el modo Virtual con la carga de datos Just-In-Time en el Windows Forms DataGridView Control](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).  
  
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
- [Cómo: Implementar el modo Virtual en el Control DataGridView de formularios de Windows](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)
