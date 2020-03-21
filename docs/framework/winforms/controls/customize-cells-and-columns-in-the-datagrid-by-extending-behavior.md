---
title: Personalizar celdas y columnas en DataGridView Control ampliando su comportamiento y apariencia
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], cell customization
- columns [Windows Forms], customizing in DataGridView control
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 9b7dc7b6-5ce6-4566-9949-902f74f17a81
ms.openlocfilehash: e111f0bce812fc0851fabd1fde0fc2a6d44dd25f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182394"
---
# <a name="how-to-customize-cells-and-columns-in-the-windows-forms-datagridview-control-by-extending-their-behavior-and-appearance"></a>Cómo: Personalizar celdas y columnas en el control DataGridView de formularios Windows Forms ampliando su comportamiento y apariencia
El control <xref:System.Windows.Forms.DataGridView> ofrece varias maneras de personalizar su apariencia y comportamiento mediante propiedades, eventos y clases complementarias. Ocasionalmente podría tener requisitos para sus celdas que van más allá de lo que pueden proporcionar estas características. Puede crear su propia clase <xref:System.Windows.Forms.DataGridViewCell> personalizado para proporcionar una funcionalidad ampliada.  
  
 Puede crear una clase <xref:System.Windows.Forms.DataGridViewCell> derivando de la clase base <xref:System.Windows.Forms.DataGridViewCell> o de una de sus clases derivadas. Aunque puede mostrar cualquier tipo de celda en cualquier tipo de columna, normalmente también creará una clase <xref:System.Windows.Forms.DataGridViewColumn> personalizado especializada para mostrar el tipo de celda. Las clases de columna derivan de <xref:System.Windows.Forms.DataGridViewColumn> o de uno de sus tipos derivados.  
  
 En el ejemplo de código siguiente, creará una clase de celda personalizada llamada `DataGridViewRolloverCell` que detecta cuándo el mouse entra y sale de los límites de la celda. Mientras el mouse está dentro de los límites de la celda, se dibuja un rectángulo de bajorrelieve. Este nuevo tipo deriva de <xref:System.Windows.Forms.DataGridViewTextBoxCell> y se comporta en todos los demás aspectos como su clase base. La clase de columna complementaria se llama `DataGridViewRolloverColumn`.  
  
 Para usar estas clases, cree un formulario que contenga un control <xref:System.Windows.Forms.DataGridView>, agregue uno o varios objetos `DataGridViewRolloverColumn` a la colección <xref:System.Windows.Forms.DataGridView.Columns%2A> y rellene el control con filas que contengan valores.  
  
> [!NOTE]
> Este ejemplo no funcionará correctamente si agrega filas vacías. Se crean filas vacías, por ejemplo, cuando se agregan filas al control estableciendo la propiedad <xref:System.Windows.Forms.DataGridView.RowCount%2A>. Esto se debe a que las filas agregadas en este caso se comparten automáticamente, lo que significa que no se crean instancias de los objetos `DataGridViewRolloverCell` hasta que haga clic en cada celda individual, y esto hace que las filas asociadas dejan de estar compartidas.  
  
 Como este tipo de personalización de celda requiere filas no compartidas, no es adecuado para su uso con grandes conjuntos de datos. Para obtener más información sobre el uso compartido de filas, vea [Prácticas recomendadas para escalar el control DataGridView de formularios Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
> [!NOTE]
> Al derivar de <xref:System.Windows.Forms.DataGridViewCell> o <xref:System.Windows.Forms.DataGridViewColumn> y agregar nuevas propiedades a la clase derivada, asegúrese de invalidar el método `Clone` para copiar las nuevas propiedades durante las operaciones de clonación. También debe llamar al método `Clone` de la clase base para copiar las propiedades de la clase base a la nueva celda o columna.  
  
### <a name="to-customize-cells-and-columns-in-the-datagridview-control"></a>Para personalizar las celdas y columnas del control DataGridView  
  
1. Derive una nueva clase de celda, llamada `DataGridViewRolloverCell`, del tipo <xref:System.Windows.Forms.DataGridViewTextBoxCell>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#201](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#201)]
     [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#201](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#201)]  
    [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#202](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#202)]
    [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#202](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#202)]  
  
2. Invalide el método <xref:System.Windows.Forms.DataGridViewTextBoxCell.Paint%2A> en la clase `DataGridViewRolloverCell` . En la invalidación, llame primero a la implementación de la clase base, que controla la funcionalidad del cuadro de texto hospedado. Después, use el método <xref:System.Windows.Forms.Control.PointToClient%2A> del control para transformar la posición del cursor (en coordenadas de pantalla) en las coordenadas de área de cliente de <xref:System.Windows.Forms.DataGridView>. Si las coordenadas del mouse se encuentran dentro de los límites de la celda, dibuje el rectángulo de bajorrelieve.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#210](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#210)]
     [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#210](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#210)]  
  
3. Invalide los métodos <xref:System.Windows.Forms.DataGridViewCell.OnMouseEnter%2A> y <xref:System.Windows.Forms.DataGridViewCell.OnMouseLeave%2A> en la clase `DataGridViewRolloverCell` para forzar que las celdas se vuelvan a dibujar cuando el puntero del mouse entre o salga de ellas.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#220](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#220)]
     [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#220](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#220)]  
  
4. Derive una nueva clase, llamada `DataGridViewRolloverCellColumn`, del tipo <xref:System.Windows.Forms.DataGridViewColumn>. En el constructor, asigne un nuevo objeto `DataGridViewRolloverCell` a su propiedad <xref:System.Windows.Forms.DataGridViewColumn.CellTemplate%2A>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#300](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#300)]
     [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#300](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#300)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código completo se incluye un pequeño formulario de prueba que muestra el comportamiento del tipo de celda personalizado.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#000)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Referencias a los ensamblados System, System.Windows.Forms y System.Drawing.  

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCell>
- <xref:System.Windows.Forms.DataGridViewColumn>
- [Personalizar el control DataGridView de formularios Windows Forms](customizing-the-windows-forms-datagridview-control.md)
- [Arquitectura del control DataGridView](datagridview-control-architecture-windows-forms.md)
- [Tipos de columnas en el control DataGridView de formularios Windows Forms](column-types-in-the-windows-forms-datagridview-control.md)
- [Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
