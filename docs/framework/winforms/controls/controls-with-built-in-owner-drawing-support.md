---
title: Controles compatibles con dibujos propietarios integrados
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drawing [Windows Forms], owner
- drawing [Windows Forms], custom
- controls [Windows Forms], changing appearance
- custom drawing
- owner drawing
ms.assetid: 3823d01e-9610-43e6-864d-99f9b7c2b351
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: efd297dcc11005d6b6d47bb9ce3853a757046e8f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="controls-with-built-in-owner-drawing-support"></a>Controles compatibles con dibujos propietarios integrados
Los dibujos propietarios en formularios Windows Forms, que también se conocen como dibujos personalizados, es una técnica para cambiar la apariencia visual de determinados controles.  
  
> [!NOTE]
>  La palabra "control" en este tema se utiliza para indicar que las clases que derivan de <xref:System.Windows.Forms.Control> o <xref:System.ComponentModel.Component>.  
  
 Normalmente, Windows controla el dibujo automáticamente mediante la configuración de la propiedad como <xref:System.Windows.Forms.Control.BackColor%2A> para determinar la apariencia de un control. Con el dibujo del propietario, toma el control sobre el proceso de dibujo, con lo que puede cambiar los elementos de apariencia que no están disponibles mediante las propiedades. Por ejemplo, muchos controles le permiten establecer el color del texto que se muestra, pero está limitado a un único color. El dibujo del propietario le permite realizar tareas como mostrar una parte del texto en negro y otra en rojo.  
  
 En la práctica, el dibujo del propietario es similar a dibujar gráficos en un formulario. Por ejemplo, podría utilizar métodos de gráficos en un controlador para el formulario <xref:System.Windows.Forms.Control.Paint> eventos para emular un `ListBox` control, pero se tendría que escribir su propio código para controlar toda la interacción del usuario. Con el dibujo del propietario, el control utiliza su código para dibujar el contenido, pero por lo demás conserva todas sus funciones intrínsecas. Puede utilizar métodos gráficos para dibujar cada elemento en el control o personalizar algunos aspectos de cada elemento mientras utiliza la apariencia predeterminada para otros aspectos de cada elemento.  
  
## <a name="owner-drawing-in-windows-forms-controls"></a>Dibujo del propietario en controles de formularios Windows Forms  
 Para realizar el dibujo propietario en controles compatibles, normalmente establece una propiedad y controla uno o más eventos.  
  
 La mayoría de los controles que admiten el dibujo del propietario tienen una propiedad `OwnerDraw` o `DrawMode` que indica si el control generará eventos relacionados con el dibujo cuando se pinta a sí mismo.  
  
 Los controles que no tienen una propiedad `OwnerDraw` o `DrawMode` incluyen el control `DataGridView`, que proporciona eventos de dibujo que se producen automáticamente, y el control `ToolStrip`, que se dibuja utilizando una clase de representación externa que tiene sus propios eventos relacionados con el dibujo.  
  
 Hay muchos tipos diferentes de eventos de dibujo, pero se produce un evento de dibujo típico con el fin de dibujar un solo elemento dentro de un control. El controlador de eventos recibe un objeto `EventArgs` que contiene información sobre el elemento que se va a dibujar y herramientas que puede utilizar para dibujarlo. Por ejemplo, este objeto suele contener el número de índice del elemento en la colección primaria, un <xref:System.Drawing.Rectangle> que indica el elemento Mostrar límites y un <xref:System.Drawing.Graphics> objeto para llamar a métodos de paint. En algunos eventos, el objeto `EventArgs` proporciona información adicional sobre el elemento y los métodos que puede llamar para dibujar algunos aspectos del elemento de forma predeterminada, como el fondo o un rectángulo de enfoque.  
  
 Para crear un control reutilizable que contenga sus personalizaciones para dibujo del propietario, cree una nueva clase que derive de una clase de control que admita el dibujo del propietario. En lugar de controlar eventos de dibujo, incluya el código de dibujo del propietario en invalidaciones para el método o los métodos `On`*EventName* de la clase nueva. Asegúrese de llamar al método o los métodos `On`*EventName* de la clase base en este caso para que los usuarios de su control puedan controlar eventos del dibujo del propietario y proporcionar una personalización adicional.  
  
 Los siguientes controles de formularios Windows Forms son compatibles con el dibujo del propietario en todas las versiones de .NET Framework:  
  
-   <xref:System.Windows.Forms.ListBox>  
  
-   <xref:System.Windows.Forms.ComboBox>  
  
-   <xref:System.Windows.Forms.MenuItem>(usa <xref:System.Windows.Forms.MainMenu> y <xref:System.Windows.Forms.ContextMenu>)  
  
