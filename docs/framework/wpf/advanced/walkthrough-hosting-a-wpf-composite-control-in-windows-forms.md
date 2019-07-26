---
title: 'Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
ms.assetid: 0ac41286-4c1b-4b17-9196-d985cb844ce1
ms.openlocfilehash: bff89f1d81b16c8c66d73901ef951626f6d2cb9e
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2019
ms.locfileid: "68400625"
---
# <a name="walkthrough-hosting-a-wpf-composite-control-in-windows-forms"></a>Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona un entorno rico para crear aplicaciones. Sin embargo, si tiene una inversión sustancial en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] código, puede ser más eficaz ampliar su aplicación existente [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en lugar de volver a escribirla desde el principio. Un escenario común es cuando desea insertar uno o varios controles implementados con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dentro de la aplicación Windows Forms. Para obtener más información sobre cómo personalizar controles de WPF [](../controls/control-customization.md), vea personalización de controles.  
  
 Este tutorial le guía a través de una aplicación que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hospeda un control compuesto para realizar la entrada de datos en una aplicación Windows Forms. El control compuesto se empaqueta en un archivo DLL. Este procedimiento general se puede extender a aplicaciones y controles más complejos. Este tutorial está diseñado para ser casi idéntico en aspecto y funcionalidad al [Tutorial: Hospedar un control compuesto de Windows Forms](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)en WPF. La principal diferencia es que se invierte el escenario de hospedaje.  
  
 Este tutorial está dividido en dos secciones. En la primera sección se describe brevemente la implementación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] del control compuesto. En la segunda sección se explica en detalle cómo hospedar el control compuesto en una aplicación Windows Forms, recibir eventos del control y tener acceso a algunas de las propiedades del control.  
  
 Las tareas ilustradas en este tutorial incluyen:  
  
- Implementar el control compuesto de WPF.  
  
