---
title: Arquitectura del control ToolStrip
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], architecture
ms.assetid: 71df2d18-862e-4701-9ff9-c1fe606f94f2
ms.openlocfilehash: 91813928344f9210ce1383daa9ba7f765117833a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59296217"
---
# <a name="toolstrip-control-architecture"></a>Arquitectura del control ToolStrip
El <xref:System.Windows.Forms.ToolStrip> y <xref:System.Windows.Forms.ToolStripItem> clases proporcionan un sistema flexible y extensible para mostrar la barra de herramientas, estado y elementos de menú. Estas clases están incluidas en el <xref:System.Windows.Forms> espacio de nombres y normalmente se denominan con el prefijo "ToolStrip" (como <xref:System.Windows.Forms.ToolStripOverflow>) o con el sufijo "Quitar" (como <xref:System.Windows.Forms.MenuStrip>).  
  
## <a name="toolstrip"></a>ToolStrip  
 Los temas siguientes describen <xref:System.Windows.Forms.ToolStrip> y los controles que derivan de ella.  
  
 <xref:System.Windows.Forms.ToolStrip> es la clase base abstracta para <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.StatusStrip>, y <xref:System.Windows.Forms.ContextMenuStrip>. El siguiente objeto de modelo se muestra en el <xref:System.Windows.Forms.ToolStrip> jerarquía de herencia.  
  
 ![Diagrama que muestra el modelo de objeto ToolStrip.](./media/toolstrip-control-architecture/toolstrip-object-model.gif)  
  
 Puede obtener acceso a todos los elementos de un <xref:System.Windows.Forms.ToolStrip> a través de la <xref:System.Windows.Forms.ToolStrip.Items%2A> colección. Puede obtener acceso a todos los elementos de un <xref:System.Windows.Forms.ToolStripDropDownItem> a través de la <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A> colección. En una clase derivada de <xref:System.Windows.Forms.ToolStrip>, también puede usar el <xref:System.Windows.Forms.ToolStrip.DisplayedItems%2A> propiedad para tener acceso a solo aquellos elementos que se muestran actualmente. Estos son los elementos que no están actualmente en un menú de desbordamiento.  
  
 Los siguientes elementos están específicamente diseñados para funcionar perfectamente con ambos <xref:System.Windows.Forms.ToolStripSystemRenderer> y <xref:System.Windows.Forms.ToolStripProfessionalRenderer> en todas las orientaciones. Están disponibles de forma predeterminada en tiempo de diseño para el <xref:System.Windows.Forms.ToolStrip> control:  
  
-   <xref:System.Windows.Forms.ToolStripButton>  
  
-   <xref:System.Windows.Forms.ToolStripSeparator>  
  
-   <xref:System.Windows.Forms.ToolStripLabel>  
  
-   <xref:System.Windows.Forms.ToolStripDropDownButton>  
  
-   <xref:System.Windows.Forms.ToolStripSplitButton>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### <a name="menustrip"></a>MenuStrip  
 <xref:System.Windows.Forms.MenuStrip> es el contenedor de nivel superior que reemplaza a <xref:System.Windows.Forms.MainMenu>. También proporciona control de claves y documento de varias características MDI (interfaz). Funcionalmente, <xref:System.Windows.Forms.ToolStripDropDownItem> y <xref:System.Windows.Forms.ToolStripMenuItem> profesional junto con <xref:System.Windows.Forms.MenuStrip>, aunque se deriven de <xref:System.Windows.Forms.ToolStripItem>.  
  
 Los siguientes elementos están específicamente diseñados para funcionar perfectamente con ambos <xref:System.Windows.Forms.ToolStripSystemRenderer> y <xref:System.Windows.Forms.ToolStripProfessionalRenderer> en todas las orientaciones. Están disponibles de forma predeterminada en tiempo de diseño para el <xref:System.Windows.Forms.MenuStrip> control:  
  
-   <xref:System.Windows.Forms.ToolStripMenuItem>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### <a name="statusstrip"></a>StatusStrip  
 <xref:System.Windows.Forms.StatusStrip> reemplaza el <xref:System.Windows.Forms.StatusBar> control. Las características especiales de <xref:System.Windows.Forms.StatusStrip> incluyen un diseño de tabla personalizado, la compatibilidad con el formato del tamaño y moviendo enfrentarme y el `Spring` propiedad, que permite un <xref:System.Windows.Forms.ToolStripStatusLabel> para rellenar automáticamente el espacio disponible.  
  
 Los siguientes elementos están específicamente diseñados para funcionar perfectamente con ambos <xref:System.Windows.Forms.ToolStripSystemRenderer> y <xref:System.Windows.Forms.ToolStripProfessionalRenderer> en todas las orientaciones. Están disponibles de forma predeterminada en tiempo de diseño para el <xref:System.Windows.Forms.StatusStrip> control:  
  
-   <xref:System.Windows.Forms.ToolStripStatusLabel>  
  
-   <xref:System.Windows.Forms.ToolStripDropDownButton>  
  
-   <xref:System.Windows.Forms.ToolStripSplitButton>  
  
-   <xref:System.Windows.Forms.ToolStripProgressBar>  
  
