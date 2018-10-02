---
title: 'Cómo: Garantizar que la fila seleccionada de una tabla secundaria conserva la posición correcta'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- master-details view
- row position [Windows Forms]
- parent/child view [Windows Forms]
- resetting child position
- data binding [.NET Framework], row selection
- caching [.NET Framework], child position
- child position
- master/details view [Windows Forms]
- child tables row selection
- current child position
ms.assetid: c5fa2562-43a4-46fa-a604-52d8526a87bd
ms.openlocfilehash: e1fdb007451c157e60a1ad723b5d2d06bc85ecdf
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48037085"
---
# <a name="how-to-ensure-the-selected-row-in-a-child-table-remains-at-the-correct-position"></a>Cómo: Garantizar que la fila seleccionada de una tabla secundaria conserva la posición correcta
A menudo, cuando se trabaja con enlace de datos en Windows Forms, los datos se muestran en lo que se denomina una vista primaria/secundaria o una vista maestra/detalles. Esto hace referencia a un escenario de enlace de datos donde los datos del mismo origen se muestran en dos controles. Al cambiar la selección en un control, los datos mostrados en el segundo control cambiarán. Por ejemplo, el primer control puede contener una lista de clientes y el segundo de una lista de pedidos relacionados con el cliente seleccionado en el primer control.  
  
 A partir de .NET Framework versión 2.0, cuando se muestran datos en una vista primaria/secundaria, quizás tenga que realizar algunos pasos adicionales para asegurarse de que la fila seleccionada actualmente en la tabla secundaria no se restablece a la primera fila de la tabla. Para ello, tendrá que almacenar en caché la posición de la tabla secundaria y restablecerla después de que cambie la tabla primaria. Normalmente, el restablecimiento del elemento secundario se produce la primera vez que cambia un campo en una fila de la tabla primaria.  
  
### <a name="to-cache-the-current-child-position"></a>Para almacenar en caché la posición secundaria actual  
  
1.  Declare una variable entera para almacenar la posición de lista secundaria y una variable booleana para almacenar en caché la posición secundaria.  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#4)]  
  
2.  Controle el evento <xref:System.Windows.Forms.CurrencyManager.ListChanged> del <xref:System.Windows.Forms.CurrencyManager> del enlace y busque un <xref:System.ComponentModel.ListChangedType> de <xref:System.ComponentModel.ListChangedType.Reset>.  
  
3.  Compruebe la posición actual del <xref:System.Windows.Forms.CurrencyManager>. Si es mayor que la primera entrada de la lista (normalmente 0), guárdela en una variable.  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#2)]  
  
4.  Controle el evento <xref:System.Windows.Forms.BindingManagerBase.CurrentChanged> de la lista primaria para el administrador de moneda principal. En el controlador, establezca el valor booleano para indicar que no es un escenario de almacenamiento en caché. Si se produce <xref:System.Windows.Forms.BindingManagerBase.CurrentChanged>, el cambio en el elemento primario es un cambio de posición de lista y no un cambio de valor del elemento.  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#5)]  
  
### <a name="to-reset-the-child-position"></a>Para restablecer la posición secundaria  
  
1.  Controle el evento <xref:System.Windows.Forms.BindingManagerBase.PositionChanged> del <xref:System.Windows.Forms.CurrencyManager> del enlace secundario.  
  
2.  Restablezca la posición de la tabla secundaria a la posición almacenada en caché que se guardó en el procedimiento anterior.  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#3)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo guardar la posición actual en el <xref:System.Windows.Forms.CurrencyManager> para una tabla secundaria y cómo restablecer la posición de una vez completada una modificación en la tabla primaria. Este ejemplo contiene dos controles <xref:System.Windows.Forms.DataGridView> enlazados a dos tablas en un <xref:System.Data.DataSet> mediante el componente <xref:System.Windows.Forms.BindingSource>. Se establece una relación entre las dos tablas y la relación se agrega al <xref:System.Data.DataSet>. La posición en la tabla secundaria se establece inicialmente en la tercera fila para fines de demostración.  
  
 [!code-csharp[System.Windows.Forms.CurrencyManagerReset#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.CurrencyManagerReset#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#1)]  
  
 Para probar el ejemplo de código, realice los pasos siguientes:  
  
1.  Ejecute el ejemplo.  
  
2.  Asegúrese de que la casilla **Cache and reset position** está activada.  
  
3.  Haga clic en el botón **Clear parent field** para producir un cambio en un campo de la tabla primaria. Observe que la fila seleccionada en la tabla secundaria no cambia.  
  
4.  Cierre y vuelva a ejecutar el ejemplo. Deberá hacerlo porque el restablecimiento solo se produce en el primer cambio de la fila primaria.  
  
5.  Desactive la casilla **Cache and reset position**.  
  
6.  Haga clic en el botón **Clear parent field**. Observe que la fila seleccionada en la tabla secundaria cambia a la primera fila.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System, System.Data, System.Drawing, System.Windows.Forms y System.XML.  
  
 Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [compilación de línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.  Vea también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Vea también  
 [Garantizar que varios controles enlazados al mismo origen de datos permanezcan sincronizados](../../../docs/framework/winforms/multiple-controls-bound-to-data-source-synchronized.md)  
 [Componente BindingSource](../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [Enlace de datos y Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)
