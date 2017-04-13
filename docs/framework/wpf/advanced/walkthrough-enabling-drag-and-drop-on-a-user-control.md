---
title: "Tutorial: Habilitar la t&#233;cnica de arrastrar y colocar en un control de usuario | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "arrastrar y colocar [WPF], tutorial"
  - "tutorial [WPF], arrastrar y colocar"
ms.assetid: cc844419-1a77-4906-95d9-060d79107fc7
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Tutorial: Habilitar la t&#233;cnica de arrastrar y colocar en un control de usuario
Este tutorial muestra cómo crear un control de usuario personalizado que pueda participar en la transferencia de datos mediante arrastrar y colocar en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
 En este tutorial, creará un control <xref:System.Windows.Controls.UserControl> personalizado de WPF que representa una forma circular.  Implementará la funcionalidad del control para habilitar la transferencia de datos mediante arrastrar y colocar.  Por ejemplo, si arrastra desde un control Circle a otro, los datos de color de relleno se copian del círculo del origen al de destino.  Si arrastra de un control Circle a <xref:System.Windows.Controls.TextBox>, la representación de cadena del color de relleno se copia a <xref:System.Windows.Controls.TextBox>.  También creará una pequeña aplicación que contenga dos controles de panel y <xref:System.Windows.Controls.TextBox> para probar la funcionalidad de arrastrar y colocar.  Escribirá código que permita a los paneles procesar los datos de Circle colocados, lo que le permitirá mover o copiar círculos de la colección de elementos secundarios de un panel a otro.  
  
 En este tutorial se muestran las tareas siguientes:  
  
-   Crear un control de usuario personalizado.  
  
-   Permitir al control de usuario ser un origen de arrastre.  
  
-   Permitir al control de usuario ser un destino de colocación.  
  
-   Permitir a un panel recibir los datos colocados desde el control de usuario.  
  
## Requisitos previos  
 Necesita los componentes siguientes para completar este tutorial:  
  
-   Visual Studio 2010  
  
## Crear el proyecto de aplicación  
 En esta sección, creará la infraestructura de la aplicación, que incluye una página principal con dos paneles y <xref:System.Windows.Controls.TextBox>.  
  
### Para crear el proyecto  
  
1.  Cree un nuevo proyecto de aplicación WPF en Visual Basic o en Visual C\# denominado `DragDropExample`.  Para obtener más información, vea [Cómo: Crear un nuevo proyecto de aplicación de WPF](http://msdn.microsoft.com/es-es/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).  
  
2.  Abra MainWindow.xaml.  
  