### <a name="contextmenustrip"></a>ContextMenuStrip  
 <xref:System.Windows.Forms.ContextMenuStrip> reemplaza a <xref:System.Windows.Forms.ContextMenu>. Puede asociar un <xref:System.Windows.Forms.ContextMenuStrip> con cualquier control y secundario del mouse haga clic en muestra automáticamente el menú contextual (o el menú contextual). Puede mostrar un <xref:System.Windows.Forms.ContextMenuStrip> mediante programación usando el <xref:System.Windows.Forms.ToolStripDropDown.Show%2A> método. <xref:System.Windows.Forms.ContextMenuStrip> admite cancelable <xref:System.Windows.Forms.ToolStripDropDown.Opening> y <xref:System.Windows.Forms.ToolStripDropDown.Closing> eventos para controlar el relleno dinámico y escenarios de varios clic. <xref:System.Windows.Forms.ContextMenuStrip> Comprobar estado de elemento de menú, admite imágenes, texto, las claves de acceso, accesos directos y menús en cascada.  
  
 Los siguientes elementos están específicamente diseñados para funcionar perfectamente con ambos <xref:System.Windows.Forms.ToolStripSystemRenderer> y <xref:System.Windows.Forms.ToolStripProfessionalRenderer> en todas las orientaciones. Están disponibles de forma predeterminada en tiempo de diseño para el <xref:System.Windows.Forms.ContextMenuStrip> control:  
  
-   <xref:System.Windows.Forms.ToolStripMenuItem>  
  
-   <xref:System.Windows.Forms.ToolStripSeparator>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### <a name="toolstrip-generic-features"></a>Características genéricas de ToolStrip  
 Los temas siguientes describen las características y comportamiento que son genéricos para el <xref:System.Windows.Forms.ToolStrip> y controles derivados.  
  
#### <a name="painting"></a>Dibujo  
 Puede hacer el dibujo personalizado en <xref:System.Windows.Forms.ToolStrip> controles de varias maneras. Al igual que con otros controles de Windows Forms, el <xref:System.Windows.Forms.ToolStrip> y <xref:System.Windows.Forms.ToolStripItem> tienen reemplazable `OnPaint` métodos y `Paint` eventos. Como con el dibujo normal, el sistema de coordenadas es relativo al área cliente del control; es decir, la esquina superior izquierda del control es 0, 0. El `Paint` eventos y `OnPaint` método para un <xref:System.Windows.Forms.ToolStripItem> se comportan como otros eventos de dibujo del control.  
  
 El <xref:System.Windows.Forms.ToolStrip> controles también proporcionan un mayor acceso a la representación de los elementos y el contenedor a través de la <xref:System.Windows.Forms.ToolStripRenderer> (clase), que tiene métodos reemplazables para dibujar el fondo, fondo del elemento, imagen del elemento, elemento flecha, texto del elemento y el borde de la <xref:System.Windows.Forms.ToolStrip>. Los argumentos de evento para estos métodos exponen varias propiedades como rectángulos, colores y formatos de texto que puede ajustar según sea necesario.  
  
 Para ajustar solo unos pocos aspectos de cómo se pinta un elemento, normalmente se reemplaza el <xref:System.Windows.Forms.ToolStripRenderer>.  
  
 Si está escribiendo un nuevo elemento y desea controlar todos los aspectos de la pintura, invalidar el `OnPaint` método. Desde `OnPaint`, puede usar los métodos de la <xref:System.Windows.Forms.ToolStripRenderer>.  
  
 De forma predeterminada, el <xref:System.Windows.Forms.ToolStrip> es double almacenados en búfer, que aprovecha la <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> configuración.  
  
#### <a name="parenting"></a>Relación jerárquica  
 Es más complejo en el concepto de la propiedad de contenedor y la relación jerárquica <xref:System.Windows.Forms.ToolStrip> controla que en otros controles de contenedor de Windows Forms. Que es necesario para admitir escenarios dinámicos como desbordamiento, para compartir elementos desplegables entre varios <xref:System.Windows.Forms.ToolStrip> elementos y para admitir la generación de un <xref:System.Windows.Forms.ContextMenuStrip> de un control.  
  
 En la lista siguiente se describe los miembros relacionados con la relación jerárquica y explica su uso.  
  
-   <xref:System.Windows.Forms.ToolStripDropDown.OwnerItem%2A> Obtiene acceso al elemento que es el origen del elemento de lista desplegable. Esto es similar a <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A>, pero en lugar de devolver un control, devuelve un <xref:System.Windows.Forms.ToolStripItem>.  
  
-   <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A> Determina qué control es el origen de la <xref:System.Windows.Forms.ContextMenuStrip> cuando varios controles comparten el mismo <xref:System.Windows.Forms.ContextMenuStrip>.  
  
-   <xref:System.Windows.Forms.ToolStripItem.GetCurrentParent%2A> es un descriptor de acceso de solo lectura a la <xref:System.Windows.Forms.ToolStripItem.Parent%2A> propiedad. Un elemento primario difiere de un propietario en que un elemento primario indica actual devuelto <xref:System.Windows.Forms.ToolStrip> en que se muestra el elemento, que podría estar en el área de desbordamiento.  
  
-   <xref:System.Windows.Forms.ToolStripItem.Owner%2A> Devuelve el <xref:System.Windows.Forms.ToolStrip> cuya colección de elementos contiene actual <xref:System.Windows.Forms.ToolStripItem>. Esta es la mejor manera para hacer referencia a <xref:System.Windows.Forms.ToolStrip.ImageList%2A> u otras propiedades en el nivel superior <xref:System.Windows.Forms.ToolStrip> sin necesidad de escribir código especial para controlar el desbordamiento.  
  
#### <a name="behavior-of-inherited-controls"></a>Comportamiento de los controles heredados  
 Cada vez que se usan en la herencia, se bloquean los controles siguientes:  
  
