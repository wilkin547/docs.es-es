---
title: Hospedar un WPFWPF control compuesto en Windows Forms
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
ms.assetid: 0ac41286-4c1b-4b17-9196-d985cb844ce1
ms.openlocfilehash: 4e98dd41606bff559abb981397acf2582a961cef
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111860"
---
# <a name="walkthrough-hosting-a-wpf-composite-control-in-windows-forms"></a>Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona un entorno rico para crear aplicaciones. Sin embargo, cuando tiene una inversión sustancial en código de formularios Windows [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Forms, puede ser más eficaz ampliar la aplicación de formularios Windows Forms existente con en lugar de volver a escribirla desde cero. Un escenario común es cuando desea incrustar uno [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] o varios controles implementados con dentro de la aplicación de Windows Forms. Para obtener más información acerca de cómo personalizar controles WPFWPF, vea [Personalización](../controls/control-customization.md)de controles .  
  
 Este tutorial le guía a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] través de una aplicación que hospeda un control compuesto para realizar la entrada de datos en una aplicación de windows Forms. El control compuesto se empaqueta en un archivo DLL. Este procedimiento general se puede extender a aplicaciones y controles más complejos. Este tutorial está diseñado para ser casi idéntico en apariencia y funcionalidad a Tutorial: Hospedar un control compuesto de [formularios Windows Forms en WPFWPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md). La principal diferencia es que se invierte el escenario de hospedaje.  
  
 Este tutorial está dividido en dos secciones. En la primera sección se describe [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] brevemente la implementación del control compuesto. En la segunda sección se describe en detalle cómo hospedar el control compuesto en una aplicación de formularios Windows Forms, recibir eventos del control y tener acceso a algunas de las propiedades del control.  
  
 Las tareas ilustradas en este tutorial incluyen:  
  
- Implementar el control compuesto de WPF.  
  
- Implementar la aplicación host de Windows Forms.  
  
 Para obtener una lista completa del código de las tareas que se ilustran en este tutorial, vea [Hospedar un control compuesto de WPF en el ejemplo](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WindowsFormsHostingWpfControl)de formularios Windows Forms .  
  
## <a name="prerequisites"></a>Requisitos previos  

Necesita Visual Studio para completar este tutorial.  
  
## <a name="implementing-the-wpf-composite-control"></a>Implementar el control compuesto de WPF  
 El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control compuesto utilizado en este ejemplo es un formulario de entrada de datos simple que toma el nombre y la dirección del usuario. Cuando el usuario hace clic en uno de los dos botones para indicar que la tarea ha finalizado, el control genera un evento personalizado para devolver esa información al host. En la ilustración siguiente se muestra la representación del control.

 La siguiente imagen muestra un WPFWPF control compuesto:

 ![Captura de pantalla que muestra un control WPF simple.](./media/walkthrough-hosting-a-wpf-composite-control-in-windows-forms/windows-presentation-foundation-composite-control.png)  
  
### <a name="creating-the-project"></a>Crear el proyecto  
 Para iniciar el proyecto:  
  
1. Inicie Visual Studio y abra el cuadro de diálogo **Nuevo proyecto.**  
  
2. En Visual C- y la categoría de Windows, seleccione la wpfwpf plantilla de biblioteca de controles de **usuario.**  
  
3. Asigne al nuevo proyecto el nombre de `MyControls`.  
  
4. Para la ubicación, especifique una carpeta de nivel `WindowsFormsHostingWpfControl`superior con el nombre conveniente, como . Más tarde, colocará la aplicación host en esta carpeta.  
  
5. Haga clic en **Aceptar** para crear el proyecto. El proyecto predeterminado contiene `UserControl1`un único control denominado .  
  
6. En el Explorador `UserControl1` `MyControl1`de soluciones, cambie el nombre a .  
  
 El proyecto debe tener referencias a los siguientes archivos DLL del sistema. Si alguno de estos archivos DLL no está incluido de forma predeterminada, agréguelos al proyecto.  
  
