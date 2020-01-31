---
title: Hospedar un control compuesto de Windows Forms en WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
- composite controls [WPF], hosting in WPF
ms.assetid: 96fcd78d-1c77-4206-8928-3a0579476ef4
ms.openlocfilehash: 22eb323d1c1921832630d1d1b30463b4ecb7d1fd
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794231"
---
# <a name="walkthrough-hosting-a-windows-forms-composite-control-in-wpf"></a>Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona un entorno rico para crear aplicaciones. Sin embargo, si tiene una inversión sustancial en Windows Forms código, puede ser más eficaz reutilizar al menos parte de ese código en su aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en lugar de volver a escribirlo desde el principio. El escenario más común es cuando tiene controles de Windows Forms existentes. En algunos casos, incluso podría no tener acceso al código fuente de estos controles. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona un procedimiento sencillo para hospedar estos controles en una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Por ejemplo, puede usar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para la mayor parte de la programación mientras hospeda los controles de <xref:System.Windows.Forms.DataGridView> especializados.  
  
 Este tutorial le guía a través de una aplicación que hospeda un Windows Forms control compuesto para realizar la entrada de datos en una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. El control compuesto se empaqueta en un archivo DLL. Este procedimiento general se puede extender a aplicaciones y controles más complejos. Este tutorial está diseñado para ser casi idéntico en aspecto y funcionalidad al [Tutorial: hospedar un control compuesto de WPF en Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md). La principal diferencia es que se invierte el escenario de hospedaje.  
  
 Este tutorial está dividido en dos secciones. En la primera sección se describe brevemente la implementación de Windows Forms control compuesto. En la segunda sección se explica en detalle cómo hospedar el control compuesto en una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], recibir eventos del control y tener acceso a algunas de las propiedades del control.  
  
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
  
1. Inicie Visual Studio y abra el cuadro de diálogo **nuevo proyecto** .  
  
2. En la categoría de ventana, seleccione la plantilla **biblioteca de controles de Windows Forms** .  
  
3. Asigne al nuevo proyecto el nombre de `MyControls`.  
  
4. Para la ubicación, especifique una carpeta de nivel superior con un nombre adecuado, como `WpfHostingWindowsFormsControl`. Más tarde, colocará la aplicación host en esta carpeta.  
  
5. Haga clic en **Aceptar** para crear el proyecto. El proyecto predeterminado contiene un solo control denominado `UserControl1`.  
  
6. En Explorador de soluciones, cambie el nombre de `UserControl1` a `MyControl1`.  
  
 El proyecto debe tener referencias a los siguientes archivos DLL del sistema. Si alguno de estos archivos DLL no está incluido de forma predeterminada, agréguelo al proyecto.  
  
- System  
  
- System.Data  
  
- System.Drawing  
  
- System.Windows.Forms  
  
- System.Xml  
  
### <a name="adding-controls-to-the-form"></a>Agregar controles al formulario  
 Para agregar controles al formulario:  
  
- Abra `MyControl1` en el diseñador.  
  
 En el formulario, agregue cinco controles <xref:System.Windows.Forms.Label> y sus controles de <xref:System.Windows.Forms.TextBox> correspondientes, con el tamaño y el orden en que se encuentran en la ilustración anterior. En el ejemplo, los controles de <xref:System.Windows.Forms.TextBox> se denominan:  
  
- `txtName`  
  
- `txtAddress`  
  
- `txtCity`  
  
- `txtState`  
  
- `txtZip`  
  
 Agregue dos <xref:System.Windows.Forms.Button> controles con la etiqueta **Aceptar** y **Cancelar**. En el ejemplo, los nombres de los botones son `btnOK` y `btnCancel`, respectivamente.  
  
