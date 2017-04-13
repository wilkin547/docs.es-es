---
title: "Controles compatibles con dibujos propietarios integrados | Microsoft Docs"
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
  - "propietario del dibujo,"
  - "dibujo personalizado"
  - "controles [Windows Forms], cambiar la apariencia"
  - "dibujo personalizado"
  - "dibujo del propietario"
ms.assetid: 3823d01e-9610-43e6-864d-99f9b7c2b351
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Controles compatibles con dibujos propietarios integrados
Dibujo propietario en formularios Windows Forms, que también se conoce como dibujo personalizado, es una técnica para cambiar la apariencia visual de determinados controles.  
  
> [!NOTE]
>  La palabra "control" en este tema se utiliza para indicar que las clases que derivan de <xref:System.Windows.Forms.Control> o <xref:System.ComponentModel.Component>.  
  
 Normalmente, Windows controla el dibujo automático mediante la configuración de la propiedad como <xref:System.Windows.Forms.Control.BackColor%2A> para determinar la apariencia de un control. Con el dibujo del propietario, tomar sobre el proceso de dibujo, cambiar los elementos de la apariencia de que no están disponibles mediante las propiedades. Por ejemplo, muchos controles permiten establecer el color del texto que se muestra, pero está limitado a un único color. Dibujo del propietario le permite realizar tareas como mostrar una parte del texto en negro y otra en rojo.  
  
 En la práctica, el dibujo del propietario es similar a dibujar gráficos en un formulario. Por ejemplo, podría utilizar métodos gráficos en un controlador para el formulario <xref:System.Windows.Forms.Control.Paint> eventos para emular un `ListBox` control, pero tendría que escribir su propio código para controlar toda la interacción del usuario. Con el dibujo del propietario, el control utiliza su código para dibujar el contenido pero por lo demás retiene todas sus funciones intrínsecas. Puede utilizar métodos gráficos para dibujar cada elemento en el control o para personalizar algunos aspectos de cada elemento mientras utiliza la apariencia predeterminada para otros aspectos de cada elemento.  
  
## <a name="owner-drawing-in-windows-forms-controls"></a>Controles de dibujo propietario en Windows Forms  
 Para realizar el dibujo propietario en controles que lo admiten, normalmente se establece una propiedad y controlar uno o más eventos.  
  
 La mayoría de los controles que admiten el dibujo propietario tienen una `OwnerDraw` o `DrawMode` propiedad que indica si el control provocará su evento relacionado con el dibujo o eventos cuando pinta a sí mismo.  
  
 Controles que no tienen un `OwnerDraw` o `DrawMode` propiedad incluye la `DataGridView` control, que proporciona eventos de dibujo que se producen automáticamente, y el `ToolStrip` control, que se dibuja utilizando una clase de representación externa que tiene sus propios eventos relacionados con el dibujo.  
  
 Hay muchos tipos diferentes de eventos de dibujo, pero se produce un evento de dibujo típico para dibujar un solo elemento dentro de un control. El controlador de eventos recibe un `EventArgs` objeto que contiene información acerca del elemento que se va a dibujar y herramientas puede utilizar para dibujarlo. Por ejemplo, este objeto contiene normalmente el número de índice del elemento en la colección primaria, un <xref:System.Drawing.Rectangle> que indica que el elemento muestre los límites y un <xref:System.Drawing.Graphics> objeto para llamar a métodos de pintura. En algunos casos, la `EventArgs` objeto proporciona información adicional sobre el elemento y los métodos que se pueden llamar para dibujar algunos aspectos del elemento de forma predeterminada, como el fondo o un rectángulo de foco.  
  
 Para crear un control reutilizable que contiene sus personalizaciones dibujado por el propietario, cree una nueva clase que deriva de una clase de control que admite el dibujo del propietario. En lugar de controlar eventos de dibujo, incluya el código de dibujo propietario en invalidaciones adecuado `On` *EventName* método o métodos de la clase nueva. Asegúrese de que llama a la clase base `On` *EventName* método o métodos en este caso para que pueden controlar eventos de dibujo propietario y proporcionar una personalización adicional a los usuarios de su control.  
  
 Lo siguientes formularios Windows Forms controles admiten el dibujo propietario en todas las versiones de .NET Framework:  
  
-   <xref:System.Windows.Forms.ListBox>  
  
-   <xref:System.Windows.Forms.ComboBox>  
  
-   <xref:System.Windows.Forms.MenuItem> (utilizado por <xref:System.Windows.Forms.MainMenu> y <xref:System.Windows.Forms.ContextMenu>)  
  
-   <xref:System.Windows.Forms.TabControl>  
  
 Los controles siguientes admiten el dibujo en propietario [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]:  
  