-   <xref:System.Windows.Forms.TabControl>  
  
 Los controles siguientes son compatibles solamente con el dibujo del propietario en [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]:  
  
-   <xref:System.Windows.Forms.ToolTip>  
  
-   <xref:System.Windows.Forms.ListView>  
  
-   <xref:System.Windows.Forms.TreeView>  
  
 Los controles siguientes son compatibles con el dibujo del propietario y son nuevos en [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]:  
  
-   <xref:System.Windows.Forms.DataGridView>  
  
-   <xref:System.Windows.Forms.ToolStrip>  
  
 Las secciones siguientes ofrecen detalles adicionales para cada uno de estos controles.  
  
### <a name="listbox-and-combobox-controls"></a>Controles ListBox y ComboBox  
 El <xref:System.Windows.Forms.ListBox> y <xref:System.Windows.Forms.ComboBox> controles le permiten dibujar elementos individuales en el control en un tamaño, o en diferentes tamaños.  
  
> [!NOTE]
>  Aunque la <xref:System.Windows.Forms.CheckedListBox> control se deriva de la <xref:System.Windows.Forms.ListBox> (control), no admite dibujo del propietario.  
  
 Para dibujar cada elemento del mismo tamaño, establezca la `DrawMode` propiedad <xref:System.Windows.Forms.DrawMode.OwnerDrawFixed> y controlar la `DrawItem` eventos.  
  
 Para dibujar cada elemento con un tamaño distinto, establezca la `DrawMode` propiedad <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable> y controlar tanto la `MeasureItem` y `DrawItem` eventos. El evento `MeasureItem` le permite indicar el tamaño de un elemento antes de que se produzca el evento `DrawItem` para ese elemento.  
  
 Para obtener más información, incluidos los ejemplos de código, consulte los temas siguientes:  
  
-   <xref:System.Windows.Forms.ListBox.DrawMode%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListBox.MeasureItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListBox.DrawItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ComboBox.DrawMode%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ComboBox.MeasureItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ComboBox.DrawItem?displayProperty=nameWithType>  
  
-   [Procedimiento para crear texto de tamaño variable en un control ComboBox](../../../../docs/framework/winforms/controls/how-to-create-variable-sized-text-in-a-combobox-control.md)  
  
### <a name="menuitem-component"></a>Componente MenuItem  
 El <xref:System.Windows.Forms.MenuItem> componente representa un solo elemento de menú en un <xref:System.Windows.Forms.MainMenu> o <xref:System.Windows.Forms.ContextMenu> componente.  
  
 Para dibujar un <xref:System.Windows.Forms.MenuItem>, establezca su `OwnerDraw` propiedad `true` y controlar su `DrawItem` eventos. Para personalizar el tamaño del elemento de menú antes de que se produzca el evento `DrawItem`, controle el evento `MeasureItem` del elemento.  
  
 Para obtener más información, incluidos los ejemplos de código, consulte los temas de consulta siguientes:  
  
-   <xref:System.Windows.Forms.MenuItem.OwnerDraw%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.MenuItem.DrawItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.MenuItem.MeasureItem?displayProperty=nameWithType>  
  
### <a name="tabcontrol-control"></a>TabControl (Control)  
 El <xref:System.Windows.Forms.TabControl> control permite dibujar fichas individuales en el control. Dibujo del propietario afecta a sólo las fichas; el <xref:System.Windows.Forms.TabPage> no afecta al contenido.  
  
 Para dibujar cada ficha un <xref:System.Windows.Forms.TabControl>, establezca el `DrawMode` propiedad <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed> y controlar la `DrawItem` eventos. Este evento se produce una vez para cada pestaña solo cuando la pestaña está visible en el control.  
  
 Para obtener más información, incluidos los ejemplos de código, consulte los temas de consulta siguientes:  
  
-   <xref:System.Windows.Forms.TabControl.DrawMode%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.TabControl.DrawItem?displayProperty=nameWithType>  
  
### <a name="tooltip-component"></a>ToolTip  
 El <xref:System.Windows.Forms.ToolTip> componente permite dibujar la información sobre herramientas completa cuando se muestre.  
  
 Para dibujar un <xref:System.Windows.Forms.ToolTip>, establezca su `OwnerDraw` propiedad `true` y controlar su `Draw` eventos. Para personalizar el tamaño de la <xref:System.Windows.Forms.ToolTip> antes de la `Draw` se produce el evento, controlar el `Popup` eventos y establezca la <xref:System.Windows.Forms.PopupEventArgs.ToolTipSize%2A> propiedad en el controlador de eventos.  
  
 Para obtener más información, incluidos los ejemplos de código, consulte los temas de consulta siguientes:  
  
