---
title: "Informaci&#243;n general sobre el control RichTextBox | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "controles, RichTextBox"
  - "RichTextBox (control) [WPF], acerca del control RichTextBox"
ms.assetid: c94548b2-c1e9-4b62-b10c-dd8740eb23d8
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Informaci&#243;n general sobre el control RichTextBox
El control <xref:System.Windows.Controls.RichTextBox> permite mostrar o modificar el contenido dinámico, incluidos párrafos, imágenes, tablas, etc.  En este tema se presenta la clase <xref:System.Windows.Controls.TextBox> y se proporcionan ejemplos de cómo utilizarla en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y [!INCLUDE[TLA#tla_lhcshrp](../../../../includes/tlasharptla-lhcshrp-md.md)].  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="textbox_or_richtextbox"></a>   
## ¿TextBox o RichTextBox?  
 Tanto <xref:System.Windows.Controls.RichTextBox> como <xref:System.Windows.Controls.TextBox> permiten al usuario editar texto; sin embargo, se utilizan en escenarios diferentes.  <xref:System.Windows.Controls.RichTextBox> es preferible cuando es necesario que el usuario modifique texto con formato, imágenes, tablas u otro contenido enriquecido.  Por ejemplo, la edición de un documento, artículo o blog que requieran formato, imágenes, etc. se logra mejor mediante <xref:System.Windows.Controls.RichTextBox>.  <xref:System.Windows.Controls.TextBox> requiere menos recursos del sistema que <xref:System.Windows.Controls.RichTextBox> y es idóneo cuando sólo se necesita editar texto sin formato \(por ejemplo,   para usarlo en formularios\).  Consulte [Información general sobre TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md) para obtener más información sobre <xref:System.Windows.Controls.TextBox>.  En la tabla siguiente se resumen las principales características de <xref:System.Windows.Controls.TextBox> y <xref:System.Windows.Controls.RichTextBox>.  
  
|Control|Revisión ortográfica en tiempo real|Menú contextual|Formatos de comando como <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> \(Ctr\+N\)|Contenido de <xref:System.Windows.Documents.FlowDocument> como imágenes, párrafos, tablas, etc.|  
|-------------|-----------------------------------------|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.TextBox>|Sí|Sí|No|No.|  
|<xref:System.Windows.Controls.RichTextBox>|Sí|Sí|Sí|Sí|  
  
 **Nota:** aunque <xref:System.Windows.Controls.TextBox> no permite los comandos relacionados con el formato, como <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> \(Ctr\+N\), ambos controles admiten numerosos comandos básicos, como <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>.  
  
 Las características de la tabla anterior se abordan más adelante con más detalle.  
  
<a name="creating_a_richtextbox"></a>   
## Crear un control RichTextBox  
 En el código siguiente se muestra cómo crear un control <xref:System.Windows.Controls.RichTextBox> que permite al usuario modificar su contenido enriquecido.  
  
 [!code-xml[RichTextBoxMiscSnippets_snip#BasicRichTextBoxExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/BasicRichTextBoxExample.xaml#basicrichtextboxexamplewholepage)]  
  
 Específicamente, el contenido que se edita en un <xref:System.Windows.Controls.RichTextBox> es contenido dinámico.  El contenido dinámico puede contener muchos tipos de elementos, que incluyen texto con formato, imágenes, listas y tablas.  Consulte [Información general sobre documentos dinámicos](../../../../docs/framework/wpf/advanced/flow-document-overview.md) para obtener información detallada documentos dinámicos.  Para incluir contenido dinámico, <xref:System.Windows.Controls.RichTextBox> hospeda un objeto <xref:System.Windows.Documents.FlowDocument> que, a su vez, incluye el contenido modificable.  Para mostrar el contenido dinámico en un control <xref:System.Windows.Controls.RichTextBox>, en el código siguiente se muestra cómo crear un control <xref:System.Windows.Controls.RichTextBox> con un párrafo y texto en negrita.  
  
 [!code-xml[RichTextBoxMiscSnippets_snip#RichTextBoxWithContentExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/RichTextBoxWithContentExample.xaml#richtextboxwithcontentexamplewholepage)]  
  
 [!code-csharp[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/CSharp/BasicRichTextBoxWithContentExample.cs#basicrichtextboxwithcontentcodeonlyexample)]
 [!code-vb[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/visualbasic/basicrichtextboxwithcontentexample.vb#basicrichtextboxwithcontentcodeonlyexample)]  
  
 En la ilustración siguiente se muestra cómo se representa este ejemplo.  
  
 ![RichTextBox con contenido](../../../../docs/framework/wpf/controls/media/editing-richtextbox-with-content.png "Editing\_RichTextBox\_with\_Content")  
  
 Los elementos como <xref:System.Windows.Documents.Paragraph> y <xref:System.Windows.Documents.Bold> determinan cómo aparece el contenido dentro de <xref:System.Windows.Controls.RichTextBox>.  Cuando un usuario edita el contenido de <xref:System.Windows.Controls.RichTextBox>, lo que cambia es este contenido dinámico.  Para obtener más información sobre las características del contenido dinámico de flujo y cómo trabajar con él, consulte [Información general sobre documentos dinámicos](../../../../docs/framework/wpf/advanced/flow-document-overview.md).  
  
 **Nota:** el contenido dinámico existente dentro de un control <xref:System.Windows.Controls.RichTextBox> no se comporta exactamente como el contenido dinámico incluido en otros controles.  Por ejemplo, en <xref:System.Windows.Controls.RichTextBox> no hay ninguna columna, por lo que no existe un comportamiento de cambio de tamaño automático.  En un control <xref:System.Windows.Controls.RichTextBox> tampoco están disponibles características tales como la búsqueda, el modo de visualización, la navegación de páginas ni el zoom.  
  
<a name="realtime_spellechecking"></a>   
## Revisión ortográfica en tiempo real  
 Puede habilitar la revisión ortográfica en tiempo real en <xref:System.Windows.Controls.TextBox> o <xref:System.Windows.Controls.RichTextBox>.  Cuando se activa la revisión ortográfica, aparece una línea roja debajo de todas las palabras con errores ortográficos \(consulte la ilustración mostrada a continuación\).  
  
 ![Textbox con corrección ortográfica](../../../../docs/framework/wpf/controls/media/editing-textbox-with-spellchecking.png "Editing\_TextBox\_with\_Spellchecking")  
  
 Consulte [Habilitar el corrector ortográfico en un control de edición de texto](../../../../docs/framework/wpf/controls/how-to-enable-spell-checking-in-a-text-editing-control.md) para obtener información sobre cómo habilitar la revisión ortográfica.  
  
<a name="context_menu"></a>   
## Menú contextual  
 De manera predeterminada, <xref:System.Windows.Controls.TextBox> y <xref:System.Windows.Controls.RichTextBox> tienen un menú contextual que aparece cuando un usuario hace clic con el botón secundario del mouse dentro del control.  El menú contextual permite al usuario cortar, copiar o pegar \(consulte la ilustración mostrada a continuación\).  
  
 ![TextBox con menú contextual](../../../../docs/framework/wpf/controls/media/editing-textbox-with-context-menu.png "Editing\_TextBox\_with\_Context\_Menu")  
  
 Puede crear su propio menú contextual personalizado para invalidar el predeterminado.  Consulte [Colocar un menú contextual personalizado en un control RichTextBox](../../../../docs/framework/wpf/controls/how-to-position-a-custom-context-menu-in-a-richtextbox.md) para obtener más información.  
  
<a name="detect_when_content_changes"></a>   
## Comandos de edición  
 Los comandos de edición permiten a los usuarios dar formato al contenido modificable de un control <xref:System.Windows.Controls.RichTextBox>.  Además de los comandos de edición básicos, <xref:System.Windows.Controls.RichTextBox> incluye comandos de formato que <xref:System.Windows.Controls.TextBox> no admite.  Por ejemplo, al editar en un control <xref:System.Windows.Controls.RichTextBox>, un usuario podría presionar Ctr\+N para alternar la aplicación del formato de negrita al texto.  Para obtener una lista completa de los comandos disponibles, consulte <xref:System.Windows.Documents.EditingCommands>.  Además de utilizar métodos abreviados de teclado, puede enlazar comandos a otros controles, como los botones.  En el ejemplo siguiente se muestra cómo crear una barra de herramientas simple que contiene botones que el usuario puede utilizar para cambiar el formato del texto.  
  
 [!code-xml[RichTextBox_InputPanel_snip#RichTextBoxWithToolBarExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_InputPanel_snip/CS/Window1.xaml#richtextboxwithtoolbarexamplewholepage)]  
  
 En la ilustración siguiente se muestra cómo se muestra este ejemplo.  
  
 ![RichTextBox con ToolBar](../../../../docs/framework/wpf/controls/media/editing-richtextbox-with-toobar.png "Editing\_RichTextBox\_with\_TooBar")  
  
<a name="editing_commands"></a>   
## Detectar los cambios de contenido  
 Normalmente, se debe utilizar el evento <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> para detectar los cambios del texto de un control <xref:System.Windows.Controls.TextBox> o <xref:System.Windows.Controls.RichTextBox>, en lugar de <xref:System.Windows.UIElement.KeyDown>, como cabría esperar.  Vea [Detectar cuándo cambia el texto en un control TextBox](../../../../docs/framework/wpf/controls/how-to-detect-when-text-in-a-textbox-has-changed.md) para obtener un ejemplo.  
  
<a name="save_load_and_print_richtextbox_content"></a>   
## Guardar, cargar e imprimir contenido de un control RichTextBox  
 En el ejemplo siguiente, se muestra cómo guardar el contenido de un control <xref:System.Windows.Controls.RichTextBox> en un archivo, cargar ese contenido de nuevo en <xref:System.Windows.Controls.RichTextBox> e imprimirlo.  A continuación se muestra el marcado para obtener el ejemplo.  
  
 [!code-xml[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml#saveloadprintrtbexamplewholepage)]  
  
 A continuación, se muestra el código subyacente del ejemplo.  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml.cs#saveloadprintrtbcodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/SaveLoadPrintRTB.xaml.vb#saveloadprintrtbcodeexamplewholepage)]  
  
## Vea también  
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/richtextbox-how-to-topics.md)   
 [Información general sobre TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)