3.  Entre las etiquetas de apertura y cierre <xref:System.Windows.Controls.Grid>, agregue el marcado siguiente.  
  
     Este marcado crea la interfaz de usuario para la aplicación de prueba.  
  
     [!code-xml[DragDropWalkthrough#PanelsStep1XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep1xaml)]  
  
## Agregar un nuevo control de usuario al proyecto  
 En esta sección, agregará un nuevo control de usuario al proyecto.  
  
### Para agregar a un nuevo control de usuario  
  
1.  En el menú Proyecto, seleccione **Agregar control de usuario**.  
  
2.  En el cuadro de diálogo Agregar nuevo elemento, cambie el nombre a `Circle.xaml` y haga clic en **Agregar**.  
  
     Circle.xaml y su código subyacente se agregan al proyecto.  
  
3.  Abra Circle.xaml.  
  
     Este archivo contendrá los elementos de la interfaz de usuario del control de usuario.  
  
4.  Agregue el marcado siguiente al elemento <xref:System.Windows.Controls.Grid> raíz para crear un control de usuario simple con un círculo azul como interfaz de usuario.  
  
     [!code-xml[DragDropWalkthrough#EllipseXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#ellipsexaml)]  
  
5.  Abra Circle.xaml.cs o Circle.xaml.vb.  
  
6.  En C\#, agregue el código siguiente después del constructor predeterminado para crear un constructor de copia.  En Visual Basic, agregue el código siguiente para crear un constructor predeterminado y un constructor de copia.  
  
     Para permitir que el control de usuario se pueda copiar, agregará un método constructor de copia en el archivo de código subyacente.  En el control de usuario Circle simplificado, copiará sólo el relleno y el tamaño del control de usuario.  
  
     [!code-csharp[DragDropWalkthrough#CopyCtor](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#copyctor)]
     [!code-vb[DragDropWalkthrough#CopyCtor](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#copyctor)]  
  
### Para agregar el control de usuario a la ventana principal  
  
1.  Abra MainWindow.xaml.  
  
2.  Agregue el código XAML siguiente a la etiqueta <xref:System.Windows.Window> de apertura para crear una referencia de espacio de nombres XML a la aplicación actual.  
  
    ```  
    xmlns:local="clr-namespace:DragDropExample"  
    ```  
  
3.  En el primer <xref:System.Windows.Controls.StackPanel>, agregue el siguiente XAML para crear dos instancias del control de usuario Circle en el primer panel.  
  
     [!code-xml[DragDropWalkthrough#CirclesXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#circlesxaml)]  
  
     El XAML completo del panel tendrá un aspecto similar al siguiente.  
  
     [!code-xml[DragDropWalkthrough#PanelsStep2XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep2xaml)]  
  
## Implementar eventos de origen de arrastre en el control de usuario  
 En esta sección, reemplazará el método <xref:System.Windows.UIElement.OnMouseMove%2A> e iniciará la operación de arrastrar y colocar.  
  
 Si se inicia una arrastre \(se presiona un botón del mouse y se mueve el mouse\), empaquetará los datos que se transferirán en un <xref:System.Windows.DataObject>.  En este caso, el control Circle empaquetará tres elementos de datos; una representación de cadena del color de relleno, una representación doble de su alto y una copia de sí mismo.  
  
### Para iniciar una operación de arrastrar y colocar  
  
1.  Abra Circle.xaml.cs o Circle.xaml.vb.  
  
2.  Agregue la siguiente invalidación de <xref:System.Windows.UIElement.OnMouseMove%2A> para proporcionar control de clases para el evento <xref:System.Windows.UIElement.MouseMove>.  
  
     [!code-csharp[DragDropWalkthrough#OnMouseMove](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#onmousemove)]
     [!code-vb[DragDropWalkthrough#OnMouseMove](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#onmousemove)]  
  
     La invalidación de <xref:System.Windows.UIElement.OnMouseMove%2A> realiza las tareas siguientes:  
  
    -   Comprueba si el botón primario del mouse está presionado mientras se mueve el mouse.  
  
    -   Empaqueta los datos de Circle en un <xref:System.Windows.DataObject>.  En este caso, el control Circle empaqueta tres elementos de datos; una representación de cadena del color de relleno, una representación doble de su alto y una copia de sí mismo.  
  
    -   Llama al método estático <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=fullName> para iniciar la operación de arrastrar y colocar.  Pase los tres parámetros siguientes al método <xref:System.Windows.DragDrop.DoDragDrop%2A>:  
  
        -   `dragSource` : una referencia a este control.  
  
        -   `data`: el <xref:System.Windows.DataObject> creado en el código anterior.  
  
        -   `allowedEffects` : las operaciones de arrastrar y colocar permitidas, que son <xref:System.Windows.DragDropEffects> o <xref:System.Windows.DragDropEffects>.  
  
3.  Presione F5 para compilar y ejecutar la aplicación.  
  
4.  Haga clic en uno de los controles Circle y arrástrelo sobre los paneles, el otro círculo, y el control <xref:System.Windows.Controls.TextBox>.  Al arrastrar sobre <xref:System.Windows.Controls.TextBox>, el cursor cambia para indicar un movimiento.  
  
5.  Al arrastrar un círculo sobre <xref:System.Windows.Controls.TextBox>, presione la tecla CTRL.  Observe cómo cambia el cursor para indicar una copia.  
  
6.  Arrastre y coloque un círculo sobre <xref:System.Windows.Controls.TextBox>.  La representación de cadena del color de relleno del círculo se agrega a <xref:System.Windows.Controls.TextBox>.  
  
     ![Representación de cadena del color de relleno del círculo](../../../../docs/framework/wpf/advanced/media/dragdrop-colorstring.png "DragDrop\_ColorString")  
  
 De forma predeterminada, el cursor cambiará durante una operación de arrastrar y colocar para indicar qué efecto tendrá la colocación de los datos.  Puede personalizar los comentarios proporcionados al usuario si controla el evento <xref:System.Windows.UIElement.GiveFeedback> y establece un cursor diferente.  
  
### Para proporcionar información al usuario  
  
1.  Abra Circle.xaml.cs o Circle.xaml.vb.  
  
2.  Agregue la siguiente invalidación de <xref:System.Windows.UIElement.OnGiveFeedback%2A> para proporcionar control de clases para el evento <xref:System.Windows.UIElement.GiveFeedback>.  
  
     [!code-csharp[DragDropWalkthrough#OnGiveFeedback](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ongivefeedback)]
     [!code-vb[DragDropWalkthrough#OnGiveFeedback](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ongivefeedback)]  
  
     La invalidación de <xref:System.Windows.UIElement.OnGiveFeedback%2A> realiza las tareas siguientes:  
  
    -   Comprueba los valores de <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> que se establecen en el controlador de eventos <xref:System.Windows.UIElement.DragOver> del destino de colocación.  
  
    -   Establece un cursor personalizado basado en el valor de <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A>.  El cursor está diseñado para proporcionar información visual al usuario sobre qué efecto tendrá la colocación de los datos.  
  
3.  Presione F5 para compilar y ejecutar la aplicación.  
  
4.  Arrastre uno de los controles Circle sobre los paneles, el otro círculo y el control <xref:System.Windows.Controls.TextBox>.  Observe que los cursores son ahora los cursores personalizados que especificó en la invalidación de <xref:System.Windows.UIElement.OnGiveFeedback%2A>.  
  
     ![Arrastrar y colocar con cursores personalizados](../../../../docs/framework/wpf/advanced/media/dragdrop-customcursor.png "DragDrop\_CustomCursor")  
  
5.  Seleccione el texto `green` de <xref:System.Windows.Controls.TextBox>.  
  
6.  Arrastre el texto `green` a un control Circle.  Observe que los cursores predeterminados se muestran para indicar los efectos de la operación de arrastrar y colocar.  El origen de arrastre establece siempre el cursor de comentarios.  
  
## Implementar eventos de destino de colocación en el control de usuario  
 En esta sección, especificará que el control de usuario sea un destino de colocación, reemplazará los métodos que permiten que el control de usuario sea un destino de colocación y procesará los datos que se colocan en él.  
  
### Para permitir que el control de usuario sea un destino de colocación  
  
1.  Abra Circle.xaml.  
  
2.  En la etiqueta <xref:System.Windows.Controls.UserControl> de apertura, agregue la propiedad <xref:System.Windows.UIElement.AllowDrop%2A> y establézcala en `true`.  
  
     [!code-xml[DragDropWalkthrough#UCTagXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#uctagxaml)]  
  
 Se llama al método <xref:System.Windows.UIElement.OnDrop%2A> cuando la propiedad <xref:System.Windows.UIElement.AllowDrop%2A> se establece en `true` y los datos del origen de arrastre se colocan en el control de usuario Circle.  En este método, procesará los datos que se han quitado y aplicará los datos al círculo.  
  
### Para procesar los datos colocados  
  
1.  Abra Circle.xaml.cs o Circle.xaml.vb.  
  
2.  Agregue la siguiente invalidación de <xref:System.Windows.UIElement.OnDrop%2A> para proporcionar control de clases para el evento <xref:System.Windows.UIElement.Drop>.  
  
     [!code-csharp[DragDropWalkthrough#OnDrop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondrop)]
     [!code-vb[DragDropWalkthrough#OnDrop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondrop)]  
  
     La invalidación de <xref:System.Windows.UIElement.OnDrop%2A> realiza las tareas siguientes:  
  
    -   Utiliza el método <xref:System.Windows.DataObject.GetDataPresent%2A> para comprobar si los datos arrastrados contienen un objeto de cadena.  
  
    -   Utiliza el método <xref:System.Windows.DataObject.GetData%2A> para extraer los datos de cadena si están presentes.  
  
    -   Utiliza <xref:System.Windows.Media.BrushConverter> para intentar convertir la cadena en <xref:System.Windows.Media.Brush>.  
  
    -   Si la conversión se realiza correctamente, se aplica el pincel al valor <xref:System.Windows.Shapes.Shape.Fill%2A> del objeto <xref:System.Windows.Shapes.Ellipse> que proporciona la interfaz de usuario del control Circle.  
  
    -   Marca el evento <xref:System.Windows.UIElement.Drop> como controlado.  Debe marcar el evento de colocación como controlado para que los otros elementos que reciben este evento sepan que el control de usuario Circle lo controló.  
  
3.  Presione F5 para compilar y ejecutar la aplicación.  
  
4.  Seleccione el texto `green`en <xref:System.Windows.Controls.TextBox>.  
  
5.  Arrastre el texto hasta un control Circle y colóquelo.  El círculo cambia de azul a verde.  
  
     ![Convertir una cadena en un pincel](../../../../docs/framework/wpf/advanced/media/dragdrop-dropgreentext.png "DragDrop\_DropGreenText")  
  
6.  Escriba el texto `green` en <xref:System.Windows.Controls.TextBox>.  
  
7.  Seleccione el texto `gre` en <xref:System.Windows.Controls.TextBox>.  
  
8.  Arrástrelo hasta un control Circle y colóquelo.  Observe que el cursor cambia para indicar que se permite la colocación, pero el color del círculo no cambia porque `gre` no es un color válido.  
  
9. Arrastre desde el control Circle verde y coloque en el control Circle azul.  El círculo cambia de azul a verde.  Observe que el cursor que se muestra depende de si el origen de arrastre es <xref:System.Windows.Controls.TextBox> o el círculo.  
  
 Establecer la propiedad <xref:System.Windows.UIElement.AllowDrop%2A> en `true` y procesar los datos colocados es todo lo que hace falta para permitir que un elemento sea un destino de colocación.  Sin embargo, para que la experiencia de usuario sea mejor, también debería controlar los eventos <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave> y <xref:System.Windows.UIElement.DragOver>.  En estos eventos, puede realizar comprobaciones y proporcionar información adicional al usuario antes de colocar los datos.  
  
 Cuando los datos se arrastran sobre el control de usuario Circle, el control debe notificar al origen de arrastre si puede procesar los datos que se están arrastrando.  Si el control no sabe cómo procesar los datos, debe rechazar la colocación.  Para ello, controlará el evento <xref:System.Windows.UIElement.DragOver> y establecerá la propiedad <xref:System.Windows.DragEventArgs.Effects%2A>.  
  
### Para comprobar que se permite la colocación de los datos  
  
1.  Abra Circle.xaml.cs o Circle.xaml.vb.  
  
2.  Agregue la siguiente invalidación de <xref:System.Windows.UIElement.OnDragOver%2A> para proporcionar control de clases para el evento <xref:System.Windows.UIElement.DragOver>.  
  
     [!code-csharp[DragDropWalkthrough#OnDragOver](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragover)]
     [!code-vb[DragDropWalkthrough#OnDragOver](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragover)]  
  
     La invalidación de <xref:System.Windows.UIElement.OnDragOver%2A> realiza las tareas siguientes:  
  
    -   Establece la propiedad <xref:System.Windows.DragEventArgs.Effects%2A> en <xref:System.Windows.DragDropEffects>.  
  
    -   Realiza las mismas comprobaciones que se realizan en el método <xref:System.Windows.UIElement.OnDrop%2A> para determinar si el control de usuario Circle puede procesar los datos arrastrados.  
  
    -   Si el control de usuario puede procesar los datos, establece la propiedad <xref:System.Windows.DragEventArgs.Effects%2A> en <xref:System.Windows.DragDropEffects> o <xref:System.Windows.DragDropEffects>.  
  
3.  Presione F5 para compilar y ejecutar la aplicación.  
  
4.  Seleccione el texto `gre` en <xref:System.Windows.Controls.TextBox>.  
  
5.  Arrastre el texto hasta un control Circle.  Observe que ahora el cursor cambia para indicar que no se permite la colocación porque `gre` no es un color válido.  
  
 Puede mejorar aún más la experiencia del usuario aplicando una vista previa de la operación de colocar.  Para el control de usuario Circle, invalidará los métodos <xref:System.Windows.UIElement.OnDragEnter%2A> y <xref:System.Windows.UIElement.OnDragLeave%2A>.  Cuando los datos se arrastran sobre el control, el valor <xref:System.Windows.Shapes.Shape.Fill%2A> de fondo actual se guarda en una variable de marcador de posición.  A continuación, la cadena se convierte en un pincel y se aplica al objeto <xref:System.Windows.Shapes.Ellipse> que proporciona la interfaz de usuario del círculo.  Si los datos se arrastran fuera del círculo sin colocarse, se vuelve a aplicar al círculo el valor original de <xref:System.Windows.Shapes.Shape.Fill%2A>.  
  
### Para obtener una vista previa de los efectos de la operación de arrastrar y colocar  
  
1.  Abra Circle.xaml.cs o Circle.xaml.vb.  
  
2.  En la clase Circle, declare una variable privada <xref:System.Windows.Media.Brush> denominada `_previousFill` e inicialícela en `null`.  
  
     [!code-csharp[DragDropWalkthrough#Brush](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#brush)]
     [!code-vb[DragDropWalkthrough#Brush](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#brush)]  
  
3.  Agregue la siguiente invalidación de <xref:System.Windows.UIElement.OnDragEnter%2A> para proporcionar control de clases para el evento <xref:System.Windows.UIElement.DragEnter>.  
  
     [!code-csharp[DragDropWalkthrough#OnDragEnter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragenter)]
     [!code-vb[DragDropWalkthrough#OnDragEnter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragenter)]  
  
     La invalidación de <xref:System.Windows.UIElement.OnDragEnter%2A> realiza las tareas siguientes:  
  
    -   Guarda la propiedad <xref:System.Windows.Shapes.Shape.Fill%2A> de <xref:System.Windows.Shapes.Ellipse> en la variable `_previousFill`.  
  
    -   Realiza las mismas comprobaciones que se realizan en el método <xref:System.Windows.UIElement.OnDrop%2A> para determinar si los datos se pueden convertir a <xref:System.Windows.Media.Brush>.  
  
    -   Si los datos se convierten en un <xref:System.Windows.Media.Brush> válido, se aplica a la propiedad <xref:System.Windows.Shapes.Shape.Fill%2A> de <xref:System.Windows.Shapes.Ellipse>.  
  
4.  Agregue la siguiente invalidación de <xref:System.Windows.UIElement.OnDragLeave%2A> para proporcionar control de clases para el evento <xref:System.Windows.UIElement.DragLeave>.  
  
     [!code-csharp[DragDropWalkthrough#OnDragLeave](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragleave)]
     [!code-vb[DragDropWalkthrough#OnDragLeave](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragleave)]  
  
     La invalidación de <xref:System.Windows.UIElement.OnDragLeave%2A> realiza las tareas siguientes:  
  
    -   Aplica el <xref:System.Windows.Media.Brush> guardado en la variable `_previousFill` a la propiedad <xref:System.Windows.Shapes.Shape.Fill%2A> del objeto <xref:System.Windows.Shapes.Ellipse> que proporciona la interfaz de usuario del control de usuario Circle.  
  
5.  Presione F5 para compilar y ejecutar la aplicación.  
  
6.  Seleccione el texto `green`en <xref:System.Windows.Controls.TextBox>.  
  
7.  Arrastre el texto sobre un control Circle sin colocarlo.  El círculo cambia de azul a verde.  
  
     ![Obtener una vista previa de los efectos de una operación de arrastrar y colocar](../../../../docs/framework/wpf/advanced/media/dragdrop-previeweffects.png "DragDrop\_PreviewEffects")  
  
8.  Arrastre el texto fuera del control Circle.  El círculo cambia de nuevo de verde a azul.  
  
## Habilitar un panel para recibir los datos colocados  
 En esta sección, permitirá que los paneles que hospedan los controles de usuario Circle actúen como destinos de colocación para los datos de Circle arrastrados.  Implementará código que permita mover un círculo de un panel a otro, o realizar una copia de un control Circle manteniendo presionada la tecla CTRL mientras se arrastra y coloca un círculo.  
  
### Para permitir que el panel sea un destino de colocación  
  
1.  Abra MainWindow.xaml.  
  
2.  Como se muestra en el código XAML siguiente, en cada uno de los controles <xref:System.Windows.Controls.StackPanel>, agregue controladores para los eventos <xref:System.Windows.UIElement.DragOver> y <xref:System.Windows.UIElement.Drop>.  Dé al controlador de eventos <xref:System.Windows.UIElement.DragOver> el nombre `panel_DragOver` y dé al controlador de eventos <xref:System.Windows.UIElement.Drop> el nombre `panel_Drop`.  
  
     [!code-xml[DragDropWalkthrough#PanelsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml#panelsxaml)]  
  
3.  Abra MainWindows.xaml.cs o MainWindow.xaml.vb.  
  
4.  Agregue el código siguiente para el controlador de eventos <xref:System.Windows.UIElement.DragOver>.  
  
     [!code-csharp[DragDropWalkthrough#PanelDragOver](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldragover)]
     [!code-vb[DragDropWalkthrough#PanelDragOver](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldragover)]  
  
     Este controlador de eventos <xref:System.Windows.UIElement.DragOver> realiza las tareas siguientes:  
  
    -   Comprueba si los datos arrastrados contienen los datos de "objeto" empaquetados en <xref:system.Windows.DataObject> por el control de usuario Circle y pasados en la llamada a <xref:System.Windows.DragDrop.DoDragDrop%2A>.  
  
    -   Si los datos de "objeto" están presentes, comprueba si la tecla CTRL está presionada.  
  
    -   Si la tecla CTRL está presionada, establece la propiedad <xref:System.Windows.DragEventArgs.Effects%2A> en <xref:System.Windows.DragDropEffects>.  En caso contrario, la propiedad <xref:System.Windows.DragEventArgs.Effects%2A> se establece en <xref:System.Windows.DragDropEffects>.  
  
5.  Agregue el código siguiente para el controlador de eventos <xref:System.Windows.UIElement.Drop>.  
  
     [!code-csharp[DragDropWalkthrough#PanelDrop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldrop)]
     [!code-vb[DragDropWalkthrough#PanelDrop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldrop)]  
  
     Este controlador de eventos <xref:System.Windows.UIElement.Drop> realiza las tareas siguientes:  
  
    -   Comprueba si el evento <xref:System.Windows.UIElement.Drop> ya se ha controlado.  Por ejemplo, si un círculo se coloca en otro círculo que controla el evento <xref:System.Windows.UIElement.Drop>, no sería deseable que lo controlase también el panel que contiene el círculo.  
  
    -   Si el evento <xref:System.Windows.UIElement.Drop> no está controlado, comprueba si la tecla CTRL está presionada.  
  
    -   Si la tecla CTRL está presionada cuando se produce <xref:System.Windows.UIElement.Drop>, realiza una copia de control Circle y la agrega a la colección <xref:System.Windows.Controls.Panel.Children%2A> de <xref:System.Windows.Controls.StackPanel>.  
  
    -   Si la tecla CTRL no está presionada, desplaza el círculo desde la colección de <xref:System.Windows.Controls.Panel.Children%2A> del panel primario hasta la colección <xref:System.Windows.Controls.Panel.Children%2A> del panel en el que se colocó.  
  
    -   Establece la propiedad <xref:System.Windows.DragEventArgs.Effects%2A> para notificar al método <xref:System.Windows.DragDrop.DoDragDrop%2A> si se realizó una operación de mover o copiar.  
  
6.  Presione F5 para compilar y ejecutar la aplicación.  
  
7.  Seleccione el texto `green` de <xref:System.Windows.Controls.TextBox>.  
  
8.  Arrastre el texto sobre un control Circle y colóquelo.  
  
9. Arrastre un control Circle del panel izquierdo al panel derecho y colóquelo.  El círculo se quita de la colección de <xref:System.Windows.Controls.Panel.Children%2A> del panel izquierdo y se agrega a la colección Children del panel derecho.  
  
10. Arrastre un control Circle del panel donde se encuentra hasta el otro panel y colóquelo mientras presiona la tecla CTRL.  Se copia el círculo y la copia se agrega a la colección <xref:System.Windows.Controls.Panel.Children%2A> del panel receptor.  
  
     ![Arrastrar un círculo mientras se presiona la tecla CTRL](../../../../docs/framework/wpf/advanced/media/dragdrop-paneldrop.png "DragDrop\_PanelDrop")  
  
## Vea también  
 [Información general sobre la función de arrastrar y colocar](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)