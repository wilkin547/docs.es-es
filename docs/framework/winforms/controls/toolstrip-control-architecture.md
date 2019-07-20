---
title: Arquitectura del control ToolStrip
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], architecture
ms.assetid: 71df2d18-862e-4701-9ff9-c1fe606f94f2
ms.openlocfilehash: d0a1441e9bae8d2c1f938e7399c11e736708da4d
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2019
ms.locfileid: "68363829"
---
# <a name="toolstrip-control-architecture"></a>Arquitectura del control ToolStrip

Las <xref:System.Windows.Forms.ToolStrip> clases <xref:System.Windows.Forms.ToolStripItem> y proporcionan un sistema flexible y extensible para mostrar la barra de herramientas, el estado y los elementos de menú. Todas estas clases están contenidas <xref:System.Windows.Forms> en el espacio de nombres y todas se denominan normalmente con el prefijo " <xref:System.Windows.Forms.ToolStripOverflow>ToolStrip" (como) o con el sufijo "strip <xref:System.Windows.Forms.MenuStrip>" (por ejemplo,).

## <a name="toolstrip"></a>ToolStrip

En los temas siguientes <xref:System.Windows.Forms.ToolStrip> se describen y los controles que derivan de él.

<xref:System.Windows.Forms.ToolStrip>es la clase base abstracta para <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.StatusStrip>y <xref:System.Windows.Forms.ContextMenuStrip>. En el modelo de objetos siguiente <xref:System.Windows.Forms.ToolStrip> se muestra la jerarquía de herencia.

![Diagrama que muestra el modelo de objetos ToolStrip.](./media/toolstrip-control-architecture/toolstrip-object-model.gif)

Puede tener acceso a todos los elementos de <xref:System.Windows.Forms.ToolStrip> a través <xref:System.Windows.Forms.ToolStrip.Items%2A> de la colección. Puede tener acceso a todos los elementos de <xref:System.Windows.Forms.ToolStripDropDownItem> a través <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A> de la colección. En una clase derivada de <xref:System.Windows.Forms.ToolStrip>, también puede utilizar la <xref:System.Windows.Forms.ToolStrip.DisplayedItems%2A> propiedad para tener acceso únicamente a los elementos que se muestran actualmente. Estos son los elementos que no están actualmente en un menú de desbordamiento.

Los elementos siguientes están diseñados específicamente para funcionar sin problemas con <xref:System.Windows.Forms.ToolStripSystemRenderer> y <xref:System.Windows.Forms.ToolStripProfessionalRenderer> en todas las orientaciones. Están disponibles de forma predeterminada en tiempo de diseño para <xref:System.Windows.Forms.ToolStrip> el control:

- <xref:System.Windows.Forms.ToolStripButton>

- <xref:System.Windows.Forms.ToolStripSeparator>

- <xref:System.Windows.Forms.ToolStripLabel>

- <xref:System.Windows.Forms.ToolStripDropDownButton>

- <xref:System.Windows.Forms.ToolStripSplitButton>

- <xref:System.Windows.Forms.ToolStripTextBox>

- <xref:System.Windows.Forms.ToolStripComboBox>

### <a name="menustrip"></a>MenuStrip

<xref:System.Windows.Forms.MenuStrip>es el contenedor de nivel superior que reemplaza <xref:System.Windows.Forms.MainMenu>a. También proporciona funciones de control de claves y de interfaz de múltiples documentos (MDI). Funcionalmente <xref:System.Windows.Forms.ToolStripMenuItem> <xref:System.Windows.Forms.MenuStrip>y funcionan junto con, aunque se derivan de <xref:System.Windows.Forms.ToolStripItem>. <xref:System.Windows.Forms.ToolStripDropDownItem>

Los elementos siguientes están diseñados específicamente para funcionar sin problemas con <xref:System.Windows.Forms.ToolStripSystemRenderer> y <xref:System.Windows.Forms.ToolStripProfessionalRenderer> en todas las orientaciones. Están disponibles de forma predeterminada en tiempo de diseño para <xref:System.Windows.Forms.MenuStrip> el control:

- <xref:System.Windows.Forms.ToolStripMenuItem>

- <xref:System.Windows.Forms.ToolStripTextBox>

- <xref:System.Windows.Forms.ToolStripComboBox>

### <a name="statusstrip"></a>StatusStrip

<xref:System.Windows.Forms.StatusStrip>reemplaza el <xref:System.Windows.Forms.StatusBar> control. Entre las características <xref:System.Windows.Forms.StatusStrip> especiales de se incluyen un diseño de tabla personalizado, la compatibilidad con el ajuste de tamaño y el `Spring` desplazamiento del formulario, y <xref:System.Windows.Forms.ToolStripStatusLabel> la propiedad, que permite a un para rellenar el espacio disponible automáticamente.

Los elementos siguientes están diseñados específicamente para funcionar sin problemas con <xref:System.Windows.Forms.ToolStripSystemRenderer> y <xref:System.Windows.Forms.ToolStripProfessionalRenderer> en todas las orientaciones. Están disponibles de forma predeterminada en tiempo de diseño para <xref:System.Windows.Forms.StatusStrip> el control:

- <xref:System.Windows.Forms.ToolStripStatusLabel>

- <xref:System.Windows.Forms.ToolStripDropDownButton>

- <xref:System.Windows.Forms.ToolStripSplitButton>

- <xref:System.Windows.Forms.ToolStripProgressBar>

