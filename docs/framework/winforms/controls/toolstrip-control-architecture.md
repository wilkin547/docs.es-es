---
title: "Arquitectura del control ToolStrip | Microsoft Docs"
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
  - "ToolStrip (control) [Windows Forms], arquitectura"
ms.assetid: 71df2d18-862e-4701-9ff9-c1fe606f94f2
caps.latest.revision: 32
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 32
---
# Arquitectura del control ToolStrip
Las clases <xref:System.Windows.Forms.ToolStrip> y <xref:System.Windows.Forms.ToolStripItem> proporcionan un sistema flexible y extensible para mostrar elementos de menú, estado y barras de herramientas.  Estas clases están todas en el espacio de nombres <xref:System.Windows.Forms> y su nombre lleva normalmente el prefijo "ToolStrip" \(como <xref:System.Windows.Forms.ToolStripOverflow>\) o el sufijo "Strip" \(como <xref:System.Windows.Forms.MenuStrip>\).  
  
## ToolStrip  
 En los temas siguientes se explican la clase <xref:System.Windows.Forms.ToolStrip> y los controles que derivan de ella.  
  
 <xref:System.Windows.Forms.ToolStrip> es la clase base abstracta de <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.StatusStrip> y <xref:System.Windows.Forms.ContextMenuStrip>.  El modelo de objetos siguiente muestra la jerarquía de herencia de <xref:System.Windows.Forms.ToolStrip>.  
  
 ![Modelo de objeto ToolStrip](../../../../docs/framework/winforms/controls/media/toolstripobjectmodel.png "ToolStripObjectModel")  
Modelo de objetos ToolStrip  
  
 Se puede obtener acceso a todos los elementos de <xref:System.Windows.Forms.ToolStrip> a través de la colección <xref:System.Windows.Forms.ToolStrip.Items%2A>.  Se puede obtener acceso a todos los elementos de un control <xref:System.Windows.Forms.ToolStripDropDownItem> a través de la colección <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A>.  En una clase derivada de <xref:System.Windows.Forms.ToolStrip>, también puede utilizar la propiedad <xref:System.Windows.Forms.ToolStrip.DisplayedItems%2A> para obtener sólo acceso a los elementos que se muestran actualmente.  Éstos son los elementos que no están actualmente en un menú de desbordamiento.  
  
 Los elementos siguientes están diseñados específicamente para trabajar sin problemas con <xref:System.Windows.Forms.ToolStripSystemRenderer> y <xref:System.Windows.Forms.ToolStripProfessionalRenderer> en todas las orientaciones.  Están disponibles de forma predeterminada en tiempo de diseño para el control <xref:System.Windows.Forms.ToolStrip>:  
  
-   <xref:System.Windows.Forms.ToolStripButton>  
  
-   <xref:System.Windows.Forms.ToolStripSeparator>  
  
-   <xref:System.Windows.Forms.ToolStripLabel>  
  
-   <xref:System.Windows.Forms.ToolStripDropDownButton>  
  
-   <xref:System.Windows.Forms.ToolStripSplitButton>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### MenuStrip  
 <xref:System.Windows.Forms.MenuStrip> es el contenedor de nivel superior que reemplaza a <xref:System.Windows.Forms.MainMenu>.  También proporciona las características de control de claves y de interfaz de múltiples documentos \(MDI\).  Funcionalmente, <xref:System.Windows.Forms.ToolStripDropDownItem> y <xref:System.Windows.Forms.ToolStripMenuItem> operan junto con <xref:System.Windows.Forms.MenuStrip>, aunque se derivan de <xref:System.Windows.Forms.ToolStripItem>.  
  
 Los elementos siguientes están diseñados específicamente para trabajar sin problemas con <xref:System.Windows.Forms.ToolStripSystemRenderer> y <xref:System.Windows.Forms.ToolStripProfessionalRenderer> en todas las orientaciones.  Están disponibles de forma predeterminada en tiempo de diseño para el control <xref:System.Windows.Forms.MenuStrip>:  
  
-   <xref:System.Windows.Forms.ToolStripMenuItem>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### StatusStrip  
 <xref:System.Windows.Forms.StatusStrip> reemplaza el control <xref:System.Windows.Forms.StatusBar>.  Las características especiales de <xref:System.Windows.Forms.StatusStrip> incluyen un diseño de tabla personalizada, compatibilidad con controles de cambio de tamaño y desplazamiento de formularios y la propiedad `Spring`, que permite que <xref:System.Windows.Forms.ToolStripStatusLabel> rellene automáticamente el espacio disponible.  
  
 Los elementos siguientes están diseñados específicamente para trabajar sin problemas con <xref:System.Windows.Forms.ToolStripSystemRenderer> y <xref:System.Windows.Forms.ToolStripProfessionalRenderer> en todas las orientaciones.  Están disponibles de forma predeterminada en tiempo de diseño para el control <xref:System.Windows.Forms.StatusStrip>:  
  
-   <xref:System.Windows.Forms.ToolStripStatusLabel>  
  
-   <xref:System.Windows.Forms.ToolStripDropDownButton>  
  
-   <xref:System.Windows.Forms.ToolStripSplitButton>  
  
-   <xref:System.Windows.Forms.ToolStripProgressBar>  
  
