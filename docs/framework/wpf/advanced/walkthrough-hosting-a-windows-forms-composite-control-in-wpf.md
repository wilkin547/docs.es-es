---
title: 'Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
- composite controls [WPF], hosting in WPF
ms.assetid: 96fcd78d-1c77-4206-8928-3a0579476ef4
ms.openlocfilehash: e4c1de17b131ee68c6e6fce0035b703eb5b489a0
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991881"
---
# <a name="walkthrough-hosting-a-windows-forms-composite-control-in-wpf"></a>Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona un entorno rico para crear aplicaciones. Sin embargo, si tiene una inversión sustancial en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] código, puede ser más eficaz reutilizar al menos parte de ese código en la aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en lugar de volver a escribirlo desde el principio. El escenario más común es cuando tiene controles de Windows Forms existentes. En algunos casos, incluso podría no tener acceso al código fuente de estos controles. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]proporciona un procedimiento sencillo para hospedar estos controles en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] una aplicación. Por ejemplo, puede usar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para la mayor parte de la programación mientras hospeda los controles especializados. <xref:System.Windows.Forms.DataGridView>  
  
 Este tutorial le guía a través de una aplicación que hospeda un Windows Forms control compuesto para realizar entradas de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] datos en una aplicación. El control compuesto se empaqueta en un archivo DLL. Este procedimiento general se puede extender a aplicaciones y controles más complejos. Este tutorial está diseñado para ser casi idéntico en aspecto y funcionalidad al [Tutorial: Hospedar un control compuesto de WPF](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)en Windows Forms. La principal diferencia es que se invierte el escenario de hospedaje.  
  
 Este tutorial está dividido en dos secciones. En la primera sección se describe brevemente la implementación de Windows Forms control compuesto. En la segunda sección se explica en detalle cómo hospedar el control compuesto en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] una aplicación, recibir eventos del control y tener acceso a algunas de las propiedades del control.  
  
 Las tareas ilustradas en este tutorial incluyen:  
  
- Implementar el control compuesto de formularios Windows Forms.  
  