### <a name="contextmenustrip"></a>ContextMenuStrip

<xref:System.Windows.Forms.ContextMenuStrip> reemplaza a <xref:System.Windows.Forms.ContextMenu>. Puede asociar un <xref:System.Windows.Forms.ContextMenuStrip> a cualquier control y hacer clic con el botón derecho automáticamente en el menú contextual (o menú contextual). Puede mostrar un <xref:System.Windows.Forms.ContextMenuStrip> mediante programación con el <xref:System.Windows.Forms.ToolStripDropDown.Show%2A> método. <xref:System.Windows.Forms.ContextMenuStrip>admite eventos <xref:System.Windows.Forms.ToolStripDropDown.Opening> cancelables <xref:System.Windows.Forms.ToolStripDropDown.Closing> y para administrar escenarios de rellenado dinámico y de varios clics. <xref:System.Windows.Forms.ContextMenuStrip>admite imágenes, estado de comprobación de elementos de menú, texto, claves de acceso, accesos directos y menús en cascada.

Los elementos siguientes están diseñados específicamente para funcionar sin problemas con <xref:System.Windows.Forms.ToolStripSystemRenderer> y <xref:System.Windows.Forms.ToolStripProfessionalRenderer> en todas las orientaciones. Están disponibles de forma predeterminada en tiempo de diseño para <xref:System.Windows.Forms.ContextMenuStrip> el control:

- <xref:System.Windows.Forms.ToolStripMenuItem>

- <xref:System.Windows.Forms.ToolStripSeparator>

- <xref:System.Windows.Forms.ToolStripTextBox>

- <xref:System.Windows.Forms.ToolStripComboBox>

### <a name="toolstrip-generic-features"></a>Características genéricas de ToolStrip

En los temas siguientes se describen las características y el comportamiento genéricos de los <xref:System.Windows.Forms.ToolStrip> controles derivados de y.

#### <a name="painting"></a>Vuelva

Puede realizar una representación personalizada en <xref:System.Windows.Forms.ToolStrip> los controles de varias maneras. Como con otros controles Windows Forms <xref:System.Windows.Forms.ToolStrip> , y <xref:System.Windows.Forms.ToolStripItem> tienen `OnPaint` métodos y `Paint` eventos reemplazables. Al igual que con la pintura normal, el sistema de coordenadas es relativo al área cliente del control. es decir, la esquina superior izquierda del control es 0,0. El `Paint` evento y `OnPaint` el método de <xref:System.Windows.Forms.ToolStripItem> un se comportan como otros eventos de dibujo de control.

Los <xref:System.Windows.Forms.ToolStrip> controles también proporcionan un acceso más preciso a la representación de los elementos y el contenedor <xref:System.Windows.Forms.ToolStripRenderer> a través de la clase, que tiene métodos reemplazables para dibujar el fondo, el fondo del elemento, la imagen del elemento, la flecha del elemento, el texto del elemento y el borde de la <xref:System.Windows.Forms.ToolStrip>. Los argumentos de evento de estos métodos exponen varias propiedades como rectángulos, colores y formatos de texto que se pueden ajustar según se desee.

Para ajustar solo algunos aspectos de cómo se pinta un elemento, normalmente se invalida el <xref:System.Windows.Forms.ToolStripRenderer>.

Si está escribiendo un nuevo elemento y desea controlar todos los aspectos del dibujo, invalide el `OnPaint` método. Desde, puede usar los métodos <xref:System.Windows.Forms.ToolStripRenderer>de. `OnPaint`

De forma predeterminada, <xref:System.Windows.Forms.ToolStrip> se almacena en búfer doble y se aprovecha la <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> configuración.

#### <a name="parenting"></a>Relación jerárquica

El concepto de propiedad del contenedor y del control parental es más complejo <xref:System.Windows.Forms.ToolStrip> en los controles que en otros controles contenedor de Windows Forms. Esto es necesario para admitir escenarios dinámicos como el desbordamiento, el uso compartido de elementos desplegables en varios <xref:System.Windows.Forms.ToolStrip> elementos y para admitir la generación de un <xref:System.Windows.Forms.ContextMenuStrip> desde un control.

En la lista siguiente se describen los miembros relacionados con el control parental y se explica su uso.

- <xref:System.Windows.Forms.ToolStripDropDown.OwnerItem%2A>obtiene acceso al elemento que es el origen del elemento desplegable. Esto es similar a <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A>, pero en lugar de devolver un control, <xref:System.Windows.Forms.ToolStripItem>devuelve.

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A>determina qué control es el origen de <xref:System.Windows.Forms.ContextMenuStrip> cuando varios controles comparten el mismo. <xref:System.Windows.Forms.ContextMenuStrip>

- <xref:System.Windows.Forms.ToolStripItem.GetCurrentParent%2A>es un descriptor de acceso de <xref:System.Windows.Forms.ToolStripItem.Parent%2A> solo lectura a la propiedad. Un elemento primario se diferencia de un propietario en que un elemento primario denota el actual <xref:System.Windows.Forms.ToolStrip> devuelto en el que se muestra el elemento, que puede estar en el área de desbordamiento.

- <xref:System.Windows.Forms.ToolStripItem.Owner%2A>Devuelve el <xref:System.Windows.Forms.ToolStrip> cuya colección de elementos contiene el <xref:System.Windows.Forms.ToolStripItem>actual. Esta es la mejor manera de hacer <xref:System.Windows.Forms.ToolStrip.ImageList%2A> referencia u otras propiedades en el nivel <xref:System.Windows.Forms.ToolStrip> superior sin escribir código especial para controlar el desbordamiento.