### ContextMenuStrip  
 <xref:System.Windows.Forms.ContextMenuStrip> reemplaza <xref:System.Windows.Forms.ContextMenu>.  Puede asociar <xref:System.Windows.Forms.ContextMenuStrip> a cualquier control, y un clic con el botón secundario del mouse muestra automáticamente el menú contextual.  También es posible mostrar un objeto <xref:System.Windows.Forms.ContextMenuStrip> mediante programación utilizando el método <xref:System.Windows.Forms.ToolStripDropDown.Show%2A>.  <xref:System.Windows.Forms.ContextMenuStrip> admite eventos <xref:System.Windows.Forms.ToolStripDropDown.Closing> y <xref:System.Windows.Forms.ToolStripDropDown.Opening>, que se pueden cancelar, para controlar escenarios de relleno dinámico y uso de varios clic.  <xref:System.Windows.Forms.ContextMenuStrip> admite imágenes, el estado de activación de elementos de menú, texto, teclas de acceso, accesos directos y menús en cascada.  
  
 Los elementos siguientes están diseñados específicamente para trabajar sin problemas con <xref:System.Windows.Forms.ToolStripSystemRenderer> y <xref:System.Windows.Forms.ToolStripProfessionalRenderer> en todas las orientaciones.  Están disponibles de forma predeterminada en tiempo de diseño para el control <xref:System.Windows.Forms.ContextMenuStrip>:  
  
-   <xref:System.Windows.Forms.ToolStripMenuItem>  
  
-   <xref:System.Windows.Forms.ToolStripSeparator>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### Características genéricas de ToolStrip  
 En los temas siguientes se describen las características y el comportamiento que son genéricos de <xref:System.Windows.Forms.ToolStrip> y los controles derivados.  
  
#### Dibujo  
 Puede dibujar de forma personalizada en los controles <xref:System.Windows.Forms.ToolStrip> de varias maneras.  Como ocurre con otros controles de formularios Windows Forms, tanto <xref:System.Windows.Forms.ToolStrip> como <xref:System.Windows.Forms.ToolStripItem> tienen métodos `OnPaint` y eventos `Paint` que se pueden reemplazar.  Como con el dibujo normal, el sistema de coordenadas es relativo al área de cliente del control; es decir, la esquina superior izquierda del control es 0, 0.  El evento `Paint` y el método `OnPaint` de un control <xref:System.Windows.Forms.ToolStripItem> se comportan como otros eventos de dibujo de controles.  
  
 Los controles <xref:System.Windows.Forms.ToolStrip> también proporcionan un acceso más preciso a la representación de los elementos y el contenedor, por medio de la clase <xref:System.Windows.Forms.ToolStripRenderer>, que tiene métodos reemplazables para dibujar el fondo, el fondo del elemento, la imagen del elemento, la flecha del elemento, el texto del elemento y el borde de <xref:System.Windows.Forms.ToolStrip>.  Los argumentos de evento de estos métodos exponen varias propiedades como rectángulos, colores y formatos de texto que puede ajustar como desee.  
  
 Para ajustar sólo algunos aspectos de cómo se dibuja un elemento, normalmente se reemplaza la clase <xref:System.Windows.Forms.ToolStripRenderer>.  
  
 Si escribe un nuevo elemento y desea controlar todos los aspectos del dibujo, reemplace el método `OnPaint`.  Desde el interior de `OnPaint`, puede utilizar los métodos de <xref:System.Windows.Forms.ToolStripRenderer>.  
  
 De forma predeterminada, <xref:System.Windows.Forms.ToolStrip> tiene un búfer doble y saca partido de la configuración de <xref:System.Windows.Forms.ControlStyles>.  
  
#### Relación jerárquica  
 El concepto de propiedad de los contenedores y relación jerárquica es más complicado en los controles <xref:System.Windows.Forms.ToolStrip> que en otros controles de contenedor de formularios Windows Forms.  Esto es necesario para la compatibilidad con escenarios dinámicos como el desbordamiento, para compartir elementos desplegables entre varios elementos de <xref:System.Windows.Forms.ToolStrip> y para admitir la generación de <xref:System.Windows.Forms.ContextMenuStrip> desde un control.  
  
 En la lista siguiente se describen los miembros relacionados con la relación jerárquica y se explica su uso.  
  
-   <xref:System.Windows.Forms.ToolStripDropDown.OwnerItem%2A> obtiene acceso al elemento que es el origen del elemento desplegable.  Es similar a <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A>, pero en lugar de devolver un control, devuelve <xref:System.Windows.Forms.ToolStripItem>.  
  
-   <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A> determina qué control es el origen de <xref:System.Windows.Forms.ContextMenuStrip> cuando varios controles comparten la misma <xref:System.Windows.Forms.ContextMenuStrip>.  
  
-   <xref:System.Windows.Forms.ToolStripItem.GetCurrentParent%2A> es un descriptor de acceso de sólo lectura para la propiedad <xref:System.Windows.Forms.ToolStripItem.Parent%2A>.  Un elemento primario difiere de un propietario en que el elemento primario denota la <xref:System.Windows.Forms.ToolStrip> actual devuelta en la que se muestra el elemento, que podría estar en el área de desbordamiento.  
  