-   <xref:System.Windows.Forms.ToolTip>  
  
-   <xref:System.Windows.Forms.ListView>  
  
-   <xref:System.Windows.Forms.TreeView>  
  
 Los controles siguientes admiten el dibujo propietario y son nuevo en [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]:  
  
-   <xref:System.Windows.Forms.DataGridView>  
  
-   <xref:System.Windows.Forms.ToolStrip>  
  
 Las secciones siguientes proporcionan detalles adicionales para cada uno de estos controles.  
  
### <a name="listbox-and-combobox-controls"></a>Controles ListBox y ComboBox  
 El <xref:System.Windows.Forms.ListBox> y <xref:System.Windows.Forms.ComboBox> controles le permiten dibujar elementos individuales en el control en un tamaño, o en varios tamaños.  
  
> [!NOTE]
>  Aunque la <xref:System.Windows.Forms.CheckedListBox> control se deriva el <xref:System.Windows.Forms.ListBox> control, no admite el dibujo del propietario.  
  
 Para dibujar cada elemento del mismo tamaño, establezca la `DrawMode` propiedad <xref:System.Windows.Forms.DrawMode> y controlar la `DrawItem` eventos.  
  
 Para dibujar cada elemento con un tamaño diferente, establezca la `DrawMode` propiedad <xref:System.Windows.Forms.DrawMode> y controlar tanto el `MeasureItem` y `DrawItem` eventos. El `MeasureItem` evento le permite indicar el tamaño de un elemento antes de la `DrawItem` evento tiene lugar para ese elemento.  
  
 Para obtener más información, incluidos ejemplos de código, vea los temas siguientes:  
  
-   <xref:System.Windows.Forms.ListBox.DrawMode%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ListBox.MeasureItem?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ListBox.DrawItem?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ComboBox.DrawMode%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ComboBox.MeasureItem?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ComboBox.DrawItem?displayProperty=fullName>  
  
-   [Cómo: crear texto de tamaño Variable en un Control ComboBox](../../../../docs/framework/winforms/controls/how-to-create-variable-sized-text-in-a-combobox-control.md)  
  
### <a name="menuitem-component"></a>Componente MenuItem  
 El <xref:System.Windows.Forms.MenuItem> componente representa un solo elemento de menú en un <xref:System.Windows.Forms.MainMenu> o <xref:System.Windows.Forms.ContextMenu> componente.  
  
 Para dibujar un <xref:System.Windows.Forms.MenuItem>, establezca su `OwnerDraw` propiedad `true` y controlar su `DrawItem` eventos. Para personalizar el tamaño del elemento de menú antes de la `DrawItem` evento se produce, controlar el elemento `MeasureItem` eventos.  
  
 Para obtener más información, incluidos ejemplos de código, vea los temas de referencia siguientes:  
  
-   <xref:System.Windows.Forms.MenuItem.OwnerDraw%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.MenuItem.DrawItem?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.MenuItem.MeasureItem?displayProperty=fullName>  
  
### <a name="tabcontrol-control"></a>TabControl (Control)  
 El <xref:System.Windows.Forms.TabControl> control permite dibujar fichas individuales en el control. Dibujo del propietario afecta sólo a las fichas; el <xref:System.Windows.Forms.TabPage> no afecta al contenido.  
  
 Para dibujar cada ficha en un <xref:System.Windows.Forms.TabControl>, establezca el `DrawMode` propiedad <xref:System.Windows.Forms.TabDrawMode> y controlar la `DrawItem` eventos. Este evento se produce una vez para cada ficha sólo cuando la ficha está visible en el control.  
  
 Para obtener más información, incluidos ejemplos de código, vea los temas de referencia siguientes:  
  
-   <xref:System.Windows.Forms.TabControl.DrawMode%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.TabControl.DrawItem?displayProperty=fullName>  
  
### <a name="tooltip-component"></a>ToolTip  
 El <xref:System.Windows.Forms.ToolTip> componente permite dibujar la información sobre herramientas completa cuando se muestra.  
  
 Para dibujar un <xref:System.Windows.Forms.ToolTip>, establezca su `OwnerDraw` propiedad `true` y controlar su `Draw` eventos. Para personalizar el tamaño de la <xref:System.Windows.Forms.ToolTip> antes de la `Draw` se produce el evento, controlar el `Popup` eventos y establezca la <xref:System.Windows.Forms.PopupEventArgs.ToolTipSize%2A> propiedad en el controlador de eventos.  
  
 Para obtener más información, incluidos ejemplos de código, vea los temas de referencia siguientes:  
  
-   <xref:System.Windows.Forms.ToolTip.OwnerDraw%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ToolTip.Draw?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ToolTip.Popup?displayProperty=fullName>  
  
