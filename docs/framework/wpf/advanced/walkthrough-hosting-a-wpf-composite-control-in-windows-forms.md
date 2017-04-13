---
title: "Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms | Microsoft Docs"
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
  - "hospedar contenido de WPF en formularios Windows Forms"
ms.assetid: 0ac41286-4c1b-4b17-9196-d985cb844ce1
caps.latest.revision: 34
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 31
---
# Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona un entorno enriquecido para la creación de aplicaciones.  Sin embargo, cuando se tiene una inversión sustancial en código [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], puede ser más efectivo extender la aplicación [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] existente con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en lugar de rescribirla desde el principio.  Un escenario común se da cuando se desea incrustar uno o varios controles implementados con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dentro de una aplicación de [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)].  Para obtener más información sobre cómo personalizar los controles de WPF, vea [Personalización de controles](../../../../docs/framework/wpf/controls/control-customization.md).  
  
 Este tutorial describe una aplicación que hospeda un control compuesto de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para realizar la entrada de datos en una aplicación de [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)].  El control compuesto se empaqueta en una DLL.  Este procedimiento general se puede hacer extensivo a aplicaciones y controles más complejos.  Este tutorial se ha diseñado para que sea casi idéntico en aspecto y funcionalidad a [Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md).  La diferencia principal es que se invierte el escenario de hospedaje.  
  
 El tutorial está dividido en dos secciones.  La primera sección describe brevemente la implementación del control compuesto de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  La segunda sección explica en detalle cómo hospedar el control compuesto en una aplicación de [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)], recibir eventos del control y obtener acceso a algunas de las propiedades del control.  
  
 Las tareas ilustradas en este tutorial incluyen:  
  
-   Implementar el control compuesto de WPF.  
  
