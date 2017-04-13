---
title: "Informaci&#243;n general sobre cuadros de di&#225;logo | Microsoft Docs"
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
  - "cuadros de diálogo no modales"
  - "cuadros de diálogo"
  - "cuadros de mensaje"
  - "cuadros de diálogo modales"
ms.assetid: 0d23d544-a393-4a02-a3aa-d8cd5d3d6511
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# Informaci&#243;n general sobre cuadros de di&#225;logo
Aplicaciones independientes tienen normalmente una ventana principal, que tanto muestra los datos principales en el que la aplicación funciona y expone la funcionalidad para procesar datos a través de [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] mecanismos, como barras de menús, barras de herramientas y barras de estado. Una aplicación no trivial también puede mostrar ventanas adicionales para hacer lo siguiente:  
  
-   Mostrar información específica a los usuarios.  
  
-   Recopilar información de los usuarios.  
  
-   Mostrar y recopilar información.  
  
 Estos tipos de ventanas se conocen como *cuadros de diálogo*, y hay dos tipos: modales y no modales.  
  
 Un *modal* cuadro de diálogo se muestra una función cuando la función necesita datos adicionales de un usuario para continuar. Porque depende de la función en el cuadro de diálogo modal para recopilar datos, el cuadro de diálogo modal también impide que un usuario active otras ventanas de la aplicación mientras permanece abierto. En la mayoría de los casos, un cuadro de diálogo modal permite a los usuarios señalar cuando haya terminado con el cuadro de diálogo modal presionando un **Aceptar** o **cancelar** botón. Al presionar el **Aceptar** botón indica que el usuario ha especificado datos y desea que la función para continuar el procesamiento de datos. Al presionar el **cancelar** botón indica que un usuario desea detener la ejecución de la función. Los ejemplos más comunes de cuadros de diálogo modales se muestran para abrir, guardar e imprimir datos.  
  
 Un *no modales* cuadro de diálogo, por otro lado, no impide que un usuario active otras ventanas mientras está abierto. Por ejemplo, si un usuario desea buscar apariciones de una palabra determinada en un documento, una ventana principal a menudo abrirá un cuadro de diálogo para pedir al usuario qué palabra está buscando. Dado que la búsqueda de una palabra no impide que un usuario edita el documento, sin embargo, no es necesario el cuadro de diálogo sea modal. Un cuadro de diálogo no modal proporciona al menos un **cerrar** botón para cerrar el cuadro de diálogo y puede proporcionar botones adicionales para ejecutar funciones específicas, como un **Buscar siguiente** para buscar la palabra siguiente que coincida con los criterios de búsqueda de una búsqueda de palabras.  
  
 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]le permite crear varios tipos de cuadros de diálogo, incluidos cuadros de mensaje, cuadros de diálogo comunes y cuadros de diálogo personalizados. Este tema describe cada uno y el [Dialog Box Sample](http://go.microsoft.com/fwlink/?LinkID=159984) proporciona ejemplos relacionados.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="Message_Boxes"></a>   
## <a name="message-boxes"></a>Cuadros de mensaje  
 Un *cuadro de mensaje* es un cuadro de diálogo que se puede utilizar para mostrar información textual y permitir que los usuarios tomen decisiones con botones. En la siguiente ilustración se muestra un cuadro de mensaje que muestra información de texto, plantea una pregunta y proporciona al usuario tres botones para responder la pregunta.  
  
 ![Cuadro de diálogo de procesador de textos](../../../../docs/framework/wpf/app-development/media/dialogboxesoverviewfigure1.png "DialogBoxesOverviewFigure1")  
  
 Para crear un cuadro de mensaje, utilice la <xref:System.Windows.MessageBox> clase.                  <xref:System.Windows.MessageBox> le permite configurar el texto del cuadro de mensaje, título, icono y botones, mediante código como el siguiente.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxconfigurecodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxconfigurecodebehind)]  
  
 Para mostrar un cuadro de mensaje, llame a la `static` <xref:System.Windows.MessageBox.Show%2A> método, como se muestra en el código siguiente.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowcodebehind)]  
  
 Cuando el código que muestra un cuadro de mensaje debe detectar y procesar la Decisión del usuario (qué botón se presionó), el código puede inspeccionar el resultado de cuadro de mensaje, como se muestra en el código siguiente.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowandresultcodebehind1)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowandresultcodebehind1)]  
  
 Para obtener más información sobre el uso de cuadros de mensaje, consulte <xref:System.Windows.MessageBox>, [MessageBox Sample](http://go.microsoft.com/fwlink/?LinkID=160023), y [ejemplo de cuadro de diálogo](http://go.microsoft.com/fwlink/?LinkID=159984).  
  
 Aunque <xref:System.Windows.MessageBox> puede ofrecer una experiencia de usuario del cuadro de diálogo sencillo, la ventaja de utilizar <xref:System.Windows.MessageBox> es que es el único tipo de ventana que se puede mostrar las aplicaciones que se ejecutan en un recinto de seguridad de confianza parcial (vea [seguridad](../../../../docs/framework/wpf/security-wpf.md)), como [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)].  
  
 La mayoría de los cuadros de diálogo Mostrar y recopilan datos más complejos que el resultado de un cuadro de mensaje, incluidos texto, selecciones (casillas), selecciones mutuamente excluyentes (botones de radio) y la lista de selección (cuadros de lista, cuadros combinados, cuadros de lista desplegable). En estos casos, [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] proporciona varios cuadros de diálogo comunes y le permite crear sus propios cuadros de diálogo, aunque el uso de uno de ellos se limita a aplicaciones que se ejecutan con plena confianza.  
  