-   <xref:System.Windows.Forms.ToolStripItem.Owner%2A> devuelve la <xref:System.Windows.Forms.ToolStrip> cuya colección Items contiene la <xref:System.Windows.Forms.ToolStripItem> actual.  Ésta es la mejor manera de hacer referencia a <xref:System.Windows.Forms.ToolStrip.ImageList%2A> o a otras propiedades en la <xref:System.Windows.Forms.ToolStrip> de nivel superior sin escribir un código especial para controlar el desbordamiento.  
  
#### Comportamiento de los controles heredados  
 Los controles siguientes se bloquean cada vez que se utilizan en herencia:  
  
-   <xref:System.Windows.Forms.ToolStrip>  
  
-   <xref:System.Windows.Forms.MenuStrip>  
  
-   <xref:System.Windows.Forms.ContextMenuStrip>  
  
-   <xref:System.Windows.Forms.StatusStrip>  
  
-   <xref:System.Windows.Forms.ToolStripPanel> que incluye los paneles de un <xref:System.Windows.Forms.ToolStripContainer> y también los controles <xref:System.Windows.Forms.ToolStripPanel> individuales.  
  
 Por ejemplo, cree una aplicación nueva de formularios Windows Forms que use uno o más de los controles de la lista anterior.  Establezca el modificador de acceso de uno o varios controles en `public` o `protected` y, a continuación, compile el proyecto.  Agregue un formulario que herede del primer formulario y, a continuación, seleccione un control heredado.  El control aparece bloqueado y se comporta como si su modificador de acceso fuera `private`.  
  
#### Compatibilidad de ToolStripContainer con la herencia  
 El control <xref:System.Windows.Forms.ToolStripContainer> admite escenarios heredados limitados, como en el ejemplo siguiente:  
  
1.  Crear una nueva aplicación de Windows Forms.  
  
2.  Agregue un control <xref:System.Windows.Forms.ToolStripContainer> al formulario.  
  
3.  Establezca el modificador de acceso de <xref:System.Windows.Forms.ToolStripContainer> en `public` o `protected`.  
  
4.  Agregue una combinación de los controles <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip> y <xref:System.Windows.Forms.ContextMenuStrip> a las regiones <xref:System.Windows.Forms.ToolStripPanel> de <xref:System.Windows.Forms.ToolStripContainer>.  
  
5.  Compile el proyecto.  
  
6.  Agregue un formulario que herede del primer formulario.  
  
7.  Seleccione el <xref:System.Windows.Forms.ToolStripContainer> heredado en el formulario.  
  
#### Comportamiento heredado de los controles secundarios  
 Después de finalizar los pasos anteriores, el comportamiento heredado es el siguiente:  
  
-   En el diseñador, el control aparece con un icono heredado.  
  
-   Se bloquean los controles <xref:System.Windows.Forms.ToolStripPanel>; no puede seleccionar ni reorganizar su contenido.  
  
-   Puede agregar controles a <xref:System.Windows.Forms.ToolStripContentPanel>, mover los controles y convertirlos en controles secundarios de <xref:System.Windows.Forms.ToolStripContentPanel>.  
  
-   Los cambios que efectúe permanecerán después de compilar el formulario.  
  
    > [!NOTE]
    >  Quite los modificadores de acceso de todos los controles <xref:System.Windows.Forms.ToolStripPanel> que formen parte de un <xref:System.Windows.Forms.ToolStripContainer>.  El modificador de acceso de <xref:System.Windows.Forms.ToolStripContainer> gobierna el control entero.  
  
#### Confianza parcial  
 Las limitaciones de `ToolStrip` bajo confianza parcial están diseñadas para evitar la entrada inadvertida de datos personales que puedan ser utilizados por personas o servicios sin autorización.  Las medidas de protección son las siguientes:  
  
-   Los controles `ToolStripDropDown` requieren que <xref:System.Security.Permissions.UIPermissionWindow> muestre los elementos en un <xref:System.Windows.Forms.ToolStripControlHost>.  Esto es aplicable tanto a los controles intrínsecos, por ejemplo, <xref:System.Windows.Forms.ToolStripTextBox>, <xref:System.Windows.Forms.ToolStripComboBox> y <xref:System.Windows.Forms.ToolStripProgressBar>, como a los controles creados por el usuario.  Si no se cumple este requisito, no se muestran estos elementos.  No se produce ninguna excepción.  
  
-   No se puede establecer la propiedad <xref:System.Windows.Forms.ToolStripDropDown.AutoClose%2A> en `false` y el parámetro de evento cancelable <xref:System.Windows.Forms.ToolStripDropDown.Closing> se omite.  A causa de esto, no es posible presionar más de una tecla sin que se cierre el elemento desplegable.  Si no se cumple este requisito, no se muestran estos elementos.  No se produce ninguna excepción.  
  
-   No se provocan muchos eventos de control de pulsación de tecla si se producen en contextos de confianza parcial distintos de <xref:System.Security.Permissions.UIPermissionWindow>.  
  
-   Las teclas de acceso no se procesan si no se dispone del permiso <xref:System.Security.Permissions.UIPermissionWindow>.  
  
#### Uso  
 Los modelos de uso siguientes inciden en el diseño de <xref:System.Windows.Forms.ToolStrip>, la interacción con el teclado y el comportamiento de usuario final:  
  