### <a name="listview-control"></a>Control ListView  
 El <xref:System.Windows.Forms.ListView> control permite dibujar elementos individuales, subelementos y encabezados de columna en el control.  
  
 Para habilitar el dibujo propietario en el control, establezca la `OwnerDraw` propiedad `true`.  
  
 Para dibujar cada elemento en el control, controle el `DrawItem` eventos.  
  
 Para dibujar cada subelemento o encabezado de columna en el control cuando el <xref:System.Windows.Forms.ListView.View%2A> propiedad está establecida en <xref:System.Windows.Forms.View>, controlar el `DrawSubItem` y `DrawColumnHeader` eventos.  
  
 Para obtener más información, incluidos ejemplos de código, vea los temas de referencia siguientes:  
  
-   <xref:System.Windows.Forms.ListView.OwnerDraw%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ListView.DrawItem?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ListView.DrawSubItem?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.ListView.DrawColumnHeader?displayProperty=fullName>  
  
### <a name="treeview-control"></a>TreeView (Control)  
 El <xref:System.Windows.Forms.TreeView> control permite dibujar nodos individuales en el control.  
  
 Para dibujar sólo el texto mostrado en cada nodo, establezca la `DrawMode` propiedad <xref:System.Windows.Forms.TreeViewDrawMode> y controlar la `DrawNode` eventos para dibujar el texto.  
  
 Para dibujar todos los elementos de cada nodo, establezca la `DrawMode` propiedad <xref:System.Windows.Forms.TreeViewDrawMode> y controlar la `DrawNode` eventos para dibujar cualquier elemento que necesite, como texto, iconos, casillas, signos, más y menos y líneas que conectan los nodos.  
  
 Para obtener más información, incluidos ejemplos de código, vea los temas de referencia siguientes:  
  
-   <xref:System.Windows.Forms.TreeView.DrawMode%2A?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.TreeView.DrawNode?displayProperty=fullName>  
  
### <a name="datagridview-control"></a>Control DataGridView  
 El <xref:System.Windows.Forms.DataGridView> control permite dibujar celdas y filas individuales en el control.  
  
 Para dibujar celdas individuales, controle el `CellPainting` eventos.  
  
 Para dibujar elementos de filas o filas individuales, controle uno o ambos de los `RowPrePaint` y `RowPostPaint` eventos. El `RowPrePaint` evento se produce antes de que se dibujan las celdas de una fila y el `RowPostPaint` evento se produce después de que se dibujan las celdas. Puede controlar ambos eventos y la `CellPainting` eventos para pintar el fondo de la fila, celdas individuales y filas en primer plano por separado, o puede proporcionar personalizaciones específicas donde necesite y utilizar la presentación predeterminada de otros elementos de la fila.  
  
 Para obtener más información, incluidos ejemplos de código, vea los temas siguientes:  
  
-   <xref:System.Windows.Forms.DataGridView.CellPainting>  
  
-   <xref:System.Windows.Forms.DataGridView.RowPrePaint>  
  
-   <xref:System.Windows.Forms.DataGridView.RowPostPaint>  
  
-   [Cómo: personalizar la apariencia de las celdas en el Control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md)  
  
-   [Cómo: personalizar la apariencia de las filas en el Control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md)  
  
### <a name="toolstrip-control"></a>ToolStrip  
 <xref:System.Windows.Forms.ToolStrip> y controles derivados le permiten personalizar cualquier aspecto de su apariencia.  
  
 Para proporcionar una representación personalizada para <xref:System.Windows.Forms.ToolStrip> controles, establecer el `Renderer` propiedad de un <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripManager>, <xref:System.Windows.Forms.ToolStripPanel>, o <xref:System.Windows.Forms.ToolStripContentPanel> a una `ToolStripRenderer` de objetos y administrar uno o varios de los muchos eventos de dibujos proporcionados por la `ToolStripRenderer` clase. Como alternativa, establezca un `Renderer` propiedad a una instancia de su propia clase derivada de `ToolStripRenderer`, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>, o <xref:System.Windows.Forms.ToolStripSystemRenderer> que implementa o reemplaza específico `On` *EventName* métodos.  
  
 Para obtener más información, incluidos ejemplos de código, vea los temas siguientes:  
  
-   <xref:System.Windows.Forms.ToolStripRenderer>  
  
-   [Cómo: crear y establecer un representador personalizado para el Control ToolStrip de Windows Forms](../../../../docs/framework/winforms/controls/create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md)  
  
-   [Cómo: personalizar dibujar un Control ToolStrip](../../../../docs/framework/winforms/controls/how-to-custom-draw-a-toolstrip-control.md)  
  
## <a name="see-also"></a>Vea también  
 [Controles que se utilizan en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)