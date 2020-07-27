---
title: 'Tutorial: Habilitar la técnica de arrastrar y colocar en un control de usuario'
description: Obtenga información sobre cómo crear un control de usuario personalizado que pueda participar en la transferencia de datos de arrastrar y colocar en Windows Presentation Foundation.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthrough [WPF], drag-and-drop
- drag-and-drop [WPF], walkthrough
ms.assetid: cc844419-1a77-4906-95d9-060d79107fc7
ms.openlocfilehash: 12ad47035a09995094014841b083062743fc2574
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168285"
---
# <a name="walkthrough-enabling-drag-and-drop-on-a-user-control"></a>Tutorial: Habilitar la técnica de arrastrar y colocar en un control de usuario

En este tutorial se muestra cómo crear un control de usuario personalizado que pueda participar en la transferencia de datos de arrastrar y colocar en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].

En este tutorial, creará un WPF personalizado <xref:System.Windows.Controls.UserControl> que representa una forma circular. Implementará la funcionalidad del control para habilitar la transferencia de datos mediante la técnica de arrastrar y colocar. Por ejemplo, si arrastra de un control de círculo a otro, se copian los datos del color de relleno del círculo de origen al de destino. Si arrastra de un control de círculo a un <xref:System.Windows.Controls.TextBox> , la representación de cadena del color de relleno se copia en <xref:System.Windows.Controls.TextBox> . También creará una pequeña aplicación que contiene dos controles de panel y un <xref:System.Windows.Controls.TextBox> para probar la funcionalidad de arrastrar y colocar. Escribirá código para que los paneles puedan procesar los datos del círculo colocado, lo que le permitirá mover o copiar círculos de la colección secundaria de un panel a otro.

En este tutorial se muestran las tareas siguientes:

- Crear un control de usuario personalizado.

- Permitir que el control de usuario sea un origen de arrastre.

- Permitir que el control de usuario sea un destino de colocación.

- Permitir que un panel reciba los datos que se colocan desde el control de usuario.

## <a name="prerequisites"></a>Requisitos previos

Necesita Visual Studio para completar este tutorial.

## <a name="create-the-application-project"></a>Crear el proyecto de aplicación
 En esta sección, creará la infraestructura de la aplicación, que incluye una página principal con dos paneles y un <xref:System.Windows.Controls.TextBox> .

1. Cree un proyecto de aplicación de WPF en Visual Basic o Visual C# denominado `DragDropExample`. Para obtener más información, vea [Tutorial: Mi primera aplicación de escritorio WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md).

2. Abra MainWindow.xaml.