-   <xref:System.Windows.Forms.ToolStrip>  
  
-   <xref:System.Windows.Forms.MenuStrip>  
  
-   <xref:System.Windows.Forms.ContextMenuStrip>  
  
-   <xref:System.Windows.Forms.StatusStrip>  
  
-   <xref:System.Windows.Forms.ToolStripPanel> que incluye los paneles en una <xref:System.Windows.Forms.ToolStripContainer> y también individuales <xref:System.Windows.Forms.ToolStripPanel> controles.  
  
 Por ejemplo, cree una nueva aplicación de Windows Forms mediante el uso de uno o varios de los controles de la lista anterior. Establecer el modificador de acceso de uno o más controles a `public` o `protected`y, a continuación, compile el proyecto. Agregue un formulario que herede del primer formulario y, a continuación, seleccione un control heredado. El control aparece bloqueado y se comporta como si fuera su modificador de acceso `private`.  
  
#### <a name="toolstripcontainer-support-of-inheritance"></a>ToolStripContainer compatibilidad de herencia  
 El <xref:System.Windows.Forms.ToolStripContainer> control admite escenarios heredados limitados, similares al ejemplo siguiente:  
  
1. Cree una nueva aplicación de Windows Forms.  
  
2. Agregue un control <xref:System.Windows.Forms.ToolStripContainer> al formulario.  
  
3. Establecer el modificador de acceso de la <xref:System.Windows.Forms.ToolStripContainer> a `public` o `protected`.  
  
4. Agregue cualquier combinación de <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, y <xref:System.Windows.Forms.ContextMenuStrip> controles a la <xref:System.Windows.Forms.ToolStripPanel> regiones de la <xref:System.Windows.Forms.ToolStripContainer>.  
  
5. Compile el proyecto.  
  
6. Agregue un formulario que herede del primer formulario.  
  
7. Seleccione el heredado <xref:System.Windows.Forms.ToolStripContainer> en el formulario.  
  
#### <a name="inherited-behavior-of-child-controls"></a>Comportamiento heredado de controles secundarios  
 Después de completar los pasos anteriores, se produce el siguiente comportamiento heredado:  
  
-   En el diseñador, el control aparece con un icono heredado.  
  
-   El <xref:System.Windows.Forms.ToolStripPanel> controles están bloqueados; no puede seleccionar ni volver a organizar su contenido.  
  
-   Puede agregar controles a la <xref:System.Windows.Forms.ToolStripContentPanel>, mueva los controles y convertirlos en controles secundarios de la <xref:System.Windows.Forms.ToolStripContentPanel>.  
  
-   Los cambios se conservan después de compilar el formulario.  
  
    > [!NOTE]
    >  Quite los modificadores de acceso de todos los <xref:System.Windows.Forms.ToolStripPanel> controles que forman parte de un <xref:System.Windows.Forms.ToolStripContainer>. El modificador de acceso de la <xref:System.Windows.Forms.ToolStripContainer> rige la totalidad del control.  
  
#### <a name="partial-trust"></a>Confianza parcial  
 Las limitaciones de `ToolStrip`bajo confianza parcial están diseñadas para evitar la entrada inadvertida de información personal que podría utilizarse en las personas no autorizadas o servicios. Las medidas de protección son los siguientes:  
  
-   `ToolStripDropDown` controles requieren <xref:System.Security.Permissions.UIPermissionWindow.AllWindows> para mostrar los elementos en un <xref:System.Windows.Forms.ToolStripControlHost>. Esto se aplica a ambos controles intrínsecos como <xref:System.Windows.Forms.ToolStripTextBox>, <xref:System.Windows.Forms.ToolStripComboBox>, y <xref:System.Windows.Forms.ToolStripProgressBar> como controles de así como a creada por el usuario. Si no se cumple este requisito, no se muestran estos elementos. No se inicia ninguna excepción.  
  
-   Establecer el <xref:System.Windows.Forms.ToolStripDropDown.AutoClose%2A> propiedad `false` no está permitido, la pueden cancelar <xref:System.Windows.Forms.ToolStripDropDown.Closing> se omite el parámetro de evento. Esto hace imposible escribir más de una pulsación de tecla sin descarta el elemento de lista desplegable. Si no se cumple este requisito, no se muestran estos elementos. No se inicia ninguna excepción.  
  
-   Muchas presiones de tecla control de eventos, no se generará si se producen en contextos de confianza parcial no sea <xref:System.Security.Permissions.UIPermissionWindow.AllWindows>.  
  
-   Las claves de acceso no son procesados cuando <xref:System.Security.Permissions.UIPermissionWindow.AllWindows> no se ha concedido.  
  
#### <a name="usage"></a>Uso  
 Los siguientes patrones de uso tienen una incidencia en <xref:System.Windows.Forms.ToolStrip> diseño, la interacción con el teclado y el comportamiento del usuario final:  
  
-   Unidas en un <xref:System.Windows.Forms.ToolStripPanel>  
  
     El <xref:System.Windows.Forms.ToolStrip> se puede mover dentro de la <xref:System.Windows.Forms.ToolStripPanel> y en <xref:System.Windows.Forms.ToolStripPanel>s. El `Dock` propiedad se omite y si el <xref:System.Windows.Forms.ToolStrip.Stretch%2A> propiedad es `false`, el tamaño de la <xref:System.Windows.Forms.ToolStrip> crece a medida que se agregan elementos a la <xref:System.Windows.Forms.ToolStripPanel>. Normalmente, el <xref:System.Windows.Forms.ToolStrip> no participa en el orden de tabulación.  
  
