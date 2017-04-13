---
title: "Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF | Microsoft Docs"
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
  - "controles compuestos, hospedar en WPF"
  - "hospedar control de formularios Windows Forms en WPF"
ms.assetid: 96fcd78d-1c77-4206-8928-3a0579476ef4
caps.latest.revision: 33
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 30
---
# Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona un entorno enriquecido para la creación de aplicaciones.  Sin embargo, cuando se tiene una inversión sustancial en código de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], puede resultar más efectivo reutilizar al menos parte de ese código en la aplicación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en lugar de volver a escribirlo todo desde el principio.  El escenario más común es el caso en que ya existen controles de [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)].  En algunos casos, puede que ni siquiera tenga acceso al código fuente de estos controles.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona un procedimiento sencillo para hospedar estos controles en una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Por ejemplo, puede utilizar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para realizar la mayoría de la programación al hospedar los controles <xref:System.Windows.Forms.DataGridView> especializados.  
  
 Este tutorial describe una aplicación que hospeda un control compuesto de [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] para realizar la entrada de datos en una aplicación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  El control compuesto se empaqueta en una DLL.  Este procedimiento general se puede hacer extensivo a aplicaciones y controles más complejos.  Este tutorial se ha diseñado para que sea casi idéntico en aspecto y funcionalidad a [Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md).  La diferencia principal es que se invierte el escenario de hospedaje.  
  
 El tutorial está dividido en dos secciones.  La primera sección describe brevemente la implementación del control compuesto de [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)].  La segunda sección explica en detalle cómo hospedar el control compuesto en una aplicación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], recibir eventos del control y obtener acceso a algunas de las propiedades del control.  
  
 Las tareas ilustradas en este tutorial incluyen:  
  
-   Implementar el control compuesto de Windows Forms.  
  