- Implementar la aplicación host de WPF.  
  
 Para obtener una lista de código completa de las tareas ilustradas en este tutorial, vea [hospedar un Windows Forms control compuesto en el ejemplo de WPF](https://go.microsoft.com/fwlink/?LinkID=159999).  
  
## <a name="prerequisites"></a>Requisitos previos  

Necesita Visual Studio para completar este tutorial.
  
## <a name="implementing-the-windows-forms-composite-control"></a>Implementar el control compuesto de formularios Windows Forms  
 El Windows Forms control compuesto utilizado en este ejemplo es un formulario de entrada de datos simple. Este formulario toma el nombre y la dirección del usuario y, después, usa un evento personalizado para devolver esa información al host. En la ilustración siguiente se muestra la representación del control.  

 La siguiente imagen muestra un Windows Forms control compuesto:  

 ![Captura de pantalla que muestra un control de Windows Forms simple.](./media/walkthrough-hosting-a-windows-forms-composite-control-in-wpf/windows-forms-control.gif)  
  
### <a name="creating-the-project"></a>Crear el proyecto  
 Para iniciar el proyecto:  
  
1. Inicie [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]y abra el cuadro de diálogo **nuevo proyecto** .  
  
2. En la categoría de ventana, seleccione la plantilla **biblioteca de controles de Windows Forms** .  
  
3. Asigne al nuevo proyecto el nombre de `MyControls`.  
  
4. Para la ubicación, especifique una carpeta de nivel superior con un nombre adecuado, `WpfHostingWindowsFormsControl`como. Más tarde, colocará la aplicación host en esta carpeta.  
  
5. Haga clic en **Aceptar** para crear el proyecto. El proyecto predeterminado contiene un único control denominado `UserControl1`.  
  
6. En explorador de soluciones, cambie el `UserControl1` nombre `MyControl1`a.  
  
 El proyecto debe tener referencias a los siguientes archivos DLL del sistema. Si alguno de estos archivos DLL no está incluido de forma predeterminada, agréguelo al proyecto.  
  
- Sistema  
  
- System.Data  
  
- System.Drawing  
  
- System.Windows.Forms  
  
- System.Xml  
  
### <a name="adding-controls-to-the-form"></a>Agregar controles al formulario  
 Para agregar controles al formulario:  
  
- Abra `MyControl1` en el diseñador.  
  
 En el <xref:System.Windows.Forms.Label> formulario, agregue cinco <xref:System.Windows.Forms.TextBox> controles y sus controles correspondientes, con el tamaño y el orden en que se encuentran en la ilustración anterior. En el ejemplo, los <xref:System.Windows.Forms.TextBox> controles se denominan:  
  
- `txtName`  
  
- `txtAddress`  
  
- `txtCity`  
  
- `txtState`  
  
- `txtZip`  
  
 Agregue dos <xref:System.Windows.Forms.Button> controles con la etiqueta **Aceptar** y **Cancelar**. En el ejemplo, los nombres de botón `btnOK` son `btnCancel`y, respectivamente.  
  
### <a name="implementing-the-supporting-code"></a>Implementar el código auxiliar  
 Abra el formulario en la vista Código. El control devuelve los datos recopilados a su host generando el `OnButtonClick` evento personalizado. Los datos están contenidos en el objeto de argumento de evento. En el código siguiente se muestra la declaración de evento y delegado.  
  
 Agregue el código siguiente a la clase `MyControl1` .  
  
 [!code-csharp[WpfHostingWindowsFormsControl#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#2)]
 [!code-vb[WpfHostingWindowsFormsControl#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#2)]

 La `MyControlEventArgs` clase contiene la información que se va a devolver al host.

 Agregue la clase siguiente al formulario.

 [!code-csharp[WpfHostingWindowsFormsControl#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#3)]
 [!code-vb[WpfHostingWindowsFormsControl#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#3)]

 Cuando el usuario hace clic en el botón **Aceptar** o **Cancelar** , <xref:System.Windows.Forms.Control.Click> los controladores de eventos crean `MyControlEventArgs` un objeto que contiene los datos y genera `OnButtonClick` el evento. La única diferencia entre los dos controladores es la propiedad del argumento del `IsOK` evento. Esta propiedad permite que el host determine en qué botón se ha hecho clic. Se establece en `true` para el botón **Aceptar** y `false` para el botón **Cancelar** . En el código siguiente se muestran los dos controladores de botón.

 Agregue el código siguiente a la clase `MyControl1` .

 [!code-csharp[WpfHostingWindowsFormsControl#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#4)]
 [!code-vb[WpfHostingWindowsFormsControl#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#4)]

### <a name="giving-the-assembly-a-strong-name-and-building-the-assembly"></a>Dar un nombre seguro al ensamblado y compilar el ensamblado
 Para que una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación haga referencia a este ensamblado, debe tener un nombre seguro. Para crear un nombre seguro, cree un archivo de clave con SN. exe y agréguelo al proyecto.

1. Abra un símbolo del sistema de [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]. Para ello, haga clic en el menú **Inicio** y, a continuación, seleccione **todos los programas/Microsoft Visual Studio 2010/Visual Studio Tools/símbolo del sistema de Visual Studio**. Esto inicia una ventana de consola con variables de entorno personalizadas.

2. En el símbolo del sistema, use `cd` el comando para ir a la carpeta del proyecto.

3. Ejecute el comando siguiente para generar un archivo de clave denominado MyControls.snk.

    ```console
    Sn.exe -k MyControls.snk
    ```

4. Para incluir el archivo de clave en el proyecto, haga clic con el botón secundario en el nombre del proyecto en Explorador de soluciones y, a continuación, haga clic en **propiedades**. En el diseñador de proyectos, haga clic en la pestaña **firma** , active la casilla **firmar el ensamblado** y, a continuación, busque el archivo de clave.

5. Compile la solución. La compilación generará un archivo DLL denominado MyControls.dll.

## <a name="implementing-the-wpf-host-application"></a>Implementar la aplicación host de WPF
 La [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación host utiliza el <xref:System.Windows.Forms.Integration.WindowsFormsHost> control para hospedar `MyControl1`. La aplicación controla el `OnButtonClick` evento para recibir los datos del control. También tiene una colección de botones de opción que le permiten cambiar algunas de las propiedades del control de la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación. En la ilustración siguiente se muestra la aplicación finalizada.

En la imagen siguiente se muestra la aplicación completa, incluido el control insertado en la aplicación WPF:

 ![Captura de pantalla que muestra un control incrustado en una página de WPF.](./media/walkthrough-hosting-a-windows-forms-composite-control-in-wpf/windows-presentation-foundation-page-control.gif)

### <a name="creating-the-project"></a>Crear el proyecto
 Para iniciar el proyecto:

1. Abra [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]y seleccione **nuevo proyecto**.

2. En la categoría de ventana, seleccione la plantilla **aplicación WPF** .

3. Asigne al nuevo proyecto el nombre de `WpfHost`.

4. Para la ubicación, especifique la misma carpeta de nivel superior que contiene el proyecto MyControls.

5. Haga clic en **Aceptar** para crear el proyecto.

 También debe agregar referencias al archivo DLL que contenga `MyControl1` y a otros ensamblados.

1. Haga clic con el botón derecho en el nombre del proyecto en Explorador de soluciones y seleccione **Agregar referencia**.

2. Haga clic en la pestaña **examinar** y busque la carpeta que contiene DataControl. dll. En este tutorial, esta carpeta es MyControls\bin\Debug.

3. Seleccione Datacontrols. dll y, a continuación, haga clic en **Aceptar**.

4. Agregue una referencia al ensamblado WindowsFormsIntegration, denominado WindowsFormsIntegration. dll.

### <a name="implementing-the-basic-layout"></a>Implementar el diseño básico
 La [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] de la aplicación host se implementa en MainWindow. Xaml. Este archivo contiene [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] el marcado que define el diseño y hospeda el control Windows Forms. La aplicación se divide en tres regiones:

- El panel **propiedades del control** , que contiene una colección de botones de opción que puede usar para modificar diversas propiedades del control hospedado.

- Los **datos del panel de control** , que contiene <xref:System.Windows.Controls.TextBlock> varios elementos que muestran los datos devueltos por el control hospedado.

- El control hospedado.

 En el siguiente código XAML se muestra el diseño básico. El marcado que se necesita para hospedar `MyControl1` se omite en este ejemplo, pero se tratará más adelante.

 Reemplace el código XAML del archivo MainWindow.xaml.vb por el código siguiente. Si está utilizando Visual Basic, cambie la clase a `x:Class="MainWindow"`.

 [!code-xaml[WpfHostingWindowsFormsControl#100](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#100)]

 El primer <xref:System.Windows.Controls.StackPanel> elemento contiene varios conjuntos de <xref:System.Windows.Controls.RadioButton> controles que le permiten modificar varias propiedades predeterminadas del control hospedado. Seguido de un <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento, que hospeda `MyControl1`. El último <xref:System.Windows.Controls.StackPanel> elemento contiene varios <xref:System.Windows.Controls.TextBlock> elementos que muestran los datos devueltos por el control hospedado. El orden de los elementos y los <xref:System.Windows.Controls.DockPanel.Dock%2A> valores <xref:System.Windows.FrameworkElement.Height%2A> de los atributos y insertan el control hospedado en la ventana sin espacios ni distorsión.

#### <a name="hosting-the-control"></a>Hospedar el control
 La siguiente versión editada del código XAML anterior se centra en los elementos que son necesarios `MyControl1`para hospedar.

 [!code-xaml[WpfHostingWindowsFormsControl#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#101)]
[!code-xaml[WpfHostingWindowsFormsControl#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#102)]

 El `xmlns` atributo de asignación de espacio de nombres crea `MyControls` una referencia al espacio de nombres que contiene el control hospedado. Esta asignación permite representar `MyControl1` en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] como `<mcl:MyControl1>`.

 Dos elementos del código XAML controlan el hospedaje:

- `WindowsFormsHost`representa el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento que permite hospedar un control de Windows Forms en una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación.

- `mcl:MyControl1`, que representa `MyControl1`, se agrega a la <xref:System.Windows.Forms.Integration.WindowsFormsHost> colección secundaria del elemento. Como resultado, este Windows Forms control se representa como parte de la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ventana y puede comunicarse con el control desde la aplicación.

### <a name="implementing-the-code-behind-file"></a>Implementar el archivo de código subyacente
 El archivo de código subyacente, MainWindow. Xaml. vb o MainWindow.Xaml.CS, contiene el código de procedimiento que implementa la funcionalidad del [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] descrito en la sección anterior. Las tareas principales son:

- Adjuntar un controlador de `MyControl1`eventos `OnButtonClick` al evento de.

- Modificar diversas propiedades de `MyControl1`, en función de cómo se establezca la colección de botones de opción.

- Mostrar los datos recopilados por el control.

#### <a name="initializing-the-application"></a>Inicializar la aplicación
 El código de inicialización está contenido en un controlador de eventos para <xref:System.Windows.FrameworkElement.Loaded> el evento de la ventana y asocia un controlador de eventos `OnButtonClick` al evento del control.

 En MainWindow. Xaml. vb o MainWindow.Xaml.CS, agregue el código siguiente a la `MainWindow` clase.

 [!code-csharp[WpfHostingWindowsFormsControl#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#11)]
 [!code-vb[WpfHostingWindowsFormsControl#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#11)]

 <xref:System.Windows.Forms.Integration.WindowsFormsHost> <xref:System.Windows.Forms.Integration.WindowsFormsHost> <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> `MyControl1`Dado que se ha `MyControl1` [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] descrito anteriormente en la colección de elementos secundarios del elemento, puede convertir el del elemento para obtener la referencia a. Después, puede usar esa referencia para adjuntar un controlador `OnButtonClick`de eventos a.

 Además de proporcionar una referencia al propio control, <xref:System.Windows.Forms.Integration.WindowsFormsHost> expone una serie de propiedades del control, que se pueden manipular desde la aplicación. El código de inicialización asigna estos valores a variables globales privadas para su uso posterior en la aplicación.

 Para que pueda tener acceso fácilmente a los tipos en `MyControls` el archivo dll, agregue `Imports` la `using` siguiente instrucción o en la parte superior del archivo.

```vb
Imports MyControls
```

```csharp
using MyControls;
```

#### <a name="handling-the-onbuttonclick-event"></a>Controlar el evento OnButtonClick
 `MyControl1`provoca el `OnButtonClick` evento cuando el usuario hace clic en cualquiera de los botones del control.

 Agregue el código siguiente a la clase `MainWindow` .

 [!code-csharp[WpfHostingWindowsFormsControl#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#12)]
 [!code-vb[WpfHostingWindowsFormsControl#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#12)]

 Los datos de los cuadros de texto se empaquetan `MyControlEventArgs` en el objeto. Si el usuario hace clic en el botón **Aceptar** , el controlador de eventos extrae los datos y los muestra en `MyControl1`el panel siguiente.

#### <a name="modifying-the-controls-properties"></a>Modificar las propiedades del control
 El <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento expone algunas de las propiedades predeterminadas del control hospedado. Como resultado, puede cambiar el aspecto del control para que se adapte mejor al estilo de la aplicación. Los conjuntos de botones de opción del panel izquierdo permiten al usuario modificar varias propiedades de color y fuente. Cada conjunto de botones tiene un controlador para el <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento, que detecta las selecciones del botón de opción del usuario y cambia la propiedad correspondiente en el control.

 Agregue el código siguiente a la clase `MainWindow` .

 [!code-csharp[WpfHostingWindowsFormsControl#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#13)]
 [!code-vb[WpfHostingWindowsFormsControl#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#13)]  
  
 Compile y ejecute la aplicación. Agregue texto en el Windows Forms control compuesto y, a continuación, haga clic en **Aceptar**. El texto aparece en las etiquetas. Haga clic en los diferentes botones de radio para ver el efecto en el control.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Diseño de XAML en Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Tutorial: Hospedar un control de Windows Forms en WPF](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [Tutorial: Hospedar un control compuesto de WPF en Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
