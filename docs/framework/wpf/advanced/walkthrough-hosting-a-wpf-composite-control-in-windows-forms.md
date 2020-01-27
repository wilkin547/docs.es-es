---
title: Hospedar un control compuesto de WPF en Windows Forms
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
ms.assetid: 0ac41286-4c1b-4b17-9196-d985cb844ce1
ms.openlocfilehash: 59243e1810757ff0ff58a60ac3eb007bbc227be0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742684"
---
# <a name="walkthrough-hosting-a-wpf-composite-control-in-windows-forms"></a>Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona un entorno rico para crear aplicaciones. Sin embargo, si tiene una inversión sustancial en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] código, puede ser más eficaz ampliar su aplicación de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] existente con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en lugar de volver a escribirla desde el principio. Un escenario común es cuando desea incrustar uno o más controles implementados con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dentro de la aplicación de Windows Forms. Para obtener más información sobre cómo personalizar controles de WPF, vea [Personalización de controles](../controls/control-customization.md).  
  
 Este tutorial le guía a través de una aplicación que hospeda un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control compuesto para realizar la entrada de datos en una aplicación Windows Forms. El control compuesto se empaqueta en un archivo DLL. Este procedimiento general se puede extender a aplicaciones y controles más complejos. Este tutorial está diseñado para ser casi idéntico en aspecto y funcionalidad al [Tutorial: hospedar un Windows Forms control compuesto en WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md). La principal diferencia es que se invierte el escenario de hospedaje.  
  
 Este tutorial está dividido en dos secciones. En la primera sección se describe brevemente la implementación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control compuesto. En la segunda sección se explica en detalle cómo hospedar el control compuesto en una aplicación Windows Forms, recibir eventos del control y tener acceso a algunas de las propiedades del control.  
  
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
  
1. Inicie Visual Studio y abra el cuadro de diálogo **nuevo proyecto** .  
  
2. En la C# categoría visual y Windows, seleccione la plantilla **biblioteca de controles de usuario de WPF** .  
  
3. Asigne al nuevo proyecto el nombre de `MyControls`.  
  
4. Para la ubicación, especifique una carpeta de nivel superior con un nombre adecuado, como `WindowsFormsHostingWpfControl`. Más tarde, colocará la aplicación host en esta carpeta.  
  
5. Haga clic en **Aceptar** para crear el proyecto. El proyecto predeterminado contiene un solo control denominado `UserControl1`.  
  
6. En Explorador de soluciones, cambie el nombre de `UserControl1` a `MyControl1`.  
  
 El proyecto debe tener referencias a los siguientes archivos DLL del sistema. Si alguno de estos archivos DLL no está incluido de forma predeterminada, agréguelos al proyecto.  
  
- PresentationCore  
  
- PresentationFramework  
  
- System  
  
- WindowsBase  
  
