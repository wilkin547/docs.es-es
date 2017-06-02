---
title: "C&#243;mo: Personalizar celdas y columnas en el control DataGridView de formularios Windows Forms ampliando su comportamiento y apariencia | Microsoft Docs"
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
  - "celdas, personalizar en el control DataGridView"
  - "columnas [Windows Forms], personalizar en el control DataGridView"
  - "DataGridView (control) [Windows Forms], personalización de celdas"
ms.assetid: 9b7dc7b6-5ce6-4566-9949-902f74f17a81
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# C&#243;mo: Personalizar celdas y columnas en el control DataGridView de formularios Windows Forms ampliando su comportamiento y apariencia
El control <xref:System.Windows.Forms.DataGridView> ofrece varias maneras de personalizar su apariencia y comportamiento mediante propiedades, eventos y clases complementarias.  Ocasionalmente podría tener requisitos para sus celdas que van más allá de lo que pueden proporcionar estas características.  Puede crear su propia clase <xref:System.Windows.Forms.DataGridViewCell> personalizado para proporcionar una funcionalidad ampliada.  
  
 Puede crear una clase <xref:System.Windows.Forms.DataGridViewCell> derivando de la clase base <xref:System.Windows.Forms.DataGridViewCell> o de una de sus clases derivadas.  Aunque puede mostrar cualquier tipo de celda en cualquier tipo de columna, normalmente también creará una clase <xref:System.Windows.Forms.DataGridViewColumn> personalizado especializada para mostrar el tipo de celda.  Las clases de columna derivan de <xref:System.Windows.Forms.DataGridViewColumn> o de uno de sus tipos derivados.  
  
 En el ejemplo de código siguiente, creará una clase de celda personalizada llamada `DataGridViewRolloverCell` que detecta cuándo el mouse entra y sale de los límites de la celda.  Mientras el mouse está dentro de los límites de la celda, se dibuja un rectángulo de bajorrelieve.  Este nuevo tipo deriva de <xref:System.Windows.Forms.DataGridViewTextBoxCell> y se comporta en todos los demás aspectos como su clase base.  La clase de columna complementaria se llama `DataGridViewRolloverColumn`.  
  
 Para usar estas clases, cree un formulario que contenga un control <xref:System.Windows.Forms.DataGridView>, agregue uno o varios objetos `DataGridViewRolloverColumn` a la colección <xref:System.Windows.Forms.DataGridView.Columns%2A> y rellene el control con filas que contengan valores.  
  
> [!NOTE]
>  Este ejemplo no funcionará correctamente si agrega filas vacías.  Se crean filas vacías, por ejemplo, cuando se agregan filas al control estableciendo la propiedad <xref:System.Windows.Forms.DataGridView.RowCount%2A>.  Esto se debe a que las filas agregadas en este caso se comparten automáticamente, lo que significa que no se crean instancias de los objetos `DataGridViewRolloverCell` hasta que haga clic en cada celda individual, y esto hace que las filas asociadas dejan de estar compartidas.  
  
 Como este tipo de personalización de celda requiere filas no compartidas, no es adecuado para su uso con grandes conjuntos de datos.  Para obtener más información sobre cómo compartir filas, consulte [Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
> [!NOTE]
>  Al derivar de <xref:System.Windows.Forms.DataGridViewCell> o <xref:System.Windows.Forms.DataGridViewColumn> y agregar nuevas propiedades a la clase derivada, asegúrese de invalidar el método `Clone` para copiar las nuevas propiedades durante las operaciones de clonación.  También debe llamar al método `Clone` de la clase base para copiar las propiedades de la clase base a la nueva celda o columna.  
  
### Para personalizar las celdas y columnas del control DataGridView  
  
1.  Derive una nueva clase de celda, llamada `DataGridViewRolloverCell`, del tipo <xref:System.Windows.Forms.DataGridViewTextBoxCell>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#201](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#201)]
     [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#201](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#201)]  
    [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#202](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#202)]
    [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#202](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#202)]  
  
2.  Invalide el método <xref:System.Windows.Forms.DataGridViewTextBoxCell.Paint%2A> en la clase `DataGridViewRolloverCell`.  En la invalidación, llame primero a la implementación de la clase base, que controla la funcionalidad del cuadro de texto hospedado.  Después, use el método <xref:System.Windows.Forms.Control.PointToClient%2A> del control para transformar la posición del cursor \(en coordenadas de pantalla\) en las coordenadas de área de cliente de <xref:System.Windows.Forms.DataGridView>.  Si las coordenadas del mouse se encuentran dentro de los límites de la celda, dibuje el rectángulo de bajorrelieve.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#210](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#210)]
     [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#210](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#210)]  
  
3.  Invalide los métodos <xref:System.Windows.Forms.DataGridViewCell.OnMouseEnter%2A> y <xref:System.Windows.Forms.DataGridViewCell.OnMouseLeave%2A> en la clase `DataGridViewRolloverCell` para forzar que las celdas se vuelvan a dibujar cuando el puntero del mouse entre o salga de ellas.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#220](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#220)]
     [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#220](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#220)]  
  
4.  Derive una nueva clase, llamada `DataGridViewRolloverCellColumn`, del tipo <xref:System.Windows.Forms.DataGridViewColumn>.  En el constructor, asigne un nuevo objeto `DataGridViewRolloverCell` a su propiedad <xref:System.Windows.Forms.DataGridViewColumn.CellTemplate%2A>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#300](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#300)]
     [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#300](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#300)]  
  
## Ejemplo  
 En el ejemplo de código completo se incluye un pequeño formulario de prueba que muestra el comportamiento del tipo de celda personalizado.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewRolloverCell#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/CS/rollovercell.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewRolloverCell#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRolloverCell/VB/rollovercell.vb#000)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System, System.Windows.Forms y System.Drawing.  
  
 Para obtener información acerca de cómo compilar este ejemplo desde la línea de comandos para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [Compilar desde la línea de comandos](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) o [Compilar la línea de comandos con csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  También puede compilar este ejemplo en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] pegando el código en un nuevo proyecto.  Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228%20\(v=vs.110\)).  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewCell>   
 <xref:System.Windows.Forms.DataGridViewColumn>   
 [Personalizar el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)   
 [Arquitectura del control DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)   
 [Tipos de columnas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)   
 [Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)