-   Acoplado  
  
     El <xref:System.Windows.Forms.ToolStrip> se coloca en un lado de un contenedor en una posición fija, y su tamaño se expande a través de todo el borde al que está acoplada. Normalmente, el <xref:System.Windows.Forms.ToolStrip> no participa en el orden de tabulación.  
  
-   Posición absoluta  
  
     El <xref:System.Windows.Forms.ToolStrip> es similar a otros controles, que se coloca el <xref:System.Windows.Forms.Control.Location%2A> propiedad, tiene un tamaño fijo y normalmente participa en el orden de tabulación.  
  
#### <a name="keyboard-interaction"></a>Interacción con el teclado  
  
##### <a name="access-keys"></a>Teclas de acceso  
 En combinación con o después de la tecla ALT, las claves de acceso son una forma de activar un control mediante el teclado. <xref:System.Windows.Forms.ToolStrip> es compatible con las dos claves de acceso explícitas e implícitas. La definición explícita utiliza un carácter (&) precede a la letra. Definición implícita usa un algoritmo que intenta encontrar un elemento correspondiente en función del orden de los caracteres en un determinado `Text` propiedad.  
  
##### <a name="shortcut-keys"></a>Teclas de método abreviado  
 Las teclas de método abreviado utilizadas por un <xref:System.Windows.Forms.MenuStrip> usan una combinación de la <xref:System.Windows.Forms.Keys> enumeración (que no es específico de pedido) para definir la tecla de método abreviado. También puede usar el <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> propiedad para mostrar una tecla de método abreviado con sólo texto, como mostrar "Del" en lugar de "Delete".  
  
##### <a name="navigation"></a>Navegación  
 La tecla ALT activa el <xref:System.Windows.Forms.MenuStrip> apunta <xref:System.Windows.Forms.Form.MainMenuStrip%2A>. Desde allí, CTRL+TAB navega entre <xref:System.Windows.Forms.ToolStrip> controla dentro `ToolStripPanel`s. La tecla TAB y las teclas de flecha del teclado numérico navegan entre elementos de un <xref:System.Windows.Forms.ToolStrip>. Un algoritmo especial controla la navegación en el área de desbordamiento. BARRA ESPACIADORA selecciona un <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton>, o <xref:System.Windows.Forms.ToolStripSplitButton>.  
  
##### <a name="focus-and-validation"></a>El foco y validación  
 Cuando se activa la tecla ALT, el <xref:System.Windows.Forms.MenuStrip> o <xref:System.Windows.Forms.ToolStrip> normalmente no tomar ni quitar el foco del control que tiene actualmente el foco. Si hay un control hospedado dentro de la <xref:System.Windows.Forms.MenuStrip> o una lista desplegable de la <xref:System.Windows.Forms.MenuStrip>, el control obtiene el foco cuando el usuario presiona la tecla TAB. En general, el <xref:System.Windows.Forms.Control.GotFocus>, <xref:System.Windows.Forms.Control.LostFocus>, <xref:System.Windows.Forms.Control.Enter>, y <xref:System.Windows.Forms.Control.Leave> eventos de <xref:System.Windows.Forms.MenuStrip> no es posible que se genera cuando se activan mediante el teclado. En tales casos, utilice el <xref:System.Windows.Forms.MenuStrip.MenuActivate> y <xref:System.Windows.Forms.MenuStrip.MenuDeactivate> eventos en su lugar.  
  
 De forma predeterminada, <xref:System.Windows.Forms.ToolStrip.CausesValidation%2A> es `false`. Llamar a <xref:System.Windows.Forms.ContainerControl.Validate%2A> explícitamente en el formulario para realizar la validación.  
  
#### <a name="layout"></a>Diseño  
 Puede controlar <xref:System.Windows.Forms.ToolStrip> diseño eligiendo uno de los miembros de <xref:System.Windows.Forms.ToolStripLayoutStyle> con el <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> propiedad.  
  
##### <a name="stack-layouts"></a>Diseños de pila  
 Apilamiento es organizar los elementos contiguas entre sí en ambos extremos de la <xref:System.Windows.Forms.ToolStrip>. La lista siguiente describe los diseños de pila.  
  
-   <xref:System.Windows.Forms.ToolStripLayoutStyle.StackWithOverflow> es el valor predeterminado. Esta configuración hace que el <xref:System.Windows.Forms.ToolStrip> modifique su diseño automáticamente de acuerdo con la <xref:System.Windows.Forms.ToolStrip.Orientation%2A> propiedad controlen arrastrando y escenarios de acoplamiento.  
  
-   <xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow> representa el <xref:System.Windows.Forms.ToolStrip> elementos verticalmente contiguas entre sí.  
  
-   <xref:System.Windows.Forms.ToolStripLayoutStyle.HorizontalStackWithOverflow> representa el <xref:System.Windows.Forms.ToolStrip> elementos horizontalmente contiguas entre sí.  
  