#### <a name="behavior-of-inherited-controls"></a>Comportamiento de los controles heredados

Los controles siguientes se bloquean siempre que se usan en la herencia:

- <xref:System.Windows.Forms.ToolStrip>

- <xref:System.Windows.Forms.MenuStrip>

- <xref:System.Windows.Forms.ContextMenuStrip>

- <xref:System.Windows.Forms.StatusStrip>

- <xref:System.Windows.Forms.ToolStripPanel>Esto incluye los paneles en <xref:System.Windows.Forms.ToolStripContainer> y también los controles individuales. <xref:System.Windows.Forms.ToolStripPanel>

Por ejemplo, cree una nueva aplicación de Windows Forms con uno o varios de los controles de la lista anterior. Establezca el modificador de acceso de uno o varios controles `public` en `protected`o y, a continuación, compile el proyecto. Agregue un formulario que herede del primer formulario y, a continuación, seleccione un control heredado. El control parece bloqueado y se comporta como si su modificador de acceso `private`fuera.

#### <a name="toolstripcontainer-support-of-inheritance"></a>Compatibilidad de ToolStripContainer con la herencia

El <xref:System.Windows.Forms.ToolStripContainer> control admite escenarios heredados limitados, similar al ejemplo siguiente:

1. Cree una nueva aplicación de Windows Forms.

2. Agregue un control <xref:System.Windows.Forms.ToolStripContainer> al formulario.

3. Establezca el modificador de acceso de <xref:System.Windows.Forms.ToolStripContainer> en `public` o `protected`.

4. Agregue cualquier combinación de <xref:System.Windows.Forms.ToolStrip>controles <xref:System.Windows.Forms.MenuStrip>, y <xref:System.Windows.Forms.ContextMenuStrip> a las <xref:System.Windows.Forms.ToolStripPanel> regiones de <xref:System.Windows.Forms.ToolStripContainer>.

5. Compile el proyecto.

6. Agregue un formulario que herede del primer formulario.

7. Seleccione el heredado <xref:System.Windows.Forms.ToolStripContainer> en el formulario.

#### <a name="inherited-behavior-of-child-controls"></a>Comportamiento heredado de los controles secundarios

Después de completar los pasos anteriores, se produce el siguiente comportamiento heredado:

- En el diseñador, el control aparece con un icono heredado.

- Los <xref:System.Windows.Forms.ToolStripPanel> controles están bloqueados; no se puede seleccionar ni reorganizar el contenido.

- Puede Agregar controles a <xref:System.Windows.Forms.ToolStripContentPanel>, mover los controles y convertirlos en controles secundarios <xref:System.Windows.Forms.ToolStripContentPanel>de.

- Los cambios se conservan después de compilar el formulario.

  > [!NOTE]
  > Quite los modificadores de acceso de <xref:System.Windows.Forms.ToolStripPanel> todos los controles que forman parte <xref:System.Windows.Forms.ToolStripContainer>de un. El modificador de acceso de <xref:System.Windows.Forms.ToolStripContainer> controla todo el control.

#### <a name="partial-trust"></a>Confianza parcial

Las limitaciones de `ToolStrip`s en confianza parcial están diseñadas para evitar la entrada involuntaria de información personal que podrían utilizar personas o servicios no autorizados. Las medidas de protección son las siguientes:

- `ToolStripDropDown`los controles <xref:System.Security.Permissions.UIPermissionWindow.AllWindows> requieren para mostrar los elementos <xref:System.Windows.Forms.ToolStripControlHost>en un. Esto se aplica a los controles intrínsecos <xref:System.Windows.Forms.ToolStripTextBox>como <xref:System.Windows.Forms.ToolStripComboBox>, y <xref:System.Windows.Forms.ToolStripProgressBar> , así como a los controles creados por el usuario. Si no se cumple este requisito, no se muestran estos elementos. No se inicia ninguna excepción.

- No se <xref:System.Windows.Forms.ToolStripDropDown.AutoClose%2A> permite establecer `false` la propiedad en y se omite el parámetro <xref:System.Windows.Forms.ToolStripDropDown.Closing> de evento cancelable. Esto hace que sea imposible entrar más de una pulsación de tecla sin descartar el elemento desplegable. Si no se cumple este requisito, no se muestran estos elementos. No se inicia ninguna excepción.

- No se producirán muchos eventos de control de pulsaciones de teclas Si se producen en contextos de confianza parcial que no sean <xref:System.Security.Permissions.UIPermissionWindow.AllWindows>.

- No se procesan las claves <xref:System.Security.Permissions.UIPermissionWindow.AllWindows> de acceso cuando no se concede.

#### <a name="usage"></a>Uso

Los siguientes patrones de uso tienen un cojinete <xref:System.Windows.Forms.ToolStrip> en el diseño, la interacción con el teclado y el comportamiento del usuario final:

- Se combina en un<xref:System.Windows.Forms.ToolStripPanel>

  Se puede cambiar de posición <xref:System.Windows.Forms.ToolStripPanel> dentro de y entre <xref:System.Windows.Forms.ToolStripPanel>s. <xref:System.Windows.Forms.ToolStrip> Se `Dock` omite la propiedad y, si la <xref:System.Windows.Forms.ToolStrip.Stretch%2A> propiedad es `false`, el tamaño del <xref:System.Windows.Forms.ToolStrip> crece a medida que se agregan elementos <xref:System.Windows.Forms.ToolStripPanel>a. Normalmente, <xref:System.Windows.Forms.ToolStrip> no participa en el orden de tabulación.