-   Se une en un <xref:System.Windows.Forms.ToolStripPanel>  
  
     <xref:System.Windows.Forms.ToolStrip> se puede cambiar de posición en <xref:System.Windows.Forms.ToolStripPanel> y en los controles <xref:System.Windows.Forms.ToolStripPanel>.  La propiedad `Dock` se omite y, si la propiedad <xref:System.Windows.Forms.ToolStrip.Stretch%2A> es `false`, el tamaño de <xref:System.Windows.Forms.ToolStrip> aumenta cuando se agregan elementos a <xref:System.Windows.Forms.ToolStripPanel>.  Normalmente, <xref:System.Windows.Forms.ToolStrip> no participa en el orden de tabulación.  
  
-   Acoplado  
  
     <xref:System.Windows.Forms.ToolStrip> se coloca en un lado de un contenedor en una posición fija y su tamaño se expande sobre el borde completo en el que se acopla.  Normalmente, <xref:System.Windows.Forms.ToolStrip> no participa en el orden de tabulación.  
  
-   En posición absoluta  
  
     <xref:System.Windows.Forms.ToolStrip> se parece a otros controles, en cuanto que lo coloca la propiedad <xref:System.Windows.Forms.Control.Location%2A>, tiene un tamaño fijo y normalmente participa en el orden de tabulación.  
  
#### Interacción del teclado  
  
##### Teclas de acceso  
 Las teclas de acceso, presionadas a la vez que la tecla ALT o después de esta, ofrecen una manera de activar un control mediante el teclado.  <xref:System.Windows.Forms.ToolStrip> admite las teclas de acceso explícitas e implícitas.  La definición explícita utiliza un carácter & \(Y comercial\) que precede a la letra.  La definición implícita utiliza un algoritmo que intenta encontrar un elemento correspondiente basándose en el orden de los caracteres en una propiedad `Text` determinada.  
  
##### Teclas de método abreviado  
 Las teclas de método abreviado utilizadas por una clase <xref:System.Windows.Forms.MenuStrip> definen la tecla de método abreviado mediante una combinación de la enumeración <xref:System.Windows.Forms.Keys> \(sin orden específico\).  También puede utilizar la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> para mostrar una tecla de método abreviado con solo texto, por ejemplo, mostrar "Supr" en lugar de "Suprimir".  
  
##### Navegación  
 La tecla ALT activa el <xref:System.Windows.Forms.MenuStrip> al que señala <xref:System.Windows.Forms.Form.MainMenuStrip%2A>.  Desde allí, CTRL\+TAB navega entre los controles <xref:System.Windows.Forms.ToolStrip> que se encuentren en los `ToolStripPanel`.  La tecla TAB y las teclas de dirección del teclado numérico permiten navegar entre los elementos de <xref:System.Windows.Forms.ToolStrip>.  Un algoritmo especial controla la navegación en el área de desbordamiento.  La BARRA ESPACIADORA selecciona un control <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton> o <xref:System.Windows.Forms.ToolStripSplitButton>.  
  
##### Foco y validación  
 Cuando la tecla ALT los activa, <xref:System.Windows.Forms.MenuStrip> o <xref:System.Windows.Forms.ToolStrip> normalmente no quitan ni ponen el foco en el control que esté seleccionado.  Si hay un control hospedado en el contenedor de objetos <xref:System.Windows.Forms.MenuStrip> o un control desplegable del objeto <xref:System.Windows.Forms.MenuStrip>, el control obtiene el foco cuando el usuario presiona la tecla TAB.  En general, puede que los eventos <xref:System.Windows.Forms.Control.GotFocus>, <xref:System.Windows.Forms.Control.LostFocus>, <xref:System.Windows.Forms.Control.Enter> y <xref:System.Windows.Forms.Control.Leave> de <xref:System.Windows.Forms.MenuStrip> no se generen si se activan con el teclado.  En tales casos, utilice en su lugar los eventos <xref:System.Windows.Forms.MenuStrip.MenuActivate> y <xref:System.Windows.Forms.MenuStrip.MenuDeactivate>.  
  
 De manera predeterminada, <xref:System.Windows.Forms.ToolStrip.CausesValidation%2A> es `false`.  Llame explícitamente a <xref:System.Windows.Forms.ContainerControl.Validate%2A> en el formulario para realizar la validación.  
  
#### Diseño  
 Puede controlar el diseño de <xref:System.Windows.Forms.ToolStrip> eligiendo uno de los miembros de <xref:System.Windows.Forms.ToolStripLayoutStyle> con la propiedad <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A>.  
  
##### Diseños de pila  
 El apilamiento consiste en la disposición de los elementos uno al lado de otro a ambos extremos del contenedor de objetos <xref:System.Windows.Forms.ToolStrip>.  La lista siguiente describe los diseños de pila.  
  
-   El valor predeterminado es <xref:System.Windows.Forms.ToolStripLayoutStyle>.  Esta configuración hace que el contenedor <xref:System.Windows.Forms.ToolStrip> modifique automáticamente su diseño de acuerdo con la propiedad <xref:System.Windows.Forms.ToolStrip.Orientation%2A> para controlar las situaciones de arrastre y acoplamiento.  
  
-   <xref:System.Windows.Forms.ToolStripLayoutStyle> representa los elementos <xref:System.Windows.Forms.ToolStrip> uno al lado de otro verticalmente.  
  