##### <a name="other-features-of-stack-layouts"></a>Otras características de los diseños de pila  
 <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> Determina el extremo de la <xref:System.Windows.Forms.ToolStrip> al que se alinea el elemento.  
  
 Cuando no caben dentro de la <xref:System.Windows.Forms.ToolStrip>, aparece automáticamente un botón de desbordamiento. El <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> configuración de la propiedad determina si un elemento aparece en el área de desbordamiento siempre, según sea necesario o nunca.  
  
 En el <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> eventos, puede inspeccionar el <xref:System.Windows.Forms.ToolStripItem.Placement%2A> propiedad para determinar si un elemento se colocó en el método main <xref:System.Windows.Forms.ToolStrip>, el desbordamiento <xref:System.Windows.Forms.ToolStrip>, o si no está actualmente visible en absoluto. ¿Por qué no se muestra un elemento de las causas más habituales son que el elemento no cabe en el principal <xref:System.Windows.Forms.ToolStrip> y su <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> propiedad se estableció en <xref:System.Windows.Forms.ToolStripItemOverflow.Never>.  
  
 Realizar una <xref:System.Windows.Forms.ToolStrip> movible colocándola un <xref:System.Windows.Forms.ToolStripPanel> y estableciendo su <xref:System.Windows.Forms.ToolStrip.GripStyle%2A> a <xref:System.Windows.Forms.ToolStripGripStyle.Visible>.  
  
##### <a name="other-layout-options"></a>Otras opciones de diseño  
 Las demás opciones de diseño son <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> y <xref:System.Windows.Forms.ToolStripLayoutStyle.Table>.  
  
##### <a name="flow-layout"></a>Diseño de flujo  
 <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> diseño es el valor predeterminado para <xref:System.Windows.Forms.ContextMenuStrip>, <xref:System.Windows.Forms.ToolStripDropDownMenu>, y <xref:System.Windows.Forms.ToolStripOverflow>. Es similar a la <xref:System.Windows.Forms.FlowLayoutPanel>. Las características de <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> diseño son los siguientes:  
  
-   Todas las características de <xref:System.Windows.Forms.FlowLayoutPanel> expuestas por la <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A> propiedad. Primero debe convertir el <xref:System.Windows.Forms.LayoutSettings> clase a un <xref:System.Windows.Forms.FlowLayoutSettings> clase.  
  
-   Puede usar el <xref:System.Windows.Forms.ToolStripItem.Dock%2A> y <xref:System.Windows.Forms.ToolStripItem.Anchor%2A> propiedades en el código para alinear los elementos dentro de la fila.  
  
-   Se omite la propiedad <xref:System.Windows.Forms.ToolStripItem.Alignment%2A>.  
  
-   En el <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> eventos, puede inspeccionar el <xref:System.Windows.Forms.ToolStripItem.Placement%2A> propiedad para determinar si un elemento se colocó en el método main <xref:System.Windows.Forms.ToolStrip> o no se ajustaban.  
  
-   No se representa el control y por lo tanto, un <xref:System.Windows.Forms.ToolStrip> en <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> estilo de diseño en un <xref:System.Windows.Forms.ToolStripPanel> no se puede mover.  
  
-   El <xref:System.Windows.Forms.ToolStrip> no se representa el botón de desbordamiento, y <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> se omite.  
  
##### <a name="table-layout"></a>Diseño de tabla  
 <xref:System.Windows.Forms.ToolStripLayoutStyle.Table> diseño es el valor predeterminado para <xref:System.Windows.Forms.StatusStrip>. Es similar a <xref:System.Windows.Forms.TableLayoutPanel>. Las características de <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> diseño son los siguientes:  
  
-   Todas las características de <xref:System.Windows.Forms.TableLayoutPanel> expuestas por la <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A> propiedad. Primero debe convertir el <xref:System.Windows.Forms.LayoutSettings> clase a un <xref:System.Windows.Forms.TableLayoutSettings> clase.  
  
-   Puede usar el <xref:System.Windows.Forms.ToolStripItem.Dock%2A> y <xref:System.Windows.Forms.ToolStripItem.Anchor%2A> propiedades en el código para alinear los elementos dentro de la celda de tabla.  
  
-   Se omite la propiedad <xref:System.Windows.Forms.ToolStripItem.Alignment%2A>.  
  
-   En el <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> eventos, puede inspeccionar el <xref:System.Windows.Forms.ToolStripItem.Placement%2A> propiedad para determinar si un elemento se colocó en el método main <xref:System.Windows.Forms.ToolStrip> o no se ajustaban.  
  
-   No se representa el control y por lo tanto, un <xref:System.Windows.Forms.ToolStrip> en <xref:System.Windows.Forms.ToolStripLayoutStyle.Table> estilo de diseño en un <xref:System.Windows.Forms.ToolStripPanel> no se puede mover.  
  
-   El <xref:System.Windows.Forms.ToolStrip> no se representa el botón de desbordamiento, y <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> se omite.  
  
## <a name="toolstripitem"></a>ToolStripItem  
 Los temas siguientes describen <xref:System.Windows.Forms.ToolStripItem> y los controles que derivan de ella.  
  
 <xref:System.Windows.Forms.ToolStripItem> es la clase base abstracta para todos los elementos que se incluyen en un <xref:System.Windows.Forms.ToolStrip>. El siguiente objeto de modelo se muestra en el <xref:System.Windows.Forms.ToolStripItem> jerarquía de herencia.  
  
 ![Diagrama que muestra el modelo de objeto ToolStripItem.](./media/toolstrip-control-architecture/toolstripitem-object-model.gif)  
  
 <xref:System.Windows.Forms.ToolStripItem> las clases que heredan directamente de <xref:System.Windows.Forms.ToolStripItem>, o heredan indirectamente <xref:System.Windows.Forms.ToolStripItem> a través de <xref:System.Windows.Forms.ToolStripControlHost> o <xref:System.Windows.Forms.ToolStripDropDownItem>.  
  
 <xref:System.Windows.Forms.ToolStripItem> los controles deben encontrarse en un <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.StatusStrip>, o <xref:System.Windows.Forms.ContextMenuStrip> y no se puede agregar directamente a un formulario. Las distintas clases de contenedor están diseñadas para contener un subconjunto apropiado de <xref:System.Windows.Forms.ToolStripItem> controles.  
  
 En la tabla siguiente se enumera las existencias <xref:System.Windows.Forms.ToolStripItem> controles y los contenedores en el que se ven mejor. Aunque cualquier <xref:System.Windows.Forms.ToolStrip> elemento puede hospedarse en cualquier <xref:System.Windows.Forms.ToolStrip>-derivado contenedor, estos elementos se han diseñado para verse mejor en los contenedores siguientes:  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStripDropDown> no aparece en el cuadro de herramientas de diseñador.  
  