- Acoplado

  <xref:System.Windows.Forms.ToolStrip> Se coloca en un lado de un contenedor en una posición fija y su tamaño se expande sobre todo el borde al que está acoplado. Normalmente, <xref:System.Windows.Forms.ToolStrip> no participa en el orden de tabulación.

- Posición absoluta

  Es como otros controles, en que se coloca por la <xref:System.Windows.Forms.Control.Location%2A> propiedad, tiene un tamaño fijo y normalmente participa en el orden de tabulación. <xref:System.Windows.Forms.ToolStrip>

#### <a name="keyboard-interaction"></a>Interacción con el teclado

##### <a name="access-keys"></a>Claves de acceso

Junto con o después de la tecla ALT, las teclas de acceso son una manera de activar un control mediante el teclado. <xref:System.Windows.Forms.ToolStrip>admite claves de acceso explícitas e implícitas. La definición explícita usa un carácter de y comercial (&) que precede a la letra. La definición implícita usa un algoritmo que intenta buscar un elemento coincidente según el orden de los caracteres de una propiedad `Text` determinada.

##### <a name="shortcut-keys"></a>Teclas de método abreviado

Las teclas de método abreviado <xref:System.Windows.Forms.MenuStrip> utilizadas por utilizan una combinación <xref:System.Windows.Forms.Keys> de la enumeración (que no es específica del orden) para definir la tecla de método abreviado. También puede usar la <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> propiedad para mostrar una tecla de método abreviado solo con texto, como mostrar "del" en lugar de "eliminar".

##### <a name="navigation"></a>Navegación

La tecla Alt activa el <xref:System.Windows.Forms.MenuStrip> señalado por. <xref:System.Windows.Forms.Form.MainMenuStrip%2A> Desde ahí, Ctrl + Tab navega entre <xref:System.Windows.Forms.ToolStrip> los controles de `ToolStripPanel`s. La tecla TAB y las teclas de dirección del teclado numérico navegan entre los elementos <xref:System.Windows.Forms.ToolStrip>de un. Un algoritmo especial controla la navegación en la región de desbordamiento. La barra espaciadora <xref:System.Windows.Forms.ToolStripDropDownButton>selecciona un <xref:System.Windows.Forms.ToolStripSplitButton> <xref:System.Windows.Forms.ToolStripButton>, o.

##### <a name="focus-and-validation"></a>Foco y validación

Cuando se activa mediante la tecla Alt, <xref:System.Windows.Forms.MenuStrip> o <xref:System.Windows.Forms.ToolStrip> no suelen tomar ni quitar el foco del control que tiene actualmente el foco. Si hay un control hospedado dentro de <xref:System.Windows.Forms.MenuStrip> la o una lista desplegable <xref:System.Windows.Forms.MenuStrip>de, el control obtiene el foco cuando el usuario presiona la tecla TAB. En general, los <xref:System.Windows.Forms.Control.GotFocus>eventos <xref:System.Windows.Forms.Control.LostFocus>, <xref:System.Windows.Forms.Control.Enter>, y <xref:System.Windows.Forms.Control.Leave> de <xref:System.Windows.Forms.MenuStrip> podrían no producirse cuando se activan con el teclado. En estos casos, use los <xref:System.Windows.Forms.MenuStrip.MenuActivate> eventos <xref:System.Windows.Forms.MenuStrip.MenuDeactivate> y en su lugar.

De forma predeterminada <xref:System.Windows.Forms.ToolStrip.CausesValidation%2A> , `false`es. Llame <xref:System.Windows.Forms.ContainerControl.Validate%2A> a explícitamente en el formulario para realizar la validación.

#### <a name="layout"></a>Diseño

Puede controlar <xref:System.Windows.Forms.ToolStrip> el diseño eligiendo uno de los miembros <xref:System.Windows.Forms.ToolStripLayoutStyle> de con <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> la propiedad.

##### <a name="stack-layouts"></a>Diseños de pila

La apilación es la organización de elementos al lado de otros en ambos extremos de <xref:System.Windows.Forms.ToolStrip>. En la lista siguiente se describen los diseños de pila.

- <xref:System.Windows.Forms.ToolStripLayoutStyle.StackWithOverflow>es el valor predeterminado. Esta configuración hace <xref:System.Windows.Forms.ToolStrip> que modifique su diseño automáticamente de acuerdo con la propiedad <xref:System.Windows.Forms.ToolStrip.Orientation%2A> para controlar los escenarios de arrastre y acoplamiento.

- <xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow>representa verticalmente <xref:System.Windows.Forms.ToolStrip> los elementos que se encuentran al lado del otro.

- <xref:System.Windows.Forms.ToolStripLayoutStyle.HorizontalStackWithOverflow>representa los elementos <xref:System.Windows.Forms.ToolStrip> al lado de otros horizontalmente.

##### <a name="other-features-of-stack-layouts"></a>Otras características de los diseños de pila

<xref:System.Windows.Forms.ToolStripItem.Alignment%2A>determina el final del <xref:System.Windows.Forms.ToolStrip> objeto en el que se alinea el elemento.

Cuando los elementos no caben en <xref:System.Windows.Forms.ToolStrip>el, aparece automáticamente un botón de desbordamiento. El <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> valor de la propiedad determina si un elemento aparece siempre en el área de desbordamiento, según sea necesario, o nunca.