### <a name="implementing-the-supporting-code"></a>Implementar el código auxiliar  
 Abra el formulario en la vista Código. El control devuelve los datos recopilados a su host mediante la generación del evento de `OnButtonClick` personalizado. Los datos están contenidos en el objeto de argumento de evento. En el código siguiente se muestra la declaración de evento y delegado.  
  
 Agregue el código siguiente a la clase `MyControl1` .  
  
 [!code-csharp[WpfHostingWindowsFormsControl#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#2)]
 [!code-vb[WpfHostingWindowsFormsControl#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#2)]

 La clase `MyControlEventArgs` contiene la información que se va a devolver al host.

 Agregue la clase siguiente al formulario.

 [!code-csharp[WpfHostingWindowsFormsControl#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#3)]
 [!code-vb[WpfHostingWindowsFormsControl#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#3)]

 Cuando el usuario hace clic en el botón **Aceptar** o **Cancelar** , los controladores de eventos <xref:System.Windows.Forms.Control.Click> crean un objeto `MyControlEventArgs` que contiene los datos y genera el evento `OnButtonClick`. La única diferencia entre los dos controladores es la propiedad `IsOK` del argumento de evento. Esta propiedad permite que el host determine en qué botón se ha hecho clic. Se establece en `true` para el botón **Aceptar** y `false` para el botón **Cancelar** . En el código siguiente se muestran los dos controladores de botón.

 Agregue el código siguiente a la clase `MyControl1` .

 [!code-csharp[WpfHostingWindowsFormsControl#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#4)]
 [!code-vb[WpfHostingWindowsFormsControl#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#4)]

### <a name="giving-the-assembly-a-strong-name-and-building-the-assembly"></a>Dar un nombre seguro al ensamblado y compilar el ensamblado
 Para que una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] haga referencia a este ensamblado, debe tener un nombre seguro. Para crear un nombre seguro, cree un archivo de clave con SN. exe y agréguelo al proyecto.

1. Abra un símbolo del sistema de Visual Studio 2010. Para ello, haga clic en el menú **Inicio** y, a continuación, seleccione **todos los programas/Microsoft Visual Studio 2010/Visual Studio Tools/símbolo del sistema de Visual Studio**. Esto inicia una ventana de consola con variables de entorno personalizadas.

2. En el símbolo del sistema, use el comando `cd` para ir a la carpeta del proyecto.

3. Ejecute el comando siguiente para generar un archivo de clave denominado MyControls.snk.

    ```console
    Sn.exe -k MyControls.snk
    ```

4. Para incluir el archivo de clave en el proyecto, haga clic con el botón secundario en el nombre del proyecto en Explorador de soluciones y, a continuación, haga clic en **propiedades**. En el diseñador de proyectos, haga clic en la pestaña **firma** , active la casilla **firmar el ensamblado** y, a continuación, busque el archivo de clave.

5. Compile la solución. La compilación generará un archivo DLL denominado MyControls.dll.

## <a name="implementing-the-wpf-host-application"></a>Implementar la aplicación host de WPF
 La aplicación host de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utiliza el control <xref:System.Windows.Forms.Integration.WindowsFormsHost> para hospedar `MyControl1`. La aplicación controla el evento `OnButtonClick` para recibir los datos del control. También tiene una colección de botones de opción que le permiten cambiar algunas de las propiedades del control de la aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. En la ilustración siguiente se muestra la aplicación finalizada.

En la imagen siguiente se muestra la aplicación completa, incluido el control insertado en la aplicación WPF:

 ![Captura de pantalla que muestra un control incrustado en una página de WPF.](./media/walkthrough-hosting-a-windows-forms-composite-control-in-wpf/windows-presentation-foundation-page-control.gif)

### <a name="creating-the-project"></a>Crear el proyecto
 Para iniciar el proyecto:

1. Abra Visual Studio y seleccione **nuevo proyecto**.

2. En la categoría de ventana, seleccione la plantilla **aplicación WPF** .

3. Asigne al nuevo proyecto el nombre de `WpfHost`.

4. Para la ubicación, especifique la misma carpeta de nivel superior que contiene el proyecto MyControls.

5. Haga clic en **Aceptar** para crear el proyecto.

 También debe agregar referencias al archivo DLL que contiene `MyControl1` y otros ensamblados.

1. Haga clic con el botón derecho en el nombre del proyecto en Explorador de soluciones y seleccione **Agregar referencia**.

2. Haga clic en la pestaña **examinar** y busque la carpeta que contiene DataControl. dll. En este tutorial, esta carpeta es MyControls\bin\Debug.

3. Seleccione Datacontrols. dll y, a continuación, haga clic en **Aceptar**.

4. Agregue una referencia al ensamblado WindowsFormsIntegration, denominado WindowsFormsIntegration. dll.

### <a name="implementing-the-basic-layout"></a>Implementar el diseño básico
 La [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] de la aplicación host se implementa en MainWindow. Xaml. Este archivo contiene [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] marcado que define el diseño y hospeda el control Windows Forms. La aplicación se divide en tres regiones:

- El panel **propiedades del control** , que contiene una colección de botones de opción que puede usar para modificar diversas propiedades del control hospedado.

- Los **datos del panel de control** , que contiene varios elementos <xref:System.Windows.Controls.TextBlock> que muestran los datos devueltos por el control hospedado.

- El control hospedado.

 En el siguiente código XAML se muestra el diseño básico. El marcado que se necesita para hospedar `MyControl1` se omite en este ejemplo, pero se tratará más adelante.

 Reemplace el código XAML del archivo MainWindow.xaml.vb por el código siguiente. Si está utilizando Visual Basic, cambie la clase a `x:Class="MainWindow"`.

 [!code-xaml[WpfHostingWindowsFormsControl#100](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#100)]

 El primer elemento <xref:System.Windows.Controls.StackPanel> contiene varios conjuntos de controles <xref:System.Windows.Controls.RadioButton> que permiten modificar diversas propiedades predeterminadas del control hospedado. Seguido de un elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>, que hospeda `MyControl1`. El último elemento <xref:System.Windows.Controls.StackPanel> contiene varios elementos <xref:System.Windows.Controls.TextBlock> que muestran los datos devueltos por el control hospedado. El orden de los elementos y los valores de los atributos <xref:System.Windows.Controls.DockPanel.Dock%2A> y <xref:System.Windows.FrameworkElement.Height%2A> insertan el control hospedado en la ventana sin espacios ni distorsión.

#### <a name="hosting-the-control"></a>Hospedar el control
 La siguiente versión editada del código XAML anterior se centra en los elementos necesarios para hospedar `MyControl1`.

 [!code-xaml[WpfHostingWindowsFormsControl#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#101)]
[!code-xaml[WpfHostingWindowsFormsControl#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#102)]

 El atributo de asignación de espacio de nombres `xmlns` crea una referencia al espacio de nombres `MyControls` que contiene el control hospedado. Esta asignación permite representar `MyControl1` en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] como `<mcl:MyControl1>`.

 Dos elementos del código XAML controlan el hospedaje:

- `WindowsFormsHost` representa el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> que permite hospedar un control Windows Forms en una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

- `mcl:MyControl1`, que representa `MyControl1`, se agrega a la colección secundaria del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>. Como resultado, este control de Windows Forms se representa como parte de la ventana de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y puede comunicarse con el control desde la aplicación.

### <a name="implementing-the-code-behind-file"></a>Implementar el archivo de código subyacente
 El archivo de código subyacente, MainWindow. Xaml. vb o MainWindow.xaml.cs, contiene el código de procedimiento que implementa la funcionalidad de los [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] descritos en la sección anterior. Las tareas principales son:

- Adjuntar un controlador de eventos al evento `OnButtonClick` de `MyControl1`.

- Modificar varias propiedades de `MyControl1`, en función de cómo se establece la colección de botones de opción.

- Mostrar los datos recopilados por el control.

#### <a name="initializing-the-application"></a>Inicializar la aplicación
 El código de inicialización está contenido en un controlador de eventos para el evento de <xref:System.Windows.FrameworkElement.Loaded> de la ventana y asocia un controlador de eventos al evento de `OnButtonClick` del control.

 En MainWindow. Xaml. vb o MainWindow.xaml.cs, agregue el código siguiente a la clase `MainWindow`.

 [!code-csharp[WpfHostingWindowsFormsControl#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#11)]
 [!code-vb[WpfHostingWindowsFormsControl#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#11)]

 Dado que el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] explicó anteriormente ha agregado `MyControl1` a la colección de elementos secundarios del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>, puede convertir el <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> del elemento de <xref:System.Windows.Forms.Integration.WindowsFormsHost> para obtener la referencia a `MyControl1`. Después, puede usar esa referencia para adjuntar un controlador de eventos a `OnButtonClick`.

 Además de proporcionar una referencia al propio control, <xref:System.Windows.Forms.Integration.WindowsFormsHost> expone una serie de las propiedades del control, que se pueden manipular desde la aplicación. El código de inicialización asigna estos valores a variables globales privadas para su uso posterior en la aplicación.

 Para que pueda tener acceso fácilmente a los tipos de la DLL `MyControls`, agregue la siguiente `Imports` o `using` instrucción en la parte superior del archivo.

```vb
Imports MyControls
```

```csharp
using MyControls;
```

#### <a name="handling-the-onbuttonclick-event"></a>Controlar el evento OnButtonClick
 `MyControl1` provoca el evento `OnButtonClick` cuando el usuario hace clic en cualquiera de los botones del control.

 Agregue el código siguiente a la clase `MainWindow` .

 [!code-csharp[WpfHostingWindowsFormsControl#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#12)]
 [!code-vb[WpfHostingWindowsFormsControl#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#12)]

 Los datos de los cuadros de texto se empaquetan en el objeto `MyControlEventArgs`. Si el usuario hace clic en el botón **Aceptar** , el controlador de eventos extrae los datos y los muestra en el panel siguiente `MyControl1`.

#### <a name="modifying-the-controls-properties"></a>Modificar las propiedades del control
 El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> expone algunas de las propiedades predeterminadas del control hospedado. Como resultado, puede cambiar el aspecto del control para que se adapte mejor al estilo de la aplicación. Los conjuntos de botones de opción del panel izquierdo permiten al usuario modificar varias propiedades de color y fuente. Cada conjunto de botones tiene un controlador para el evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click>, que detecta las selecciones del botón de opción del usuario y cambia la propiedad correspondiente en el control.

 Agregue el código siguiente a la clase `MainWindow` .

 [!code-csharp[WpfHostingWindowsFormsControl#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#13)]
 [!code-vb[WpfHostingWindowsFormsControl#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#13)]  
  
 Compile y ejecute la aplicación. Agregue texto en el Windows Forms control compuesto y, a continuación, haga clic en **Aceptar**. El texto aparece en las etiquetas. Haga clic en los diferentes botones de radio para ver el efecto en el control.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Diseño de XAML en Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Tutorial: Hospedar un control de Windows Forms en WPF](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