|Elemento contenido|ToolStrip|MenuStrip|ContextMenuStrip|StatusStrip|ToolStripDropDown|  
|--------------------|---------------|---------------|----------------------|-----------------|-----------------------|  
|<xref:System.Windows.Forms.ToolStripButton>|Sí|No|No|No|Sí|  
|<xref:System.Windows.Forms.ToolStripComboBox>|Sí|Sí|Sí|No|Sí|  
|<xref:System.Windows.Forms.ToolStripSplitButton>|Sí|No|No|Sí|Sí|  
|<xref:System.Windows.Forms.ToolStripLabel>|Sí|No|No|Sí|Sí|  
|<xref:System.Windows.Forms.ToolStripSeparator>|Sí|Sí|Sí|No|Sí|  
|<xref:System.Windows.Forms.ToolStripDropDownButton>|Sí|No|No|Sí|Sí|  
|<xref:System.Windows.Forms.ToolStripTextBox>|Sí|Sí|Sí|No|Sí|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|No|Sí|Sí|No|No|  
|<xref:System.Windows.Forms.ToolStripStatusLabel>|No|No|No|Sí|No|  
|<xref:System.Windows.Forms.ToolStripProgressBar>|Sí|No|No|Sí|No|  
|<xref:System.Windows.Forms.ToolStripControlHost>|Sí|Sí|No|Sí|Sí|  
  
### <a name="toolstripbutton"></a>ToolStripButton  
 <xref:System.Windows.Forms.ToolStripButton> el elemento de botón para <xref:System.Windows.Forms.ToolStrip>. Puede mostrarlo con varios estilos de borde y se puede usar para representar y activar estados operativos. También puede definir para que tiene el foco de forma predeterminada.  
  
### <a name="toolstriplabel"></a>ToolStripLabe  
 El <xref:System.Windows.Forms.ToolStripLabel> proporciona una funcionalidad de etiqueta <xref:System.Windows.Forms.ToolStrip> controles. El <xref:System.Windows.Forms.ToolStripLabel> es similar a un <xref:System.Windows.Forms.ToolStripButton> que no obtiene el foco de forma predeterminada y que no se representará como presionado ni resaltado.  
  
 <xref:System.Windows.Forms.ToolStripLabel> es compatible con las claves de acceso como un elemento hospedado.  
  
 Use la <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>, y <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> propiedades en un <xref:System.Windows.Forms.ToolStripLabel> para admitir el control de vínculo en un <xref:System.Windows.Forms.ToolStrip>.  
  
### <a name="toolstripstatuslabel"></a>ToolStripStatusLabel  
 <xref:System.Windows.Forms.ToolStripStatusLabel> es una versión de <xref:System.Windows.Forms.ToolStripLabel> diseñado específicamente para su uso en <xref:System.Windows.Forms.StatusStrip>. Las características especiales incluyen <xref:System.Windows.Forms.ToolStripStatusLabel.BorderStyle%2A>, <xref:System.Windows.Forms.ToolStripStatusLabel.BorderSides%2A>, y <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>.  
  
### <a name="toolstripseparator"></a>ToolStripSeparator  
 El <xref:System.Windows.Forms.ToolStripSeparator> agrega una línea vertical u horizontal a una barra de herramientas o menú, según la orientación. Proporciona agrupación de o distinción entre elementos, como los de un menú.  
  
 Puede agregar un <xref:System.Windows.Forms.ToolStripSeparator> en tiempo de diseño al seleccionarlo en una lista desplegable. Sin embargo, puede crear automáticamente un <xref:System.Windows.Forms.ToolStripSeparator> escribiendo un guión (-) en el nodo de plantilla de diseñador o en el <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> método.  
  
### <a name="toolstripcontrolhost"></a>ToolStripControlHost  
 <xref:System.Windows.Forms.ToolStripControlHost> es la clase base abstracta para <xref:System.Windows.Forms.ToolStripComboBox>, <xref:System.Windows.Forms.ToolStripTextBox>, y <xref:System.Windows.Forms.ToolStripProgressBar>. <xref:System.Windows.Forms.ToolStripControlHost> puede hospedar otros controles, incluidos los controles personalizados, de dos maneras:  
  
-   Construir un <xref:System.Windows.Forms.ToolStripControlHost> con una clase que deriva de <xref:System.Windows.Forms.Control>. Para obtener acceso completamente el control hospedado y propiedades, primero debe convertir el <xref:System.Windows.Forms.ToolStripControlHost.Control%2A> propiedad a los datos reales de la clase representa.  
  
-   Extender <xref:System.Windows.Forms.ToolStripControlHost>y en el constructor predeterminado de la clase heredada, llame al constructor de clase base pasando una clase que deriva de <xref:System.Windows.Forms.Control>. Esta opción le permite encapsular los métodos de control comunes y propiedades para facilitar el acceso en un <xref:System.Windows.Forms.ToolStrip>.  
  
