---
title: Información general sobre cuadros de diálogo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- modeless dialog boxes [WPF]
- dialog boxes [WPF]
- message boxes [WPF]
- modal dialog boxes [WPF]
ms.assetid: 0d23d544-a393-4a02-a3aa-d8cd5d3d6511
ms.openlocfilehash: c98d6a45d151d4b683a21e48eaeb5f4a19eaadb1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187451"
---
# <a name="dialog-boxes-overview"></a>Resumen de cuadros de diálogo
Las aplicaciones independientes suelen tener una ventana principal que muestra los datos principales sobre los [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] que opera la aplicación y expone la funcionalidad para procesar esos datos a través de mecanismos como barras de menú, barras de herramientas y barras de estado. Una aplicación no trivial también puede mostrar ventanas adicionales para realizar lo siguiente:  
  
- Mostrar información específica a los usuarios.  
  
- Recopilar información de los usuarios.  
  
- Mostrar y recopilar información.  
  
 Estos tipos de ventanas se conocen como *cuadros*de diálogo y hay dos tipos: modal y no modal.  
  
 Una función muestra un cuadro de diálogo *modal* cuando la función necesita datos adicionales de un usuario para continuar. Como la función depende del cuadro de diálogo modal para recopilar datos, el cuadro de diálogo modal también impide que un usuario active otras ventanas de la aplicación mientras permanece abierto. En la mayoría de los casos, un cuadro de diálogo modal permite al usuario señalar cuando ha terminado con el cuadro de diálogo modal pulsando un botón **Aceptar** o **Cancelar.** Al pulsar el botón **Aceptar** se indica que un usuario ha introducido datos y desea que la función continúe el procesamiento con esos datos. Al pulsar el botón **Cancelar** se indica que un usuario desea impedir que la función se ejecute por completo. Los ejemplos más comunes de cuadros de diálogo modales se muestran para abrir, guardar e imprimir datos.  
  
 Un cuadro de diálogo *no basado* en la no ción, por otro lado, no impide que un usuario active otras ventanas mientras está abierto. Por ejemplo, si un usuario quiere buscar las repeticiones de una palabra determinada en un documento, a menudo una ventana principal abrirá un cuadro de diálogo para solicitar al usuario la palabra que está buscando. En cambio, como buscar una palabra no impide que un usuario edite el documento, el cuadro de diálogo no necesita ser modal. Un cuadro de diálogo no quedado al menos proporciona un botón **Cerrar** para cerrar el cuadro de diálogo y puede proporcionar botones adicionales para ejecutar funciones específicas, como un botón **Buscar siguiente** para buscar la siguiente palabra que coincida con los criterios de búsqueda de una búsqueda de palabras.  
  
 Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF) permite crear varios tipos de cuadros de diálogo, incluidos cuadros de mensaje, cuadros de diálogo comunes y cuadros de diálogo personalizados. En este tema se describe cada uno y el ejemplo de cuadro de [diálogo](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox) proporciona ejemplos coincidentes.  