-   <xref:System.Windows.Forms.ToolStripLayoutStyle> representa los elementos <xref:System.Windows.Forms.ToolStrip> uno al lado de otro horizontalmente.  
  
##### Otras características de los diseños de pila  
 <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> determina el fin del contenedor <xref:System.Windows.Forms.ToolStrip> con el que se alinea el elemento.  
  
 Cuando los productos no caben en el contenedor <xref:System.Windows.Forms.ToolStrip>, aparece automáticamente un botón de desbordamiento.  El valor de la propiedad <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> determina si un elemento aparecerá siempre en el área de desbordamiento, cuando sea necesario, o nunca.  
  
 En el evento <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>, puede inspeccionar la propiedad <xref:System.Windows.Forms.ToolStripItem.Placement%2A> para determinar si un elemento se ha colocado en el contenedor <xref:System.Windows.Forms.ToolStrip> principal, en el contenedor <xref:System.Windows.Forms.ToolStrip> de desbordamiento, o si actualmente no se muestra en absoluto.  Las razones típicas de que un elemento no se muestre son que el elemento no quepa en el <xref:System.Windows.Forms.ToolStrip> principal y que su propiedad <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> esté establecida en <xref:System.Windows.Forms.ToolStripItemOverflow>.  
  
 Haga que un objeto <xref:System.Windows.Forms.ToolStrip> sea movible colocándolo en un contenedor <xref:System.Windows.Forms.ToolStripPanel> y establezca su propiedad <xref:System.Windows.Forms.ToolStrip.GripStyle%2A> en <xref:System.Windows.Forms.ToolStripGripStyle>.  
  
##### Otras opciones de diseño  
 Las otras opciones de diseño son <xref:System.Windows.Forms.ToolStripLayoutStyle> y <xref:System.Windows.Forms.ToolStripLayoutStyle>.  
  
##### Diseño de flujo  
 El diseño de <xref:System.Windows.Forms.ToolStripLayoutStyle> es el valor predeterminado de los controles <xref:System.Windows.Forms.ContextMenuStrip>, <xref:System.Windows.Forms.ToolStripDropDownMenu> y <xref:System.Windows.Forms.ToolStripOverflow>.  Es similar al panel <xref:System.Windows.Forms.FlowLayoutPanel>.  A continuación se detallan las características del diseño de <xref:System.Windows.Forms.ToolStripLayoutStyle>:  
  
-   La propiedad <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A> expone todas las características de la clase <xref:System.Windows.Forms.FlowLayoutPanel>.  Debe convertir la clase <xref:System.Windows.Forms.LayoutSettings> a una clase <xref:System.Windows.Forms.FlowLayoutSettings>.  
  
-   Puede utilizar las propiedades <xref:System.Windows.Forms.ToolStripItem.Dock%2A> y <xref:System.Windows.Forms.ToolStripItem.Anchor%2A> en el código para alinear los elementos dentro de la fila.  
  
-   Se omite la propiedad <xref:System.Windows.Forms.ToolStripItem.Alignment%2A>.  
  
-   En el evento <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>, puede examinar la propiedad <xref:System.Windows.Forms.ToolStripItem.Placement%2A> para determinar si se ha colocado un elemento en el contenedor <xref:System.Windows.Forms.ToolStrip> principal o no ha cabido.  
  
-   No se representa el control y por consiguiente no se puede mover un objeto <xref:System.Windows.Forms.ToolStrip> de estilo de diseño <xref:System.Windows.Forms.ToolStripLayoutStyle> en un panel <xref:System.Windows.Forms.ToolStripPanel>.  
  
-   El botón de desbordamiento <xref:System.Windows.Forms.ToolStrip> no está representado y <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> se omite.  
  
##### Diseño de tabla  
 El diseño de <xref:System.Windows.Forms.ToolStripLayoutStyle> es el valor predeterminado de <xref:System.Windows.Forms.StatusStrip>.  Es similar a <xref:System.Windows.Forms.TableLayoutPanel>.  A continuación se detallan las características del diseño de <xref:System.Windows.Forms.ToolStripLayoutStyle>:  
  
-   La propiedad <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A> expone todas las características de la clase <xref:System.Windows.Forms.TableLayoutPanel>.  Debe convertir la clase <xref:System.Windows.Forms.LayoutSettings> a una clase <xref:System.Windows.Forms.TableLayoutSettings>.  
  
-   Puede utilizar las propiedades <xref:System.Windows.Forms.ToolStripItem.Dock%2A> y <xref:System.Windows.Forms.ToolStripItem.Anchor%2A> en el código para alinear los elementos dentro de la celda de la tabla.  
  
-   Se omite la propiedad <xref:System.Windows.Forms.ToolStripItem.Alignment%2A>.  
  
-   En el evento <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>, puede examinar la propiedad <xref:System.Windows.Forms.ToolStripItem.Placement%2A> para determinar si se ha colocado un elemento en el contenedor <xref:System.Windows.Forms.ToolStrip> principal o no ha cabido.  
  
-   El control de ajuste no está representado y, por consiguiente, no se puede desplazar una <xref:System.Windows.Forms.ToolStrip> en el estilo de diseño <xref:System.Windows.Forms.ToolStripLayoutStyle> de un <xref:System.Windows.Forms.ToolStripPanel>.  
  