En el <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> evento, puede inspeccionar la <xref:System.Windows.Forms.ToolStripItem.Placement%2A> propiedad para determinar si un elemento se colocó en el principal <xref:System.Windows.Forms.ToolStrip>, el desbordamiento <xref:System.Windows.Forms.ToolStrip>o si no se muestra actualmente en absoluto. Los motivos típicos por los que no se muestra un elemento son que el elemento no quepa en el <xref:System.Windows.Forms.ToolStrip> principal y <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> su propiedad se haya <xref:System.Windows.Forms.ToolStripItemOverflow.Never>establecido en.

Haga que <xref:System.Windows.Forms.ToolStrip> un móvil lo coloque en un <xref:System.Windows.Forms.ToolStripPanel> y establezca su <xref:System.Windows.Forms.ToolStrip.GripStyle%2A> en <xref:System.Windows.Forms.ToolStripGripStyle.Visible>.

##### <a name="other-layout-options"></a>Otras opciones de diseño

Las demás opciones de diseño <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> son <xref:System.Windows.Forms.ToolStripLayoutStyle.Table>y.

##### <a name="flow-layout"></a>Diseño de flujo

<xref:System.Windows.Forms.ToolStripLayoutStyle.Flow>el diseño es el valor <xref:System.Windows.Forms.ContextMenuStrip>predeterminado <xref:System.Windows.Forms.ToolStripDropDownMenu>para, <xref:System.Windows.Forms.ToolStripOverflow>y. Es similar a <xref:System.Windows.Forms.FlowLayoutPanel>. Las características de <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> diseño son las siguientes:

- Todas las características de <xref:System.Windows.Forms.FlowLayoutPanel> se exponen mediante la <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A> propiedad. Debe convertir la <xref:System.Windows.Forms.LayoutSettings> clase en una <xref:System.Windows.Forms.FlowLayoutSettings> clase.

- Puede usar las <xref:System.Windows.Forms.ToolStripItem.Dock%2A> propiedades y <xref:System.Windows.Forms.ToolStripItem.Anchor%2A> en el código para alinear los elementos dentro de la fila.

- Se omite la propiedad <xref:System.Windows.Forms.ToolStripItem.Alignment%2A>.

- En el <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> evento, puede inspeccionar la <xref:System.Windows.Forms.ToolStripItem.Placement%2A> propiedad para determinar si un elemento se colocó en la principal <xref:System.Windows.Forms.ToolStrip> o no cabe.

- El control no se representa y, por tanto, <xref:System.Windows.Forms.ToolStrip> no <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> se <xref:System.Windows.Forms.ToolStripPanel> puede desplace un en el estilo de diseño de.

- El <xref:System.Windows.Forms.ToolStrip> botón de desbordamiento no se representa y <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> se omite.

##### <a name="table-layout"></a>Diseño de tabla

<xref:System.Windows.Forms.ToolStripLayoutStyle.Table>diseño es el valor predeterminado <xref:System.Windows.Forms.StatusStrip>para. Es similar a <xref:System.Windows.Forms.TableLayoutPanel>. Las características de <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> diseño son las siguientes:

- Todas las características de <xref:System.Windows.Forms.TableLayoutPanel> se exponen mediante la <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A> propiedad. Debe convertir la <xref:System.Windows.Forms.LayoutSettings> clase en una <xref:System.Windows.Forms.TableLayoutSettings> clase.

- Puede usar las <xref:System.Windows.Forms.ToolStripItem.Dock%2A> propiedades y <xref:System.Windows.Forms.ToolStripItem.Anchor%2A> en el código para alinear los elementos dentro de la celda de la tabla.

- Se omite la propiedad <xref:System.Windows.Forms.ToolStripItem.Alignment%2A>.

- En el <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> evento, puede inspeccionar la <xref:System.Windows.Forms.ToolStripItem.Placement%2A> propiedad para determinar si un elemento se colocó en la principal <xref:System.Windows.Forms.ToolStrip> o no cabe.

- El control no se representa y, por tanto, <xref:System.Windows.Forms.ToolStrip> no <xref:System.Windows.Forms.ToolStripLayoutStyle.Table> se <xref:System.Windows.Forms.ToolStripPanel> puede desplace un en el estilo de diseño de.

- El <xref:System.Windows.Forms.ToolStrip> botón de desbordamiento no se representa y <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> se omite.

## <a name="toolstripitem"></a>ToolStripItem

En los temas siguientes <xref:System.Windows.Forms.ToolStripItem> se describen y los controles que derivan de él.

<xref:System.Windows.Forms.ToolStripItem>es la clase base abstracta para todos los elementos que se incluyen en <xref:System.Windows.Forms.ToolStrip>. En el modelo de objetos siguiente <xref:System.Windows.Forms.ToolStripItem> se muestra la jerarquía de herencia.

![Diagrama que muestra el modelo de objetos ToolStripItem.](./media/toolstrip-control-architecture/toolstripitem-object-model.gif)

<xref:System.Windows.Forms.ToolStripItem>las clases heredan directamente <xref:System.Windows.Forms.ToolStripItem>de, o heredan indirectamente <xref:System.Windows.Forms.ToolStripControlHost> de <xref:System.Windows.Forms.ToolStripDropDownItem> <xref:System.Windows.Forms.ToolStripItem> a o.