<a name="Message_Boxes"></a>
## <a name="message-boxes"></a>Cuadros de mensajes  
 Un cuadro de *mensaje* es un cuadro de diálogo que se puede utilizar para mostrar información textual y para permitir a los usuarios tomar decisiones con botones. En la siguiente figura se muestra un cuadro de mensaje que muestra información de texto, realiza una pregunta y proporciona tres botones al usuario para responderla.  
  
 ![Un cuadro de diálogo Procesador de Word que le preguntará si desea guardar los cambios en el documento antes de que se cierre la aplicación.](./media/dialog-boxes-overview/word-processor-dialog.png)  
  
 Para crear un cuadro de <xref:System.Windows.MessageBox> mensaje, utilice la clase. <xref:System.Windows.MessageBox>le permite configurar el texto, el título, el icono y los botones del cuadro de mensaje, utilizando código como el siguiente.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxconfigurecodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxconfigurecodebehind)]  
  
 Para mostrar un cuadro de `static` <xref:System.Windows.MessageBox.Show%2A> mensaje, llame al método, como se muestra en el código siguiente.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowcodebehind)]  
  
 Cuando el código que muestra un cuadro de mensaje necesita detectar y procesar la decisión del usuario (qué botón se ha presionado), el código puede inspeccionar el resultado del cuadro de mensaje, como se muestra en el código siguiente.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowandresultcodebehind1)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowandresultcodebehind1)]  
  
 Para obtener más información sobre <xref:System.Windows.MessageBox>el uso de cuadros de mensaje, vea , Ejemplo de cuadro de [mensajes](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/MessageBox)y [Ejemplo](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox)de cuadro de diálogo .  
  
 Aunque <xref:System.Windows.MessageBox> puede ofrecer una experiencia de usuario <xref:System.Windows.MessageBox> de cuadro de diálogo simple, la ventaja de usar es que es el único tipo de ventana que pueden mostrar las aplicaciones que se ejecutan dentro de un entorno limitado de seguridad de confianza parcial (consulte [Seguridad](../security-wpf.md)), como las aplicaciones de explorador XAML (XBAP).  
  
 La mayoría de los cuadros de diálogo muestran y recopilan datos más complejos que el resultado de un cuadro de mensaje, incluidos texto, selección (casillas), selección mutuamente exclusiva (botón de selección) y selección de listas (cuadros de lista, cuadros combinados, cuadros de lista desplegable). Para estos, Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF) proporciona varios cuadros de diálogo comunes y le permite crear sus propios cuadros de diálogo, aunque el uso de cualquiera de ellos se limita a las aplicaciones que se ejecutan con plena confianza.  
  
<a name="Common_Dialogs"></a>
## <a name="common-dialog-boxes"></a>Cuadros de diálogo comunes  
 Windows implementa una variedad de cuadros de diálogo reutilizables que son comunes a todas las aplicaciones, incluidos los cuadros de diálogo para abrir archivos, guardar archivos e imprimir. Como estos cuadros de diálogo se implementan mediante el sistema operativo, pueden compartirse entre todas las aplicaciones que se ejecutan en el sistema operativo, que ayuda a la coherencia de la experiencia de usuario; cuando los usuarios están familiarizados con el uso de un cuadro de diálogo proporcionado por el sistema operativo en una aplicación, no necesitan obtener información sobre cómo usar ese cuadro de diálogo en otras aplicaciones. Dado que estos cuadros de diálogo están disponibles para todas las aplicaciones y porque ayudan a proporcionar una experiencia de usuario coherente, se conocen como cuadros de *diálogo comunes.*  
  
 Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF) encapsula el archivo abierto, guardar archivo e imprimir cuadros de diálogo comunes y los expone como clases administradas para que los use en aplicaciones independientes. En este tema se proporciona una breve introducción de cada uno.  
  
<a name="Open_File_Dialog"></a>
### <a name="open-file-dialog"></a>Cuadro de diálogo Abrir archivo  
 El cuadro de diálogo Abrir archivo, que se muestra en la siguiente figura, se usa por la función de apertura de archivos para recuperar el nombre de un archivo que se va a abrir.  
  
 ![Un cuadro de diálogo Abrir que muestra la ubicación para recuperar el archivo.](./media/dialog-boxes-overview/open-file-dialog-box.png)  
  
 El cuadro de diálogo de archivo <xref:Microsoft.Win32.OpenFileDialog> abierto común se <xref:Microsoft.Win32> implementa como la clase y se encuentra en el espacio de nombres. En el siguiente código se muestra cómo crear, configurar y mostrar uno, y cómo procesar el resultado.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#openfiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#openfiledialogboxcodebehind)]  
  
 Para obtener más información sobre el <xref:Microsoft.Win32.OpenFileDialog?displayProperty=nameWithType>cuadro de diálogo Abrir archivo, consulte .  
  