- PresentationCore  
  
- PresentationFramework  
  
- Sistema  
  
- WindowsBase  
  
### <a name="creating-the-user-interface"></a>Crear la interfaz de usuario  
 El [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] control compuesto para el [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]compuesto se implementa con . El control [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] compuesto <xref:System.Windows.Controls.TextBox> consta de cinco elementos. Cada <xref:System.Windows.Controls.TextBox> elemento tiene <xref:System.Windows.Controls.TextBlock> un elemento asociado que actúa como una etiqueta. Hay dos <xref:System.Windows.Controls.Button> elementos en la parte inferior, **OK** y **Cancel**. Cuando el usuario hace clic en cualquiera de los botones, el control genera un evento personalizado para devolver la información al host.  
  
#### <a name="basic-layout"></a>Diseño básico  
 Los [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] distintos elementos <xref:System.Windows.Controls.Grid> están contenidos en un elemento. Puede usar <xref:System.Windows.Controls.Grid> para organizar el contenido del control compuesto de `Table` la misma manera que usaría un elemento en HTML. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]también tiene <xref:System.Windows.Documents.Table> un <xref:System.Windows.Controls.Grid> elemento, pero es más ligero y más adecuado para tareas de diseño simples.  
  
 En el siguiente código XAML se muestra el diseño básico. Este XAML define la estructura general del control especificando el <xref:System.Windows.Controls.Grid> número de columnas y filas en el elemento.  
  
 En MyControl1.xaml, reemplace el código XAML existente por el siguiente código XAML.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#101)]  