<xref:System.Windows.Forms.ToolStripItem>los controles deben estar contenidos en <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.StatusStrip>o <xref:System.Windows.Forms.ContextMenuStrip> y no se pueden agregar directamente a un formulario. Las diversas clases de contenedor están diseñadas para contener un subconjunto <xref:System.Windows.Forms.ToolStripItem> de controles adecuado.

En la tabla siguiente se enumeran los controles estándar <xref:System.Windows.Forms.ToolStripItem> y los contenedores en los que se ven mejores. Aunque cualquier <xref:System.Windows.Forms.ToolStrip> elemento se puede hospedar en <xref:System.Windows.Forms.ToolStrip>cualquier contenedor derivado de, estos elementos se diseñaron para ser más adecuados en los siguientes contenedores:

> [!NOTE]
> <xref:System.Windows.Forms.ToolStripDropDown>no aparece en el cuadro de herramientas del diseñador.

|Elemento contenido|ToolStrip|MenuStrip|ContextMenuStrip|StatusStrip|ToolStripDropDown|
|--------------------|---------------|---------------|----------------------|-----------------|-----------------------|
|<xref:System.Windows.Forms.ToolStripButton>|Sí|Sin|Sin|No|Sí|
|<xref:System.Windows.Forms.ToolStripComboBox>|Sí|Sí|Sí|No|Sí|
|<xref:System.Windows.Forms.ToolStripSplitButton>|Sí|Sin|No|Sí|Sí|
|<xref:System.Windows.Forms.ToolStripLabel>|Sí|Sin|No|Sí|Sí|
|<xref:System.Windows.Forms.ToolStripSeparator>|Sí|Sí|Sí|No|Sí|
|<xref:System.Windows.Forms.ToolStripDropDownButton>|Sí|Sin|No|Sí|Sí|
|<xref:System.Windows.Forms.ToolStripTextBox>|Sí|Sí|Sí|No|Sí|
|<xref:System.Windows.Forms.ToolStripMenuItem>|No|Sí|Sí|Sin|Sin|
|<xref:System.Windows.Forms.ToolStripStatusLabel>|Sin|Sin|No|Sí|No|
|<xref:System.Windows.Forms.ToolStripProgressBar>|Sí|Sin|No|Sí|No|
|<xref:System.Windows.Forms.ToolStripControlHost>|Sí|Sí|No|Sí|Sí|

### <a name="toolstripbutton"></a>ToolStripButton

<xref:System.Windows.Forms.ToolStripButton>es el elemento de botón <xref:System.Windows.Forms.ToolStrip>para. Se puede mostrar con varios estilos de borde y se puede usar para representar y activar Estados operativos. También puede definirlo para que tenga el foco de forma predeterminada.

### <a name="toolstriplabel"></a>ToolStripLabel

Proporciona <xref:System.Windows.Forms.ToolStripLabel> la funcionalidad de etiqueta <xref:System.Windows.Forms.ToolStrip> en los controles. Es como un que <xref:System.Windows.Forms.ToolStripButton> no obtiene el foco de forma predeterminada y que no se representa como insertado o resaltado. <xref:System.Windows.Forms.ToolStripLabel>

<xref:System.Windows.Forms.ToolStripLabel>como un elemento hospedado admite claves de acceso.

Utilice las <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>propiedades <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>, y <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> en<xref:System.Windows.Forms.ToolStripLabel>para admitir el control de vínculos en. <xref:System.Windows.Forms.ToolStrip>

### <a name="toolstripstatuslabel"></a>ToolStripStatusLabel

<xref:System.Windows.Forms.ToolStripStatusLabel>es una versión de <xref:System.Windows.Forms.ToolStripLabel> diseñada específicamente para su uso <xref:System.Windows.Forms.StatusStrip>en. Las características especiales incluyen <xref:System.Windows.Forms.ToolStripStatusLabel.BorderStyle%2A>, <xref:System.Windows.Forms.ToolStripStatusLabel.BorderSides%2A>y <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>.

### <a name="toolstripseparator"></a>ToolStripSeparator

<xref:System.Windows.Forms.ToolStripSeparator> Agrega una línea vertical u horizontal a una barra de herramientas o un menú, dependiendo de la orientación. Proporciona agrupación o distinción entre elementos, como los de un menú.

Puede Agregar una <xref:System.Windows.Forms.ToolStripSeparator> en tiempo de diseño seleccionándola en una lista desplegable. Sin embargo, también puede crear automáticamente un <xref:System.Windows.Forms.ToolStripSeparator> escribiendo un guión (-) en el nodo de la plantilla del diseñador o en <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> el método.

### <a name="toolstripcontrolhost"></a>ToolStripControlHost

<xref:System.Windows.Forms.ToolStripControlHost>es la clase base abstracta para <xref:System.Windows.Forms.ToolStripComboBox>, <xref:System.Windows.Forms.ToolStripTextBox>y <xref:System.Windows.Forms.ToolStripProgressBar>. <xref:System.Windows.Forms.ToolStripControlHost>puede hospedar otros controles, incluidos los controles personalizados, de dos maneras:

- Construya un <xref:System.Windows.Forms.ToolStripControlHost> con una clase que deriva de <xref:System.Windows.Forms.Control>. Para tener acceso totalmente al control hospedado y a las propiedades, <xref:System.Windows.Forms.ToolStripControlHost.Control%2A> debe volver a convertir la propiedad en la clase real que representa.