> [!NOTE]
> <xref:Microsoft.Win32.OpenFileDialog>se puede utilizar para recuperar de forma segura los nombres de archivo mediante aplicaciones que se ejecutan con confianza parcial (consulte [Seguridad](../security-wpf.md)).  
  
<a name="Save_File_Dialog"></a>
### <a name="save-file-dialog-box"></a>Guardar archivo (cuadro de diálogo)  
 El cuadro de diálogo Guardar archivo, que se muestra en la siguiente figura, se usa por la función de guardado de archivos para recuperar el nombre de un archivo que se va a guardar.  
  
 ![Cuadro de diálogo Guardar como que muestra la ubicación para guardar el archivo.](./media/dialog-boxes-overview/save-file-dialog-box.png)  
  
 El cuadro de diálogo de archivo <xref:Microsoft.Win32.SaveFileDialog> de guardado común <xref:Microsoft.Win32> se implementa como la clase y se encuentra en el espacio de nombres. En el siguiente código se muestra cómo crear, configurar y mostrar uno, y cómo procesar el resultado.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#savefiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#savefiledialogboxcodebehind)]  
  
 Para obtener más información sobre el <xref:Microsoft.Win32.SaveFileDialog?displayProperty=nameWithType>cuadro de diálogo Guardar archivo, consulte .  
  
<a name="Print_Dialog"></a>
### <a name="print-dialog-box"></a>Cuadro de diálogo Imprimir

El cuadro de diálogo Imprimir, que se muestra en la siguiente figura, se usa por la función de impresión para elegir y configurar la impresora con la que el usuario quiere imprimir los datos.  
  
![Captura de pantalla que muestra un cuadro de diálogo Imprimir.](./media/dialog-boxes-overview/print-data-dialog-box.png)  
  
El cuadro de diálogo de <xref:System.Windows.Controls.PrintDialog> impresión común se <xref:System.Windows.Controls> implementa como la clase y se encuentra en el espacio de nombres. En el siguiente código se muestra cómo crear, configurar y mostrar uno.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#printdialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#printdialogboxcodebehind)]  
  
 Para obtener más información sobre <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType>el cuadro de diálogo de impresión, consulte . Para obtener información detallada sobre la impresión en WPFWPF, vea [Información general sobre la impresión](../advanced/printing-overview.md).  
  
<a name="Custom_Dialog_Boxes"></a>
## <a name="custom-dialog-boxes"></a>Cuadros de diálogo personalizados

Aunque los cuadros de diálogo comunes son útiles, y deben usarse cuando sea posible, no admiten los requisitos de los cuadros de diálogo específicos de dominio. En estos casos, necesita crear sus propios cuadros de diálogo. Como veremos, un cuadro de diálogo es una ventana con comportamientos especiales. <xref:System.Windows.Window>implementa esos comportamientos y, en <xref:System.Windows.Window> consecuencia, se usa para crear cuadros de diálogo modales y no modales personalizados.  
  
<a name="Creating_a_Modal_Custom_Dialog_Box"></a>
### <a name="creating-a-modal-custom-dialog-box"></a>Creación de un cuadro de diálogo personalizado modal

En este tema <xref:System.Windows.Window> se muestra cómo utilizar cómo crear `Margins` una implementación de cuadro de diálogo modal típica, utilizando el cuadro de diálogo como ejemplo (vea Ejemplo de cuadro de [diálogo](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox)). El `Margins` cuadro de diálogo se muestra en la figura siguiente.  
  
 ![Un cuadro de diálogo Márgenes con campos para definir el margen izquierdo, el margen superior, el margen derecho y el margen inferior.](./media/dialog-boxes-overview/margin-size-dialog-box.png)  
  
#### <a name="configuring-a-modal-dialog-box"></a>Configuración de un cuadro de diálogo modal

La interfaz de usuario de un cuadro de diálogo típico incluye lo siguiente:  
  
- Los distintos controles que se necesitan para recopilar los datos deseados.  
  