3. Agregue el marcado siguiente entre las etiquetas de apertura y cierre <xref:System.Windows.Controls.Grid> .

     Este marcado crea la interfaz de usuario de la aplicación de prueba.

     [!code-xaml[DragDropWalkthrough#PanelsStep1XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep1xaml)]

## <a name="add-a-new-user-control-to-the-project"></a>Agregar un nuevo control de usuario al proyecto
 En esta sección, agregará un nuevo control de usuario al proyecto.

1. En el menú Proyecto, seleccione **Agregar control de usuario**.

2. En el cuadro de diálogo **Agregar nuevo elemento** , cambie el nombre a `Circle.xaml` y haga clic en **Agregar**.

     Circle.xaml y su código subyacente se agregan al proyecto.

3. Abra Circle.xaml.

     Este archivo contendrá los elementos de la interfaz de usuario del control de usuario.

4. Agregue el siguiente marcado a la raíz <xref:System.Windows.Controls.Grid> para crear un control de usuario simple que tenga un círculo azul como su interfaz de usuario.

     [!code-xaml[DragDropWalkthrough#EllipseXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#ellipsexaml)]

5. Abra Circle.xaml.cs o Circle.xaml.vb.

6. En C#, agregue el código siguiente después del constructor sin parámetros para crear un constructor de copias. En Visual Basic, agregue el código siguiente para crear un constructor sin parámetros y un constructor de copias.

     Para permitir que se copie el control de usuario, puede agregar un método de constructor de copias en el archivo de código subyacente. En el control de usuario de círculo simplificado, solo copiará el relleno y el tamaño del control de usuario.

     [!code-csharp[DragDropWalkthrough#CopyCtor](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#copyctor)]
     [!code-vb[DragDropWalkthrough#CopyCtor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#copyctor)]

## <a name="add-the-user-control-to-the-main-window"></a>Agregar el control de usuario a la ventana principal

1. Abra MainWindow.xaml.

2. Agregue el código XAML siguiente a la <xref:System.Windows.Window> etiqueta de apertura para crear una referencia de espacio de nombres XML a la aplicación actual.

    ```xaml
    xmlns:local="clr-namespace:DragDropExample"
    ```

3. En la primera <xref:System.Windows.Controls.StackPanel> , agregue el código XAML siguiente para crear dos instancias del control de usuario de círculo en el primer panel.

     [!code-xaml[DragDropWalkthrough#CirclesXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#circlesxaml)]

     El código XAML completo del panel tendrá el aspecto siguiente.

     [!code-xaml[DragDropWalkthrough#PanelsStep2XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep2xaml)]

## <a name="implement-drag-source-events-in-the-user-control"></a>Implementar eventos de origen de arrastre en el control de usuario
 En esta sección, se invalidará el <xref:System.Windows.UIElement.OnMouseMove%2A> método y se iniciará la operación de arrastrar y colocar.

 Si se inicia un arrastre (se presiona un botón del mouse y se mueve el mouse), se empaquetarán los datos que se van a transferir a <xref:System.Windows.DataObject> . En este caso, el control de círculo empaquetará tres elementos de datos: una representación de cadena de su color de relleno, una representación doble de su altura y una copia de sí mismo.

### <a name="to-initiate-a-drag-and-drop-operation"></a>Para iniciar una operación de arrastrar y colocar

1. Abra Circle.xaml.cs o Circle.xaml.vb.

2. Agregue la siguiente <xref:System.Windows.UIElement.OnMouseMove%2A> invalidación para proporcionar el control de clases para el <xref:System.Windows.UIElement.MouseMove> evento.

     [!code-csharp[DragDropWalkthrough#OnMouseMove](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#onmousemove)]
     [!code-vb[DragDropWalkthrough#OnMouseMove](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#onmousemove)]

     Esta <xref:System.Windows.UIElement.OnMouseMove%2A> invalidación realiza las siguientes tareas:

    - Comprueba si el botón primario del mouse está presionado mientras este se mueve.

    - Empaqueta los datos del círculo en un <xref:System.Windows.DataObject> . En este caso, el control de círculo empaqueta tres elementos de datos: una representación de cadena de su color de relleno, una representación doble de su altura y una copia de sí mismo.

    - Llama al <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> método estático para iniciar la operación de arrastrar y colocar. Pase los tres parámetros siguientes al <xref:System.Windows.DragDrop.DoDragDrop%2A> método:

        - `dragSource`: una referencia a este control.

        - `data`: <xref:System.Windows.DataObject> Creado en el código anterior.

        - `allowedEffects`: Las operaciones de arrastrar y colocar permitidas, que son <xref:System.Windows.DragDropEffects.Copy> o <xref:System.Windows.DragDropEffects.Move> .

3. Presione **F5** para compilar y ejecutar la aplicación.

4. Haga clic en uno de los controles de círculo y arrástrelo sobre los paneles, el otro círculo y el <xref:System.Windows.Controls.TextBox> . Al arrastrar sobre <xref:System.Windows.Controls.TextBox> , el cursor cambia para indicar un movimiento.

5. Mientras arrastra un círculo sobre el <xref:System.Windows.Controls.TextBox> **control** , presione la tecla Ctrl. Observe que el cursor cambia para indicar una copia.

6. Arrastre y coloque un círculo en el <xref:System.Windows.Controls.TextBox> . La representación de cadena del color de relleno del círculo se anexa al <xref:System.Windows.Controls.TextBox> .

     ![Representación de cadena del color de relleno del círculo](./media/dragdrop-colorstring.png "DragDrop_ColorString")

De forma predeterminada, el cursor cambiará durante una operación de arrastrar y colocar para indicar el efecto que tendrá la colocación de los datos. Puede personalizar los comentarios asignados al usuario controlando el <xref:System.Windows.UIElement.GiveFeedback> evento y estableciendo un cursor diferente.

## <a name="give-feedback-to-the-user"></a>Enviar comentarios al usuario

1. Abra Circle.xaml.cs o Circle.xaml.vb.

2. Agregue la siguiente <xref:System.Windows.UIElement.OnGiveFeedback%2A> invalidación para proporcionar el control de clases para el <xref:System.Windows.UIElement.GiveFeedback> evento.

     [!code-csharp[DragDropWalkthrough#OnGiveFeedback](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ongivefeedback)]
     [!code-vb[DragDropWalkthrough#OnGiveFeedback](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ongivefeedback)]

     Esta <xref:System.Windows.UIElement.OnGiveFeedback%2A> invalidación realiza las siguientes tareas:

    - Comprueba los <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> valores que se establecen en el controlador de eventos del destino de colocación <xref:System.Windows.UIElement.DragOver> .

    - Establece un cursor personalizado basado en el <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> valor. El cursor está diseñado para proporcionar información visual al usuario sobre el efecto que tendrá la colocación de los datos.

3. Presione **F5** para compilar y ejecutar la aplicación.

4. Arrastre uno de los controles de círculo sobre los paneles, el otro círculo y <xref:System.Windows.Controls.TextBox> . Observe que los cursores son ahora los cursores personalizados que especificó en la <xref:System.Windows.UIElement.OnGiveFeedback%2A> invalidación.

     ![Arrastrar y colocar con cursores personalizados](./media/dragdrop-customcursor.png "DragDrop_CustomCursor")

5. Seleccione el texto `green` de la <xref:System.Windows.Controls.TextBox> .

6. Arrastre el texto `green` a un control de círculo. Observe que los cursores predeterminados se muestran para indicar los efectos de la operación de arrastrar y colocar. El origen de arrastre siempre establece el cursor de retroacción.

## <a name="implement-drop-target-events-in-the-user-control"></a>Implementar eventos de destino de colocación en el control de usuario
 En esta sección, especificará que el control de usuario es un destino de colocación, invalidará los métodos que permiten que el control de usuario sea un destino de colocación y procesará los datos que se colocan en él.

### <a name="to-enable-the-user-control-to-be-a-drop-target"></a>Para permitir que el control de usuario sea un destino de colocación

1. Abra Circle.xaml.

2. En la etiqueta de apertura <xref:System.Windows.Controls.UserControl> , agregue la <xref:System.Windows.UIElement.AllowDrop%2A> propiedad y establézcala en `true` .

     [!code-xaml[DragDropWalkthrough#UCTagXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#uctagxaml)]

<xref:System.Windows.UIElement.OnDrop%2A>Se llama al método cuando la <xref:System.Windows.UIElement.AllowDrop%2A> propiedad se establece en `true` y los datos del origen de arrastre se colocan en el control de usuario del círculo. En este método, procesará los datos que se han colocado y aplicará los datos al círculo.

### <a name="to-process-the-dropped-data"></a>Para procesar los datos colocados

1. Abra Circle.xaml.cs o Circle.xaml.vb.

2. Agregue la siguiente <xref:System.Windows.UIElement.OnDrop%2A> invalidación para proporcionar el control de clases para el <xref:System.Windows.UIElement.Drop> evento.

     [!code-csharp[DragDropWalkthrough#OnDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondrop)]
     [!code-vb[DragDropWalkthrough#OnDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondrop)]

     Esta <xref:System.Windows.UIElement.OnDrop%2A> invalidación realiza las siguientes tareas:

    - Utiliza el <xref:System.Windows.DataObject.GetDataPresent%2A> método para comprobar si los datos arrastrados contienen un objeto de cadena.

    - Utiliza el <xref:System.Windows.DataObject.GetData%2A> método para extraer los datos de cadena si están presentes.

    - Utiliza un <xref:System.Windows.Media.BrushConverter> para intentar convertir la cadena en un <xref:System.Windows.Media.Brush> .

    - Si la conversión se realiza correctamente, aplica el pincel al <xref:System.Windows.Shapes.Shape.Fill%2A> del <xref:System.Windows.Shapes.Ellipse> que proporciona la interfaz de usuario del control de círculo.

    - Marca el <xref:System.Windows.UIElement.Drop> evento como controlado. Debe marcar el evento de colocación como controlado para que los elementos que reciban este evento sepan que el control de usuario de círculo lo ha controlado.

3. Presione **F5** para compilar y ejecutar la aplicación.

4. Seleccione el texto `green` en el <xref:System.Windows.Controls.TextBox> .

5. Arrastre el texto a un control de círculo y colóquelo. El círculo cambia de azul a verde.

     ![Convertir una cadena en un pincel](./media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")

6. Escriba el texto `green` en <xref:System.Windows.Controls.TextBox> .

7. Seleccione el texto `gre` en el <xref:System.Windows.Controls.TextBox> .

8. Arrástrelo a un control de círculo y colóquelo. Observe que el cursor cambia para indicar que se permite la colocación, pero el color del círculo no cambia porque `gre` no es un color válido.

9. Arrastre desde el control de círculo verde y coloque en el control de círculo azul. El círculo cambia de azul a verde. Observe que el cursor que se muestra depende de si el <xref:System.Windows.Controls.TextBox> o el círculo es el origen de arrastre.

La configuración de la <xref:System.Windows.UIElement.AllowDrop%2A> propiedad en `true` y el procesamiento de los datos colocados es todo lo necesario para permitir que un elemento sea un destino de colocación. Sin embargo, para proporcionar una mejor experiencia de usuario, también debe controlar <xref:System.Windows.UIElement.DragEnter> los <xref:System.Windows.UIElement.DragLeave> eventos, y <xref:System.Windows.UIElement.DragOver> . En estos eventos, puede realizar comprobaciones y proporcionar repuesta adicional al usuario antes de que se coloquen los datos.

Cuando los datos se arrastran sobre el control de usuario de círculo, el control debe notificarle al origen de arrastre si puede procesar los datos que se están arrastrando. Si el control no sabe cómo procesar los datos, debe rechazar la operación de colocar. Para ello, controlará el <xref:System.Windows.UIElement.DragOver> evento y establecerá la <xref:System.Windows.DragEventArgs.Effects%2A> propiedad.

### <a name="to-verify-that-the-data-drop-is-allowed"></a>Para comprobar que se permite la colocación de datos

1. Abra Circle.xaml.cs o Circle.xaml.vb.

2. Agregue la siguiente <xref:System.Windows.UIElement.OnDragOver%2A> invalidación para proporcionar el control de clases para el <xref:System.Windows.UIElement.DragOver> evento.

     [!code-csharp[DragDropWalkthrough#OnDragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragover)]
     [!code-vb[DragDropWalkthrough#OnDragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragover)]

     Esta <xref:System.Windows.UIElement.OnDragOver%2A> invalidación realiza las siguientes tareas:

    - Establece la propiedad <xref:System.Windows.DragEventArgs.Effects%2A> como <xref:System.Windows.DragDropEffects.None>.

    - Realiza las mismas comprobaciones que se realizan en el <xref:System.Windows.UIElement.OnDrop%2A> método para determinar si el control de usuario de círculo puede procesar los datos arrastrados.

    - Si el control de usuario puede procesar los datos, establece la <xref:System.Windows.DragEventArgs.Effects%2A> propiedad en <xref:System.Windows.DragDropEffects.Copy> o <xref:System.Windows.DragDropEffects.Move> .

3. Presione **F5** para compilar y ejecutar la aplicación.

4. Seleccione el texto `gre` en el <xref:System.Windows.Controls.TextBox> .

5. Arrastre el texto a un control de círculo. Observe que ahora el cursor cambia para indicar que no se permite la colocación porque `gre` no es un color válido.

 Puede mejorar la experiencia del usuario si aplica una vista previa de la operación de colocar. Para el control de usuario de círculo, invalidará los <xref:System.Windows.UIElement.OnDragEnter%2A> <xref:System.Windows.UIElement.OnDragLeave%2A> métodos y. Cuando los datos se arrastran sobre el control, el fondo actual <xref:System.Windows.Shapes.Shape.Fill%2A> se guarda en una variable de marcador de posición. A continuación, la cadena se convierte en un pincel y se aplica al <xref:System.Windows.Shapes.Ellipse> que proporciona la interfaz de usuario del círculo. Si los datos se arrastran fuera del círculo sin quitarlos, el valor original <xref:System.Windows.Shapes.Shape.Fill%2A> se vuelve a aplicar al círculo.

### <a name="to-preview-the-effects-of-the-drag-and-drop-operation"></a>Para obtener una vista previa de los efectos de la operación de arrastrar y colocar

1. Abra Circle.xaml.cs o Circle.xaml.vb.

2. En la clase Circle, declare una <xref:System.Windows.Media.Brush> variable privada denominada `_previousFill` e inicialícela en `null` .

     [!code-csharp[DragDropWalkthrough#Brush](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#brush)]
     [!code-vb[DragDropWalkthrough#Brush](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#brush)]

3. Agregue la siguiente <xref:System.Windows.UIElement.OnDragEnter%2A> invalidación para proporcionar el control de clases para el <xref:System.Windows.UIElement.DragEnter> evento.

     [!code-csharp[DragDropWalkthrough#OnDragEnter](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragenter)]
     [!code-vb[DragDropWalkthrough#OnDragEnter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragenter)]

     Esta <xref:System.Windows.UIElement.OnDragEnter%2A> invalidación realiza las siguientes tareas:

    - Guarda la <xref:System.Windows.Shapes.Shape.Fill%2A> propiedad de <xref:System.Windows.Shapes.Ellipse> en la `_previousFill` variable.

    - Realiza las mismas comprobaciones que se realizan en el <xref:System.Windows.UIElement.OnDrop%2A> método para determinar si los datos se pueden convertir en <xref:System.Windows.Media.Brush> .

    - Si los datos se convierten en un válido <xref:System.Windows.Media.Brush> , se aplica a la <xref:System.Windows.Shapes.Shape.Fill%2A> de <xref:System.Windows.Shapes.Ellipse> .

4. Agregue la siguiente <xref:System.Windows.UIElement.OnDragLeave%2A> invalidación para proporcionar el control de clases para el <xref:System.Windows.UIElement.DragLeave> evento.

     [!code-csharp[DragDropWalkthrough#OnDragLeave](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragleave)]
     [!code-vb[DragDropWalkthrough#OnDragLeave](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragleave)]

     Esta <xref:System.Windows.UIElement.OnDragLeave%2A> invalidación realiza las siguientes tareas:

    - Aplica el <xref:System.Windows.Media.Brush> guardado en la `_previousFill` variable al <xref:System.Windows.Shapes.Shape.Fill%2A> del <xref:System.Windows.Shapes.Ellipse> que proporciona la interfaz de usuario del control de usuario de círculo.

5. Presione **F5** para compilar y ejecutar la aplicación.

6. Seleccione el texto `green` en el <xref:System.Windows.Controls.TextBox> .

7. Arrastre el texto sobre un control de círculo sin colocarlo. El círculo cambia de azul a verde.

     ![Obtener una vista previa de los efectos de una&#45;de arrastre y&#45;operación de colocar](./media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")

8. Arrastre el texto fuera del control de círculo. El círculo cambia de verde a azul.

## <a name="enable-a-panel-to-receive-dropped-data"></a>Habilitar un panel para recibir datos colocados

En esta sección, habilitará los paneles que hospedan los controles de usuario de círculo para que actúen como destinos de colocación de los datos de círculo arrastrados. Implementará código que le permite mover un círculo de un panel a otro, o realizar una copia de un control de círculo manteniendo presionada la tecla **Ctrl** mientras arrastra y coloca un círculo.

1. Abra MainWindow.xaml.

2. Como se muestra en el código XAML siguiente, en cada uno de los <xref:System.Windows.Controls.StackPanel> controles, agregue Controladores para los <xref:System.Windows.UIElement.DragOver> <xref:System.Windows.UIElement.Drop> eventos y. Asigne al controlador de eventos el nombre, <xref:System.Windows.UIElement.DragOver> `panel_DragOver` , y el nombre del <xref:System.Windows.UIElement.Drop> controlador de eventos, `panel_Drop` .

     [!code-xaml[DragDropWalkthrough#PanelsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml#panelsxaml)]

3. Abra MainWindows.xaml.cs o MainWindow.xaml.vb.

4. Agregue el código siguiente para el <xref:System.Windows.UIElement.DragOver> controlador de eventos.

     [!code-csharp[DragDropWalkthrough#PanelDragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldragover)]
     [!code-vb[DragDropWalkthrough#PanelDragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldragover)]

     Este <xref:System.Windows.UIElement.DragOver> controlador de eventos realiza las siguientes tareas:

    - Comprueba que los datos arrastrados contienen los datos de "objeto" empaquetados <xref:System.Windows.DataObject> por el control de usuario de círculo y que se han pasado en la llamada a <xref:System.Windows.DragDrop.DoDragDrop%2A> .

    - Si los datos de "objeto" están presentes, comprueba si se ha presionado la tecla **Ctrl** .

    - Si se presiona la tecla **Ctrl** , establece la <xref:System.Windows.DragEventArgs.Effects%2A> propiedad en <xref:System.Windows.DragDropEffects.Copy> . En caso contrario, establezca la <xref:System.Windows.DragEventArgs.Effects%2A> propiedad en <xref:System.Windows.DragDropEffects.Move> .

5. Agregue el código siguiente para el <xref:System.Windows.UIElement.Drop> controlador de eventos.

     [!code-csharp[DragDropWalkthrough#PanelDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldrop)]
     [!code-vb[DragDropWalkthrough#PanelDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldrop)]

     Este <xref:System.Windows.UIElement.Drop> controlador de eventos realiza las siguientes tareas:

    - Comprueba si el <xref:System.Windows.UIElement.Drop> evento ya se ha controlado. Por ejemplo, si se coloca un círculo en otro círculo que controla el <xref:System.Windows.UIElement.Drop> evento, no se desea que el panel que contiene el círculo también lo controle.

    - Si <xref:System.Windows.UIElement.Drop> no se controla el evento, comprueba si se ha presionado la tecla **Ctrl** .

    - Si se presiona la tecla **Ctrl** cuando <xref:System.Windows.UIElement.Drop> sucede, realiza una copia del control de círculo y la agrega a la <xref:System.Windows.Controls.Panel.Children%2A> colección de <xref:System.Windows.Controls.StackPanel> .

    - Si no se presiona la tecla **Ctrl** , mueve el círculo de la <xref:System.Windows.Controls.Panel.Children%2A> colección de su panel primario a la <xref:System.Windows.Controls.Panel.Children%2A> colección del panel en el que se colocó.

    - Establece la <xref:System.Windows.DragEventArgs.Effects%2A> propiedad para notificar al <xref:System.Windows.DragDrop.DoDragDrop%2A> método si se realizó una operación de movimiento o copia.

6. Presione **F5** para compilar y ejecutar la aplicación.

7. Seleccione el texto `green` de la <xref:System.Windows.Controls.TextBox> .

8. Arrastre el texto sobre un control de círculo y colóquelo.

9. Arrastre un control de círculo del panel izquierdo al panel derecho y colóquelo. El círculo se quita de la <xref:System.Windows.Controls.Panel.Children%2A> colección del panel izquierdo y se agrega a la colección de elementos secundarios del panel derecho.

10. Arrastre un control Circle desde el panel en el que se encuentra al otro panel y colóquelo mientras presiona la tecla **Ctrl** . Se copia el círculo y la copia se agrega a la <xref:System.Windows.Controls.Panel.Children%2A> colección del panel receptor.

     ![Arrastrar un círculo mientras se presiona la tecla CTRL](./media/dragdrop-paneldrop.png "DragDrop_PanelDrop")

## <a name="see-also"></a>Vea también

- [Información general sobre la función de arrastrar y colocar](drag-and-drop-overview.md)
