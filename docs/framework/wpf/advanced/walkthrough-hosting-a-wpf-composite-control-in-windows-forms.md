---
title: 'Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
ms.assetid: 0ac41286-4c1b-4b17-9196-d985cb844ce1
ms.openlocfilehash: 75e60a3a9b39c0dd63a24a1e71c4823e7cb0bd74
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052552"
---
# <a name="walkthrough-hosting-a-wpf-composite-control-in-windows-forms"></a>Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona un entorno rico para crear aplicaciones. Sin embargo, cuando tiene una inversión sustancial [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] código, puede ser más efectivo extender existentes [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] aplicación con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en lugar de a escribirlo desde cero. Un escenario común es cuando quiere insertar uno o más controles implementados con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dentro de la aplicación de Windows Forms. Para obtener más información acerca de cómo personalizar los controles de WPF, vea [personalización de controles](../controls/control-customization.md).  
  
 Este tutorial le guía a través de una aplicación que hospeda un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control compuesto para realizar la entrada de datos en una aplicación de Windows Forms. El control compuesto se empaqueta en un archivo DLL. Este procedimiento general se puede extender a aplicaciones y controles más complejos. En este tutorial está diseñado para ser casi idéntico en aspecto y funcionalidad al [Tutorial: Hospedaje de un Windows Forms Control compuesto de WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md). La principal diferencia es que se invierte el escenario de hospedaje.  
  
 Este tutorial está dividido en dos secciones. La primera sección describe brevemente la implementación de la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control compuesto. La segunda sección explica en detalle cómo hospedar un control compuesto en una aplicación Windows Forms, recibir eventos del control y tener acceso a algunas de las propiedades del control.  
  
 Las tareas ilustradas en este tutorial incluyen:  
  
- Implementar el control compuesto de WPF.  
  
