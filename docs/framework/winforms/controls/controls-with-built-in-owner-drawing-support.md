---
title: Controles compatibles con dibujos propietarios integrados
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [Windows Forms], owner
- drawing [Windows Forms], custom
- controls [Windows Forms], changing appearance
- custom drawing
- owner drawing
ms.assetid: 3823d01e-9610-43e6-864d-99f9b7c2b351
ms.openlocfilehash: f0d4b99f9ee0134fc7334a941dd5ef4fd7ba3df3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930195"
---
# <a name="controls-with-built-in-owner-drawing-support"></a>Controles compatibles con dibujos propietarios integrados
Los dibujos propietarios en formularios Windows Forms, que también se conocen como dibujos personalizados, es una técnica para cambiar la apariencia visual de determinados controles.  
  
> [!NOTE]
> La palabra "control" de este tema se usa para hacer referencia a las clases que <xref:System.Windows.Forms.Control> derivan de o <xref:System.ComponentModel.Component>.  
  
 Normalmente, Windows controla el dibujo automático mediante la configuración de propiedades <xref:System.Windows.Forms.Control.BackColor%2A> como para determinar la apariencia de un control. Con el dibujo del propietario, toma el control sobre el proceso de dibujo, con lo que puede cambiar los elementos de apariencia que no están disponibles mediante las propiedades. Por ejemplo, muchos controles le permiten establecer el color del texto que se muestra, pero está limitado a un único color. El dibujo del propietario le permite realizar tareas como mostrar una parte del texto en negro y otra en rojo.  
  
 En la práctica, el dibujo del propietario es similar a dibujar gráficos en un formulario. Por ejemplo, podría utilizar métodos gráficos en un controlador para que el evento del <xref:System.Windows.Forms.Control.Paint> formulario eMule un `ListBox` control, pero tendría que escribir su propio código para controlar toda la interacción del usuario. Con el dibujo del propietario, el control utiliza su código para dibujar el contenido, pero por lo demás conserva todas sus funciones intrínsecas. Puede utilizar métodos gráficos para dibujar cada elemento en el control o personalizar algunos aspectos de cada elemento mientras utiliza la apariencia predeterminada para otros aspectos de cada elemento.  
  
## <a name="owner-drawing-in-windows-forms-controls"></a>Dibujo del propietario en controles de formularios Windows Forms  
 Para realizar el dibujo propietario en controles compatibles, normalmente establece una propiedad y controla uno o más eventos.  
  
 La mayoría de los controles que admiten el dibujo del propietario tienen una propiedad `OwnerDraw` o `DrawMode` que indica si el control generará eventos relacionados con el dibujo cuando se pinta a sí mismo.  
  
 Los controles que no tienen una propiedad `OwnerDraw` o `DrawMode` incluyen el control `DataGridView`, que proporciona eventos de dibujo que se producen automáticamente, y el control `ToolStrip`, que se dibuja utilizando una clase de representación externa que tiene sus propios eventos relacionados con el dibujo.  
  
 Hay muchos tipos diferentes de eventos de dibujo, pero se produce un evento de dibujo típico con el fin de dibujar un solo elemento dentro de un control. El controlador de eventos recibe un objeto `EventArgs` que contiene información sobre el elemento que se va a dibujar y herramientas que puede utilizar para dibujarlo. Por ejemplo, este objeto contiene normalmente el número de índice del elemento dentro de su colección primaria <xref:System.Drawing.Rectangle> , que indica los límites de presentación del elemento y <xref:System.Drawing.Graphics> un objeto para llamar a métodos de dibujo. En algunos eventos, el objeto `EventArgs` proporciona información adicional sobre el elemento y los métodos que puede llamar para dibujar algunos aspectos del elemento de forma predeterminada, como el fondo o un rectángulo de enfoque.  
  
 Para crear un control reutilizable que contenga sus personalizaciones para dibujo del propietario, cree una nueva clase que derive de una clase de control que admita el dibujo del propietario. En lugar de controlar eventos de dibujo, incluya el código de dibujo del propietario en invalidaciones para el método o los métodos `On`*EventName* de la clase nueva. Asegúrese de llamar al método o los métodos `On`*EventName* de la clase base en este caso para que los usuarios de su control puedan controlar eventos del dibujo del propietario y proporcionar una personalización adicional.  
  
 Los siguientes controles de formularios Windows Forms son compatibles con el dibujo del propietario en todas las versiones de .NET Framework:  
  
- <xref:System.Windows.Forms.ListBox>  
  
- <xref:System.Windows.Forms.ComboBox>  
  
- <xref:System.Windows.Forms.MenuItem>(utilizado por <xref:System.Windows.Forms.MainMenu> y <xref:System.Windows.Forms.ContextMenu>)  
  