[!code-xaml[WindowsFormsHostingWpfControl#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#102)]  
  
#### <a name="adding-textblock-and-textbox-elements-to-the-grid"></a>Agregar elementos TextBlock y TextBox a la cuadrícula  
 Coloque un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elemento en la cuadrícula estableciendo <xref:System.Windows.Controls.Grid.ColumnProperty> los atributos y los atributos del <xref:System.Windows.Controls.Grid.RowProperty> elemento en el número de fila y columna adecuado. Recuerde que la numeración de filas y columnas está basada en ceros. Puede hacer que un elemento abarque varias columnas estableciendo su <xref:System.Windows.Controls.Grid.ColumnSpanProperty> atributo. Para obtener <xref:System.Windows.Controls.Grid> más información acerca de los elementos, vea [Crear un elemento](../controls/how-to-create-a-grid-element.md)de cuadrícula .  
  
 El XAML siguiente muestra los <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.TextBlock> elementos <xref:System.Windows.Controls.Grid.RowProperty> y <xref:System.Windows.Controls.Grid.ColumnProperty> controles compuestos con sus atributos, que se establecen para colocar los elementos correctamente en la cuadrícula.  
  
 En MyControl1.xaml, agregue el <xref:System.Windows.Controls.Grid> siguiente XAML dentro del elemento.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#103)]  
  
#### <a name="styling-the-ui-elements"></a>Aplicar estilos a los elementos de interfaz de usuario  
 Muchos de los elementos del formulario de entrada de datos tienen un aspecto similar, lo que significa que tienen valores idénticos para varias de sus propiedades. En lugar de establecer los atributos de <xref:System.Windows.Style> cada elemento por separado, el XAML anterior usa elementos para definir la configuración de propiedades estándar para las clases de elementos. Este enfoque reduce la complejidad del control y le permite cambiar la apariencia de varios elementos mediante un solo atributo de estilo.  
  
 Los <xref:System.Windows.Style> elementos están <xref:System.Windows.Controls.Grid> contenidos <xref:System.Windows.FrameworkElement.Resources%2A> en la propiedad del elemento, por lo que pueden ser utilizados por todos los elementos del control. Si se nombra un estilo, se aplica <xref:System.Windows.Style> a un elemento agregando un elemento establecido al nombre del estilo. Los estilos que no tienen nombre se convierten en el estilo predeterminado del elemento. Para obtener [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] más información acerca de los estilos, vea [Estilo y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md).  
  
 El XAML siguiente <xref:System.Windows.Style> muestra los elementos para el control compuesto. Para ver cómo se aplican los estilos a los elementos, vea el código XAML anterior. Por ejemplo, <xref:System.Windows.Controls.TextBlock> el último `inlineText` elemento tiene <xref:System.Windows.Controls.TextBox> el estilo y el último elemento utiliza el estilo predeterminado.  
  
 En MyControl1.xaml, agregue el siguiente <xref:System.Windows.Controls.Grid> XAML justo después del elemento start.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#104)]  
  
#### <a name="adding-the-ok-and-cancel-buttons"></a>Agregar los botones Aceptar y Cancelar  
 Los elementos finales del control compuesto son los elementos **OK** y **Cancel,** <xref:System.Windows.Controls.Button> que ocupan las dos primeras columnas de la última fila del <xref:System.Windows.Controls.Grid>archivo . Estos elementos usan un `ButtonClicked`controlador de <xref:System.Windows.Controls.Button> eventos común, , y el estilo predeterminado definido en el XAML anterior.  
  
 En MyControl1.xaml, agregue el siguiente <xref:System.Windows.Controls.TextBox> XAML después del último elemento. La [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] parte del control compuesto ya está completa.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#105](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#105)]  
  
### <a name="implementing-the-code-behind-file"></a>Implementar el archivo de código subyacente  
 El archivo de código subyacente, MyControl1.xaml.cs, implementa tres tareas esenciales:
  
1. Controla el evento que se produce cuando el usuario hace clic en uno de los botones.  
  
2. Recupera los datos <xref:System.Windows.Controls.TextBox> de los elementos y los empaqueta en un objeto de argumento de evento personalizado.  
  
3. Provoca el `OnButtonClick` evento personalizado, que notifica al host que el usuario ha terminado y devuelve los datos al host.  
  
 El control también expone una serie de propiedades de color y fuente con las que puede cambiar la apariencia. A <xref:System.Windows.Forms.Integration.WindowsFormsHost> diferencia de la clase, que se <xref:System.Windows.Forms.Integration.ElementHost> usa para hospedar un <xref:System.Windows.Controls.Panel.Background%2A> control de formularios Windows Forms, la clase expone solo la propiedad del control. Para mantener la similitud entre este ejemplo de código y el ejemplo descrito en Tutorial: hospedar un control compuesto de [formularios Windows Forms en WPFWPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md), el control expone las propiedades restantes directamente.  
  
#### <a name="the-basic-structure-of-the-code-behind-file"></a>Estructura básica del archivo de código subyacente  
 El archivo de código subyacente consta `MyControls`de un único `MyControl1` espacio `MyControlEventArgs`de nombres, , que contendrá dos clases y .  
  
```csharp  
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
  
 La primera `MyControl1`clase, , es una clase parcial que contiene [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] el código que implementa la funcionalidad de lo definido en MyControl1.xaml. Cuando se analiza MyControl1.xaml, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] se convierte en la misma clase parcial y las dos clases parciales se combinan para formar el control compilado. Por este motivo, el nombre de clase del archivo de código subyacente debe coincidir con el nombre de clase asignado a MyControl1.xaml y debe heredar del elemento raíz del control. La segunda `MyControlEventArgs`clase, , es una clase de argumentos de evento que se utiliza para devolver los datos al host.  
  
 Abra MyControl1.xaml.cs. Cambie la declaración de clase existente para que <xref:System.Windows.Controls.Grid>tenga el siguiente nombre y herede de .  
  
 [!code-csharp[WindowsFormsHostingWpfControl#21](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#21)]  
  
#### <a name="initializing-the-control"></a>Inicializar el control  
 En el código siguiente se implementan varias tareas básicas:  
  
- Declara un evento `OnButtonClick`privado, , y `MyControlEventHandler`su delegado asociado, .  
  
- Crea distintas variables globales privadas que almacenan los datos del usuario. Estos datos se exponen a través de las propiedades correspondientes.  
  
- Implementa un controlador, `Init`, para <xref:System.Windows.FrameworkElement.Loaded> el evento del control. Este controlador inicializa las variables globales al asignarles los valores definidos en MyControl1.xaml. Para ello, utiliza <xref:System.Windows.FrameworkElement.Name%2A> el asignado <xref:System.Windows.Controls.TextBlock> a `nameLabel`un elemento típico, , para tener acceso a la configuración de propiedades de ese elemento.  
  
 Elimine el constructor existente y agregue `MyControl1` el código siguiente a la clase.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#11)]  
  
#### <a name="handling-the-buttons-click-events"></a>Administrar los eventos de clic de los botones  
 El usuario indica que la tarea de entrada de datos ha finalizado haciendo clic en el botón **Aceptar** o en el botón **Cancelar.** Ambos botones <xref:System.Windows.Controls.Primitives.ButtonBase.Click> usan el `ButtonClicked`mismo controlador de eventos, . Ambos botones tienen `btnOK` `btnCancel`un nombre o , que permite al controlador determinar qué `sender` botón se hizo clic examinando el valor del argumento. El controlador hace lo siguiente:  
  
- Crea `MyControlEventArgs` un objeto que contiene <xref:System.Windows.Controls.TextBox> los datos de los elementos.  
  
- Si el usuario ha haciendo clic `MyControlEventArgs` en `IsOK` el `false`botón **Cancelar,** establece la propiedad del objeto en .  
  
- Provoca el `OnButtonClick` evento para indicar al host que el usuario ha terminado y devuelve los datos recopilados.  
  
 Agregue el código `MyControl1` siguiente a `Init` la clase, después del método.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#12)]  
  
#### <a name="creating-properties"></a>Crear propiedades  
 El resto de la clase simplemente expone propiedades que corresponden a las variables globales que se han descrito anteriormente. Cuando se cambia una propiedad, el descriptor de acceso set modifica el aspecto del control cambiando las propiedades de elemento correspondientes y actualizando las variables globales subyacentes.  
  
 Agregue el siguiente `MyControl1` código a la clase.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#13)]  
  
#### <a name="sending-the-data-back-to-the-host"></a>Devolver los datos al host  
 El componente final del `MyControlEventArgs` archivo es la clase, que se utiliza para devolver los datos recopilados al host.  
  
 Agregue el código `MyControls` siguiente al espacio de nombres. La implementación es sencilla, por lo que no se tratará más adelante.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#14)]  
  
 Compile la solución. La compilación generará un archivo DLL denominado MyControls.dll.  
  
<a name="winforms_host_section"></a>
## <a name="implementing-the-windows-forms-host-application"></a>Implementar la aplicación host de Windows Forms  
 La aplicación host de <xref:System.Windows.Forms.Integration.ElementHost> formularios Windows [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Forms usa un objeto para hospedar el control compuesto. La aplicación `OnButtonClick` controla el evento para recibir los datos del control compuesto. La aplicación también tiene un conjunto de botones de opción que se pueden usar para modificar la apariencia del control. En la siguiente ilustración se muestra la aplicación.  

En la siguiente imagen se muestra un control compuesto WPFWPF hospedado en una aplicación de Windows Forms"  

 ![Scteenshot que muestra un control Avalon de Windows Form Hosting.](./media/walkthrough-hosting-a-wpf-composite-control-in-windows-forms/windows-form-hosting-avalon-control.png)  
  
### <a name="creating-the-project"></a>Crear el proyecto  
 Para iniciar el proyecto:  
  
1. Inicie Visual Studio y abra el cuadro de diálogo **Nuevo proyecto.**  
  
2. En Visual C- y la categoría de Windows, seleccione la plantilla Aplicación de **formularios Windows Forms.**  
  
3. Asigne al nuevo proyecto el nombre de `WFHost`.  
  
4. Para la ubicación, especifique la misma carpeta de nivel superior que contiene el proyecto MyControls.  
  
5. Haga clic en **Aceptar** para crear el proyecto.  
  
 También debe agregar referencias al archivo `MyControl1` DLL que contiene y otros ensamblados.  
  
1. Haga clic con el botón secundario en el nombre del proyecto en el Explorador de soluciones y seleccione **Agregar referencia**.  
  
2. Haga clic en la pestaña **Examinar** y vaya a la carpeta que contiene MyControls.dll. En este tutorial, esta carpeta es MyControls\bin\Debug.  
  
3. Seleccione MyControls.dll y, a continuación, haga clic en **Aceptar**.  
  
4. Agregue referencias a los ensamblados siguientes.  
  
    - PresentationCore  
  
    - PresentationFramework  
  
    - System.Xaml  
  
    - WindowsBase  
  
    - WindowsFormsIntegration  
  
### <a name="implementing-the-user-interface-for-the-application"></a>Implementar la interfaz de usuario de la aplicación  
 La interfaz de usuario de la aplicación de Windows Forms contiene varios controles para interactuar con el control compuesto de WPF.  
  
1. Abra Form1 en el Diseñador de Windows Forms.  
  
2. Amplíe el formulario para que quepan los controles.  
  
3. En la esquina superior derecha del <xref:System.Windows.Forms.Panel?displayProperty=nameWithType> formulario, agregue [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] un control para mantener el control compuesto.  
  
4. Agregue los <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType> siguientes controles al formulario.  
  
    |Nombre|Texto|  
    |----------|----------|  
    |groupBox1|Color de fondo|  
    |groupBox2|Color de primer plano|  
    |groupBox3|Tamaño de fuente|  
    |groupBox4|Familia de fuentes|  
    |groupBox5|Estilo de fuente|  
    |groupBox6|Espesor de fuente|  
    |groupBox7|Datos del control|  
  
5. Agregue los <xref:System.Windows.Forms.RadioButton?displayProperty=nameWithType> siguientes <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType> controles a los controles.  
  
    |GroupBox|Nombre|Texto|  
    |--------------|----------|----------|  
    |groupBox1|radioBackgroundOriginal|Original|  
    |groupBox1|radioBackgroundLightGreen|LightGreen|  
    |groupBox1|radioBackgroundLightSalmon|LightSalmon|  
    |groupBox2|radioForegroundOriginal|Original|  
    |groupBox2|radioForegroundRed|Rojo|  
    |groupBox2|radioForegroundYellow|Amarillo|  
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
  
6. Agregue los <xref:System.Windows.Forms.Label?displayProperty=nameWithType> siguientes controles <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType>al último archivo . Estos controles muestran los [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] datos devueltos por el control compuesto.  
  
    |GroupBox|Nombre|Texto|  
    |--------------|----------|----------|  
    |groupBox7|lblName|Nombre:|  
    |groupBox7|lblAddress|Dirección postal:|  
    |groupBox7|lblCity|Ciudad:|  
    |groupBox7|lblState|Estado:|  
    |groupBox7|lblZip|Código postal:|  
  
### <a name="initializing-the-form"></a>Inicializar el formulario  
 Por lo general, se implementa el <xref:System.Windows.Forms.Form.Load> código de hospedaje en el controlador de eventos del formulario. El código siguiente <xref:System.Windows.Forms.Form.Load> muestra el controlador [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de eventos, <xref:System.Windows.FrameworkElement.Loaded> un controlador para el evento del control compuesto y declaraciones para varias variables globales que se usan más adelante.  
  
 En el Diseñador de Windows Forms, haga <xref:System.Windows.Forms.Form.Load> doble clic en el formulario para crear un controlador de eventos. En la parte superior de `using` Form1.cs, agregue las siguientes instrucciones.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#10)]  
  
 Reemplace el contenido `Form1` de la clase existente por el código siguiente.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#2)]  
  
 El `Form1_Load` método del código anterior muestra el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] procedimiento general para hospedar un control:  
  
1. Cree un nuevo objeto <xref:System.Windows.Forms.Integration.ElementHost>.  
  
2. Establezca la propiedad <xref:System.Windows.Forms.Control.Dock%2A> del <xref:System.Windows.Forms.DockStyle.Fill?displayProperty=nameWithType>control en .  
  
3. Agregue <xref:System.Windows.Forms.Integration.ElementHost> el control <xref:System.Windows.Forms.Panel> a <xref:System.Windows.Forms.Control.Controls%2A> la colección del control.  
  
4. Cree una instancia [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] del control.  
  
5. Hospede el control compuesto en el <xref:System.Windows.Forms.Integration.ElementHost> formulario <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> asignando el control a la propiedad del control.  
  
 Las dos líneas restantes del `Form1_Load` método adjuntan controladores a dos eventos de control:  
  
- `OnButtonClick`es un evento personalizado que se desencadena por el control compuesto cuando el usuario hace clic en el **aceptar** o **cancelar** botón. El evento se controla para obtener la respuesta del usuario y recopilar los datos que este haya especificado.  
  
- <xref:System.Windows.FrameworkElement.Loaded>es un evento estándar que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] genera un control cuando está completamente cargado. El evento se usa aquí porque el ejemplo necesita inicializar distintas variables globales usando las propiedades del control. En el momento del <xref:System.Windows.Forms.Form.Load> evento del formulario, el control no está `null`completamente cargado y esos valores todavía se establecen en . Debe esperar hasta que se <xref:System.Windows.FrameworkElement.Loaded> produzca el evento del control para poder tener acceso a esas propiedades.  
  
 El <xref:System.Windows.FrameworkElement.Loaded> controlador de eventos se muestra en el código anterior. El `OnButtonClick` controlador se describe en la sección siguiente.  
  
### <a name="handling-onbuttonclick"></a>Administrar OnButtonClick  
 El `OnButtonClick` evento se produce cuando el usuario hace clic en el botón **Aceptar** o **Cancelar.**  
  
 El controlador de eventos comprueba `IsOK` el campo del argumento de evento para determinar en qué botón se hizo clic. Las `lbl` *data* variables de <xref:System.Windows.Forms.Label> datos corresponden a los controles que se discutieron anteriormente. Si el usuario hace clic en el **Aceptar** <xref:System.Windows.Controls.TextBox> botón, los <xref:System.Windows.Forms.Label> datos de los controles del control se asignan al control correspondiente. Si el usuario **Cancel**hace <xref:System.Windows.Forms.Label.Text%2A> clic en Cancelar , los valores se establecen en las cadenas predeterminadas.  
  
 Agregue el siguiente botón haga `Form1` clic en el código del controlador de eventos a la clase.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#3)]  
  
 Compile y ejecute la aplicación. Agregue texto en el WPFWPF control compuesto y, a continuación, haga clic en **Aceptar**. El texto aparece en las etiquetas. En este momento, no se ha agregado código para controlar los botones de radio.  
  
### <a name="modifying-the-appearance-of-the-control"></a>Modificar la apariencia del control  
 Los <xref:System.Windows.Forms.RadioButton> controles del formulario permitirán al [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usuario cambiar los colores de primer plano y fondo del control compuesto, así como varias propiedades de fuente. El color de fondo <xref:System.Windows.Forms.Integration.ElementHost> se expone mediante el objeto. Las propiedades restantes se exponen como propiedades personalizadas del control.  
  
 Haga doble <xref:System.Windows.Forms.RadioButton> clic en cada <xref:System.Windows.Forms.RadioButton.CheckedChanged> control del formulario para crear controladores de eventos. Reemplace <xref:System.Windows.Forms.RadioButton.CheckedChanged> los controladores de eventos por el código siguiente.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#4)]  
  
 Compile y ejecute la aplicación. Haga clic en los diferentes botones de radio para ver el efecto en el control compuesto de WPF.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Diseño de XAML en Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Tutorial: Hospedar un control compuesto de WPF 3D en Windows Forms](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md)