### <a name="toolstripcombobox"></a>ToolStripComboBox  
 <xref:System.Windows.Forms.ToolStripComboBox> es el <xref:System.Windows.Forms.ComboBox> optimizado para el hospedaje en un <xref:System.Windows.Forms.ToolStrip>. Un subconjunto de propiedades y los eventos del control hospedado se exponen en el <xref:System.Windows.Forms.ToolStripComboBox> nivel, pero subyacente <xref:System.Windows.Forms.ComboBox> control es totalmente accesible a través de la <xref:System.Windows.Forms.ToolStripComboBox.ComboBox%2A> propiedad.  
  
### <a name="toolstriptextbox"></a>ToolStripTextBox  
 <xref:System.Windows.Forms.ToolStripTextBox> es el <xref:System.Windows.Forms.TextBox> optimizado para el hospedaje en un <xref:System.Windows.Forms.ToolStrip>. Un subconjunto de propiedades y los eventos del control hospedado se exponen en el <xref:System.Windows.Forms.ToolStripTextBox> nivel, pero subyacente <xref:System.Windows.Forms.TextBox> control es totalmente accesible a través de la <xref:System.Windows.Forms.ToolStripTextBox.TextBox%2A> propiedad.  
  
### <a name="toolstripprogressbar"></a>ToolStripProgressBar  
 <xref:System.Windows.Forms.ToolStripProgressBar> es el <xref:System.Windows.Forms.ProgressBar> optimizado para el hospedaje en un <xref:System.Windows.Forms.ToolStrip>. Un subconjunto de propiedades y los eventos del control hospedado se exponen en el <xref:System.Windows.Forms.ToolStripProgressBar> nivel, pero subyacente <xref:System.Windows.Forms.ProgressBar> control es totalmente accesible a través de la <xref:System.Windows.Forms.ToolStripProgressBar.ProgressBar%2A> propiedad.  
  
### <a name="toolstripdropdownitem"></a>ToolStripDropDownItem  
 <xref:System.Windows.Forms.ToolStripDropDownItem> es la clase base abstracta para <xref:System.Windows.Forms.ToolStripMenuItem>, <xref:System.Windows.Forms.ToolStripDropDownButton>, y <xref:System.Windows.Forms.ToolStripSplitButton>, que puede hospedar elementos directamente u hospedar elementos adicionales en un contenedor de lista desplegable. Hacerlo estableciendo la <xref:System.Windows.Forms.ToolStripDropDownItem.DropDown%2A> propiedad a un <xref:System.Windows.Forms.ToolStripDropDown> y estableciendo el <xref:System.Windows.Forms.ToolStrip.Items%2A> propiedad de la <xref:System.Windows.Forms.ToolStripDropDown>. Obtener acceso a estos elementos de lista desplegable directamente a través del <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A> propiedad.  
  
### <a name="toolstripmenuitem"></a>ToolStripMenuItem  
 <xref:System.Windows.Forms.ToolStripMenuItem> es un <xref:System.Windows.Forms.ToolStripDropDownItem> que funciona con <xref:System.Windows.Forms.ToolStripDropDownMenu> y <xref:System.Windows.Forms.ContextMenuStrip> para controlar la disposición de resaltado, el diseño y la columna especial para los menús.  
  
### <a name="toolstripdropdownbutton"></a>ToolStripDropDownButton  
 <xref:System.Windows.Forms.ToolStripDropDownButton> similar a <xref:System.Windows.Forms.ToolStripButton>, pero muestra un área desplegable cuando el usuario hace clic en él. Mostrar u ocultar la flecha de lista desplegable estableciendo el <xref:System.Windows.Forms.ToolStripDropDownButton.ShowDropDownArrow%2A> propiedad. <xref:System.Windows.Forms.ToolStripDropDownButton> hosts de un <xref:System.Windows.Forms.ToolStripOverflowButton> que muestra los elementos que desbordan el <xref:System.Windows.Forms.ToolStrip>.  
  
### <a name="toolstripsplitbutton"></a>ToolStripSplitButton  
 <xref:System.Windows.Forms.ToolStripSplitButton> combina el botón y la funcionalidad del botón de lista desplegable.  
  
 Use la <xref:System.Windows.Forms.ToolStripSplitButton.DefaultItem%2A> propiedad para sincronizar el <xref:System.Windows.Forms.Control.Click> eventos del elemento desplegable elegido con el elemento que se muestra en el botón.  
  
### <a name="toolstripitem-generic-features"></a>Características genéricas de ToolStripItem  
 <xref:System.Windows.Forms.ToolStripItem> proporciona las siguientes características genéricas y opciones para los controles heredados:  
  
-   Eventos principales  
  
-   Manipulación de imágenes  
  
-   Alineación  
  
-   Relación de texto e imagen  
  
-   Estilo de presentación  
  
#### <a name="core-events"></a>Eventos principales  
 <xref:System.Windows.Forms.ToolStripItem> controles de reciben sus propios clic, mouse y eventos paint y pueden realizar el preprocesamiento también de teclado.  
  
#### <a name="image-handling"></a>Manipulación de imágenes  
 El <xref:System.Windows.Forms.ToolStripItem.Image%2A>, <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A>, <xref:System.Windows.Forms.ToolStripItem.ImageIndex%2A>, <xref:System.Windows.Forms.ToolStripItem.ImageKey%2A>, y <xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A> propiedades corresponden a varios aspectos del control de imagen. Usar imágenes en <xref:System.Windows.Forms.ToolStrip> controles al establecer estas propiedades directamente o mediante el establecimiento de la ejecución únicamente en tiempo de <xref:System.Windows.Forms.ToolStrip.ImageList%2A> propiedad.  
  
 Escalado de imagen viene determinada por la interacción de las propiedades de ambos <xref:System.Windows.Forms.ToolStrip> y <xref:System.Windows.Forms.ToolStripItem>, como sigue:  
  