- Un botón **Aceptar** en el que los usuarios hacen clic para cerrar el cuadro de diálogo, volver a la función y continuar el procesamiento.  
  
- Un botón **Cancelar** en el que los usuarios hacen clic para cerrar el cuadro de diálogo y detener el procesamiento posterior de la función.  
  
- Un botón **Cerrar** en la barra de título.  
  
- Un icono.  
  
- **Botones Minimizar**, **Maximizar**y **Restaurar.**  
  
- Un menú **Sistema** para minimizar, maximizar, restaurar y cerrar el cuadro de diálogo.  
  
- Una posición por encima y en el centro de la ventana que abrió el cuadro de diálogo.  
  
- La capacidad de cambiar el tamaño siempre que sea posible para evitar que el cuadro de diálogo sea demasiado pequeño y para proporcionar al usuario un tamaño predeterminado útil. Esto requiere que establezca las dimensiones predeterminadas y mínimas.  
  
- La tecla ESC como método abreviado de teclado que hace que se presione el botón **Cancelar.** Para ello, establezca <xref:System.Windows.Controls.Button.IsCancel%2A> la propiedad del `true`botón **Cancelar** en .  
  
- La tecla ENTER (o RETURN) como método abreviado de teclado que hace que se presione el botón **Aceptar.** Para ello, establezca <xref:System.Windows.Controls.Button.IsDefault%2A> la propiedad `true`del botón **Aceptar** .  
  
El siguiente código muestra esta configuración.  
  
[!code-xaml[MarginsDialogBox XAML file](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml?range=1-16,106-112)]  