-   El botón de desbordamiento <xref:System.Windows.Forms.ToolStrip> no está representado y <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> se omite.  
  
## ToolStripItem  
 En los temas siguientes se explican la clase <xref:System.Windows.Forms.ToolStripItem> y los controles que derivan de ella.  
  
 <xref:System.Windows.Forms.ToolStripItem> es la clase base abstracta para todos los elementos que entran en <xref:System.Windows.Forms.ToolStrip>.  El modelo de objetos siguiente muestra la jerarquía de herencia de <xref:System.Windows.Forms.ToolStripItem>.  
  
 ![Modelo de objeto ToolStripItem](../../../../docs/framework/winforms/controls/media/toolstripitemobjectmodel.png "ToolStripItemObjectModel")  
Modelo de objetos ToolStripItem  
  
 Las clases <xref:System.Windows.Forms.ToolStripItem> heredan directamente de <xref:System.Windows.Forms.ToolStripItem> o indirectamente de <xref:System.Windows.Forms.ToolStripItem> a través de <xref:System.Windows.Forms.ToolStripControlHost> o <xref:System.Windows.Forms.ToolStripDropDownItem>.  
  
 Los controles <xref:System.Windows.Forms.ToolStripItem> se deben contener en <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.StatusStrip> o <xref:System.Windows.Forms.ContextMenuStrip> y no se deben agregar directamente a un formulario.  Las diversas clases de contenedor están diseñadas para contener un subconjunto adecuado de controles <xref:System.Windows.Forms.ToolStripItem>.  
  
 La tabla siguiente muestra los controles <xref:System.Windows.Forms.ToolStripItem> estándar y los contenedores en los que se ven mejor.  Si bien cualquier elemento de <xref:System.Windows.Forms.ToolStrip> puede hospedarse en un contenedor derivado de <xref:System.Windows.Forms.ToolStrip>, estos elementos se ven mejor en los contenedores siguientes:  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStripDropDown> no aparece en el cuadro de herramientas de diseñador.  
  
|Elemento que contiene|ToolStrip|MenuStrip|ContextMenuStrip|StatusStrip|ToolStripDropDown|  
|---------------------------|---------------|---------------|----------------------|-----------------|-----------------------|  
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
  
### ToolStripButton  
 <xref:System.Windows.Forms.ToolStripButton> es el elemento de botón para <xref:System.Windows.Forms.ToolStrip>.  Puede mostrarlo con varios estilos de borde y puede utilizarlo para representar y activar estados operacionales.  También puede definirlo para que obtenga el foco de forma predeterminada.  
  
### ToolStripLabel  
 <xref:System.Windows.Forms.ToolStripLabel> proporciona la funcionalidad de las etiquetas en los controles <xref:System.Windows.Forms.ToolStrip>.  <xref:System.Windows.Forms.ToolStripLabel> es parecido a un <xref:System.Windows.Forms.ToolStripButton> que no recibe el foco de forma predeterminada y que no se representa como presionado ni resaltado.  
  
 <xref:System.Windows.Forms.ToolStripLabel>, como elemento hospedado, admite las teclas de acceso.  
  
 Use las propiedades <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> y <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> de <xref:System.Windows.Forms.ToolStripLabel> para admitir el control de vinculación en un <xref:System.Windows.Forms.ToolStrip>.  
  
### ToolStripStatusLabel  
 <xref:System.Windows.Forms.ToolStripStatusLabel> es una versión de <xref:System.Windows.Forms.ToolStripLabel> diseñada específicamente para el uso en <xref:System.Windows.Forms.StatusStrip>.  Entre sus características especiales destacan <xref:System.Windows.Forms.ToolStripStatusLabel.BorderStyle%2A>, <xref:System.Windows.Forms.ToolStripStatusLabel.BorderSides%2A> y <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>.  
  
### ToolStripSeparator  
 <xref:System.Windows.Forms.ToolStripSeparator> agrega una línea vertical u horizontal a una barra de herramientas o de menú, dependiendo de la orientación.  Proporciona un medio para agrupar o distinguir elementos, como los de un menú.  
  
 Puede agregar un <xref:System.Windows.Forms.ToolStripSeparator> en tiempo de diseño eligiéndolo en una lista desplegable.  También puede crear automáticamente un <xref:System.Windows.Forms.ToolStripSeparator> escribiendo un guión \(\-\) en el nodo de plantilla de diseñador o en el método <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A>.  
  
### ToolStripControlHost  
 <xref:System.Windows.Forms.ToolStripControlHost> es la clase base abstracta de <xref:System.Windows.Forms.ToolStripComboBox>, <xref:System.Windows.Forms.ToolStripTextBox> y <xref:System.Windows.Forms.ToolStripProgressBar>.  <xref:System.Windows.Forms.ToolStripControlHost> puede hospedar otros controles, incluso controles personalizados, de dos maneras:  
  
-   Construir un <xref:System.Windows.Forms.ToolStripControlHost> con una clase que derive de <xref:System.Windows.Forms.Control>.  Para tener acceso total al control y las propiedades hospedados, debe volver a convertir la propiedad <xref:System.Windows.Forms.ToolStripControlHost.Control%2A> en la clase real que representa.  
  