-   Implementar la aplicación host de formularios de Windows Forms.  
  
 Para ver una lista de código completa de las tareas mostradas en este tutorial, vea [Hosting a WPF Composite Control in Windows Forms Sample](http://go.microsoft.com/fwlink/?LinkID=159996).  
  
## Requisitos previos  
 Necesita los componentes siguientes para completar este tutorial:  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## Implementar el control compuesto de WPF  
 El control compuesto de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utilizado en este ejemplo es un formulario de entrada de datos simple que toma el nombre y la dirección del usuario.  Cuando el usuario hace clic en uno de los dos botones para indicar que la tarea ha finalizado, el control compuesto genera un evento personalizado para devolver esa información al host.  En la siguiente ilustración se muestra el control representado.  
  
 ![Control simple de WPF](../../../../docs/framework/wpf/advanced/media/avaloncontrol.png "AvalonControl")  
Control compuesto de WPF  
  
### Crear el proyecto  
 Para iniciar el proyecto:  
  
1.  Inicie [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] y abra el cuadro de diálogo **Nuevo proyecto**.  
  
2.  En Visual C\# y la categoría de Windows, seleccione la plantilla **Biblioteca de controles de usuario de WPF**.  
  
3.  Denomine el nuevo proyecto `MyControls`.  
  
4.  Para la ubicación, especifique una carpeta de nivel superior con un nombre adecuado, por ejemplo `WindowsFormsHostingWpfControl`.  Más adelante, colocará la aplicación host en esta carpeta.  
  
5.  Haga clic en **Aceptar** para crear el proyecto.  El proyecto predeterminado contiene un solo control cuyo nombre es `UserControl1`.  
  
6.  En el Explorador de soluciones, cambie el nombre `UserControl1` por `MyControl1`.  
  
 El proyecto debe tener referencias a las siguientes DLL del sistema.  Si cualquiera de estas DLL no se incluye de forma predeterminada, agréguela al proyecto.  
  
-   PresentationCore  
  
-   PresentationFramework  
  
-   Sistema  
  
-   WindowsBase  
  
### Crear la interfaz de usuario  
 El elemento [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] del control compuesto se implementa mediante [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  El control compuesto [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] consta de cinco elementos <xref:System.Windows.Controls.TextBox>.  Cada elemento <xref:System.Windows.Controls.TextBox> tiene un elemento <xref:System.Windows.Controls.TextBlock> asociado que actúa como una etiqueta.  Hay dos elementos <xref:System.Windows.Controls.Button> en la parte inferior, **Aceptar** y **Cancelar**.  Cuando el usuario hace clic en cualquiera de los botones, el control genera un evento personalizado para devolver la información al host.  
  
#### Diseño básico  
 Los diversos elementos [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] se contienen en un elemento <xref:System.Windows.Controls.Grid>.  Puede utilizar <xref:System.Windows.Controls.Grid> para organizar el contenido del control compuesto de manera muy similar a como utilizaría un elemento `Table` en HTML.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] también tiene un elemento <xref:System.Windows.Documents.Table>, pero <xref:System.Windows.Controls.Grid> es más ligero y más adecuado para las tareas sencillas de diseño.  
  
 El siguiente código XAML muestra el diseño básico.  Este código XAML define la estructura global del control especificando el número de columnas y filas del elemento <xref:System.Windows.Controls.Grid>.  
  
 En MyControl1.xaml, reemplace el XAML existente por el siguiente XAML.  
  
 [!code-xml[WindowsFormsHostingWpfControl#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#101)]  
[!code-xml[WindowsFormsHostingWpfControl#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#102)]  
  
#### Agregar elementos TextBlock y TextBox a la cuadrícula  
 Para colocar un elemento [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] en la cuadrícula, establezca los atributos  <xref:System.Windows.Controls.Grid.RowProperty> y <xref:System.Windows.Controls.Grid.ColumnProperty> en los números de fila y columna correspondientes.  Recuerde que la numeración de filas y columnas está basada en cero.  Puede hacer que un elemento abarque varias columnas estableciendo su atributo <xref:System.Windows.Controls.Grid.ColumnSpanProperty>.  Para obtener más información sobre los elementos <xref:System.Windows.Controls.Grid>, vea [Crear un elemento Grid](../../../../docs/framework/wpf/controls/how-to-create-a-grid-element.md).  
  
 El siguiente XAML muestra los elementos <xref:System.Windows.Controls.TextBox> y <xref:System.Windows.Controls.TextBlock> del control compuesto con sus atributos <xref:System.Windows.Controls.Grid.RowProperty> y <xref:System.Windows.Controls.Grid.ColumnProperty>, que se establecen para colocar correctamente los elementos en la cuadrícula.  
  
 En MyControl1.xaml, agregue el siguiente XAML dentro del elemento <xref:System.Windows.Controls.Grid>.  
  
 [!code-xml[WindowsFormsHostingWpfControl#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#103)]  
  
#### Aplicar estilos a los elementos de la interfaz de usuario  
 Muchos de los elementos del formulario de entrada de datos tienen un aspecto similar, lo que significa que tienen valores idénticos para varias de sus propiedades.  En lugar de establecer los atributos de cada elemento de forma independiente, el XAML anterior utiliza elementos <xref:System.Windows.Style> para definir los valores estándar de las propiedades para las clases de elementos.  Este enfoque reduce la complejidad del control y permite cambiar el aspecto de varios elementos a través de un atributo de estilo único.  
  
 Los elementos <xref:System.Windows.Style> se incluyen en la propiedad <xref:System.Windows.FrameworkElement.Resources%2A> del elemento <xref:System.Windows.Controls.Grid>, por lo que pueden ser utilizados por todos los elementos del control.  Si un estilo tiene nombre, puede aplicarlo a un elemento agregando un elemento <xref:System.Windows.Style> establecido en el nombre del estilo.  Los estilos que no tienen nombre se convierten en el estilo predeterminado del elemento.  Para obtener más información acerca de los estilos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vea [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
 En el código XAML siguiente se muestran los elementos <xref:System.Windows.Style> del control compuesto.  Para ver cómo se aplican los estilos a los elementos, vea el XAML anterior.  Por ejemplo, el último elemento <xref:System.Windows.Controls.TextBlock> tiene el estilo `inlineText` y el último elemento <xref:System.Windows.Controls.TextBox> utiliza el estilo predeterminado.  
  
 En MyControl1.xaml, agregue el siguiente XAML justo después del elemento de inicio <xref:System.Windows.Controls.Grid>.  
  
 [!code-xml[WindowsFormsHostingWpfControl#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#104)]  
  
#### Agregar los botones Aceptar y Cancelar  
 Los elementos finales del control compuesto son los elementos **Aceptar** y **Cancelar** <xref:System.Windows.Controls.Button>, que ocupan las primeras dos columnas de la última fila del elemento <xref:System.Windows.Controls.Grid>.  Estos elementos utilizan un controlador de eventos común, `ButtonClicked` y el estilo <xref:System.Windows.Controls.Button> predeterminado definido en el código XAML anterior.  
  
 En MyControl1.xaml, agregue el siguiente XAML justo después del último elemento <xref:System.Windows.Controls.TextBox>.  El componente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] del control compuesto está ahora completo.  
  
 [!code-xml[WindowsFormsHostingWpfControl#105](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#105)]  
  
### Implementar el archivo de código subyacente  
 El archivo de código subyacente, MyControl1.xaml.cs, implementa tres tareas esenciales:  
  
1.  Controla el evento que se produce cuando el usuario hace clic en uno de los botones.  
  
2.  Recupera los datos de los elementos <xref:System.Windows.Controls.TextBox> y lo empaqueta en un objeto de argumento de evento personalizado.  
  
3.  Provoca el evento `OnButtonClick` personalizado, que notifica al host que el usuario ha finalizado y devuelve los datos al host.  
  
 El control también expone diversas propiedades de color y fuente que permiten cambiar el aspecto.  A diferencia de la clase <xref:System.Windows.Forms.Integration.WindowsFormsHost>, que se utiliza para hospedar un control [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)], la clase <xref:System.Windows.Forms.Integration.ElementHost> solamente expone la propiedad <xref:System.Windows.Controls.Panel.Background%2A> del control.  Para mantener la similitud entre este ejemplo de código y el ejemplo explicado en [Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md), el control expone directamente las propiedades restantes.  
  
#### Estructura básica del archivo de código subyacente  
 El archivo de código subyacente consta de un único espacio de nombres, `MyControls`, que contendrá dos clases, `MyControl1` y `MyControlEventArgs`.  
  
```  
  
namespace MyControls  
{  
  public partial class MyControl1 : Grid  
  {  
    //...  
  }  
  public class MyControlEventArgs : EventArgs  
  {  
    //...  
  }  
}  
  
```  
  
 La primera clase, `MyControl1`, es una clase parcial que contiene el código que implementa la funcionalidad de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] definida en MyControl1.xaml.  Cuando se analiza MyControl1.xaml, el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] se convierte en la misma clase parcial y las dos clases parciales se combinan para formar el control compilado.  Por esta razón, el nombre de clase del archivo de código subyacente debe coincidir con el nombre de clase asignado a MyControl1.xaml y debe heredar del elemento raíz del control.  La segunda clase, `MyControlEventArgs`, es una clase de argumentos de evento que se utiliza para devolver los datos al host.  
  
 Abra MyControl1.xaml.cs.  Cambie la declaración de clase existente de forma que tenga el siguiente nombre y herede de <xref:System.Windows.Controls.Grid>.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#21)]  
  
#### Inicializar el control  
 El siguiente código implementa varias tareas básicas:  
  
-   Declara un evento privado, `OnButtonClick` y su delegado asociado, `MyControlEventHandler`.  
  
-   Crea varias variables globales privadas que almacenan los datos del usuario.  Estos datos se exponen a través de las propiedades correspondientes.  
  
-   Implementa un controlador, `Init`, para el evento <xref:System.Windows.FrameworkElement.Loaded> del control.  Este controlador inicializa las variables globales asignándoles los valores definidos en MyControl1.xaml.  Utiliza para ello la propiedad <xref:System.Windows.FrameworkElement.Name%2A> asignada a un elemento <xref:System.Windows.Controls.TextBlock> típico, `nameLabel`, para tener acceso a los valores de las propiedades de ese elemento.  
  
 Elimine el constructor existente y agregue el código siguiente a la clase `MyControl1`.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#11)]  
  
#### Administrar los eventos de clic de los botones  
 El usuario indica que la tarea de entrada de datos finaliza haciendo clic en el botón **Aceptar** o en el botón **Cancelar**.  Ambos botones utilizan el mismo controlador de eventos <xref:System.Windows.Controls.Primitives.ButtonBase.Click>, `ButtonClicked`.  Ambos botones tienen un nombre, `btnOK` o `btnCancel`, que permite al controlador determinar en qué botón se hizo clic examinando el valor del argumento `sender`.  El controlador hace lo siguiente:  
  
-   Crea un objeto `MyControlEventArgs` que contiene los datos de los elementos <xref:System.Windows.Controls.TextBox>.  
  
-   Si el usuario hizo clic en el botón **Cancelar**, establece la propiedad `IsOK` del objeto `MyControlEventArgs` en `false`.  
  
-   Provoca el evento `OnButtonClick` para indicar al host que el usuario ha terminado y devuelve los datos recopilados.  
  
 Agregue el código siguiente a la clase `MyControl1`, después del método `Init`.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#12)]  
  
#### Crear propiedades  
 El resto de la clase simplemente expone propiedades que corresponden a las variables globales explicadas anteriormente.  Cuando una propiedad cambia, el descriptor de acceso set modifica el aspecto del control cambiando las propiedades de elemento correspondientes y actualizando las variables globales subyacentes.  
  
 Agregue el código siguiente a la clase `MyControl1`.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#13)]  
  
#### Devolver los datos al host  
 El último componente del archivo es la clase `MyControlEventArgs`, que se utiliza para devolver los datos recopilados al host.  
  
 Agregue el código siguiente al espacio de nombres `MyControls`.  La implementación es sencilla y no se ofrece ninguna otra explicación.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#14)]  
  
 Compile la solución.  La compilación generará una DLL denominada MyControls.dll.  
  
<a name="winforms_host_section"></a>   
## Implementar la aplicación host de formularios de Windows Forms.  
 La aplicación host de [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] utiliza un objeto <xref:System.Windows.Forms.Integration.ElementHost> para hospedar el control compuesto de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  La aplicación controla el evento `OnButtonClick` para recibir los datos del control compuesto.  La aplicación también tiene un conjunto de botones de opción que puede utilizar para modificar el aspecto del control.  En la ilustración siguiente se muestra la aplicación.  
  
 ![Control Avalon de hospedaje en Windows Forms](../../../../docs/framework/wpf/advanced/media/wfhost.png "WFHost")  
El control compuesto de WPF hospedado en una aplicación de Windows Forms  
  
### Crear el proyecto  
 Para iniciar el proyecto:  
  
1.  Inicie [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] y abra el cuadro de diálogo **Nuevo proyecto**.  
  
2.  En Visual C\# y la categoría de Windows, seleccione la plantilla **Aplicación de Windows Forms**.  
  
3.  Denomine el nuevo proyecto `WFHost`.  
  
4.  Para la ubicación, especifique la misma carpeta de nivel superior que contiene el proyecto MyControls.  
  
5.  Haga clic en **Aceptar** para crear el proyecto.  
  
 También debe agregar referencias a la DLL que contiene `MyControl1` y a otros ensamblados.  
  
1.  En el Explorador de soluciones, haga clic con el botón secundario del mouse en el nombre del proyecto y seleccione **Agregar referencia**.  
  
2.  Haga clic en la pestaña **Examinar** y busque la carpeta que contiene MyControls.dll.  Para este tutorial, esta carpeta es MyControls\\bin\\Debug.  
  
3.  Seleccione MyControls.dll y, a continuación, haga clic en **Aceptar**.  
  
4.  Agregue referencias a los siguientes ensamblados.  
  
    -   PresentationCore  
  
    -   PresentationFramework  
  
    -   System.Xaml  
  
    -   WindowsBase  
  
    -   WindowsFormsIntegration  
  
### Implementar la interfaz de usuario de la aplicación  
 La interfaz de usuario de la aplicación de Windows Forms contiene varios controles para interactuar con el control compuesto de WPF.  
  
1.  Abra Form1 en el Diseñador de Windows Forms.  
  
2.  Amplíe el formulario para alojar los controles.  
  
3.  En la esquina superior derecha del formulario, agregue un control <xref:System.Windows.Forms.Panel?displayProperty=fullName> para incluir el control compuesto de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
4.  Agregue los siguientes controles <xref:System.Windows.Forms.GroupBox?displayProperty=fullName> al formulario.  
  
    |Name|Text|  
    |----------|----------|  
    |groupBox1|Color de fondo|  
    |groupBox2|Color de primer plano|  
    |groupBox3|FontSize|  
    |groupBox4|Familia de fuentes|  
    |groupBox5|Estilo de fuente|  
    |groupBox6|Grosor de fuente|  
    |groupBox7|Datos del control|  
  
5.  Agregue los siguientes controles <xref:System.Windows.Forms.RadioButton?displayProperty=fullName> a los controles <xref:System.Windows.Forms.GroupBox?displayProperty=fullName>.  
  
    |GroupBox|Name|Text|  
    |--------------|----------|----------|  
    |groupBox1|radioBackgroundOriginal|Original|  
    |groupBox1|radioBackgroundLightGreen|LightGreen|  
    |groupBox1|radioBackgroundLightSalmon|LightSalmon|  
    |groupBox2|radioForegroundOriginal|Original|  
    |groupBox2|radioForegroundRed|Red|  
    |groupBox2|radioForegroundYellow|Yellow|  
    |groupBox3|radioSizeOriginal|Original|  
    |groupBox3|radioSizeTen|10|  
    |groupBox3|radioSizeTwelve|12|  
    |groupBox4|radioFamilyOriginal|Original|  
    |groupBox4|radioFamilyTimes|Times New Roman|  
    |groupBox4|radioFamilyWingDings|WingDings|  
    |groupBox5|radioStyleOriginal|Normal|  
    |groupBox5|radioStyleItalic|Cursiva|  
    |groupBox6|radioWeightOriginal|Original|  
    |groupBox6|radioWeightBold|Negrita|  
  
6.  Agregue los siguientes controles <xref:System.Windows.Forms.Label?displayProperty=fullName> al último <xref:System.Windows.Forms.GroupBox?displayProperty=fullName>.  Estos controles muestran los datos devueltos por el control compuesto de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
    |GroupBox|Name|Text|  
    |--------------|----------|----------|  
    |groupBox7|lblName|Nombre:|  
    |groupBox7|lblAddress|Dirección:|  
    |groupBox7|lblCity|Ciudad:|  
    |groupBox7|lblState|Estado:|  
    |groupBox7|lblZip|Código postal:|  
  
### Inicializar el formulario  
 Generalmente, implementará el código host en el controlador de eventos <xref:System.Windows.Forms.Form.Load> del formulario.  El código siguiente muestra el controlador de eventos <xref:System.Windows.Forms.Form.Load>, un controlador del evento <xref:System.Windows.FrameworkElement.Loaded> del control compuesto de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y las declaraciones de varias variables globales que se utilizarán más adelante.  
  
 En el Diseñador de Windows Forms, haga doble clic en el formulario para crear un controlador de eventos <xref:System.Windows.Forms.Form.Load>.  En la parte superior de Form1.cs, agregue las siguientes instrucciones `using`.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#10)]  
  
 Reemplace el contenido de la clase `Form1` existente por el siguiente código.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#2)]  
  
 El método `Form1_Load` del código anterior muestra el procedimiento general para hospedar un control [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
1.  Crear un nuevo objeto <xref:System.Windows.Forms.Integration.ElementHost>.  
  
2.  Establezca la propiedad <xref:System.Windows.Forms.Control.Dock%2A> del control en <xref:System.Windows.Forms.DockStyle?displayProperty=fullName>.  
  
3.  Agregue el control <xref:System.Windows.Forms.Integration.ElementHost> a la colección <xref:System.Windows.Forms.Control.Controls%2A> del control <xref:System.Windows.Forms.Panel>.  
  
4.  Cree una instancia del control de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
5.  Hospede el control compuesto en el formulario asignando el control a la propiedad <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> del control <xref:System.Windows.Forms.Integration.ElementHost>.  
  
 Las restantes dos líneas del método `Form1_Load` adjuntan controladores a dos eventos de control:  
  
-   `OnButtonClick` es un evento personalizado iniciado por el control compuesto cuando el usuario hace clic en el botón **Aceptar** o **Cancelar**.  Controle el evento para obtener la respuesta del usuario y recopilar cualquier dato que especifique el usuario.  
  
-   <xref:System.Windows.FrameworkElement.Loaded> es un evento estándar generado por un control de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] cuando se carga totalmente.  El evento se utiliza aquí porque el ejemplo debe inicializar varias variables globales utilizando propiedades del control.  En el momento del evento <xref:System.Windows.Forms.Form.Load> del formulario, el control no está cargado totalmente y esos valores todavía están establecidos en `null`.  Debe esperar hasta que se produzca el evento <xref:System.Windows.FrameworkElement.Loaded> del control para poder tener acceso a esas propiedades.  
  
 El controlador de eventos <xref:System.Windows.FrameworkElement.Loaded> se muestra en el código anterior.  El controlador `OnButtonClick` se explica en la sección siguiente.  
  
### Administrar OnButtonClick  
 El evento `OnButtonClick` se produce cuando el usuario hace clic en el botón **Aceptar** o **Cancelar**.  
  
 El controlador de eventos consulte el campo `IsOK` del argumento de evento para determinar en qué botón se hizo clic.  Las variables `lbl`*datos* corresponden a los controles <xref:System.Windows.Forms.Label> explicados anteriormente.  Si el usuario hace clic en el botón **Aceptar**, los datos de los controles <xref:System.Windows.Controls.TextBox> del control se asignan al control <xref:System.Windows.Forms.Label> correspondiente.  Si el usuario hace clic en **Cancelar**, los valores <xref:System.Windows.Forms.Label.Text%2A> se establecen en las cadenas predeterminadas.  
  
 Agregue el siguiente código de controlador de eventos de clic de botón a la clase `Form1`.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#3)]  
  
 Compile y ejecute la aplicación.  Agregue texto en el control compuesto de WPF y, a continuación, haga clic en **Aceptar**.  El texto aparece en las etiquetas.  En este punto, no se ha agregado código para controlar los botones de radio.  
  
### Modificar la apariencia del control  
 Los controles <xref:System.Windows.Forms.RadioButton> del formulario permitirán al usuario cambiar los colores de fondo y primer plano del control compuesto de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], así como diversas propiedades de fuente.  El objeto <xref:System.Windows.Forms.Integration.ElementHost> expone el color de fondo.  Las propiedades restantes se exponen como propiedades personalizadas del control.  
  
 Haga doble clic en cada control <xref:System.Windows.Forms.RadioButton> en el formulario para crear controladores de eventos <xref:System.Windows.Forms.RadioButton.CheckedChanged>.  Reemplace los controladores de eventos <xref:System.Windows.Forms.RadioButton.CheckedChanged> por el siguiente código.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#4)]  
  
 Compile y ejecute la aplicación.  Haga clic en los distintos botones de radio para ver el efecto en el control compuesto de WPF.  
  
## Vea también  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [WPF Designer](http://msdn.microsoft.com/es-es/c6c65214-8411-4e16-b254-163ed4099c26)   
 [Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)   
 [Tutorial: Hospedar un control compuesto 3 D de WPF en Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md)