-   Implementar la aplicación host de WPF.  
  
 Para ver una lista de código completa de las tareas mostradas en este tutorial, vea [Hosting a Windows Forms Composite Control in WPF Sample](http://go.microsoft.com/fwlink/?LinkID=159999).  
  
## Requisitos previos  
 Necesita los componentes siguientes para completar este tutorial:  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## Implementar el control compuesto de Windows Forms  
 El control compuesto de [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] utilizado en este ejemplo es un formulario de entrada de datos simple.  Este formulario toma el nombre del usuario y su dirección y, a continuación, utiliza un evento personalizado para devolver esa información al host.  En la siguiente ilustración se muestra el control representado.  
  
 ![Control simple de formularios Windows Forms](../../../../docs/framework/wpf/advanced/media/wfcontrol.png "WFControl")  
Control compuesto de Windows Forms  
  
### Crear el proyecto  
 Para iniciar el proyecto:  
  
1.  Inicie [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] y abra el cuadro de diálogo **Nuevo proyecto**.  
  
2.  En la categoría de ventana, seleccione la plantilla **Biblioteca de controles de Windows Forms**.  
  
3.  Denomine el nuevo proyecto `MyControls`.  
  
4.  Para la ubicación, especifique una carpeta de nivel superior con un nombre adecuado, por ejemplo `WpfHostingWindowsFormsControl`.  Más adelante, colocará la aplicación host en esta carpeta.  
  
5.  Haga clic en **Aceptar** para crear el proyecto.  El proyecto predeterminado contiene un solo control cuyo nombre es `UserControl1`.  
  
6.  En el Explorador de soluciones, cambie el nombre `UserControl1` por `MyControl1`.  
  
 El proyecto debe tener referencias a las siguientes DLL del sistema.  Si cualquiera de estas DLL no está incluida de forma predeterminada, agréguela al proyecto.  
  
-   Sistema  
  
-   System.Data  
  
-   System.Drawing  
  
-   System.Windows.Forms  
  
-   System.Xml  
  
### Agregar controles al formulario  
 Para agregar controles al formulario:  
  
-   Abra `MyControl1` en el diseñador.  
  
 Agregue cinco controles <xref:System.Windows.Forms.Label> y sus controles <xref:System.Windows.Forms.TextBox> correspondientes, con los tamaños y la organización indicados en la ilustración anterior, en el formulario.  En el ejemplo, los controles <xref:System.Windows.Forms.TextBox> tienen los nombres siguientes:  
  
-   `txtName`  
  
-   `txtAddress`  
  
-   `txtCity`  
  
-   `txtState`  
  
-   `txtZip`  
  
 Agregue dos controles <xref:System.Windows.Forms.Button> con las etiquetas **Aceptar** y **Cancelar**.  En el ejemplo, los nombres de botón son `btnOK` y `btnCancel`, respectivamente.  
  
### Implementar el código de compatibilidad  
 Abra el formulario en la vista de código.  El control devuelve los datos recolectados al host provocando el evento `OnButtonClick` personalizado.  Los datos están contenidos en el objeto de argumento de evento.  En el siguiente código se muestra la declaración del evento y el delegado.  
  
 Agregue el código siguiente a la clase `MyControl1`.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#2)]
 [!code-vb[WpfHostingWindowsFormsControl#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#2)]  
  
 La clase `MyControlEventArgs` contiene la información que se devolverá al host.  
  
 Agregue la clase siguiente al formulario.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#3)]
 [!code-vb[WpfHostingWindowsFormsControl#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#3)]  
  
 Cuando el usuario hace clic en el botón **Aceptar** o **Cancelar**, los controladores del evento <xref:System.Windows.Forms.Control.Click> crean un objeto `MyControlEventArgs` que contiene los datos y provoca el evento `OnButtonClick`.  La única diferencia entre los dos controladores es la propiedad `IsOK` del argumento de evento.  Esta propiedad permite al host determinar en qué botón se hizo clic.  Se establece en `true` para el botón **Aceptar** y en `false` para el botón **Cancelar**.  En el siguiente código se muestran los controladores de los dos botones.  
  
 Agregue el código siguiente a la clase `MyControl1`.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#4)]
 [!code-vb[WpfHostingWindowsFormsControl#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#4)]  
  
### Dar un nombre seguro al ensamblado y compilar el ensamblado  
 Para que una aplicación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pueda hacer referencia a este ensamblado, debe tener un nombre seguro.  Para crear un nombre seguro, cree un archivo de clave con Sn.exe y agréguelo al proyecto.  
  
1.  Abra un símbolo del sistema de [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)].  Para ello, haga clic en el menú **Inicio** y seleccione **Todos los programas\/Microsoft Visual Studio 2010\/Visual Studio Tools\/Símbolo del sistema de Visual Studio**.  Se iniciará una ventana de consola con variables de entorno personalizadas.  
  
2.  En el símbolo del sistema, utilice el comando `cd` para ir a la carpeta del proyecto.  
  
3.  Genere un archivo de clave con el nombre MyControls.snk ejecutando el comando siguiente.  
  
    ```  
    Sn.exe -k MyControls.snk  
    ```  
  
4.  Para incluir el archivo de clave en el proyecto, haga clic con el botón secundario en el nombre del proyecto en el Explorador de soluciones y, a continuación, haga clic en **Propiedades**.  En el Diseñador de proyectos, haga clic en la pestaña **Firma**, active la casilla **Firmar el ensamblado** y, a continuación, busque el archivo de clave.  
  
5.  Compile la solución.  La compilación generará una DLL denominada MyControls.dll.  
  
## Implementar la aplicación host de WPF  
 La aplicación host de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utiliza el control <xref:System.Windows.Forms.Integration.WindowsFormsHost> para hospedar `MyControl1`.  La aplicación controla el evento `OnButtonClick` para recibir los datos del control.  También tiene una colección de botones de opción que permiten cambiar algunas de las propiedades del control desde la aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  En la ilustración siguiente se muestra la aplicación acabada.  
  
 ![Control incrustado en una página de WPF](../../../../docs/framework/wpf/advanced/media/avalonhost.png "AvalonHost")  
La aplicación completa, que muestra el control incrustado en la aplicación WPF  
  
### Crear el proyecto  
 Para iniciar el proyecto:  
  
1.  Abra [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] y seleccione **Nuevo proyecto**.  
  
2.  En la categoría de ventana, seleccione la plantilla  **Aplicación WPF**.  
  
3.  Denomine el nuevo proyecto `WpfHost`.  
  
4.  Para la ubicación, especifique la misma carpeta de nivel superior que contiene el proyecto MyControls.  
  
5.  Haga clic en **Aceptar** para crear el proyecto.  
  
 También debe agregar referencias a la DLL que contiene `MyControl1` y a otros ensamblados.  
  
1.  En el Explorador de soluciones, haga clic con el botón secundario del mouse en el nombre del proyecto y seleccione **Agregar referencia**.  
  
2.  Haga clic en la pestaña **Examinar** y busque la carpeta que contiene MyControls.dll.  Para este tutorial, esta carpeta es MyControls\\bin\\Debug.  
  
3.  Seleccione MyControls.dll y, a continuación, haga clic en **Aceptar**.  
  
4.  Agregue una referencia al ensamblado WindowsFormsIntegration, que se denomina WindowsFormsIntegration.dll.  
  
### Implementar el diseño básico  
 La [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] de la aplicación host se implementa en MainWindow.xaml.  Este archivo contiene el marcado de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] que define el diseño y hospeda el control de [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)].  La aplicación está dividida en tres áreas:  
  
-   El panel **Control Properties** \(Propiedades del control\), que contiene una colección de botones de opción que puede utilizar para modificar varias propiedades del control hospedado.  
  
-   El panel **Data from Control** \(Datos del control\) que contiene varios elementos <xref:System.Windows.Controls.TextBlock> que muestran los datos devueltos del control hospedado.  
  
-   El propio control hospedado.  
  
 El diseño básico se muestra en el código XAML siguiente.  El marcado que se necesita para hospedar `MyControl1` se omite en este ejemplo, pero se explicará más adelante.  
  
 Reemplace el XAML de MainWindow.xaml con lo siguiente.  Si utiliza Visual Basic, cambie el nombre de la clase a `x:Class="MainWindow"`.  
  
 [!code-xml[WpfHostingWindowsFormsControl#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#100)]  
  
 El primer elemento <xref:System.Windows.Controls.StackPanel> contiene varios conjuntos de controles <xref:System.Windows.Controls.RadioButton> que permiten modificar diversas propiedades predeterminadas del control hospedado.  A continuación, hay un elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> en el que se hospeda `MyControl1`.  El último elemento <xref:System.Windows.Controls.StackPanel> contiene varios elementos <xref:System.Windows.Controls.TextBlock> que muestran los datos devueltos por el control hospedado.  El orden de los elementos y los valores de atributo de <xref:System.Windows.Controls.DockPanel.Dock%2A> y <xref:System.Windows.FrameworkElement.Height%2A> incrustan el control hospedado en la ventana sin dejar separaciones ni provocar distorsión.  
  
#### Hospedar el control  
 La versión editada siguiente del XAML anterior se centra en los elementos que se necesitan para hospedar `MyControl1`.  
  
 [!code-xml[WpfHostingWindowsFormsControl#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#101)]  
[!code-xml[WpfHostingWindowsFormsControl#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#102)]  
  
 Los atributos de asignación del espacio de nombres `xmlns` crean una referencia al espacio de nombres `MyControls` que contiene el control hospedado.  Esta asignación permite representar `MyControl1` en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] como `<mcl:MyControl1>`.  
  
 Dos elementos del XAML controlan el hospedaje:  
  
-   `WindowsFormsHost` representa el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> que permite hospedar un control de [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] en una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   `mcl:MyControl1`, que representa a `MyControl1`, se agrega a la colección de elementos secundarios del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  Por consiguiente, este control de [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] se presenta como parte de la ventana de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y es posible comunicarse con el control desde la aplicación.  
  
### Implementar el archivo de código subyacente  
 El archivo de código subyacente, MainWindow.xaml.vb o MainWindow.xaml.cs, contiene el código de procedimiento que implementa la funcionalidad de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] descrito en la sección anterior.  Las principales tareas son:  
  
-   Asociar un controlador al evento `OnButtonClick` de `MyControl1`.  
  
-   Modificar diversas propiedades de `MyControl1`, basándose en cómo se establezca la colección de botones de opción.  
  
-   Mostrar los datos recolectados por el control.  
  
#### Inicializar la aplicación  
 El código de inicialización está contenido en un controlador para el evento <xref:System.Windows.FrameworkElement.Loaded> de la ventana y adjunta un controlador al evento `OnButtonClick` del control.  
  
 En MainWindow.xaml.vb o MainWindow.xaml.cs, agregue el código siguiente a la clase `MainWindow`.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#11)]
 [!code-vb[WpfHostingWindowsFormsControl#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#11)]  
  
 Dado que en el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] descrito anteriormente se ha agregado `MyControl1` a la colección de elementos secundarios del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>, puede convertir la propiedad <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> para obtener la referencia a `MyControl1`.  A continuación, puede utilizar esa referencia para asociar un controlador de eventos a `OnButtonClick`.  
  
 Además de proporcionar una referencia al propio control, <xref:System.Windows.Forms.Integration.WindowsFormsHost> expone varias propiedades del control, que puede manipular desde la aplicación.  En el código de inicialización se asignan esos valores a las variables globales privadas para su uso posterior en la aplicación.  
  
 Para poder tener un fácil acceso a los tipos de la DLL `MyControls`, agregue la siguiente instrucción `Imports` o `using` a la parte superior del archivo.  
  
```vb  
Imports MyControls  
```  
  
```csharp  
using MyControls;  
```  
  
#### Controlar el evento OnButtonClick  
 `MyControl1` provoca el evento `OnButtonClick` cuando el usuario hace clic en cualquiera de los botones del control.  
  
 Agregue el código siguiente a la clase `MainWindow`.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#12)]
 [!code-vb[WpfHostingWindowsFormsControl#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#12)]  
  
 Los datos de los cuadros de texto se empaquetan en el objeto `MyControlEventArgs`.  Si el usuario hace clic en el botón **Aceptar** botón, el controlador de eventos extrae los datos y los muestra en el panel situado debajo de `MyControl1`.  
  
#### Modificar las propiedades del control  
 El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> expone algunas de las propiedades predeterminadas de control hospedado.  Por consiguiente, puede cambiar el aspecto del control para adaptarlo mejor al estilo de la aplicación.  Los conjuntos de botones de opción del panel izquierdo permiten al usuario modificar varias propiedades de color y fuente.  Cada conjunto de botones tiene un controlador para el evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click>, que detecta qué botón selecciona el usuario y cambia la propiedad correspondiente del control.  
  
 Agregue el código siguiente a la clase `MainWindow`.  
  
 [!code-csharp[WpfHostingWindowsFormsControl#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#13)]
 [!code-vb[WpfHostingWindowsFormsControl#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#13)]  
  
 Compile y ejecute la aplicación.  Agregue texto en el control compuesto de Windows Forms y, a continuación, haga clic en **Aceptar**.  El texto aparece en las etiquetas.  Haga clic en los distintos botones de radio para ver el efecto en el control.  
  
## Vea también  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [WPF Designer](http://msdn.microsoft.com/es-es/c6c65214-8411-4e16-b254-163ed4099c26)   
 [Tutorial: Hospedar un control de Windows Forms en WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)   
 [Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)