-   <xref:System.Windows.Forms.ToolTip.OwnerDraw%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ToolTip.Draw?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ToolTip.Popup?displayProperty=nameWithType>  
  
### <a name="listview-control"></a>Control ListView  
 El <xref:System.Windows.Forms.ListView> control permite dibujar elementos individuales, subelementos y encabezados de columna en el control.  
  
 Para habilitar el dibujo propietario en el control, establezca la propiedad `OwnerDraw` en `true`.  
  
 Para dibujar cada elemento en el control, controle el evento `DrawItem`.  
  
 Para dibujar cada subelemento o encabezado de columna en el control cuando el <xref:System.Windows.Forms.ListView.View%2A> propiedad está establecida en <xref:System.Windows.Forms.View.Details>, controlar el `DrawSubItem` y `DrawColumnHeader` eventos.  
  
 Para obtener más información, incluidos los ejemplos de código, consulte los temas de consulta siguientes:  
  
-   <xref:System.Windows.Forms.ListView.OwnerDraw%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListView.DrawItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListView.DrawSubItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListView.DrawColumnHeader?displayProperty=nameWithType>  
  
### <a name="treeview-control"></a>TreeView (Control)  
 El <xref:System.Windows.Forms.TreeView> control permite dibujar nodos individuales en el control.  
  
 Para dibujar sólo el texto mostrado en cada nodo, establezca la `DrawMode` propiedad <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawText> y controlar la `DrawNode` eventos para dibujar el texto.  
  
 Para dibujar todos los elementos de cada nodo, establezca la `DrawMode` propiedad <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawAll> y controlar la `DrawNode` eventos para dibujar cualquier elemento que necesite, como texto, iconos, casillas, signos más y menos y las líneas que conectan los nodos.  
  
 Para obtener más información, incluidos los ejemplos de código, consulte los temas de consulta siguientes:  
  
-   <xref:System.Windows.Forms.TreeView.DrawMode%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.TreeView.DrawNode?displayProperty=nameWithType>  
  
### <a name="datagridview-control"></a>Control DataGridView  
 El <xref:System.Windows.Forms.DataGridView> control permite dibujar celdas y filas individuales en el control.  
  
 Para dibujar celdas individuales, controle el evento `CellPainting`.  
  
 Para dibujar filas o elementos de filas, controle uno o ambos eventos `RowPrePaint` y `RowPostPaint`. El evento `RowPrePaint` se produce antes de que se dibujen las celdas en una fila, y el evento `RowPostPaint` se produce después de dibujar las celdas. Puede controlar ambos eventos y el evento `CellPainting` para pintar el fondo de una fila, celdas individuales y el primer plano de una fila por separado, o bien puede proporcionar personalizaciones específicas donde las necesite y usar la vista predeterminada para otros elementos de la fila.  
  
 Para obtener más información, incluidos los ejemplos de código, consulte los temas siguientes:  
  
-   <xref:System.Windows.Forms.DataGridView.CellPainting>  
  
-   <xref:System.Windows.Forms.DataGridView.RowPrePaint>  
  
-   <xref:System.Windows.Forms.DataGridView.RowPostPaint>  
  
-   [Procedimiento para personalizar la apariencia de las celdas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md)  
  
-   [Procedimiento para personalizar la apariencia de las filas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md)  
  
### <a name="toolstrip-control"></a>ToolStrip  
 <xref:System.Windows.Forms.ToolStrip>y los controles derivados le permiten personalizar cualquier aspecto de su apariencia.  
  
 Para proporcionar una representación personalizada para <xref:System.Windows.Forms.ToolStrip> controles, establecer el `Renderer` propiedad de un <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripManager>, <xref:System.Windows.Forms.ToolStripPanel>, o <xref:System.Windows.Forms.ToolStripContentPanel> a una `ToolStripRenderer` de objetos y administrar uno o varios de los diversos eventos de dibujo proporcionados por el `ToolStripRenderer` clase. Por otra parte, defina un `Renderer` propiedad a una instancia de su propia clase derivada de `ToolStripRenderer`, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>, o <xref:System.Windows.Forms.ToolStripSystemRenderer> que implementa o invalida específico `On` *EventName* métodos.  
  
 Para obtener más información, incluidos los ejemplos de código, consulte los temas siguientes:  
  
-   <xref:System.Windows.Forms.ToolStripRenderer>  
  
-   [Procedimiento para crear y establecer un representador personalizado para el control ToolStrip de formularios Windows Forms](../../../../docs/framework/winforms/controls/create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md)  
  
-   [Procedimiento para dibujar un control ToolStrip de manera personalizada](../../../../docs/framework/winforms/controls/how-to-custom-draw-a-toolstrip-control.md)  
  
## <a name="see-also"></a>Vea también  
 [Controles que se utilizan en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