[!code-csharp[MarginsDialogBox C# code-behind](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-12,67-68)]
[!code-vb[MarginsDialogBox VB code-behind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-11,61-62)]  
  
La experiencia de usuario de un cuadro de diálogo también se extiende a la barra de menús de la ventana que abre el cuadro de diálogo. Cuando un elemento de menú ejecuta una función que requiere interacción del usuario mediante un cuadro de diálogo antes de que la función pueda continuar, el elemento de menú de la función tendrá puntos suspensivos en su encabezado, como se muestra aquí.  
  
[!code-xaml[Menu bar of MainWindow.Xaml file](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#L26-L27)]  
  
Cuando un elemento de menú ejecuta una función que muestra un cuadro de diálogo que no necesita interacción del usuario, como un cuadro de diálogo Acerca de, no se necesitan los puntos suspensivos.  
  
#### <a name="opening-a-modal-dialog-box"></a>Abrir un cuadro de diálogo modal

Un cuadro de diálogo se muestra normalmente como el resultado de un usuario que selecciona un elemento de menú para realizar una función específica de dominio, como establecer los márgenes de un documento en un procesador de textos. Mostrar una ventana como un cuadro de diálogo es similar a mostrar una ventana normal, aunque necesita una configuración específica de cuadro de diálogo adicional. El proceso completo de crear instancias, configurar y abrir un cuadro de diálogo se muestra en el código siguiente.  
  
[!code-csharp[Opening a modal dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-11,78-88,193-195)]
[!code-vb[Opening a modal dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,58-67,130-132)]  

Aquí, el código pasa la información predeterminada (los márgenes actuales) al cuadro de diálogo. También establece <xref:System.Windows.Window.Owner%2A?displayProperty=nameWithType> la propiedad con una referencia a la ventana que muestra el cuadro de diálogo. En general, siempre debe establecer el propietario de un cuadro de diálogo para proporcionar comportamientos relacionados con el estado de la ventana que son comunes a todos los cuadros de diálogo (consulte [WPF Windows Overview](wpf-windows-overview.md) para obtener más información).

> [!NOTE]
> Debe proporcionar un propietario para admitir la automatización de la interfaz de usuario (UI) para los cuadros de diálogo (consulte Información general sobre [automatización](../../ui-automation/ui-automation-overview.md)de la interfaz de usuario ).

Después de configurar el cuadro de diálogo, <xref:System.Windows.Window.ShowDialog%2A> se muestra de forma modal llamando al método.  
  
#### <a name="validating-user-provided-data"></a>Validación de los datos proporcionados por el usuario

Cuando un cuadro de diálogo se abre y el usuario proporciona los datos necesarios, un cuadro de diálogo es responsable de garantizar que los datos proporcionados sean válidos por los motivos siguientes:  
  
- Desde una perspectiva de seguridad, se deben validar todas las entradas.  
  
- Desde una perspectiva específica de dominio, la validación de datos impide que los datos incorrectos se procesen por el código, que puede provocar excepciones potencialmente.  
  
- Desde una perspectiva de experiencia de usuario, un cuadro de diálogo puede ayudar a los usuarios a mostrarles qué datos de los que han especificado no son válidos.  
  
- Desde una perspectiva de rendimiento, la validación de datos en una aplicación de varios niveles puede reducir el número de recorridos de ida y vuelta entre los niveles de aplicación y cliente, especialmente cuando la aplicación está formada por servicios Web o bases de datos basadas en servidor.  

Para validar un control enlazado en WPFWPF, debe definir una regla de validación y asociarla con el enlace. Una regla de validación es <xref:System.Windows.Controls.ValidationRule>una clase personalizada que deriva de . En el ejemplo siguiente `MarginValidationRule`se muestra una regla de <xref:System.Double> validación, , que comprueba que un valor enlazado es a y está dentro de un intervalo especificado.  

[!code-csharp[Margin validation rules](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginValidationRule.cs)]
[!code-vb[Margin validation rules](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginValidationRule.vb)]  

En este código, la lógica de validación de <xref:System.Windows.Controls.ValidationRule.Validate%2A> una regla de validación se <xref:System.Windows.Controls.ValidationResult>implementa reemplazando el método, que valida los datos y devuelve un archivo .  

Para asociar la regla de validación con el control enlazado, use el siguiente marcado.  
  
[!code-xaml[Associating a validation rule with a control](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml?range=1-16,57-68,111-112)]

Una vez asociada la regla de validación, WPFWPF la aplicará automáticamente cuando se escriban datos en el control enlazado. Cuando un control contiene datos no válidos, WPFWPF mostrará un borde rojo alrededor del control no válido, como se muestra en la figura siguiente.  
  
![Un cuadro de diálogo Márgenes con un borde rojo alrededor del valor de margen izquierdo no válido.](./media/dialog-boxes-overview/invalid-left-margin-dialog.png)  

WPFWPF no restringe un usuario al control no válido hasta que han especificado datos válidos. Este es un buen comportamiento para un cuadro de diálogo; un usuario debe poder navegar libremente por los controles de un cuadro de diálogo sean los datos válidos o no. Sin embargo, esto significa que un usuario puede introducir datos no válidos y pulsar el botón **Aceptar.** Por este motivo, el código también debe validar todos **OK** los controles de <xref:System.Windows.Controls.Primitives.ButtonBase.Click> un cuadro de diálogo cuando se presiona el botón Aceptar controlando el evento.  
  
[!code-csharp[Validating all controls in a dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,26-29,33-68)]
[!code-vb[Validating all controls in a dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,27-29,33-62)]  

Este código enumera todos los objetos de dependencia de una <xref:System.Windows.Controls.Validation.GetHasError%2A>ventana y, si alguno no `IsValid` es `false`válido (como lo devuelve , el control no válido obtiene el foco, el método devuelve y la ventana se considera no válida.  
  
Una vez que un cuadro de diálogo es válido, puede cerrarse y devolverse de manera segura. Como parte del proceso de retorno, necesita devolver un resultado a la función de llamada.  
  
#### <a name="setting-the-modal-dialog-result"></a>Configuración del resultado del cuadro de diálogo modal

Abrir un cuadro <xref:System.Windows.Window.ShowDialog%2A> de diálogo mediante es fundamentalmente como llamar <xref:System.Windows.Window.ShowDialog%2A> a un <xref:System.Windows.Window.ShowDialog%2A> método: el código que abrió el cuadro de diálogo mediante espera hasta que se devuelve. Cuando <xref:System.Windows.Window.ShowDialog%2A> se devuelve, el código que lo llamó debe decidir si continuar el procesamiento o detener el procesamiento, en función de si el usuario presiona el botón **Aceptar** o el botón **Cancelar.** Para facilitar esta decisión, el cuadro de diálogo <xref:System.Boolean> debe devolver la <xref:System.Windows.Window.ShowDialog%2A> elección del usuario como un valor que se devuelve desde el método.  

Cuando se hace clic <xref:System.Windows.Window.ShowDialog%2A> en `true`el botón **Aceptar,** debe devolver . Esto se logra estableciendo la <xref:System.Windows.Window.DialogResult%2A> propiedad del cuadro de diálogo cuando se hace clic en el botón **Aceptar.**  

[!code-csharp[Responding to the OK button](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,25-27,32-33,67-68)]
[!code-vb[Responding to the OK button](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,27,31-33,61-62)]  

Tenga en <xref:System.Windows.Window.DialogResult%2A> cuenta que al establecer la propiedad también se hace <xref:System.Windows.Window.Close%2A>que la ventana se cierre automáticamente, lo que alivia la necesidad de llamar explícitamente a .  
  
Cuando se hace clic <xref:System.Windows.Window.ShowDialog%2A> en `false`el botón <xref:System.Windows.Window.DialogResult%2A> **Cancelar,** debe devolver , que también requiere establecer la propiedad.  
  
[!code-csharp[Responding to the Cancel button](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,19-24,67-68)]
[!code-vb[Responding to the Cancel button](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,22-25,61-62)]  

Cuando se establece <xref:System.Windows.Controls.Button.IsCancel%2A> la propiedad `true` de un botón y el usuario presiona <xref:System.Windows.Window.DialogResult%2A> el botón **Cancelar** o la tecla ESC, se establece automáticamente en `false`. El marcado siguiente tiene el mismo efecto que el código <xref:System.Windows.Controls.Primitives.ButtonBase.Click> anterior, sin necesidad de controlar el evento.  
  
[!code-xaml[Markup instead of handling the Click event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#L109-L109)]  

Un cuadro de `false` diálogo vuelve automáticamente cuando un usuario presiona el botón **Cerrar** en la barra de título o elige el elemento de menú **Cerrar** del menú **Sistema.**  

#### <a name="processing-data-returned-from-a-modal-dialog-box"></a>Procesamiento de datos devueltos desde un cuadro de diálogo modal  

Cuando <xref:System.Windows.Window.DialogResult%2A> se establece mediante un cuadro de diálogo, la función que <xref:System.Windows.Window.DialogResult%2A> lo <xref:System.Windows.Window.ShowDialog%2A> abrió puede obtener el resultado del cuadro de diálogo inspeccionando la propiedad cuando se devuelve.  
  
[!code-csharp[Processing data returned from the modal dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,77-79,89-96,194-195)]
[!code-vb[Processing data returned from the modal dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,58,69-73,131-132)]

Si el resultado `true`del cuadro de diálogo es , la función lo utiliza como una indicación para recuperar y procesar los datos proporcionados por el usuario.  
  
> [!NOTE]
> Una <xref:System.Windows.Window.ShowDialog%2A> vez devuelto, no se puede volver a abrir un cuadro de diálogo. En su lugar, necesita crear una instancia nueva.

Si el resultado `false`del cuadro de diálogo es , la función debe finalizar el procesamiento correctamente.  
  
<a name="Creating_a_Modeless_Custom_Dialog_Box"></a>
### <a name="creating-a-modeless-custom-dialog-box"></a>Creación de un cuadro de diálogo personalizado no quede sin sistema

Un cuadro de diálogo no modal, como el cuadro de diálogo Buscar que se muestra en la figura siguiente, tiene el mismo aspecto fundamental que el cuadro de diálogo modal.  

![Captura de pantalla que muestra un cuadro de diálogo Buscar.](./media/dialog-boxes-overview/find-modeless-dialog-box.png)  

En cambio, el comportamiento es un poco diferente, como se describe en las secciones siguientes.  
  
#### <a name="opening-a-modeless-dialog-box"></a>Abrir un cuadro de diálogo no quede

Se abre un cuadro de diálogo <xref:System.Windows.Window.Show%2A> no quede mediante una llamada al método.  

[!code-xaml[XAML to define a modeless dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#L21-L22)]  

[!code-csharp[Opening a modeless dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,65-76,194-195)]
[!code-vb[Openng a modeless dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,18-23,131,132)]  

A <xref:System.Windows.Window.ShowDialog%2A> <xref:System.Windows.Window.Show%2A> diferencia de , devuelve inmediatamente. Por consiguiente, la ventana de llamada no puede indicar cuándo se cierra el cuadro de diálogo no modal y, por lo tanto, no sabe cuándo comprobar el resultado de un cuadro de diálogo u obtener los datos de este para un procesamiento posterior. En su lugar, el cuadro de diálogo necesita crear una manera alternativa de devolver los datos a la ventana de llamada para su procesamiento.  
  
#### <a name="processing-data-returned-from-a-modeless-dialog-box"></a>Procesamiento de datos devueltos desde un cuadro de diálogo no basado en un cuadro de diálogo no basado en el  

En este ejemplo, el `FindDialogBox` puede devolver uno o más resultados de búsqueda a la ventana principal, dependiendo del texto que se busca sin ninguna frecuencia específica. Al igual que un cuadro de diálogo modal, un cuadro de diálogo no modal puede devolver resultados mediante propiedades. En cambio, la ventana que tiene el cuadro de diálogo necesita saber cuándo comprobar esas propiedades. Una manera de habilitar esto es que el cuadro de diálogo implemente un evento que se genera cuando se detecta texto. `FindDialogBox`implementa el `TextFoundEvent` para este propósito, que primero requiere un delegado.  

[!code-csharp[The TextFoundEventHandler delegate](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/TextFoundEventHandler.cs)]
[!code-vb[The TextFoundEventHandler delegate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/TextFoundEventHandler.vb)]  

Con `TextFoundEventHandler` el `FindDialogBox` delegado, `TextFoundEvent`implementa el archivo .
  
[!code-csharp[The TextFound event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-17,125-126)]
[!code-vb[The TextFound event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-15,102-103)]

Por lo `Find` tanto, puede generar el evento cuando se encuentra un resultado de búsqueda.  
  
[!code-csharp[Raising the TextFound event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-9,50-52,91-94,124-127)]
[!code-vb[Raising the TextFound event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-9,15,60-64,102-103)]  

Después, la ventana propietaria necesita registrar y controlar este evento.

[!code-csharp[Registering and handling the event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,184-195)]
[!code-vb[Registering and handling the event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,126-132)]  

#### <a name="closing-a-modeless-dialog-box"></a>Cerrar un cuadro de diálogo no esquemador

Dado <xref:System.Windows.Window.DialogResult%2A> que no es necesario establecer, se puede cerrar un cuadro de diálogo no establecido mediante mecanismos de proporcionar del sistema, incluidos los siguientes:  
  
- Haga clic en el botón **Cerrar** de la barra de título.  
  
- Presionar ALT+F4.  
  
- Elija **Cerrar** en el menú **Sistema.**  
  
Como alternativa, el <xref:System.Windows.Window.Close%2A> código puede llamar cuando se hace clic en el botón **Cerrar.**  

[!code-csharp[Calling the Close method](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-9,119-126)]
[!code-vb[Calling the Close method](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-9,99-103)]  

## <a name="see-also"></a>Consulte también

- [Información general sobre el control Popup](../controls/popup-overview.md)
- [Ejemplo de cuadro de diálogo](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox)