-   Extender <xref:System.Windows.Forms.ToolStripControlHost> y, en el constructor predeterminado de la clase heredada, llamar al constructor de clase base pasando una clase que derive de <xref:System.Windows.Forms.Control>.  Esta opción permite ajustar los métodos de control comunes y propiedades para obtener fácilmente acceso en un control <xref:System.Windows.Forms.ToolStrip>.  
  
### ToolStripComboBox  
 <xref:System.Windows.Forms.ToolStripComboBox> es el <xref:System.Windows.Forms.ComboBox> optimizado para el hospedaje en <xref:System.Windows.Forms.ToolStrip>.  Un subconjunto de las propiedades y eventos del control hospedado se expone en el nivel <xref:System.Windows.Forms.ToolStripComboBox>, pero el control <xref:System.Windows.Forms.ComboBox> subyacente es totalmente accesible por medio de la propiedad <xref:System.Windows.Forms.ToolStripComboBox.ComboBox%2A>.  
  
### ToolStripTextBox  
 <xref:System.Windows.Forms.ToolStripTextBox> es el <xref:System.Windows.Forms.TextBox> optimizado para el hospedaje en <xref:System.Windows.Forms.ToolStrip>.  Un subconjunto de las propiedades y eventos del control hospedado se expone en el nivel <xref:System.Windows.Forms.ToolStripTextBox>, pero el control <xref:System.Windows.Forms.TextBox> subyacente es totalmente accesible por medio de la propiedad <xref:System.Windows.Forms.ToolStripTextBox.TextBox%2A>.  
  
### ToolStripProgressBar  
 <xref:System.Windows.Forms.ToolStripProgressBar> es el <xref:System.Windows.Forms.ProgressBar> optimizado para el hospedaje en <xref:System.Windows.Forms.ToolStrip>.  Un subconjunto de las propiedades y eventos del control hospedado se expone en el nivel <xref:System.Windows.Forms.ToolStripProgressBar>, pero el control <xref:System.Windows.Forms.ProgressBar> subyacente es totalmente accesible por medio de la propiedad <xref:System.Windows.Forms.ToolStripProgressBar.ProgressBar%2A>.  
  
### ToolStripDropDownItem  
 <xref:System.Windows.Forms.ToolStripDropDownItem> es la clase base abstracta para <xref:System.Windows.Forms.ToolStripMenuItem>, <xref:System.Windows.Forms.ToolStripDropDownButton> y <xref:System.Windows.Forms.ToolStripSplitButton>, que puede hospedar elementos directamente u hospedar elementos adicionales en un contenedor desplegable.  Para ello, establezca la propiedad <xref:System.Windows.Forms.ToolStripDropDownItem.DropDown%2A> en un <xref:System.Windows.Forms.ToolStripDropDown> y establezca la propiedad <xref:System.Windows.Forms.ToolStrip.Items%2A> del <xref:System.Windows.Forms.ToolStripDropDown>.  Puede obtener acceso directamente a estos elementos desplegables por medio de la propiedad <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A>.  
  
### ToolStripMenuItem  
 <xref:System.Windows.Forms.ToolStripMenuItem> es un <xref:System.Windows.Forms.ToolStripDropDownItem> que, junto con <xref:System.Windows.Forms.ToolStripDropDownMenu> y <xref:System.Windows.Forms.ContextMenuStrip>, permite controlar el resaltado especial, el diseño y la organización en columnas de los menús.  
  
### ToolStripDropDownButton  
 <xref:System.Windows.Forms.ToolStripDropDownButton> se parece a <xref:System.Windows.Forms.ToolStripButton>, pero muestra un área desplegable cuando el usuario hace clic en él.  Para ocultar o mostrar la flecha desplegable, establezca la propiedad <xref:System.Windows.Forms.ToolStripDropDownButton.ShowDropDownArrow%2A>.  <xref:System.Windows.Forms.ToolStripDropDownButton> hospeda un <xref:System.Windows.Forms.ToolStripOverflowButton> que muestra los elementos que desbordan <xref:System.Windows.Forms.ToolStrip>.  
  
### ToolStripSplitButton  
 <xref:System.Windows.Forms.ToolStripSplitButton> combina las funcionalidades de botón y de botón de lista desplegable.  
  
 La propiedad <xref:System.Windows.Forms.ToolStripSplitButton.DefaultItem%2A> permite sincronizar el evento <xref:System.Windows.Forms.Control.Click> del elemento desplegable elegido con el elemento mostrado en el botón.  
  
### Características genéricas de ToolStripItem  
 <xref:System.Windows.Forms.ToolStripItem> proporciona las opciones y las características genéricas siguientes a los controles que se heredan:  
  
-   Eventos básicos  
  
-   Control de la imagen  
  
-   Alineación  
  
-   Relación entre texto e imagen  
  
-   Estilo de presentación  
  
#### Eventos básicos  
 Los controles <xref:System.Windows.Forms.ToolStripItem> reciben eventos propios de clic, mouse y dibujo, y también pueden realizar el preprocesamiento de teclado.  
  