- Implementar la aplicación host de Windows Forms.  
  
 Para obtener una lista de código completa de las tareas ilustradas en este tutorial, vea [hospedar un control compuesto de WPF en Windows Forms ejemplo](https://github.com/microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WindowsFormsHostingWpfControl).  
  
## <a name="prerequisites"></a>Requisitos previos  

Necesita Visual Studio para completar este tutorial.  
  
## <a name="implementing-the-wpf-composite-control"></a>Implementar el control compuesto de WPF  
 El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control compuesto utilizado en este ejemplo es un formulario de entrada de datos simple que toma el nombre y la dirección del usuario. Cuando el usuario hace clic en uno de los dos botones para indicar que la tarea ha finalizado, el control genera un evento personalizado para devolver esa información al host. En la ilustración siguiente se muestra la representación del control. 

 En la siguiente imagen se muestra un control compuesto de WPF: 

 ![Captura de pantalla que muestra un control WPF sencillo.](./media/walkthrough-hosting-a-wpf-composite-control-in-windows-forms/windows-presentation-foundation-composite-control.png)  
  
### <a name="creating-the-project"></a>Crear el proyecto  
 Para iniciar el proyecto:  
  
1. Inicie [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]y abra el cuadro de diálogo **nuevo proyecto** .  
  
2. En la C# categoría visual y Windows, seleccione la plantilla **biblioteca de controles de usuario de WPF** .  
  
3. Asigne al nuevo proyecto el nombre de `MyControls`.  
  
4. Para la ubicación, especifique una carpeta de nivel superior con un nombre adecuado, `WindowsFormsHostingWpfControl`como. Más tarde, colocará la aplicación host en esta carpeta.  
  
5. Haga clic en **Aceptar** para crear el proyecto. El proyecto predeterminado contiene un único control denominado `UserControl1`.  
  
6. En explorador de soluciones, cambie el `UserControl1` nombre `MyControl1`a.  
  
 El proyecto debe tener referencias a los siguientes archivos DLL del sistema. Si alguno de estos archivos DLL no está incluido de forma predeterminada, agréguelos al proyecto.  
  
- PresentationCore  
  
- PresentationFramework  
  
- Sistema  
  
- WindowsBase  
  
### <a name="creating-the-user-interface"></a>Crear la interfaz de usuario  
 El [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] para el control compuesto se implementa con [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. El control [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] compuesto consta de cinco <xref:System.Windows.Controls.TextBox> elementos. Cada <xref:System.Windows.Controls.TextBox> elemento tiene un elemento <xref:System.Windows.Controls.TextBlock> asociado que actúa como una etiqueta. Hay dos <xref:System.Windows.Controls.Button> elementos en la parte inferior, **Aceptar** y **Cancelar**. Cuando el usuario hace clic en cualquiera de los botones, el control genera un evento personalizado para devolver la información al host.  
  
#### <a name="basic-layout"></a>Diseño básico  
 Los distintos [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementos se encuentran en un <xref:System.Windows.Controls.Grid> elemento. Puede usar <xref:System.Windows.Controls.Grid> para organizar el contenido del control compuesto de la misma manera que usaría un `Table` elemento en HTML. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]también tiene un <xref:System.Windows.Documents.Table> elemento, pero <xref:System.Windows.Controls.Grid> es más ligero y más adecuado para las tareas de diseño simples.  
  
 En el siguiente código XAML se muestra el diseño básico. Este código XAML define la estructura global del control especificando el número de columnas y filas <xref:System.Windows.Controls.Grid> del elemento.  
  
 En MyControl1.xaml, reemplace el código XAML existente por el siguiente código XAML.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#101)]  
[!code-xaml[WindowsFormsHostingWpfControl#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#102)]  
  
#### <a name="adding-textblock-and-textbox-elements-to-the-grid"></a>Agregar elementos TextBlock y TextBox a la cuadrícula  
 Para colocar un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elemento en la cuadrícula, establezca los atributos y <xref:System.Windows.Controls.Grid.RowProperty> <xref:System.Windows.Controls.Grid.ColumnProperty> del elemento en el número de fila y columna adecuado. Recuerde que la numeración de filas y columnas está basada en ceros. Puede tener un elemento que abarque varias columnas estableciendo su <xref:System.Windows.Controls.Grid.ColumnSpanProperty> atributo. Para obtener más información <xref:System.Windows.Controls.Grid> sobre los elementos, vea [crear un elemento Grid](../controls/how-to-create-a-grid-element.md).  
  
 En el siguiente código XAML se muestran los <xref:System.Windows.Controls.TextBox> elementos <xref:System.Windows.Controls.TextBlock> y del control <xref:System.Windows.Controls.Grid.RowProperty> compuesto <xref:System.Windows.Controls.Grid.ColumnProperty> con sus atributos y, que se establecen para colocar los elementos correctamente en la cuadrícula.  
  
 En MyControl1. XAML, agregue el siguiente código XAML dentro <xref:System.Windows.Controls.Grid> del elemento.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#103)]  
  
#### <a name="styling-the-ui-elements"></a>Aplicar estilos a los elementos de interfaz de usuario  
 Muchos de los elementos del formulario de entrada de datos tienen un aspecto similar, lo que significa que tienen valores idénticos para varias de sus propiedades. En lugar de establecer los atributos de cada elemento por separado, el código <xref:System.Windows.Style> XAML anterior usa los elementos para definir los valores de propiedad estándar para las clases de elementos. Este enfoque reduce la complejidad del control y le permite cambiar la apariencia de varios elementos mediante un solo atributo de estilo.  
  
 Los elementos están contenidos en la <xref:System.Windows.Controls.Grid> propiedad del <xref:System.Windows.FrameworkElement.Resources%2A> elemento, por lo que todos los elementos del control pueden utilizarlos. <xref:System.Windows.Style> Si un estilo se denomina, se aplica a un elemento agregando un <xref:System.Windows.Style> conjunto de elementos al nombre del estilo. Los estilos que no tienen nombre se convierten en el estilo predeterminado del elemento. Para obtener más información [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sobre los estilos, vea [aplicar estilos y plantillas](../controls/styling-and-templating.md).  
  
 En el siguiente código XAML <xref:System.Windows.Style> se muestran los elementos para el control compuesto. Para ver cómo se aplican los estilos a los elementos, vea el código XAML anterior. Por ejemplo, el último <xref:System.Windows.Controls.TextBlock> elemento tiene el `inlineText` estilo y el último <xref:System.Windows.Controls.TextBox> elemento usa el estilo predeterminado.  
  
 En MyControl1. XAML, agregue el código XAML siguiente justo después <xref:System.Windows.Controls.Grid> del elemento de inicio.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#104)]  
  
#### <a name="adding-the-ok-and-cancel-buttons"></a>Agregar los botones Aceptar y Cancelar  
 Los elementos finales del control compuesto son los elementos **OK** y **Cancel** <xref:System.Windows.Controls.Button> , que ocupan las dos primeras columnas <xref:System.Windows.Controls.Grid>de la última fila de. Estos elementos usan un controlador de eventos común `ButtonClicked`,, y el <xref:System.Windows.Controls.Button> estilo predeterminado definido en el código XAML anterior.  
  
 En MyControl1. XAML, agregue el siguiente código XAML después del <xref:System.Windows.Controls.TextBox> último elemento. La [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] parte del control compuesto ahora está completa.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#105](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#105)]  
  
### <a name="implementing-the-code-behind-file"></a>Implementar el archivo de código subyacente  
 El archivo de código subyacente, MyControl1.xaml.cs, implementa tres tareas esenciales:
  
1. Controla el evento que se produce cuando el usuario hace clic en uno de los botones.  
  
2. Recupera los datos de los <xref:System.Windows.Controls.TextBox> elementos y los empaqueta en un objeto de argumento de evento personalizado.  
  
3. Genera el evento `OnButtonClick` personalizado, que notifica al host que el usuario ha terminado y devuelve los datos al host.  
  
 El control también expone una serie de propiedades de color y fuente con las que puede cambiar la apariencia. A diferencia de <xref:System.Windows.Forms.Integration.WindowsFormsHost> la clase, que se usa para hospedar un control de <xref:System.Windows.Forms.Integration.ElementHost> Windows Forms, la clase solo expone <xref:System.Windows.Controls.Panel.Background%2A> la propiedad del control. Para mantener la similitud entre este ejemplo de código y el ejemplo que se [describe en Tutorial: Al hospedar un Windows Forms control compuesto](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)en WPF, el control expone las propiedades restantes directamente.  
  
#### <a name="the-basic-structure-of-the-code-behind-file"></a>Estructura básica del archivo de código subyacente  
 El archivo de código subyacente está compuesto de un solo espacio `MyControls`de nombres,, que contendrá `MyControl1` dos `MyControlEventArgs`clases, y.  
  
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
  
 La primera clase, `MyControl1`, es una clase parcial que contiene el código que implementa la funcionalidad [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] del definido en MyControl1. Xaml. Cuando se analiza MyControl1. XAML, el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] se convierte en la misma clase parcial y las dos clases parciales se combinan para formar el control compilado. Por este motivo, el nombre de clase del archivo de código subyacente debe coincidir con el nombre de clase asignado a MyControl1.xaml y debe heredar del elemento raíz del control. La segunda clase, `MyControlEventArgs`, es una clase de argumentos de evento que se utiliza para devolver los datos al host.  
  
 Abra MyControl1.xaml.cs. Cambie la declaración de clase existente para que tenga el siguiente nombre y herede de <xref:System.Windows.Controls.Grid>.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#21](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#21)]  
  
#### <a name="initializing-the-control"></a>Inicializar el control  
 En el código siguiente se implementan varias tareas básicas:  
  
- Declara un evento privado, `OnButtonClick`, y su delegado asociado,. `MyControlEventHandler`  
  
- Crea distintas variables globales privadas que almacenan los datos del usuario. Estos datos se exponen a través de las propiedades correspondientes.  
  
- Implementa un controlador, `Init`, para el evento del <xref:System.Windows.FrameworkElement.Loaded> control. Este controlador inicializa las variables globales al asignarles los valores definidos en MyControl1.xaml. Para ello, usa la asignada <xref:System.Windows.FrameworkElement.Name%2A> a un elemento típico <xref:System.Windows.Controls.TextBlock> , `nameLabel`, para tener acceso a los valores de la propiedad de ese elemento.  
  
 Elimine el constructor existente y agregue el código siguiente a `MyControl1` la clase.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#11)]  
  
#### <a name="handling-the-buttons-click-events"></a>Administrar los eventos de clic de los botones  
 El usuario indica que la tarea de entrada de datos ha finalizado haciendo clic en el botón **Aceptar** o en el botón **Cancelar** . Ambos botones usan el mismo <xref:System.Windows.Controls.Primitives.ButtonBase.Click> controlador de eventos `ButtonClicked`,. Ambos botones tienen un nombre, `btnOK` o `btnCancel`, que permite al controlador determinar en qué botón se hizo clic examinando el valor del `sender` argumento. El controlador hace lo siguiente:  
  
- Crea un `MyControlEventArgs` objeto que contiene los datos de los <xref:System.Windows.Controls.TextBox> elementos.  
  
- Si el usuario hizo clic en el botón **Cancelar** , establece `MyControlEventArgs` la propiedad `IsOK` del objeto `false`en.  
  
- Genera el `OnButtonClick` evento para indicar al host que el usuario ha terminado y devuelve los datos recopilados.  
  
 Agregue el código siguiente a la `MyControl1` clase, después del `Init` método.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#12)]  
  
#### <a name="creating-properties"></a>Crear propiedades  
 El resto de la clase simplemente expone propiedades que corresponden a las variables globales que se han descrito anteriormente. Cuando se cambia una propiedad, el descriptor de acceso set modifica el aspecto del control cambiando las propiedades de elemento correspondientes y actualizando las variables globales subyacentes.  
  
 Agregue el código siguiente a la `MyControl1` clase.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#13)]  
  
#### <a name="sending-the-data-back-to-the-host"></a>Devolver los datos al host  
 El componente final del archivo es la `MyControlEventArgs` clase, que se usa para devolver los datos recopilados al host.  
  
 Agregue el código siguiente al `MyControls` espacio de nombres. La implementación es sencilla, por lo que no se tratará más adelante.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#14)]  
  
 Compile la solución. La compilación generará un archivo DLL denominado MyControls.dll.  
  
<a name="winforms_host_section"></a>   
## <a name="implementing-the-windows-forms-host-application"></a>Implementar la aplicación host de Windows Forms  
 La aplicación host de Windows Forms usa <xref:System.Windows.Forms.Integration.ElementHost> un objeto para hospedar el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control compuesto. La aplicación controla el `OnButtonClick` evento para recibir los datos del control compuesto. La aplicación también tiene un conjunto de botones de opción que se pueden usar para modificar la apariencia del control. En la siguiente ilustración se muestra la aplicación.  

La siguiente imagen muestra un control compuesto de WPF hospedado en una aplicación Windows Forms "  

 ![Scteenshot que muestra un control Avalon de hospedaje de Windows Forms.](./media/walkthrough-hosting-a-wpf-composite-control-in-windows-forms/windows-form-hosting-avalon-control.png)  
  
### <a name="creating-the-project"></a>Crear el proyecto  
 Para iniciar el proyecto:  
  
1. Inicie [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]y abra el cuadro de diálogo **nuevo proyecto** .  
  
2. En Visual C# y en la categoría de Windows, seleccione la plantilla de **aplicación Windows Forms** .  
  
3. Asigne al nuevo proyecto el nombre de `WFHost`.  
  
4. Para la ubicación, especifique la misma carpeta de nivel superior que contiene el proyecto MyControls.  
  
5. Haga clic en **Aceptar** para crear el proyecto.  
  
 También debe agregar referencias al archivo DLL que contenga `MyControl1` y a otros ensamblados.  
  
1. Haga clic con el botón derecho en el nombre del proyecto en Explorador de soluciones y seleccione **Agregar referencia**.  
  
2. Haga clic en la pestaña **examinar** y busque la carpeta que contiene DataControl. dll. En este tutorial, esta carpeta es MyControls\bin\Debug.  
  
3. Seleccione Datacontrols. dll y, a continuación, haga clic en **Aceptar**.  
  
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
  
3. En la esquina superior derecha del formulario, agregue un <xref:System.Windows.Forms.Panel?displayProperty=nameWithType> control para que contenga el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control compuesto.  
  
4. Agregue los siguientes <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType> controles al formulario.  
  
    |NOMBRE|Text|  
    |----------|----------|  
    |groupBox1|Color de fondo|  
    |groupBox2|Color de primer plano|  
    |groupBox3|Tamaño de fuente|  
    |groupBox4|Familia de fuentes|  
    |groupBox5|Estilo de fuente|  
    |groupBox6|Espesor de fuente|  
    |groupBox7|Datos del control|  
  
5. Agregue los controles <xref:System.Windows.Forms.RadioButton?displayProperty=nameWithType> siguientes a los <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType> controles.  
  
    |GroupBox|NOMBRE|Text|  
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
  
6. Agregue los siguientes <xref:System.Windows.Forms.Label?displayProperty=nameWithType> controles al último. <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType> Estos controles muestran los datos devueltos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] por el control compuesto.  
  
    |GroupBox|NOMBRE|Text|  
    |--------------|----------|----------|  
    |groupBox7|lblName|Nombre:|  
    |groupBox7|lblAddress|Dirección postal:|  
    |groupBox7|lblCity|Ciudad:|  
    |groupBox7|lblState|Estado:|  
    |groupBox7|lblZip|Código postal:|  
  
### <a name="initializing-the-form"></a>Inicializar el formulario  
 En general, se implementa el código de hospedaje en <xref:System.Windows.Forms.Form.Load> el controlador de eventos del formulario. En el código siguiente se <xref:System.Windows.Forms.Form.Load> muestra el controlador de eventos, un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controlador para el <xref:System.Windows.FrameworkElement.Loaded> evento del control compuesto y declaraciones para varias variables globales que se usan más adelante.  
  
 En el diseñador de Windows Forms, haga doble clic en el formulario para crear <xref:System.Windows.Forms.Form.Load> un controlador de eventos. En la parte superior de Form1.CS, agregue las `using` siguientes instrucciones.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#10)]  
  
 Reemplace el contenido de la clase `Form1` existente por el código siguiente.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#2)]  
  
 El `Form1_Load` método en el código anterior muestra el procedimiento general para hospedar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] un control:  
  
1. Cree un nuevo <xref:System.Windows.Forms.Integration.ElementHost> objeto.  
  
2. Establezca la propiedad del <xref:System.Windows.Forms.Control.Dock%2A> control en <xref:System.Windows.Forms.DockStyle.Fill?displayProperty=nameWithType>.  
  
3. Agregue el <xref:System.Windows.Forms.Integration.ElementHost> control a la <xref:System.Windows.Forms.Panel> colección del <xref:System.Windows.Forms.Control.Controls%2A> control.  
  
4. Cree una instancia del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control.  
  
5. Hospede el control compuesto en el formulario asignando el control a la <xref:System.Windows.Forms.Integration.ElementHost> propiedad del <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> control.  
  
 Las dos líneas restantes en el `Form1_Load` método adjuntan controladores a dos eventos de control:  
  
- `OnButtonClick`es un evento personalizado que el control compuesto desencadena cuando el usuario hace clic en el botón **Aceptar** o **Cancelar** . El evento se controla para obtener la respuesta del usuario y recopilar los datos que este haya especificado.  
  
- <xref:System.Windows.FrameworkElement.Loaded>es un evento estándar generado por un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control cuando se carga por completo. El evento se usa aquí porque el ejemplo necesita inicializar distintas variables globales usando las propiedades del control. En el momento en que se produce <xref:System.Windows.Forms.Form.Load> el evento del formulario, el control no se carga completamente y esos valores todavía `null`se establecen en. Debe esperar hasta que se produzca el evento <xref:System.Windows.FrameworkElement.Loaded> del control antes de poder tener acceso a esas propiedades.  
  
 El <xref:System.Windows.FrameworkElement.Loaded> controlador de eventos se muestra en el código anterior. El `OnButtonClick` controlador se describe en la sección siguiente.  
  
### <a name="handling-onbuttonclick"></a>Administrar OnButtonClick  
 El `OnButtonClick` evento tiene lugar cuando el usuario hace clic en el botón **Aceptar** o **Cancelar** .  
  
 El controlador de eventos comprueba el campo del `IsOK` argumento del evento para determinar en qué botón se hizo clic. Las `lbl`variables de *datos* corresponden a <xref:System.Windows.Forms.Label> los controles descritos anteriormente. Si el usuario hace clic en el botón **Aceptar** , los datos de los controles <xref:System.Windows.Controls.TextBox> del control se asignan al <xref:System.Windows.Forms.Label> control correspondiente. Si el usuario hace clic en **Cancelar**, <xref:System.Windows.Forms.Label.Text%2A> los valores se establecen en las cadenas predeterminadas.  
  
 Agregue el siguiente código de controlador de eventos de clic `Form1` de botón a la clase.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#3)]  
  
 Compile y ejecute la aplicación. Agregue texto en el control compuesto de WPF y, a continuación, haga clic en **Aceptar**. El texto aparece en las etiquetas. En este momento, no se ha agregado código para controlar los botones de radio.  
  
### <a name="modifying-the-appearance-of-the-control"></a>Modificar la apariencia del control  
 Los <xref:System.Windows.Forms.RadioButton> controles del formulario permitirán al usuario cambiar los [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] colores de primer plano y de fondo del control compuesto, así como varias propiedades de fuente. El <xref:System.Windows.Forms.Integration.ElementHost> objeto expone el color de fondo. Las propiedades restantes se exponen como propiedades personalizadas del control.  
  
 Haga doble clic en <xref:System.Windows.Forms.RadioButton> cada control del formulario para crear <xref:System.Windows.Forms.RadioButton.CheckedChanged> controladores de eventos. Reemplace los <xref:System.Windows.Forms.RadioButton.CheckedChanged> controladores de eventos por el código siguiente.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#4)]  
  
 Compile y ejecute la aplicación. Haga clic en los diferentes botones de radio para ver el efecto en el control compuesto de WPF.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Diseño de XAML en Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Tutorial: Hospedar un control compuesto de Windows Forms en WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Tutorial: Hospedar un control compuesto de WPF 3D en Windows Forms](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md)