### <a name="creating-the-user-interface"></a>Crear la interfaz de usuario  
 El [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] para el control compuesto se implementa con [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. El [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de control compuesto consta de cinco elementos <xref:System.Windows.Controls.TextBox>. Cada elemento <xref:System.Windows.Controls.TextBox> tiene un elemento <xref:System.Windows.Controls.TextBlock> asociado que actúa como etiqueta. Hay dos elementos <xref:System.Windows.Controls.Button> en la parte inferior, **Aceptar** y **Cancelar**. Cuando el usuario hace clic en cualquiera de los botones, el control genera un evento personalizado para devolver la información al host.  
  
#### <a name="basic-layout"></a>Diseño básico  
 Los distintos elementos [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] se encuentran en un elemento <xref:System.Windows.Controls.Grid>. Puede usar <xref:System.Windows.Controls.Grid> para organizar el contenido del control compuesto de la misma manera que usaría un elemento `Table` en HTML. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] también tiene un elemento <xref:System.Windows.Documents.Table>, pero <xref:System.Windows.Controls.Grid> es más ligero y adecuado para las tareas de diseño simples.  
  
 En el siguiente código XAML se muestra el diseño básico. Este código XAML define la estructura global del control especificando el número de columnas y filas en el elemento <xref:System.Windows.Controls.Grid>.  
  
 En MyControl1.xaml, reemplace el código XAML existente por el siguiente código XAML.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#101)]  
[!code-xaml[WindowsFormsHostingWpfControl#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#102)]  
  
#### <a name="adding-textblock-and-textbox-elements-to-the-grid"></a>Agregar elementos TextBlock y TextBox a la cuadrícula  
 Para colocar un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elemento en la cuadrícula, establezca los atributos <xref:System.Windows.Controls.Grid.RowProperty> y <xref:System.Windows.Controls.Grid.ColumnProperty> del elemento en el número de fila y columna adecuado. Recuerde que la numeración de filas y columnas está basada en ceros. Puede tener un elemento que abarque varias columnas estableciendo su <xref:System.Windows.Controls.Grid.ColumnSpanProperty> atributo. Para obtener más información sobre los elementos de <xref:System.Windows.Controls.Grid>, vea [crear un elemento Grid](../controls/how-to-create-a-grid-element.md).  
  
 En el siguiente código XAML se muestran los elementos <xref:System.Windows.Controls.TextBox> y <xref:System.Windows.Controls.TextBlock> del control compuesto con sus atributos <xref:System.Windows.Controls.Grid.RowProperty> y <xref:System.Windows.Controls.Grid.ColumnProperty>, que se establecen para colocar los elementos correctamente en la cuadrícula.  
  
 En MyControl1. XAML, agregue el siguiente código XAML dentro del elemento <xref:System.Windows.Controls.Grid>.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#103)]  
  
#### <a name="styling-the-ui-elements"></a>Aplicar estilos a los elementos de interfaz de usuario  
 Muchos de los elementos del formulario de entrada de datos tienen un aspecto similar, lo que significa que tienen valores idénticos para varias de sus propiedades. En lugar de establecer los atributos de cada elemento por separado, el código XAML anterior utiliza <xref:System.Windows.Style> elementos para definir los valores de propiedad estándar para las clases de elementos. Este enfoque reduce la complejidad del control y le permite cambiar la apariencia de varios elementos mediante un solo atributo de estilo.  
  
 Los elementos <xref:System.Windows.Style> se incluyen en la propiedad <xref:System.Windows.FrameworkElement.Resources%2A> del elemento <xref:System.Windows.Controls.Grid>, de modo que todos los elementos del control puedan utilizarlos. Si un estilo se denomina, se aplica a un elemento agregando un conjunto de elementos <xref:System.Windows.Style> al nombre del estilo. Los estilos que no tienen nombre se convierten en el estilo predeterminado del elemento. Para obtener más información sobre los estilos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vea [aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md).  
  
 En el siguiente código XAML se muestran los elementos <xref:System.Windows.Style> del control compuesto. Para ver cómo se aplican los estilos a los elementos, vea el código XAML anterior. Por ejemplo, el último elemento <xref:System.Windows.Controls.TextBlock> tiene el estilo `inlineText` y el último elemento <xref:System.Windows.Controls.TextBox> usa el estilo predeterminado.  
  
 En MyControl1. XAML, agregue el código XAML siguiente justo después del elemento de inicio <xref:System.Windows.Controls.Grid>.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#104)]  
  
#### <a name="adding-the-ok-and-cancel-buttons"></a>Agregar los botones Aceptar y Cancelar  
 Los elementos finales del control compuesto son los elementos **OK** y **Cancel**<xref:System.Windows.Controls.Button>, que ocupan las dos primeras columnas de la última fila de la <xref:System.Windows.Controls.Grid>. Estos elementos usan un controlador de eventos común, `ButtonClicked`y el estilo de <xref:System.Windows.Controls.Button> predeterminado definido en el código XAML anterior.  
  
 En MyControl1. XAML, agregue el siguiente código XAML después del último elemento <xref:System.Windows.Controls.TextBox>. La parte [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] del control compuesto ahora está completa.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#105](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#105)]  
  
### <a name="implementing-the-code-behind-file"></a>Implementar el archivo de código subyacente  
 El archivo de código subyacente, MyControl1.xaml.cs, implementa tres tareas esenciales:
  
1. Controla el evento que se produce cuando el usuario hace clic en uno de los botones.  
  
2. Recupera los datos de la <xref:System.Windows.Controls.TextBox> elementos y los empaqueta en un objeto de argumento de evento personalizado.  
  
3. Genera el evento de `OnButtonClick` personalizado, que notifica al host que el usuario ha terminado y devuelve los datos al host.  
  
 El control también expone una serie de propiedades de color y fuente con las que puede cambiar la apariencia. A diferencia de la clase <xref:System.Windows.Forms.Integration.WindowsFormsHost>, que se usa para hospedar un control Windows Forms, la clase <xref:System.Windows.Forms.Integration.ElementHost> solo expone la propiedad <xref:System.Windows.Controls.Panel.Background%2A> del control. Para mantener la similitud entre este ejemplo de código y el ejemplo que se describe en [Tutorial: hospedar un control compuesto de Windows Forms en WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md), el control expone las propiedades restantes directamente.  
  
#### <a name="the-basic-structure-of-the-code-behind-file"></a>Estructura básica del archivo de código subyacente  
 El archivo de código subyacente está compuesto de un solo espacio de nombres, `MyControls`, que contendrá dos clases, `MyControl1` y `MyControlEventArgs`.  
  
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
  
 La primera clase, `MyControl1`, es una clase parcial que contiene el código que implementa la funcionalidad del [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] definido en MyControl1. Xaml. Cuando se analiza MyControl1. XAML, el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] se convierte en la misma clase parcial y las dos clases parciales se combinan para formar el control compilado. Por este motivo, el nombre de clase del archivo de código subyacente debe coincidir con el nombre de clase asignado a MyControl1.xaml y debe heredar del elemento raíz del control. La segunda clase, `MyControlEventArgs`, es una clase de argumentos de evento que se utiliza para devolver los datos al host.  
  
 Abra MyControl1.xaml.cs. Cambie la declaración de clase existente para que tenga el siguiente nombre y herede de <xref:System.Windows.Controls.Grid>.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#21](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#21)]  
  
#### <a name="initializing-the-control"></a>Inicializar el control  
 En el código siguiente se implementan varias tareas básicas:  
  
- Declara un evento privado, `OnButtonClick`y su delegado asociado, `MyControlEventHandler`.  
  
- Crea distintas variables globales privadas que almacenan los datos del usuario. Estos datos se exponen a través de las propiedades correspondientes.  
  
- Implementa un controlador, `Init`, para el evento de <xref:System.Windows.FrameworkElement.Loaded> del control. Este controlador inicializa las variables globales al asignarles los valores definidos en MyControl1.xaml. Para ello, utiliza el <xref:System.Windows.FrameworkElement.Name%2A> asignado a un elemento de <xref:System.Windows.Controls.TextBlock> típico, `nameLabel`, para tener acceso a la configuración de la propiedad de ese elemento.  
  
 Elimine el constructor existente y agregue el código siguiente a la clase `MyControl1`.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#11)]  
  
#### <a name="handling-the-buttons-click-events"></a>Administrar los eventos de clic de los botones  
 El usuario indica que la tarea de entrada de datos ha finalizado haciendo clic en el botón **Aceptar** o en el botón **Cancelar** . Ambos botones usan el mismo <xref:System.Windows.Controls.Primitives.ButtonBase.Click> controlador de eventos, `ButtonClicked`. Ambos botones tienen un nombre, `btnOK` o `btnCancel`, que permite al controlador determinar en qué botón se hizo clic examinando el valor del argumento `sender`. El controlador hace lo siguiente:  
  
- Crea un objeto `MyControlEventArgs` que contiene los datos de los elementos <xref:System.Windows.Controls.TextBox>.  
  
- Si el usuario hizo clic en el botón **Cancelar** , establece la propiedad `IsOK` del objeto `MyControlEventArgs` en `false`.  
  
- Genera el evento `OnButtonClick` para indicar al host que el usuario ha terminado y devuelve los datos recopilados.  
  
 Agregue el código siguiente a la clase `MyControl1`, después del método `Init`.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#12)]  
  
#### <a name="creating-properties"></a>Crear propiedades  
 El resto de la clase simplemente expone propiedades que corresponden a las variables globales que se han descrito anteriormente. Cuando se cambia una propiedad, el descriptor de acceso set modifica el aspecto del control cambiando las propiedades de elemento correspondientes y actualizando las variables globales subyacentes.  
  
 Agregue el código siguiente a la clase `MyControl1`.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#13)]  
  
#### <a name="sending-the-data-back-to-the-host"></a>Devolver los datos al host  
 El componente final del archivo es la clase `MyControlEventArgs`, que se usa para enviar los datos recopilados de nuevo al host.  
  
 Agregue el código siguiente al espacio de nombres `MyControls`. La implementación es sencilla, por lo que no se tratará más adelante.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#14)]  
  
 Compile la solución. La compilación generará un archivo DLL denominado MyControls.dll.  
  
<a name="winforms_host_section"></a>   
## <a name="implementing-the-windows-forms-host-application"></a>Implementar la aplicación host de Windows Forms  
 La aplicación host de Windows Forms usa un objeto <xref:System.Windows.Forms.Integration.ElementHost> para hospedar el control compuesto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. La aplicación controla el evento `OnButtonClick` para recibir los datos del control compuesto. La aplicación también tiene un conjunto de botones de opción que se pueden usar para modificar la apariencia del control. En la siguiente ilustración se muestra la aplicación.  

La siguiente imagen muestra un control compuesto de WPF hospedado en una aplicación Windows Forms "  

 ![Scteenshot que muestra un control Avalon de hospedaje de Windows Forms.](./media/walkthrough-hosting-a-wpf-composite-control-in-windows-forms/windows-form-hosting-avalon-control.png)  
  
### <a name="creating-the-project"></a>Crear el proyecto  
 Para iniciar el proyecto:  
  
1. Inicie Visual Studio y abra el cuadro de diálogo **nuevo proyecto** .  
  
2. En Visual C# y en la categoría de Windows, seleccione la plantilla de **aplicación Windows Forms** .  
  
3. Asigne al nuevo proyecto el nombre de `WFHost`.  
  
4. Para la ubicación, especifique la misma carpeta de nivel superior que contiene el proyecto MyControls.  
  
5. Haga clic en **Aceptar** para crear el proyecto.  
  
 También debe agregar referencias al archivo DLL que contiene `MyControl1` y otros ensamblados.  
  
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
  
3. En la esquina superior derecha del formulario, agregue un control <xref:System.Windows.Forms.Panel?displayProperty=nameWithType> para que contenga el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control compuesto.  
  
4. Agregue los siguientes controles de <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType> al formulario.  
  
    |Name|Text|  
    |----------|----------|  
    |groupBox1|Color de fondo|  
    |groupBox2|Color de primer plano|  
    |groupBox3|Tamaño de fuente|  
    |groupBox4|Familia de fuentes|  
    |groupBox5|Estilo de fuente|  
    |groupBox6|Espesor de fuente|  
    |groupBox7|Datos del control|  
  
5. Agregue los siguientes controles de <xref:System.Windows.Forms.RadioButton?displayProperty=nameWithType> a los controles de <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType>.  
  
    |GroupBox|Name|Text|  
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
  
6. Agregue los siguientes controles de <xref:System.Windows.Forms.Label?displayProperty=nameWithType> al último <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType>. Estos controles muestran los datos devueltos por el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control compuesto.  
  
    |GroupBox|Name|Text|  
    |--------------|----------|----------|  
    |groupBox7|lblName|Nombre:|  
    |groupBox7|lblAddress|Dirección postal:|  
    |groupBox7|lblCity|City:|  
    |groupBox7|lblState|Estado:|  
    |groupBox7|lblZip|Código postal:|  
  
### <a name="initializing-the-form"></a>Inicializar el formulario  
 Normalmente, se implementa el código de hospedaje en el controlador de eventos <xref:System.Windows.Forms.Form.Load> del formulario. En el código siguiente se muestra el controlador de eventos <xref:System.Windows.Forms.Form.Load>, un controlador para el evento <xref:System.Windows.FrameworkElement.Loaded> del control compuesto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y declaraciones para varias variables globales que se usan más adelante.  
  
 En el Diseñador de Windows Forms, haga doble clic en el formulario para crear un controlador de eventos de <xref:System.Windows.Forms.Form.Load>. En la parte superior de Form1.cs, agregue las siguientes instrucciones de `using`.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#10)]  
  
 Reemplace el contenido de la clase de `Form1` existente por el código siguiente.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#2)]  
  
 El método `Form1_Load` del código anterior muestra el procedimiento general para hospedar un control [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
1. Cree un nuevo objeto de <xref:System.Windows.Forms.Integration.ElementHost>.  
  
2. Establezca la propiedad <xref:System.Windows.Forms.Control.Dock%2A> del control en <xref:System.Windows.Forms.DockStyle.Fill?displayProperty=nameWithType>.  
  
3. Agregue el control <xref:System.Windows.Forms.Integration.ElementHost> a la colección <xref:System.Windows.Forms.Control.Controls%2A> del control <xref:System.Windows.Forms.Panel>.  
  
4. Cree una instancia del control [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
5. Hospede el control compuesto en el formulario asignando el control a la propiedad <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> del control <xref:System.Windows.Forms.Integration.ElementHost>.  
  
 Las dos líneas restantes del método `Form1_Load` adjuntan controladores a dos eventos de control:  
  
- `OnButtonClick` es un evento personalizado que el control compuesto desencadena cuando el usuario hace clic en el botón **Aceptar** o **Cancelar** . El evento se controla para obtener la respuesta del usuario y recopilar los datos que este haya especificado.  
  
- <xref:System.Windows.FrameworkElement.Loaded> es un evento estándar generado por un control [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] cuando se carga por completo. El evento se usa aquí porque el ejemplo necesita inicializar distintas variables globales usando las propiedades del control. En el momento del evento de <xref:System.Windows.Forms.Form.Load> del formulario, el control no se carga completamente y esos valores todavía se establecen en `null`. Debe esperar hasta que se produzca el evento <xref:System.Windows.FrameworkElement.Loaded> del control antes de poder tener acceso a esas propiedades.  
  
 El controlador de eventos <xref:System.Windows.FrameworkElement.Loaded> se muestra en el código anterior. El controlador de `OnButtonClick` se describe en la sección siguiente.  
  
### <a name="handling-onbuttonclick"></a>Administrar OnButtonClick  
 El evento `OnButtonClick` se produce cuando el usuario hace clic en el botón **Aceptar** o **Cancelar** .  
  
 El controlador de eventos comprueba el campo `IsOK` del argumento del evento para determinar en qué botón se hizo clic. Las variables de *datos* `lbl`corresponden a los controles de <xref:System.Windows.Forms.Label> que se han explicado anteriormente. Si el usuario hace clic en el botón **Aceptar** , los datos de los controles <xref:System.Windows.Controls.TextBox> del control se asignan al control <xref:System.Windows.Forms.Label> correspondiente. Si el usuario hace clic en **Cancelar**, los valores de <xref:System.Windows.Forms.Label.Text%2A> se establecen en las cadenas predeterminadas.  
  
 Agregue el siguiente código de controlador de eventos de clic de botón a la clase `Form1`.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#3)]  
  
 Compile y ejecute la aplicación. Agregue texto en el control compuesto de WPF y, a continuación, haga clic en **Aceptar**. El texto aparece en las etiquetas. En este momento, no se ha agregado código para controlar los botones de radio.  
  
### <a name="modifying-the-appearance-of-the-control"></a>Modificar la apariencia del control  
 Los controles <xref:System.Windows.Forms.RadioButton> del formulario permitirán al usuario cambiar los colores de primer plano y de fondo del control compuesto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], así como varias propiedades de fuente. El objeto <xref:System.Windows.Forms.Integration.ElementHost> expone el color de fondo. Las propiedades restantes se exponen como propiedades personalizadas del control.  
  
 Haga doble clic en cada control de <xref:System.Windows.Forms.RadioButton> en el formulario para crear <xref:System.Windows.Forms.RadioButton.CheckedChanged> controladores de eventos. Reemplace los controladores de eventos <xref:System.Windows.Forms.RadioButton.CheckedChanged> por el código siguiente.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#4)]  
  
 Compile y ejecute la aplicación. Haga clic en los diferentes botones de radio para ver el efecto en el control compuesto de WPF.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Diseño de XAML en Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Tutorial: Hospedar un control compuesto 3D de WPF en Windows Forms](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md)