<a name="Common_Dialogs"></a>   
## <a name="common-dialog-boxes"></a>Cuadros de diálogo comunes  
 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]implementa diversos cuadros de diálogo reutilizables que son comunes a todas las aplicaciones, incluidos los cuadros de diálogo para abrir archivos, guardar archivos e imprimir. Dado que estos cuadros de diálogo se implementa el sistema operativo, se pueden compartir entre todas las aplicaciones que se ejecutan en el sistema operativo, que ayuda a los usuarios a experimentar coherencia; Cuando los usuarios están familiarizados con el uso de un cuadro de diálogo proporcionado por el sistema operativo en una aplicación, no necesitan aprender a usar ese cuadro de diálogo en otras aplicaciones. Dado que estos cuadros de diálogo están disponibles para todas las aplicaciones y ya que ayudan a proporcionar una experiencia de usuario coherente, se conocen como *cuadros de diálogo comunes*.  
  
 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]encapsula el archivo abierto, guarde el archivo y cuadros de diálogo comunes de impresión y los expone como clases administradas para su uso en aplicaciones independientes. En este tema se proporciona una breve descripción de cada uno.  
  
<a name="Open_File_Dialog"></a>   
### <a name="open-file-dialog"></a>Cuadro de diálogo Abrir archivo  
 El cuadro de diálogo Abrir archivo que se muestra en la ilustración siguiente, se utiliza la funcionalidad de apertura de archivos para recuperar el nombre de un archivo para abrirlo.  
  
 ![Cuadro de diálogo Abrir](../../../../docs/framework/wpf/app-development/media/dialogboxesoverviewfigure2.png "DialogBoxesOverviewFigure2")  
  
 El cuadro de diálogo Abrir archivo común se implementa como el <xref:Microsoft.Win32.OpenFileDialog> de clase y se encuentra en la <xref:Microsoft.Win32> espacio de nombres. El código siguiente muestra cómo crear, configurar y mostrar uno y cómo procesar el resultado.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#openfiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#openfiledialogboxcodebehind)]  
  
 Para obtener más información sobre el cuadro de diálogo Abrir archivo, consulte <xref:Microsoft.Win32.OpenFileDialog?displayProperty=fullName>.  
  
> [!NOTE]
>  <xref:Microsoft.Win32.OpenFileDialog> puede utilizarse para recuperar de manera segura los nombres de archivo por aplicaciones que se ejecutan con confianza parcial (vea [seguridad](../../../../docs/framework/wpf/security-wpf.md)).  
  