#### Control de la imagen  
 Las propiedades <xref:System.Windows.Forms.ToolStripItem.Image%2A>, <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A>, <xref:System.Windows.Forms.ToolStripItem.ImageIndex%2A>, <xref:System.Windows.Forms.ToolStripItem.ImageKey%2A> y <xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A> corresponden a varios aspectos del control de la imagen.  Utilice imágenes en los controles <xref:System.Windows.Forms.ToolStrip> estableciendo estas propiedades directamente o la propiedad <xref:System.Windows.Forms.ToolStrip.ImageList%2A> únicamente en tiempo de ejecución.  
  
 El ajuste de escala de imágenes está determinado por la interacción de propiedades en <xref:System.Windows.Forms.ToolStrip> y en <xref:System.Windows.Forms.ToolStripItem>, del siguiente modo:  
  
-   <xref:System.Windows.Forms.ToolStrip.ImageScalingSize%2A> es la escala de la imagen final, según determina la combinación del valor de  <xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A> de la imagen y el valor de <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> del contenedor.  
  
    -   Si <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> es `true` \(el valor predeterminado\) y <xref:System.Windows.Forms.ToolStripItemImageScaling> es <xref:System.Windows.Forms.ToolStripItemImageScaling>, no se ajusta la escala de la imagen y el tamaño de <xref:System.Windows.Forms.ToolStrip> es el del elemento más grande o un tamaño mínimo indicado.  
  
    -   Si <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> es `false` y <xref:System.Windows.Forms.ToolStripItemImageScaling> es <xref:System.Windows.Forms.ToolStripItemImageScaling>, no se ajusta la escala de la imagen ni de <xref:System.Windows.Forms.ToolStrip>.  
  
#### Alineación  
 El valor de la propiedad <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> determina el extremo de <xref:System.Windows.Forms.ToolStrip> en el que aparece un elemento.  La propiedad <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> sólo funciona cuando el estilo de diseño de <xref:System.Windows.Forms.ToolStrip> está establecido en uno de los valores de desbordamiento de pila.  
  
 Los elementos se colocan en <xref:System.Windows.Forms.ToolStrip> en el orden en el que aparecen en la colección Items.  Para cambiar mediante programación la ubicación donde se dispone un elemento, utilice el método <xref:System.Windows.Forms.ToolStripItemCollection.Insert%2A> para mover el elemento en la colección.  Este método mueve el elemento pero no lo duplica.  
  
#### Relación entre texto e imagen  
 La propiedad <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> define la posición relativa de la imagen con respecto al texto en un <xref:System.Windows.Forms.ToolStripItem>.  Los elementos que carecen de imagen, texto o ambos se tratan como casos especiales para que <xref:System.Windows.Forms.ToolStripItem> no muestre una zona vacía para el elemento o elementos que faltan.  
  
#### Estilo de presentación  
 <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> permite establecer los valores de las propiedades Text e Image de un elemento para que sólo muestren lo que se desee.  Por lo general, esto se utiliza para cambiar solamente el estilo de presentación cuando el mismo elemento se muestra en un contexto diferente.  
  
## Clases de accesorios  
 Las clases que proporcionan otras funcionalidades incluyen:  
  
-   <xref:System.Windows.Forms.ToolStripManager> admite tareas relacionadas con <xref:System.Windows.Forms.ToolStrip> para aplicaciones completas, como combinación, configuración y opciones de representación.  
  
-   <xref:System.Windows.Forms.ToolStripRenderer> permite aplicar con facilidad un estilo o tema determinado a <xref:System.Windows.Forms.ToolStrip>.  
  
-   <xref:System.Windows.Forms.ToolStripProfessionalRenderer> crea los lápices y pinceles basándose en una tabla de colores reemplazable \(<xref:System.Windows.Forms.ProfessionalColorTable>\).  
  
-   <xref:System.Windows.Forms.ToolStripSystemRenderer> aplica colores de sistema y un estilo visual plano a las aplicaciones <xref:System.Windows.Forms.ToolStrip>.  
  
-   <xref:System.Windows.Forms.ToolStripContainer> es similar a <xref:System.Windows.Forms.SplitContainer>.  Utiliza cuatro paneles laterales acoplados \(instancias de <xref:System.Windows.Forms.ToolStripPanel>\) y un panel central \(una instancia de <xref:System.Windows.Forms.ToolStripContentPanel>\) para crear una organización habitual.  No se pueden quitar los paneles laterales, pero se pueden ocultar.  No se puede quitar ni ocultar el panel central.  Puede disponer uno o varios controles <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip> o <xref:System.Windows.Forms.StatusStrip> en los paneles laterales y utilizar el panel central para otros controles.  <xref:System.Windows.Forms.ToolStripContentPanel> también facilita compatibilidad con el representador en el cuerpo del formulario para obtener una apariencia coherente.  <xref:System.Windows.Forms.ToolStripContainer> no admite la interfaz de múltiples documentos \(MDI\).  
  
-   <xref:System.Windows.Forms.ToolStripPanel> proporciona el espacio para desplazar y organizar los controles <xref:System.Windows.Forms.ToolStrip>.  Puede utilizar sólo un panel si lo desea y <xref:System.Windows.Forms.ToolStripPanel> es apropiada para los escenarios de MDI.  
  
## Vea también  
 [Información sobre el control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)   
 [Resumen de la tecnología ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)   
 [ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)   
 [MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)   
 [StatusStrip \(Control\)](../../../../docs/framework/winforms/controls/statusstrip-control.md)   
 [ContextMenuStrip \(Control\)](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)   
 [BindingNavigator \(Control\)](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)