- <xref:System.Windows.Forms.TabControl>  
  
 Los controles siguientes solo admiten el dibujo del propietario en .NET Framework 2,0:  
  
- <xref:System.Windows.Forms.ToolTip>  
  
- <xref:System.Windows.Forms.ListView>  
  
- <xref:System.Windows.Forms.TreeView>  
  
 Los controles siguientes admiten el dibujo del propietario y son nuevos en .NET Framework 2,0:  
  
- <xref:System.Windows.Forms.DataGridView>  
  
- <xref:System.Windows.Forms.ToolStrip>  
  
 Las secciones siguientes ofrecen detalles adicionales para cada uno de estos controles.  
  
### <a name="listbox-and-combobox-controls"></a>Controles ListBox y ComboBox  
 Los <xref:System.Windows.Forms.ListBox> controles <xref:System.Windows.Forms.ComboBox> y permiten dibujar elementos individuales en el control en un solo tamaño o en tamaños distintos.  
  
> [!NOTE]
> Aunque el <xref:System.Windows.Forms.CheckedListBox> control se deriva del control <xref:System.Windows.Forms.ListBox> , no es compatible con el dibujo del propietario.  
  
 Para dibujar cada elemento en el mismo tamaño, establezca `DrawMode` la propiedad <xref:System.Windows.Forms.DrawMode.OwnerDrawFixed> en y controle el `DrawItem` evento.  
  
 Para dibujar cada elemento con un tamaño diferente, establezca la `DrawMode` propiedad en <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable> y controle los `MeasureItem` eventos `DrawItem` y. El evento `MeasureItem` le permite indicar el tamaño de un elemento antes de que se produzca el evento `DrawItem` para ese elemento.  
  
 Para obtener más información, incluidos los ejemplos de código, consulte los temas siguientes:  
  
- <xref:System.Windows.Forms.ListBox.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListBox.MeasureItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListBox.DrawItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ComboBox.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ComboBox.MeasureItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ComboBox.DrawItem?displayProperty=nameWithType>  
  
- [Cómo: Crear texto de tamaño variable en un control ComboBox](how-to-create-variable-sized-text-in-a-combobox-control.md)  
  
### <a name="menuitem-component"></a>Componente MenuItem  
 El <xref:System.Windows.Forms.MenuItem> componente representa un elemento de menú único en <xref:System.Windows.Forms.MainMenu> un <xref:System.Windows.Forms.ContextMenu> componente de o.  
  
 Para dibujar un <xref:System.Windows.Forms.MenuItem>, establezca su `OwnerDraw` propiedad en `true` y controle `DrawItem` su evento. Para personalizar el tamaño del elemento de menú antes de que se produzca el evento `DrawItem`, controle el evento `MeasureItem` del elemento.  
  
 Para obtener más información, incluidos los ejemplos de código, consulte los temas de consulta siguientes:  
  
- <xref:System.Windows.Forms.MenuItem.OwnerDraw%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.MenuItem.DrawItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.MenuItem.MeasureItem?displayProperty=nameWithType>  
  
### <a name="tabcontrol-control"></a>TabControl (Control)  
 El <xref:System.Windows.Forms.TabControl> control permite dibujar pestañas individuales en el control. El dibujo del propietario afecta solo a las pestañas; el <xref:System.Windows.Forms.TabPage> contenido no se ve afectado.  
  
 Para <xref:System.Windows.Forms.TabControl>dibujar cada pestaña en, establezca la `DrawMode` propiedad en <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed> y controle el `DrawItem` evento. Este evento se produce una vez para cada pestaña solo cuando la pestaña está visible en el control.  
  
 Para obtener más información, incluidos los ejemplos de código, consulte los temas de consulta siguientes:  
  
- <xref:System.Windows.Forms.TabControl.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.TabControl.DrawItem?displayProperty=nameWithType>  
  
### <a name="tooltip-component"></a>ToolTip  
 El <xref:System.Windows.Forms.ToolTip> componente permite dibujar toda la información sobre herramientas cuando se muestra.  
  
 Para dibujar un <xref:System.Windows.Forms.ToolTip>, establezca su `OwnerDraw` propiedad en `true` y controle `Draw` su evento. Para <xref:System.Windows.Forms.ToolTip> personalizar el tamaño de antes de que se produzca el `Draw` evento, `Popup` controle el evento <xref:System.Windows.Forms.PopupEventArgs.ToolTipSize%2A> y establezca la propiedad en el controlador de eventos.  
  
 Para obtener más información, incluidos los ejemplos de código, consulte los temas de consulta siguientes:  
  
- <xref:System.Windows.Forms.ToolTip.OwnerDraw%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ToolTip.Draw?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ToolTip.Popup?displayProperty=nameWithType>  
  