- Extienda <xref:System.Windows.Forms.ToolStripControlHost>y, en el constructor sin parámetros de la clase heredada, llame al constructor de clase base pasando una clase que <xref:System.Windows.Forms.Control>deriva de. Esta opción permite ajustar métodos de control comunes y propiedades para facilitar el <xref:System.Windows.Forms.ToolStrip>acceso en.

### <a name="toolstripcombobox"></a>ToolStripComboBox

<xref:System.Windows.Forms.ToolStripComboBox>es el <xref:System.Windows.Forms.ComboBox> optimizado para el hospedaje <xref:System.Windows.Forms.ToolStrip>en un. En el <xref:System.Windows.Forms.ToolStripComboBox> nivel se exponen un subconjunto de propiedades y eventos del control hospedado, <xref:System.Windows.Forms.ComboBox> pero el control subyacente es totalmente <xref:System.Windows.Forms.ToolStripComboBox.ComboBox%2A> accesible a través de la propiedad.

### <a name="toolstriptextbox"></a>ToolStripTextBox

<xref:System.Windows.Forms.ToolStripTextBox>es el <xref:System.Windows.Forms.TextBox> optimizado para el hospedaje <xref:System.Windows.Forms.ToolStrip>en un. En el <xref:System.Windows.Forms.ToolStripTextBox> nivel se exponen un subconjunto de propiedades y eventos del control hospedado, <xref:System.Windows.Forms.TextBox> pero el control subyacente es totalmente <xref:System.Windows.Forms.ToolStripTextBox.TextBox%2A> accesible a través de la propiedad.

### <a name="toolstripprogressbar"></a>ToolStripProgressBar

<xref:System.Windows.Forms.ToolStripProgressBar>es el <xref:System.Windows.Forms.ProgressBar> optimizado para el hospedaje <xref:System.Windows.Forms.ToolStrip>en un. En el <xref:System.Windows.Forms.ToolStripProgressBar> nivel se exponen un subconjunto de propiedades y eventos del control hospedado, <xref:System.Windows.Forms.ProgressBar> pero el control subyacente es totalmente <xref:System.Windows.Forms.ToolStripProgressBar.ProgressBar%2A> accesible a través de la propiedad.

### <a name="toolstripdropdownitem"></a>ToolStripDropDownItem

<xref:System.Windows.Forms.ToolStripDropDownItem>es la clase base abstracta para <xref:System.Windows.Forms.ToolStripMenuItem>, <xref:System.Windows.Forms.ToolStripDropDownButton>y <xref:System.Windows.Forms.ToolStripSplitButton>, que puede hospedar elementos directamente u hospedar elementos adicionales en un contenedor desplegable. Para ello, establezca la <xref:System.Windows.Forms.ToolStripDropDownItem.DropDown%2A> propiedad en <xref:System.Windows.Forms.ToolStrip.Items%2A> <xref:System.Windows.Forms.ToolStripDropDown>y establezca la propiedad de. <xref:System.Windows.Forms.ToolStripDropDown> Obtenga acceso a estos elementos desplegables directamente <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A> a través de la propiedad.

### <a name="toolstripmenuitem"></a>ToolStripMenuItem

<xref:System.Windows.Forms.ToolStripMenuItem>es un <xref:System.Windows.Forms.ToolStripDropDownItem> que trabaja con <xref:System.Windows.Forms.ToolStripDropDownMenu> y <xref:System.Windows.Forms.ContextMenuStrip> para controlar el resaltado especial, el diseño y la organización de columnas para los menús.

### <a name="toolstripdropdownbutton"></a>ToolStripDropDownButton

<xref:System.Windows.Forms.ToolStripDropDownButton>es similar <xref:System.Windows.Forms.ToolStripButton>a, pero muestra un área desplegable cuando el usuario hace clic en él. Oculte o muestre la flecha desplegable estableciendo la <xref:System.Windows.Forms.ToolStripDropDownButton.ShowDropDownArrow%2A> propiedad. <xref:System.Windows.Forms.ToolStripDropDownButton>hospeda un <xref:System.Windows.Forms.ToolStripOverflowButton> que muestra los elementos que desbordan el <xref:System.Windows.Forms.ToolStrip>.

### <a name="toolstripsplitbutton"></a>ToolStripSplitButton

<xref:System.Windows.Forms.ToolStripSplitButton>combina la funcionalidad de botón y de botón desplegable.

Utilice la <xref:System.Windows.Forms.ToolStripSplitButton.DefaultItem%2A> propiedad para sincronizar <xref:System.Windows.Forms.Control.Click> el evento del elemento desplegable elegido con el elemento que se muestra en el botón.

### <a name="toolstripitem-generic-features"></a>Características genéricas de ToolStripItem

<xref:System.Windows.Forms.ToolStripItem>proporciona las siguientes características y opciones genéricas para heredar controles:

- Eventos principales

- Control de imágenes

- Alineación

- Relación de texto e imagen

- Estilo de presentación

#### <a name="core-events"></a>Eventos principales

<xref:System.Windows.Forms.ToolStripItem>los controles reciben sus propios eventos de clic, mouse y dibujo, y también pueden realizar algún procesamiento de teclado.

#### <a name="image-handling"></a>Control de imágenes

Las <xref:System.Windows.Forms.ToolStripItem.Image%2A>propiedades <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A>, ,<xref:System.Windows.Forms.ToolStripItem.ImageIndex%2A> ,<xref:System.Windows.Forms.ToolStripItem.ImageKey%2A>y pertenecen<xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A> a varios aspectos del control de imágenes. Utilice imágenes en <xref:System.Windows.Forms.ToolStrip> los controles estableciendo estas propiedades directamente o estableciendo la propiedad solo <xref:System.Windows.Forms.ToolStrip.ImageList%2A> en tiempo de ejecución.