<a name="Save_File_Dialog"></a>   
### <a name="save-file-dialog-box"></a>Cuadro de diálogo de archivo Guardar  
 Guardar cuadro de diálogo de archivo que se muestra en la ilustración siguiente, se utiliza la funcionalidad de guardado de archivos para recuperar el nombre de un archivo para guardar.  
  
 ![Cuadro de diálogo Guardar como](../../../../docs/framework/wpf/app-development/media/dialogboxesoverviewfigure3.png "DialogBoxesOverviewFigure3")  
  
 Guardar el cuadro de diálogo de archivo común se implementa como el <xref:Microsoft.Win32.SaveFileDialog> de clase y se encuentra en la <xref:Microsoft.Win32> espacio de nombres. El código siguiente muestra cómo crear, configurar y mostrar uno y cómo procesar el resultado.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#savefiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#savefiledialogboxcodebehind)]  
  
 Para obtener más información sobre la operación de guardar archivo de cuadro de diálogo, consulte <xref:Microsoft.Win32.SaveFileDialog?displayProperty=fullName>.  
  
<a name="Print_Dialog"></a>   
### <a name="print-dialog-box"></a>Cuadro de diálogo Imprimir  
 El cuadro de diálogo Imprimir, que se muestra en la ilustración siguiente, se utiliza la funcionalidad de impresión para elegir y configurar la impresora que desea imprimir los datos en un usuario.  
  
 ![Cuadro de diálogo Imprimir](../../../../docs/framework/wpf/app-development/media/dialogboxesoverviewfigure4.png "DialogBoxesOverviewFigure4")  
  
 El cuadro de diálogo de impresión común se implementa como el <xref:System.Windows.Controls.PrintDialog> de clase y se encuentra en la <xref:System.Windows.Controls> espacio de nombres. El código siguiente muestra cómo crear, configurar y mostrar uno.  
  
 [!code-csharp[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#printdialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#printdialogboxcodebehind)]  
  
 Para obtener más información sobre el cuadro de diálogo de impresión, consulte <xref:System.Windows.Controls.PrintDialog?displayProperty=fullName>. Para obtener información detallada acerca de la impresión en [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], consulte [información general de la impresión](../../../../docs/framework/wpf/advanced/printing-overview.md).  
  
<a name="Custom_Dialog_Boxes"></a>   
## <a name="custom-dialog-boxes"></a>Cuadros de diálogo personalizados  
 Aunque los cuadros de diálogo comunes son útiles y deben utilizarse cuando sea posible, no admiten los requisitos de los cuadros de diálogo específicos de dominio. En estos casos, debe crear sus propios cuadros de diálogo. Como veremos, un cuadro de diálogo es una ventana con comportamientos especiales.                  <xref:System.Windows.Window> implementa esos comportamientos y, por consiguiente, utilice <xref:System.Windows.Window> para crear cuadros de diálogo modales y no modales personalizados.  
  
<a name="Creating_a_Modal_Custom_Dialog_Box"></a>   
### <a name="creating-a-modal-custom-dialog-box"></a>Crear un cuadro de diálogo personalizado Modal  
 Este tema muestra cómo usar <xref:System.Windows.Window> para crear una implementación de cuadro de diálogo modal típico, utilizando el `Margins` cuadro de diálogo como ejemplo (vea [Dialog Box Sample](http://go.microsoft.com/fwlink/?LinkID=159984)). El `Margins` cuadro de diálogo se muestra en la ilustración siguiente.  
  
 ![Cuadro de diálogo márgenes](../../../../docs/framework/wpf/app-development/media/dialogboxesoverviewfigure5.png "DialogBoxesOverviewFigure5")  
  
#### <a name="configuring-a-modal-dialog-box"></a>Configuración de un cuadro de diálogo Modal  
 La interfaz de usuario para un cuadro de diálogo típico incluye lo siguiente:  
  
-   Los distintos controles necesarios para recopilar los datos deseados.  
  
-   Mostrar un **Aceptar** botón que los usuarios, haga clic para cerrar el cuadro de diálogo, vuelva a la función y continuar procesando.  
  
-   Mostrar un **cancelar** botón que los usuarios hacen clic para cerrar el cuadro de diálogo y detenga la función de procesamiento adicional.  
  
-   Mostrar un **cerrar** botón en la barra de título.  
  
-   Mostrar un icono.  
  
-   Showing                                          **Minimize**,                                          **Maximize**, and                                          **Restore** buttons.  
  
-   Mostrar un **System** menú para minimizar, maximizar, restaurar y cerrar el cuadro de diálogo.  
  
-   Apertura encima y en el centro de la ventana que abre el cuadro de diálogo.  
  
-   Cuadros de diálogo deben ser dimensiones de tamaño variable siempre que sea posible, por lo tanto, para evitar que el cuadro de diálogo es demasiado pequeño y para proporcionar al usuario con un tamaño predeterminado útil, debe establecer predeterminado y un mínimo respectivamente.  
  
-   Al presionar la tecla ESC debe estar configurado como un método abreviado de teclado que provoca la **cancelar** botón que se presionó. Esto se logra estableciendo la <xref:System.Windows.Controls.Button.IsCancel%2A> propiedad de la **cancelar** botón a `true`.  
  
-   Al presionar la tecla ENTRAR (o retorno) debe estar configurado como un método abreviado de teclado que provoca la **Aceptar** botón que se presionó. Esto se logra estableciendo la <xref:System.Windows.Controls.Button.IsDefault%2A> propiedad de la **Aceptar** botón `true`.  
  
 El código siguiente muestra esta configuración.  
  
 [!code-xml[DialogBoxSample#MarginsDialogBoxMainBitsMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#marginsdialogboxmainbitsmarkup1)]  
[!code-xml[DialogBoxSample#MarginsDialogBoxMainBitsMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#marginsdialogboxmainbitsmarkup2)]  
  
 [!code-csharp[DialogBoxSample#MarginsDialogBoxMainBitsCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxmainbitscodebehind1)]
 [!code-vb[DialogBoxSample#MarginsDialogBoxMainBitsCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxmainbitscodebehind1)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxMainBitsCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxmainbitscodebehind2)]
[!code-vb[DialogBoxSample#MarginsDialogBoxMainBitsCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxmainbitscodebehind2)]  
  
 La experiencia del usuario para un cuadro de diálogo se extiende también a la barra de menús de la ventana que se abre el cuadro de diálogo. Cuando un elemento de menú ejecuta una función que requiere la interacción del usuario mediante un cuadro de diálogo antes de continuar con la función, el elemento de menú para la función tendrá puntos suspensivos en su encabezado, como se muestra aquí.  
  
 [!code-xml[DialogBoxSample#MainWindowMarginsDialogBoxMenuItemMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#mainwindowmarginsdialogboxmenuitemmarkup1)]  
[!code-xml[DialogBoxSample#MainWindowMarginsDialogBoxMenuItemMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#mainwindowmarginsdialogboxmenuitemmarkup2)]  
  
 Cuando un elemento de menú ejecuta una función que muestra un cuadro de diálogo que no requiere interacción del usuario, como un cuadro de diálogo acerca de los puntos suspensivos no son necesario.  
  
#### <a name="opening-a-modal-dialog-box"></a>Abrir el cuadro de diálogo Modal  
 Un cuadro de diálogo se muestra normalmente como resultado de un usuario selecciona un elemento de menú para realizar una función específica del dominio, como establecer los márgenes de un documento en un procesador de textos. Mostrar una ventana como un cuadro de diálogo es similar a mostrar una ventana normal, aunque requiere la configuración específica del cuadro de diálogo adicional. Todo el proceso de creación de instancias, configurar y abrir un cuadro de diálogo se muestran en el código siguiente.  
  
 [!code-csharp[DialogBoxSample#OpenMarginsDialogCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogcodebehind1)]
 [!code-vb[DialogBoxSample#OpenMarginsDialogCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogcodebehind1)]  
[!code-csharp[DialogBoxSample#OpenMarginsDialogCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogcodebehind2)]
[!code-vb[DialogBoxSample#OpenMarginsDialogCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogcodebehind2)]  
[!code-csharp[DialogBoxSample#OpenMarginsDialogCODEBEHIND3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogcodebehind3)]
[!code-vb[DialogBoxSample#OpenMarginsDialogCODEBEHIND3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogcodebehind3)]  
[!code-csharp[DialogBoxSample#OpenMarginsDialogCODEBEHIND4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogcodebehind4)]
[!code-vb[DialogBoxSample#OpenMarginsDialogCODEBEHIND4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogcodebehind4)]  
  
 En este caso, el código está pasando información predeterminada (los márgenes actuales) en el cuadro de diálogo. También está estableciendo la <xref:System.Windows.Window.Owner%2A?displayProperty=fullName> propiedad con una referencia a la ventana que muestra el cuadro de diálogo. En general, siempre se debe establecer el propietario de un cuadro de diálogo para ofrecer comportamientos relacionados con el estado de ventana que son comunes a todos los cuadros de diálogo (consulte [WPF Windows Overview](../../../../docs/framework/wpf/app-development/wpf-windows-overview.md) para obtener más información).  
  
> [!NOTE]
>  Debe proporcionar un propietario para admitir [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] automatización para cuadros de diálogo (consulte [información general sobre la automatización de interfaz de usuario](../../../../docs/framework/ui-automation/ui-automation-overview.md)).  
  
 Después de configura el cuadro de diálogo, se mostrará modalmente llamando a la <xref:System.Windows.Window.ShowDialog%2A> método.  
  
#### <a name="validating-user-provided-data"></a>Validar datos proporcionados por el usuario  
 Cuando se abre un cuadro de diálogo y el usuario proporciona los datos necesarios, un cuadro de diálogo es responsable de garantizar que los datos proporcionados son válidos por las razones siguientes:  
  
-   Desde una perspectiva de seguridad, se deben validar todas las entradas.  
  
-   Desde una perspectiva específica del dominio, validación de datos impide que los datos erróneos que son procesadas por el código, que podría iniciar excepciones.  
  
-   Desde una perspectiva de la experiencia del usuario, un cuadro de diálogo puede ayudar a los usuarios mostrándoles qué datos ha escrito no están válidos.  
  
-   Desde una perspectiva de rendimiento, la validación de datos en una aplicación de varios niveles puede reducir el número de ida y vuelta entre el cliente y los niveles de aplicación, especialmente cuando la aplicación se compone de servicios Web o bases de datos basadas en servidor.  
  
 Para validar un control enlazado en [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], debe definir una regla de validación y asociarlo con el enlace. Una regla de validación es una clase personalizada que deriva de <xref:System.Windows.Controls.ValidationRule>. En el ejemplo siguiente se muestra una regla de validación, `MarginValidationRule`, que comprueba que un valor enlazado es un <xref:System.Double> y está dentro del intervalo especificado.  
  
 [!code-csharp[DialogBoxSample#MarginValidationRuleCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginValidationRule.cs#marginvalidationrulecode)]
 [!code-vb[DialogBoxSample#MarginValidationRuleCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginValidationRule.vb#marginvalidationrulecode)]  
  
 En este código, la lógica de validación de una regla de validación se implementa invalidando el <xref:System.Windows.Controls.ValidationRule.Validate%2A> método, que valida los datos y devuelve un <xref:System.Windows.Controls.ValidationResult>.  
  
 Para asociar la regla de validación con el control enlazado, utilice el siguiente marcado.  
  
 [!code-xml[DialogBoxSample#MarginsValidationMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#marginsvalidationmarkup1)]  
[!code-xml[DialogBoxSample#MarginsValidationMARKUP2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#marginsvalidationmarkup2)]  
[!code-xml[DialogBoxSample#MarginsValidationMARKUP3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#marginsvalidationmarkup3)]  
  
 Una vez que está asociada, la regla de validación [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] lo aplicará automáticamente cuando se escriben datos en el control enlazado. Cuando un control contiene datos no válidos, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] mostrará un borde rojo alrededor del control no válido, como se muestra en la ilustración siguiente.  
  
 ![Margen izquierdo no válido](../../../../docs/framework/wpf/app-development/media/dialogboxesoverviewfigure7.png "DialogBoxesOverviewFigure7")  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]no restringe un usuario al control no válido hasta que haya introducido datos válidos. Esto es una buena práctica para un cuadro de diálogo; un usuario debe poder navegar libremente por los controles en un cuadro de diálogo datos sea o no válidos. Sin embargo, esto significa que un usuario puede escribir datos no válidos y presionar el **Aceptar** botón. Por este motivo, el código también debe validar todos los controles en un cuadro de diálogo cuadro cuando el **Aceptar** está presionado controlando la <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventos.  
  
 [!code-csharp[DialogBoxSample#MarginsDialogBoxValidationCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxvalidationcodebehind1)]
 [!code-vb[DialogBoxSample#MarginsDialogBoxValidationCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxvalidationcodebehind1)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxValidationCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxvalidationcodebehind2)]
[!code-vb[DialogBoxSample#MarginsDialogBoxValidationCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxvalidationcodebehind2)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxValidationCODEBEHIND3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxvalidationcodebehind3)]
[!code-vb[DialogBoxSample#MarginsDialogBoxValidationCODEBEHIND3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxvalidationcodebehind3)]  
  
 Este código enumera todos los objetos de dependencia en una ventana y, si alguno no es válido (devuelto por <xref:System.Windows.Controls.Validation.GetHasError%2A>, el control no válido obtiene el foco, el `IsValid` método devuelve `false`, y la ventana se considera no válida.  
  
 Una vez que un cuadro de diálogo es válido, puede cerrar y devolver sin ningún riesgo. Como parte del proceso de retorno, debe devolver un resultado a la función de llamada.  
  
#### <a name="setting-the-modal-dialog-result"></a>Establecer el resultado del cuadro de diálogo Modal  
 Abrir un cuadro de diálogo mediante <xref:System.Windows.Window.ShowDialog%2A> es fundamentalmente como llamar a un método: el código que abre el cuadro de diálogo mediante <xref:System.Windows.Window.ShowDialog%2A> espera hasta <xref:System.Windows.Window.ShowDialog%2A> devuelve. Cuando <xref:System.Windows.Window.ShowDialog%2A> devuelve, el código que lo llamó necesita decidir si continuar procesando o detener el procesamiento, en función de si el usuario presionó el **Aceptar** botón o la **cancelar** botón. Para facilitar esta decisión, el cuadro de diálogo debe devolver la elección del usuario como un <xref:System.Boolean> valor devuelto desde el <xref:System.Windows.Window.ShowDialog%2A> (método).  
  
 Cuando el **Aceptar** se hace clic en el botón, <xref:System.Windows.Window.ShowDialog%2A> debe devolver `true`. Esto se logra estableciendo la <xref:System.Windows.Window.DialogResult%2A> cuadro propiedad del cuadro de diálogo cuando la **Aceptar** se hace clic en el botón.  
  
 [!code-csharp[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxokresultsetcodebehind1)]
 [!code-vb[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxokresultsetcodebehind1)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxokresultsetcodebehind2)]
[!code-vb[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxokresultsetcodebehind2)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxokresultsetcodebehind3)]
[!code-vb[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxokresultsetcodebehind3)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxokresultsetcodebehind4)]
[!code-vb[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxokresultsetcodebehind4)]  
  
 Tenga en cuenta esa configuración la <xref:System.Windows.Window.DialogResult%2A> propiedad también hace que la ventana para cerrar automáticamente, lo que alivia la necesidad de llamar explícitamente a <xref:System.Windows.Window.Close%2A>.  
  
 Cuando el **cancelar** se hace clic en el botón, <xref:System.Windows.Window.ShowDialog%2A> debe devolver `false`, que requiere la configuración de la <xref:System.Windows.Window.DialogResult%2A> propiedad.  
  
 [!code-csharp[DialogBoxSample#MarginsDialogBoxCancelResultSetCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxcancelresultsetcodebehind1)]
 [!code-vb[DialogBoxSample#MarginsDialogBoxCancelResultSetCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxcancelresultsetcodebehind1)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxCancelResultSetCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxcancelresultsetcodebehind2)]
[!code-vb[DialogBoxSample#MarginsDialogBoxCancelResultSetCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxcancelresultsetcodebehind2)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxCancelResultSetCODEBEHIND3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxcancelresultsetcodebehind3)]
[!code-vb[DialogBoxSample#MarginsDialogBoxCancelResultSetCODEBEHIND3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxcancelresultsetcodebehind3)]  
  
 Cuando un botón <xref:System.Windows.Controls.Button.IsCancel%2A> propiedad está establecida en `true` y el usuario presiona cualquiera el **cancelar** botón o la tecla ESC, <xref:System.Windows.Window.DialogResult%2A> se establece automáticamente en `false`. El marcado siguiente tiene el mismo efecto que el código anterior, sin necesidad de controlar la <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventos.  
  
 [!code-xml[DialogBoxSample#MarginsDialogDefaultCancelMARKUP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#marginsdialogdefaultcancelmarkup)]  
  
 Devuelve automáticamente un cuadro de diálogo `false` cuando un usuario presiona el **cerrar** situado en la barra de título o elige el **cerrar** elemento de menú de la **System** menú.  
  
#### <a name="processing-data-returned-from-a-modal-dialog-box"></a>Procesar datos devueltos desde un cuadro de diálogo Modal  
 Cuando <xref:System.Windows.Window.DialogResult%2A> se establece mediante un cuadro de diálogo, la función que lo abrió puede obtener el resultado del cuadro de diálogo inspeccionando el <xref:System.Windows.Window.DialogResult%2A> propiedad cuando <xref:System.Windows.Window.ShowDialog%2A> devuelve.  
  
 [!code-csharp[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogprocessreturncodebehind1)]
 [!code-vb[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogprocessreturncodebehind1)]  
[!code-csharp[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogprocessreturncodebehind2)]
[!code-vb[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogprocessreturncodebehind2)]  
[!code-csharp[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogprocessreturncodebehind3)]
[!code-vb[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogprocessreturncodebehind3)]  
[!code-csharp[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogprocessreturncodebehind4)]
[!code-vb[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogprocessreturncodebehind4)]  
  
 Si el resultado del diálogo es `true`, la función que utiliza como una indicación para recuperar y procesar los datos proporcionados por el usuario.  
  
> [!NOTE]
>  Después de <xref:System.Windows.Window.ShowDialog%2A> ha devuelto no se puede volver a abrir un cuadro de diálogo. En su lugar, debe crear una nueva instancia.  
  
 Si el resultado del diálogo es `false`, la función debe finalizar el procesamiento correctamente.  
  
<a name="Creating_a_Modeless_Custom_Dialog_Box"></a>   
### <a name="creating-a-modeless-custom-dialog-box"></a>Crear un cuadro de diálogo personalizado no modal  
 Un cuadro de diálogo no modales, como se muestra en la ilustración siguiente, el cuadro de diálogo Buscar tiene el mismo aspecto fundamental que el cuadro de diálogo modal.  
  
 ![Cuadro de diálogo Buscar](../../../../docs/framework/wpf/app-development/media/dialogboxesoverviewfigure6.PNG "DialogBoxesOverviewFigure6")  
  
 Sin embargo, el comportamiento es ligeramente diferente, como se describe en las secciones siguientes.  
  
#### <a name="opening-a-modeless-dialog-box"></a>Abrir un cuadro de diálogo no modales  
 Se abre un cuadro de diálogo no modal mediante una llamada a la <xref:System.Windows.Window.Show%2A> método.  
  
 [!code-xml[DialogBoxSample#OpenFindDialogMARKUP1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#openfinddialogmarkup1)]  
  
 [!code-csharp[DialogBoxSample#OpenFindDialogCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openfinddialogcodebehind1)]
 [!code-vb[DialogBoxSample#OpenFindDialogCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openfinddialogcodebehind1)]  
[!code-csharp[DialogBoxSample#OpenFindDialogCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openfinddialogcodebehind2)]
[!code-vb[DialogBoxSample#OpenFindDialogCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openfinddialogcodebehind2)]  
[!code-csharp[DialogBoxSample#OpenFindDialogCODEBEHIND3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openfinddialogcodebehind3)]
[!code-vb[DialogBoxSample#OpenFindDialogCODEBEHIND3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openfinddialogcodebehind3)]  
  
 A diferencia de <xref:System.Windows.Window.ShowDialog%2A>, <xref:System.Windows.Window.Show%2A> devuelve inmediatamente. Por consiguiente, no puede determinar la ventana de llamada cuando se cierra el cuadro de diálogo no modal y, por lo tanto, no sabe cuándo comprobar el resultado de un cuadro de diálogo u obtener datos desde el cuadro de diálogo para su posterior procesamiento. En su lugar, el cuadro de diálogo debe crear una manera alternativa de devolver datos a la ventana de llamada para su procesamiento.  
  
#### <a name="processing-data-returned-from-a-modeless-dialog-box"></a>Procesar datos devueltos desde un cuadro de diálogo no modales  
 En este ejemplo, el `FindDialogBox` puede devolver uno o más resultados de búsqueda a la ventana principal, dependiendo del texto que se están buscando sin ninguna frecuencia concreta. Al igual que con un cuadro de diálogo modal, un cuadro de diálogo no modal puede devolver resultados mediante propiedades. Sin embargo, la ventana que posee el cuadro de diálogo necesita saber cuándo debe comprobar esas propiedades. Una manera de habilitar esta opción es para que el cuadro de diálogo implementar un evento que se desencadena cuando se encuentra el texto.                                  `FindDialogBox`implementa el `TextFoundEvent` para este propósito, que primero requiere un delegado.  
  
 [!code-csharp[DialogBoxSample#TextFoundEventHandlerCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/TextFoundEventHandler.cs#textfoundeventhandlercode)]
 [!code-vb[DialogBoxSample#TextFoundEventHandlerCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/TextFoundEventHandler.vb#textfoundeventhandlercode)]  
  
 Using the                                  `TextFoundEventHandler` delegate,                                  `FindDialogBox` implements the                                  `TextFoundEvent`.  
  
 [!code-csharp[DialogBoxSample#TextFoundEventCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventcodebehind1)]
 [!code-vb[DialogBoxSample#TextFoundEventCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventcodebehind1)]  
[!code-csharp[DialogBoxSample#TextFoundEventCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventcodebehind2)]
[!code-vb[DialogBoxSample#TextFoundEventCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventcodebehind2)]  
  
 En consecuencia, `Find` puede generar el evento cuando se encuentra un resultado de búsqueda.  
  
 [!code-csharp[DialogBoxSample#TextFoundEventRaiseCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventraisecodebehind1)]
 [!code-vb[DialogBoxSample#TextFoundEventRaiseCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventraisecodebehind1)]  
[!code-csharp[DialogBoxSample#TextFoundEventRaiseCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventraisecodebehind2)]
[!code-vb[DialogBoxSample#TextFoundEventRaiseCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventraisecodebehind2)]  
[!code-csharp[DialogBoxSample#TextFoundEventRaiseCODEBEHIND3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventraisecodebehind3)]
[!code-vb[DialogBoxSample#TextFoundEventRaiseCODEBEHIND3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventraisecodebehind3)]  
[!code-csharp[DialogBoxSample#TextFoundEventRaiseCODEBEHIND4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventraisecodebehind4)]
[!code-vb[DialogBoxSample#TextFoundEventRaiseCODEBEHIND4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventraisecodebehind4)]  
[!code-csharp[DialogBoxSample#TextFoundEventRaiseCODEBEHIND5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventraisecodebehind5)]
[!code-vb[DialogBoxSample#TextFoundEventRaiseCODEBEHIND5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventraisecodebehind5)]  
  
 La ventana propietaria, a continuación, debe registrar con y controlar este evento.  
  
 [!code-csharp[DialogBoxSample#OpenFindDialogResultCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openfinddialogresultcodebehind1)]
 [!code-vb[DialogBoxSample#OpenFindDialogResultCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openfinddialogresultcodebehind1)]  
[!code-csharp[DialogBoxSample#OpenFindDialogResultCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openfinddialogresultcodebehind2)]
[!code-vb[DialogBoxSample#OpenFindDialogResultCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openfinddialogresultcodebehind2)]  
  
#### <a name="closing-a-modeless-dialog-box"></a>Cerrar un cuadro de diálogo no modales  
 Porque <xref:System.Windows.Window.DialogResult%2A> no necesita estar establecida, se puede cerrar un cuadro de diálogo no modal mediante el sistema proporcionan mecanismos, incluidos los siguientes:  
  
-   Haga clic en el **cerrar** botón en la barra de título.  
  
-   Presione ALT+F4.  
  
-   Choosing                                          **Close** from the                                          **System** menu.  
  
 Como alternativa, puede llamar su código <xref:System.Windows.Window.Close%2A> cuando el **cerrar** se hace clic en el botón.  
  
 [!code-csharp[DialogBoxSample#FindDialogCloseCODEBEHIND1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#finddialogclosecodebehind1)]
 [!code-vb[DialogBoxSample#FindDialogCloseCODEBEHIND1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#finddialogclosecodebehind1)]  
[!code-csharp[DialogBoxSample#FindDialogCloseCODEBEHIND2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#finddialogclosecodebehind2)]
[!code-vb[DialogBoxSample#FindDialogCloseCODEBEHIND2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#finddialogclosecodebehind2)]  
  
## <a name="see-also"></a>Vea también  
 [Información general del elemento emergente](../../../../docs/framework/wpf/controls/popup-overview.md)   
 [Ejemplo de cuadro de diálogo](http://go.microsoft.com/fwlink/?LinkID=159984)   
 [Ejemplo ColorPicker Custom Control](http://go.microsoft.com/fwlink/?LinkID=159977)