### <a name="listview-control"></a>Control ListView  
 El <xref:System.Windows.Forms.ListView> control permite dibujar elementos individuales, subelementos y encabezados de columna en el control.  
  
 Para habilitar el dibujo propietario en el control, establezca la propiedad `OwnerDraw` en `true`.  
  
 Para dibujar cada elemento en el control, controle el evento `DrawItem`.  
  
 Para dibujar cada subelemento o encabezado de columna del control cuando la <xref:System.Windows.Forms.ListView.View%2A> propiedad está establecida en <xref:System.Windows.Forms.View.Details>, controle `DrawSubItem` los `DrawColumnHeader` eventos y.  
  
 Para obtener más información, incluidos los ejemplos de código, consulte los temas de consulta siguientes:  
  
- <xref:System.Windows.Forms.ListView.OwnerDraw%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListView.DrawItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListView.DrawSubItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListView.DrawColumnHeader?displayProperty=nameWithType>  
  
### <a name="treeview-control"></a>TreeView (Control)  
 El <xref:System.Windows.Forms.TreeView> control permite dibujar nodos individuales en el control.  
  
 Para dibujar solo el texto que se muestra en cada nodo, `DrawMode` establezca la <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawText> propiedad en y `DrawNode` controle el evento para dibujar el texto.  
  
 Para dibujar todos los elementos de cada nodo, establezca `DrawMode` la propiedad <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawAll> en y controle el `DrawNode` evento para dibujar los elementos que necesite, como texto, iconos, casillas, signos más y menos, y líneas que conectan los nodos.  
  
 Para obtener más información, incluidos los ejemplos de código, consulte los temas de consulta siguientes:  
  
- <xref:System.Windows.Forms.TreeView.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.TreeView.DrawNode?displayProperty=nameWithType>  
  
### <a name="datagridview-control"></a>Control DataGridView  
 El <xref:System.Windows.Forms.DataGridView> control permite dibujar celdas y filas individuales en el control.  
  
 Para dibujar celdas individuales, controle el evento `CellPainting`.  
  
 Para dibujar filas o elementos de filas, controle uno o ambos eventos `RowPrePaint` y `RowPostPaint`. El evento `RowPrePaint` se produce antes de que se dibujen las celdas en una fila, y el evento `RowPostPaint` se produce después de dibujar las celdas. Puede controlar ambos eventos y el evento `CellPainting` para pintar el fondo de una fila, celdas individuales y el primer plano de una fila por separado, o bien puede proporcionar personalizaciones específicas donde las necesite y usar la vista predeterminada para otros elementos de la fila.  
  
 Para obtener más información, incluidos los ejemplos de código, consulte los temas siguientes:  
  
- <xref:System.Windows.Forms.DataGridView.CellPainting>  
  
- <xref:System.Windows.Forms.DataGridView.RowPrePaint>  
  
- <xref:System.Windows.Forms.DataGridView.RowPostPaint>  
  
- [Cómo: Personalizar la apariencia de las celdas en el control DataGridView Windows Forms](customize-the-appearance-of-cells-in-the-datagrid.md)  
  
- [Procedimientos: Personalizar la apariencia de las filas en el control DataGridView Windows Forms](customize-the-appearance-of-rows-in-the-datagrid.md)  
  
### <a name="toolstrip-control"></a>ToolStrip  
 <xref:System.Windows.Forms.ToolStrip>y los controles derivados permiten personalizar cualquier aspecto de su apariencia.  
  
 Para proporcionar una representación personalizada para <xref:System.Windows.Forms.ToolStrip> los controles, establezca `Renderer` la <xref:System.Windows.Forms.ToolStripPanel>propiedad de <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripManager>, o <xref:System.Windows.Forms.ToolStripContentPanel> en un `ToolStripRenderer` objeto y controle uno o varios de los muchos eventos de dibujo proporcionados por el `ToolStripRenderer` clase. `Renderer` También puede establecer una propiedad en una instancia de su propia clase derivada de <xref:System.Windows.Forms.ToolStripProfessionalRenderer> `ToolStripRenderer`, o <xref:System.Windows.Forms.ToolStripSystemRenderer> que implementa o invalida métodos eventName específicos. `On`  
  
 Para obtener más información, incluidos los ejemplos de código, consulte los temas siguientes:  
  
- <xref:System.Windows.Forms.ToolStripRenderer>  
  
- [Procedimientos: Crear y establecer un representador personalizado para el control ToolStrip en Windows Forms](create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md)  
  
- [Procedimientos: Dibujo personalizado de un control ToolStrip](how-to-custom-draw-a-toolstrip-control.md)  
  
## <a name="see-also"></a>Vea también

- [Controles que se utilizan en formularios Windows Forms](controls-to-use-on-windows-forms.md)