- Implementar la aplicación host de Windows Forms.  
  
 Para obtener una lista de código completo de las tareas ilustradas en este tutorial, vea [hospedar un Control compuesto de WPF en Windows Forms Sample](https://go.microsoft.com/fwlink/?LinkID=159996).  
  
## <a name="prerequisites"></a>Requisitos previos  

Necesita Visual Studio para completar este tutorial.  
  
## <a name="implementing-the-wpf-composite-control"></a>Implementar el control compuesto de WPF  
 El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control compuesto utilizado en este ejemplo es un formulario de entrada de datos simple que toma el nombre y la dirección del usuario. Cuando el usuario hace clic en uno de los dos botones para indicar que la tarea ha finalizado, el control genera un evento personalizado para devolver esa información al host. En la ilustración siguiente se muestra la representación del control. 

 La siguiente imagen muestra un control compuesto de WPF: 

 ![Captura de pantalla que muestra un control simple de WPF.](./media/walkthrough-hosting-a-wpf-composite-control-in-windows-forms/windows-presentation-foundation-composite-control.png)  
  
### <a name="creating-the-project"></a>Crear el proyecto  
 Para iniciar el proyecto:  
  
1. Iniciar [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]y abra el **nuevo proyecto** cuadro de diálogo.  
  
2. En Visual C# y la categoría de Windows, seleccione el **biblioteca de controles de usuario de WPF** plantilla.  
  
3. Asigne al nuevo proyecto el nombre de `MyControls`.  
  
4. Para la ubicación, especifique una carpeta con el nombre de nivel superior, como `WindowsFormsHostingWpfControl`. Más tarde, colocará la aplicación host en esta carpeta.  
  
5. Haga clic en **Aceptar** para crear el proyecto. El proyecto predeterminado contiene un solo control denominado `UserControl1`.  
  
6. En el Explorador de soluciones, cambie el nombre `UserControl1` a `MyControl1`.  
  
 El proyecto debe tener referencias a los siguientes archivos DLL del sistema. Si alguno de estos archivos DLL no está incluido de forma predeterminada, agréguelos al proyecto.  
  
- PresentationCore  
  
- PresentationFramework  
  
- Sistema  
  
- WindowsBase  
  
### <a name="creating-the-user-interface"></a>Crear la interfaz de usuario  
 El [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] para el control compuesto se implementa con [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. El control compuesto [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] consta de cinco <xref:System.Windows.Controls.TextBox> elementos. Cada <xref:System.Windows.Controls.TextBox> tiene asociado un elemento <xref:System.Windows.Controls.TextBlock> elemento que actúa como una etiqueta. Hay dos <xref:System.Windows.Controls.Button> elementos en la parte inferior, **Aceptar** y **cancelar**. Cuando el usuario hace clic en cualquiera de los botones, el control genera un evento personalizado para devolver la información al host.  
  
#### <a name="basic-layout"></a>Diseño básico  
 Los distintos [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementos estén incluidos en un <xref:System.Windows.Controls.Grid> elemento. Puede usar <xref:System.Windows.Controls.Grid> para organizar el contenido de la composición de control prácticamente la misma manera utilizaría un `Table` elemento de HTML. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] También tiene un <xref:System.Windows.Documents.Table> elemento, pero <xref:System.Windows.Controls.Grid> es más ligero y adecuado para las tareas de diseño simple.  
  
 En el siguiente código XAML se muestra el diseño básico. Este XAML define la estructura general del control especificando el número de columnas y filas en el <xref:System.Windows.Controls.Grid> elemento.  
  
 En MyControl1.xaml, reemplace el código XAML existente por el siguiente código XAML.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#101)]  
[!code-xaml[WindowsFormsHostingWpfControl#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#102)]  
  
#### <a name="adding-textblock-and-textbox-elements-to-the-grid"></a>Agregar elementos TextBlock y TextBox a la cuadrícula  
 Coloca un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elemento en la cuadrícula estableciendo el elemento <xref:System.Windows.Controls.Grid.RowProperty> y <xref:System.Windows.Controls.Grid.ColumnProperty> atributos para el número apropiado de fila y columna. Recuerde que la numeración de filas y columnas está basada en ceros. Puede tener un elemento abarque varias columnas estableciendo su <xref:System.Windows.Controls.Grid.ColumnSpanProperty> atributo. Para obtener más información acerca de <xref:System.Windows.Controls.Grid> elementos, vea [crear un elemento Grid](../controls/how-to-create-a-grid-element.md).  
  
 El siguiente XAML muestra el control compuesto <xref:System.Windows.Controls.TextBox> y <xref:System.Windows.Controls.TextBlock> elementos con sus <xref:System.Windows.Controls.Grid.RowProperty> y <xref:System.Windows.Controls.Grid.ColumnProperty> atributos, que se establecen para colocar correctamente los elementos en la cuadrícula.  
  
 En MyControl1.xaml, agregue el siguiente XAML dentro de la <xref:System.Windows.Controls.Grid> elemento.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#103](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#103)]  
  
#### <a name="styling-the-ui-elements"></a>Aplicar estilos a los elementos de interfaz de usuario  
 Muchos de los elementos del formulario de entrada de datos tienen un aspecto similar, lo que significa que tienen valores idénticos para varias de sus propiedades. En lugar de establecer los atributos de cada elemento por separado, se usa el XAML anterior <xref:System.Windows.Style> elementos para definir valores de propiedad estándar para las clases de elementos. Este enfoque reduce la complejidad del control y le permite cambiar la apariencia de varios elementos mediante un solo atributo de estilo.  
  
 El <xref:System.Windows.Style> elementos estén incluidos en el <xref:System.Windows.Controls.Grid> del elemento <xref:System.Windows.FrameworkElement.Resources%2A> propiedad, por lo que se pueden usar en todos los elementos del control. Si es el nombre de un estilo, se aplica a un elemento mediante la adición de un <xref:System.Windows.Style> elemento establecido en el nombre del estilo. Los estilos que no tienen nombre se convierten en el estilo predeterminado del elemento. Para obtener más información acerca de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] estilos, consulte [aplicar estilos y plantillas](../controls/styling-and-templating.md).  
  
 El siguiente XAML muestra el <xref:System.Windows.Style> elementos para el control compuesto. Para ver cómo se aplican los estilos a los elementos, vea el código XAML anterior. Por ejemplo, la última <xref:System.Windows.Controls.TextBlock> elemento tiene el `inlineText` estilo y el último <xref:System.Windows.Controls.TextBox> elemento utiliza el estilo predeterminado.  
  
 En MyControl1.xaml, agregue el XAML siguiente justo después del <xref:System.Windows.Controls.Grid> elemento de inicio.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#104](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#104)]  
  
#### <a name="adding-the-ok-and-cancel-buttons"></a>Agregar los botones Aceptar y Cancelar  
 Los elementos finales del control compuesto son el **Aceptar** y **cancelar** <xref:System.Windows.Controls.Button> elementos, que ocupan las dos primeras columnas de la última fila de la <xref:System.Windows.Controls.Grid>. Estos elementos usan un controlador de eventos comunes, `ButtonClicked`y el valor predeterminado <xref:System.Windows.Controls.Button> estilo definido en el XAML anterior.  
  
 En MyControl1.xaml, agregue el siguiente XAML después del último <xref:System.Windows.Controls.TextBox> elemento. El [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] parte de un control compuesto ya está completa.  
  
 [!code-xaml[WindowsFormsHostingWpfControl#105](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml#105)]  
  
### <a name="implementing-the-code-behind-file"></a>Implementar el archivo de código subyacente  
 El archivo de código subyacente, MyControl1.xaml.cs, implementa tres tareas esenciales:
  
1. Controla el evento que se produce cuando el usuario hace clic en uno de los botones.  
  
2. Recupera los datos desde el <xref:System.Windows.Controls.TextBox> elementos y lo empaqueta en un objeto de argumento de evento personalizado.  
  
3. Genera personalizado `OnButtonClick` evento, que notifica al host que el usuario ha terminado y pasa los datos al host.  
  
 El control también expone una serie de propiedades de color y fuente con las que puede cambiar la apariencia. A diferencia de la <xref:System.Windows.Forms.Integration.WindowsFormsHost> (clase), que se utiliza para hospedar un control de Windows Forms, el <xref:System.Windows.Forms.Integration.ElementHost> clase expone el control <xref:System.Windows.Controls.Panel.Background%2A> solo para la propiedad. Para mantener la similitud entre este ejemplo de código y el ejemplo tratado en [Tutorial: Hospedar un Control compuesto de Windows Forms en WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md), el control expone las propiedades restantes directamente.  
  
#### <a name="the-basic-structure-of-the-code-behind-file"></a>Estructura básica del archivo de código subyacente  
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
  
 La primera clase, `MyControl1`, es una clase parcial que contiene el código que implementa la funcionalidad de la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] definida en MyControl1.xaml. Al analizar MyControl1.xaml, el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] se convierte en la misma clase parcial, y las dos clases parciales se combinan para formar el control compilado. Por este motivo, el nombre de clase del archivo de código subyacente debe coincidir con el nombre de clase asignado a MyControl1.xaml y debe heredar del elemento raíz del control. La segunda clase, `MyControlEventArgs`, es una clase de argumentos de evento que se usa para enviar los datos al host.  
  
 Abra MyControl1.xaml.cs. Cambie la declaración de clase existente por lo que tiene el siguiente nombre y hereda de <xref:System.Windows.Controls.Grid>.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#21](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#21)]  
  
#### <a name="initializing-the-control"></a>Inicializar el control  
 En el código siguiente se implementan varias tareas básicas:  
  
- Declara un evento privado, `OnButtonClick`y su delegado asociado, `MyControlEventHandler`.  
  
- Crea distintas variables globales privadas que almacenan los datos del usuario. Estos datos se exponen a través de las propiedades correspondientes.  
  
- Implementa un controlador, `Init`, para el control <xref:System.Windows.FrameworkElement.Loaded> eventos. Este controlador inicializa las variables globales al asignarles los valores definidos en MyControl1.xaml. Para ello, usa el <xref:System.Windows.FrameworkElement.Name%2A> asignado a una típica <xref:System.Windows.Controls.TextBlock> elemento, `nameLabel`para tener acceso a los valores de las propiedades de ese elemento.  
  
 Elimine el constructor existente y agregue el código siguiente a su `MyControl1` clase.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#11)]  
  
#### <a name="handling-the-buttons-click-events"></a>Administrar los eventos de clic de los botones  
 El usuario indica que la tarea de entrada de datos ha finalizado con un clic en el **Aceptar** botón o la **cancelar** botón. Ambos botones usan el mismo <xref:System.Windows.Controls.Primitives.ButtonBase.Click> controlador de eventos, `ButtonClicked`. Ambos botones tienen un nombre, `btnOK` o `btnCancel`, que permite al controlador determinar qué botón se hizo clic examinando el valor de la `sender` argumento. El controlador hace lo siguiente:  
  
- Crea un `MyControlEventArgs` objeto que contiene los datos de la <xref:System.Windows.Controls.TextBox> elementos.  
  
- Si el usuario hizo clic en el **cancelar** button, conjuntos de la `MyControlEventArgs` del objeto `IsOK` propiedad `false`.  
  
- Provoca el `OnButtonClick` evento para indicar al host que el usuario ha terminado y devuelve los datos recopilados.  
  
 Agregue el código siguiente a su `MyControl1` clase, después el `Init` método.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#12)]  
  
#### <a name="creating-properties"></a>Crear propiedades  
 El resto de la clase simplemente expone propiedades que corresponden a las variables globales que se han descrito anteriormente. Cuando se cambia una propiedad, el descriptor de acceso set modifica el aspecto del control cambiando las propiedades de elemento correspondientes y actualizando las variables globales subyacentes.  
  
 Agregue el código siguiente a su `MyControl1` clase.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#13)]  
  
#### <a name="sending-the-data-back-to-the-host"></a>Devolver los datos al host  
 El último componente en el archivo es el `MyControlEventArgs` (clase), que se usa para enviar los datos recopilados al host.  
  
 Agregue el código siguiente a su `MyControls` espacio de nombres. La implementación es sencilla, por lo que no se tratará más adelante.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/MyControls/Page1.xaml.cs#14)]  
  
 Compile la solución. La compilación generará un archivo DLL denominado MyControls.dll.  
  
<a name="winforms_host_section"></a>   
## <a name="implementing-the-windows-forms-host-application"></a>Implementar la aplicación host de Windows Forms  
 Los formularios de Windows hospedar la aplicación usa un <xref:System.Windows.Forms.Integration.ElementHost> objeto para hospedar el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control compuesto. La aplicación controla el `OnButtonClick` eventos para recibir los datos del control compuesto. La aplicación también tiene un conjunto de botones de opción que se pueden usar para modificar la apariencia del control. En la siguiente ilustración se muestra la aplicación.  

La siguiente imagen muestra un control compuesto de WPF hospedado en una aplicación de Windows Forms"  

 ![Scteenshot que muestra un control Avalon de hospedaje de formulario de Windows.](./media/walkthrough-hosting-a-wpf-composite-control-in-windows-forms/windows-form-hosting-avalon-control.png)  
  
### <a name="creating-the-project"></a>Crear el proyecto  
 Para iniciar el proyecto:  
  
1. Iniciar [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]y abra el **nuevo proyecto** cuadro de diálogo.  
  
2. En Visual C# y la categoría de Windows, seleccione el **aplicación de Windows Forms** plantilla.  
  
3. Asigne al nuevo proyecto el nombre de `WFHost`.  
  
4. Para la ubicación, especifique la misma carpeta de nivel superior que contiene el proyecto MyControls.  
  
5. Haga clic en **Aceptar** para crear el proyecto.  
  
 También deberá agregar referencias a la DLL que contiene `MyControl1` y a otros ensamblados.  
  
1. Haga clic en el nombre del proyecto en el Explorador de soluciones y seleccione **Agregar referencia**.  
  
2. Haga clic en el **examinar** pestaña y vaya a la carpeta que contiene MyControls.dll. En este tutorial, esta carpeta es MyControls\bin\Debug.  
  
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
  
3. En la esquina superior derecha del formulario, agregue un <xref:System.Windows.Forms.Panel?displayProperty=nameWithType> control para contener el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control compuesto.  
  
4. Agregue las siguientes <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType> controles al formulario.  
  
    |Name|Texto|  
    |----------|----------|  
    |groupBox1|Color de fondo|  
    |groupBox2|Color de primer plano|  
    |groupBox3|Tamaño de fuente|  
    |groupBox4|Familia de fuentes|  
    |groupBox5|Estilo de fuente|  
    |groupBox6|Espesor de fuente|  
    |groupBox7|Datos del control|  
  
5. Agregue el siguiente <xref:System.Windows.Forms.RadioButton?displayProperty=nameWithType> controles a la <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType> controles.  
  
    |GroupBox|Name|Texto|  
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
  
6. Agregue el siguiente <xref:System.Windows.Forms.Label?displayProperty=nameWithType> controla al último <xref:System.Windows.Forms.GroupBox?displayProperty=nameWithType>. Estos controles muestran los datos devueltos por la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control compuesto.  
  
    |GroupBox|Name|Texto|  
    |--------------|----------|----------|  
    |groupBox7|lblName|Nombre:|  
    |groupBox7|lblAddress|Dirección postal:|  
    |groupBox7|lblCity|Ciudad:|  
    |groupBox7|lblState|Estado:|  
    |groupBox7|lblZip|Código postal:|  
  
### <a name="initializing-the-form"></a>Inicializar el formulario  
 Se suele implementa el código de hospedaje en el formulario <xref:System.Windows.Forms.Form.Load> controlador de eventos. El siguiente código muestra la <xref:System.Windows.Forms.Form.Load> controlador de eventos, un controlador para el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] del control compuesto <xref:System.Windows.FrameworkElement.Loaded> eventos y declaraciones de distintas variables globales que se usan más adelante.  
  
 En el Diseñador de formularios de Windows, haga doble clic en el formulario para crear un <xref:System.Windows.Forms.Form.Load> controlador de eventos. En la parte superior del archivo Form1.cs, agregue las siguientes `using` instrucciones.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#10](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#10)]  
  
 Reemplace el contenido de la existente `Form1` con el código siguiente.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#2)]  
  
 El `Form1_Load` método en el código anterior muestra el procedimiento general para hospedar un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control:  
  
1. Cree un nuevo <xref:System.Windows.Forms.Integration.ElementHost> objeto.  
  
2. Establecer el control <xref:System.Windows.Forms.Control.Dock%2A> propiedad <xref:System.Windows.Forms.DockStyle.Fill?displayProperty=nameWithType>.  
  
3. Agregar el <xref:System.Windows.Forms.Integration.ElementHost> el control a la <xref:System.Windows.Forms.Panel> del control <xref:System.Windows.Forms.Control.Controls%2A> colección.  
  
4. Cree una instancia de la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control.  
  
5. Hospedar un control compuesto en el formulario asignando el control a la <xref:System.Windows.Forms.Integration.ElementHost> del control <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> propiedad.  
  
 Las dos líneas restantes en el `Form1_Load` método asociar controladores a dos eventos de control:  
  
- `OnButtonClick` es un evento personalizado que se activa el control compuesto cuando el usuario hace clic en el **Aceptar** o **cancelar** botón. El evento se controla para obtener la respuesta del usuario y recopilar los datos que este haya especificado.  
  
- <xref:System.Windows.FrameworkElement.Loaded> es un evento estándar generado por un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control al se ha cargado completamente. El evento se usa aquí porque el ejemplo necesita inicializar distintas variables globales usando las propiedades del control. En el momento de la forma <xref:System.Windows.Forms.Form.Load> eventos, el control no está totalmente cargado y esos valores todavía están establecidos en `null`. Deberá esperar hasta que el control <xref:System.Windows.FrameworkElement.Loaded> evento se produce antes de que se pueden acceder a esas propiedades.  
  
 El <xref:System.Windows.FrameworkElement.Loaded> controlador de eventos se muestra en el código anterior. El `OnButtonClick` controlador se describe en la sección siguiente.  
  
### <a name="handling-onbuttonclick"></a>Administrar OnButtonClick  
 El `OnButtonClick` evento tiene lugar cuando el usuario hace clic en el **Aceptar** o **cancelar** botón.  
  
 El controlador de eventos comprueba el argumento de evento `IsOK` campo para determinar qué botón se hizo clic. El `lbl` *datos* variables corresponden a la <xref:System.Windows.Forms.Label> controles descritos anteriormente. Si el usuario hace clic en el **Aceptar** botón, los datos desde el control <xref:System.Windows.Controls.TextBox> controles se asigna a la correspondiente <xref:System.Windows.Forms.Label> control. Si el usuario hace clic **cancelar**, el <xref:System.Windows.Forms.Label.Text%2A> valores se establecen en las cadenas predeterminadas.  
  
 Agregue el siguiente botón haga clic en el código de controlador de eventos para el `Form1` clase.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#3)]  
  
 Compile y ejecute la aplicación. Agregue texto en el control compuesto de WPF y, a continuación, haga clic en **Aceptar**. El texto aparece en las etiquetas. En este momento, no se ha agregado código para controlar los botones de radio.  
  
### <a name="modifying-the-appearance-of-the-control"></a>Modificar la apariencia del control  
 El <xref:System.Windows.Forms.RadioButton> controles del formulario permitirá al usuario cambiar la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] colores de primer plano y fondo del control compuesto, así como varias propiedades de fuente. El color de fondo se expone mediante el <xref:System.Windows.Forms.Integration.ElementHost> objeto. Las propiedades restantes se exponen como propiedades personalizadas del control.  
  
 Haga doble clic en cada uno de ellos <xref:System.Windows.Forms.RadioButton> control en el formulario para crear <xref:System.Windows.Forms.RadioButton.CheckedChanged> controladores de eventos. Reemplace el <xref:System.Windows.Forms.RadioButton.CheckedChanged> controladores de eventos con el código siguiente.  
  
 [!code-csharp[WindowsFormsHostingWpfControl#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsFormsHostingWpfControl/CSharp/WFHost/Form1.cs#4)]  
  
 Compile y ejecute la aplicación. Haga clic en los diferentes botones de radio para ver el efecto en el control compuesto de WPF.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Diseño de XAML en Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Tutorial: Hospedar un Control compuesto de Windows Forms en WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Tutorial: Hospedar un Control compuesto 3D de WPF en Windows Forms](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md)