El escalado de imágenes viene determinado por la interacción de <xref:System.Windows.Forms.ToolStrip> propiedades <xref:System.Windows.Forms.ToolStripItem>en y, como se indica a continuación:

- <xref:System.Windows.Forms.ToolStrip.ImageScalingSize%2A>es la escala de la imagen final determinada por la combinación de la <xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A> configuración de la imagen y la configuración del <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> contenedor.

  - Si <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> <xref:System.Windows.Forms.ToolStripItemImageScaling> es `true` (el valor predeterminado) y <xref:System.Windows.Forms.ToolStripItemImageScaling.SizeToFit>es, no se produce el ajuste de <xref:System.Windows.Forms.ToolStrip> escala de la imagen y el tamaño es el del elemento más grande o un tamaño mínimo recomendado.

  - Si <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> es `false` y <xref:System.Windows.Forms.ToolStrip> es, no<xref:System.Windows.Forms.ToolStripItemImageScaling.None>se produce ninguna imagen ni escala. <xref:System.Windows.Forms.ToolStripItemImageScaling>

#### <a name="alignment"></a>Alineación

El valor de la <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> propiedad determina el final del objeto <xref:System.Windows.Forms.ToolStrip> en el que aparece un elemento. La <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> propiedad solo funciona cuando el estilo <xref:System.Windows.Forms.ToolStrip> de diseño de se establece en uno de los valores de desbordamiento de pila.

Los elementos se colocan <xref:System.Windows.Forms.ToolStrip> en el en el orden en que aparecen los elementos en la colección de elementos. Para cambiar mediante programación el lugar en el que se diseña un elemento <xref:System.Windows.Forms.ToolStripItemCollection.Insert%2A> , utilice el método para desplace el elemento de la colección. Este método mueve el elemento, pero no lo duplica.

#### <a name="text-and-image-relationship"></a>Relación de texto e imagen

La <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> propiedad define la posición relativa de la imagen con respecto al texto <xref:System.Windows.Forms.ToolStripItem>de. Los elementos que carecen de una imagen, texto o ambos se tratan como casos especiales para <xref:System.Windows.Forms.ToolStripItem> que no muestre una zona en blanco para el elemento o los elementos que faltan.

#### <a name="display-style"></a>Estilo de presentación

<xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A>permite establecer los valores de las propiedades de texto e imagen de un elemento y mostrar solo lo que se desea. Normalmente se usa para cambiar solo el estilo de presentación cuando se muestra el mismo elemento en un contexto diferente.

## <a name="accessory-classes"></a>Clases de accesorio

Entre las clases que proporcionan otras funciones se incluyen las siguientes:

- <xref:System.Windows.Forms.ToolStripManager>admite <xref:System.Windows.Forms.ToolStrip>tareas relacionadas con para aplicaciones completas, como la combinación, la configuración y las opciones del representador.

- <xref:System.Windows.Forms.ToolStripRenderer>permite aplicar un estilo o tema determinado a un <xref:System.Windows.Forms.ToolStrip> fácilmente.

- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>crea lápices y pinceles basados en una tabla de colores reemplazable<xref:System.Windows.Forms.ProfessionalColorTable>().

- <xref:System.Windows.Forms.ToolStripSystemRenderer>aplica colores del sistema y un estilo visual plano <xref:System.Windows.Forms.ToolStrip> a las aplicaciones.

- <xref:System.Windows.Forms.ToolStripContainer>es similar a <xref:System.Windows.Forms.SplitContainer>. Usa cuatro paneles laterales acoplados (instancias de <xref:System.Windows.Forms.ToolStripPanel>) y un panel central (una instancia de <xref:System.Windows.Forms.ToolStripContentPanel>) para crear una organización típica. No puede quitar los paneles laterales, pero puede ocultarlos. No se puede quitar ni ocultar el panel central. Puede organizar uno o varios <xref:System.Windows.Forms.ToolStrip>controles, <xref:System.Windows.Forms.MenuStrip>o <xref:System.Windows.Forms.StatusStrip> en los paneles laterales, y puede usar el panel central para otros controles. <xref:System.Windows.Forms.ToolStripContentPanel> También proporciona una manera de obtener la compatibilidad con el representador en el cuerpo del formulario para obtener una apariencia coherente. <xref:System.Windows.Forms.ToolStripContainer>no es compatible con la interfaz de múltiples documentos (MDI).

- <xref:System.Windows.Forms.ToolStripPanel>proporciona espacio para mover y organizar <xref:System.Windows.Forms.ToolStrip> controles. Puede usar un solo panel si lo desea y <xref:System.Windows.Forms.ToolStripPanel> funciona bien en escenarios MDI.

## <a name="see-also"></a>Vea también

- [Información sobre el control ToolStrip](toolstrip-control-overview-windows-forms.md)
- [Resumen de la tecnología ToolStrip](toolstrip-technology-summary.md)
- [Control ToolStrip](toolstrip-control-windows-forms.md)
- [Control MenuStrip](menustrip-control-windows-forms.md)
- [StatusStrip (control)](statusstrip-control.md)
- [ContextMenuStrip (Control)](contextmenustrip-control.md)
- [BindingNavigator (control)](bindingnavigator-control-windows-forms.md)