-   <xref:System.Windows.Forms.ToolStrip.ImageScalingSize%2A> es la escala de la imagen final determinado por la combinación de la imagen <xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A> configuración y el contenedor <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> configuración.  
  
    -   Si <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> es `true` (predeterminado) y <xref:System.Windows.Forms.ToolStripItemImageScaling> es <xref:System.Windows.Forms.ToolStripItemImageScaling.SizeToFit>, se produce ningún ajuste de escala de imagen y el <xref:System.Windows.Forms.ToolStrip> es el tamaño de elemento más grande o un tamaño mínimo establecido.  
  
    -   Si <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> es `false` y <xref:System.Windows.Forms.ToolStripItemImageScaling> es <xref:System.Windows.Forms.ToolStripItemImageScaling.None>, ninguna imagen ni <xref:System.Windows.Forms.ToolStrip> escalado se produce.  
  
#### <a name="alignment"></a>Alineación  
 El valor de la <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> propiedad determina el final de la <xref:System.Windows.Forms.ToolStrip> en la que aparece un elemento. El <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> propiedad solo funciona cuando el estilo de diseño de la <xref:System.Windows.Forms.ToolStrip> se establece en uno de los valores de desbordamiento de pila.  
  
 Los elementos se colocan en el <xref:System.Windows.Forms.ToolStrip> en el orden en que los elementos aparecen en la colección de elementos. Para cambiar mediante programación un elemento donde está dispuesto, use el <xref:System.Windows.Forms.ToolStripItemCollection.Insert%2A> método para mover el elemento de la colección. Este método mueve el elemento pero no está duplicado.  
  
#### <a name="text-and-image-relationship"></a>Relación de imagen y texto  
 El <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> propiedad define la posición relativa de la imagen con respecto al texto en un <xref:System.Windows.Forms.ToolStripItem>. Los elementos que carecen de una imagen, texto o ambos se tratan como casos especiales para que la <xref:System.Windows.Forms.ToolStripItem> no muestra una zona vacía para el elemento que falta o elementos.  
  
#### <a name="display-style"></a>Estilo de presentación  
 <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> permite establecer los valores de propiedades de un elemento de texto e imagen al mostrar sólo lo que desea. Esto se usa normalmente para cambiar el estilo de presentación sólo cuando se muestre el mismo elemento en un contexto diferente.  
  
## <a name="accessory-classes"></a>Clases de accesorios  
 Las clases que proporcionan otras funcionalidades incluyen:  
  
-   <xref:System.Windows.Forms.ToolStripManager> admite <xref:System.Windows.Forms.ToolStrip>-relacionados con las tareas para aplicaciones completas, como las opciones de combinación, la configuración y el representador.  
  
-   <xref:System.Windows.Forms.ToolStripRenderer> le permite aplicar un estilo determinado o un tema a un <xref:System.Windows.Forms.ToolStrip> fácilmente.  
  
-   <xref:System.Windows.Forms.ToolStripProfessionalRenderer> crea los lápices y pinceles basados en una tabla de colores reemplazables (<xref:System.Windows.Forms.ProfessionalColorTable>).  
  
-   <xref:System.Windows.Forms.ToolStripSystemRenderer> se aplica a los colores del sistema y un estilo visual plano a <xref:System.Windows.Forms.ToolStrip> aplicaciones.  
  
-   <xref:System.Windows.Forms.ToolStripContainer> es similar a <xref:System.Windows.Forms.SplitContainer>. Utiliza cuatro paneles laterales acoplados (instancias de <xref:System.Windows.Forms.ToolStripPanel>) y un panel central (una instancia de <xref:System.Windows.Forms.ToolStripContentPanel>) para crear una organización típica. No se puede quitar los paneles laterales, pero puede ocultarlos. No puede quitar ni ocultar el panel central. Puede organizar uno o varios <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, o <xref:System.Windows.Forms.StatusStrip> controles en los paneles laterales y pueden usar el panel central para otros controles. El <xref:System.Windows.Forms.ToolStripContentPanel> también proporciona una manera de obtener soporte técnico de representador en el cuerpo del formulario para una apariencia coherente. <xref:System.Windows.Forms.ToolStripContainer> no se admite la interfaz de múltiples documentos (MDI).  
  
-   <xref:System.Windows.Forms.ToolStripPanel> Proporciona espacio para mover y organizar <xref:System.Windows.Forms.ToolStrip> controles. Si lo prefiere, puede usar sólo un panel y <xref:System.Windows.Forms.ToolStripPanel> funciona bien en escenarios MDI.  
  
## <a name="see-also"></a>Vea también

- [Información sobre el control ToolStrip](toolstrip-control-overview-windows-forms.md)
- [Resumen de la tecnología ToolStrip](toolstrip-technology-summary.md)
- [Control ToolStrip](toolstrip-control-windows-forms.md)
- [Control MenuStrip](menustrip-control-windows-forms.md)
- [StatusStrip (control)](statusstrip-control.md)
- [ContextMenuStrip (Control)](contextmenustrip-control.md)
- [BindingNavigator (control)](bindingnavigator-control-windows-forms.md)
