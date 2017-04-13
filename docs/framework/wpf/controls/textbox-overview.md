---
title: "Informaci&#243;n general sobre TextBox | Microsoft Docs"
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
  - "controles, TextBox"
  - "TextBox (control), acerca del control TextBox"
ms.assetid: 1ba6dc5b-11a7-4247-9213-36c6729ee35f
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Informaci&#243;n general sobre TextBox
La clase <xref:System.Windows.Controls.TextBox> permite mostrar o modificar el texto sin formato.  Un uso común de <xref:System.Windows.Controls.TextBox> es editar el texto sin formato de un formulario.  Por ejemplo, un formulario que pide el nombre del usuario, el número de teléfono, etc., utilizará controles <xref:System.Windows.Controls.TextBox> para la entrada de texto.  En este tema se presenta la clase <xref:System.Windows.Controls.TextBox> y se proporcionan ejemplos de cómo utilizarla en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y [!INCLUDE[TLA#tla_lhcshrp](../../../../includes/tlasharptla-lhcshrp-md.md)].  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="textbox_or_richtextbox"></a>   
## ¿TextBox o RichTextBox?  
 Tanto <xref:System.Windows.Controls.TextBox> como <xref:System.Windows.Controls.RichTextBox> permiten al usuario especificar texto, pero estos controles se utilizan para escenarios diferentes.  <xref:System.Windows.Controls.TextBox> requiere menos recursos del sistema que <xref:System.Windows.Controls.RichTextBox>, lo que lo hace idóneo cuando sólo se necesita editar texto sin formato \(por ejemplo, para usarlo en un formulario\).  <xref:System.Windows.Controls.RichTextBox> es preferible cuando es necesario que el usuario modifique texto con formato, imágenes, tablas u otro contenido compatible.  Por ejemplo, la edición de un documento, artículo o blog que requieran formato, imágenes, etc. se logra mejor mediante <xref:System.Windows.Controls.RichTextBox>.  En la tabla siguiente se resumen las principales características de <xref:System.Windows.Controls.TextBox> y <xref:System.Windows.Controls.TextBox>.  
  
|Control|Revisión ortográfica en tiempo real|Menú contextual|Formatos de comando como <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> \(Ctr\+N\)|Contenido de <xref:System.Windows.Documents.FlowDocument> como imágenes, párrafos, tablas, etc.|  
|-------------|-----------------------------------------|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.TextBox>|Sí|Sí|No|No.|  
|<xref:System.Windows.Controls.RichTextBox>|Sí|Sí|Sí \(consulte [Información general sobre el control RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)\)|Sí \(consulte [Información general sobre el control RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)\)|  
  
> [!NOTE]
>  Aunque <xref:System.Windows.Controls.TextBox> no permite dar formato a los comandos relacionados con la edición, como <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> \(Ctr\+N\), ambos controles admiten numerosos comandos básicos, como <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>.  Vea <xref:System.Windows.Documents.EditingCommands> para obtener más información.  
  
 Las características admitidas por <xref:System.Windows.Controls.TextBox> se abarcan en las secciones siguientes.  Para obtener más información sobre <xref:System.Windows.Controls.RichTextBox>, vea [Información general sobre el control RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md).  
  
### Revisión ortográfica en tiempo real  
 Puede habilitar la revisión ortográfica en tiempo real en <xref:System.Windows.Controls.TextBox> o <xref:System.Windows.Controls.RichTextBox>.  Cuando se activa la revisión ortográfica, aparece una línea roja debajo de todas las palabras con errores ortográficos \(consulte la ilustración mostrada a continuación\).  
  
 ![Textbox con corrección ortográfica](../../../../docs/framework/wpf/controls/media/editing-textbox-with-spellchecking.png "Editing\_TextBox\_with\_Spellchecking")  
  
 Consulte [Habilitar el corrector ortográfico en un control de edición de texto](../../../../docs/framework/wpf/controls/how-to-enable-spell-checking-in-a-text-editing-control.md) para obtener información sobre cómo habilitar la revisión ortográfica.  
  
### Menú contextual  
 De manera predeterminada, <xref:System.Windows.Controls.TextBox> y <xref:System.Windows.Controls.RichTextBox> tienen un menú contextual que aparece cuando un usuario hace clic con el botón secundario del mouse dentro del control.  El menú contextual permite al usuario cortar, copiar o pegar \(consulte la ilustración mostrada a continuación\).  
  
 ![TextBox con menú contextual](../../../../docs/framework/wpf/controls/media/editing-textbox-with-context-menu.png "Editing\_TextBox\_with\_Context\_Menu")  
  
 Puede crear su propio menú contextual personalizado para invalidar el comportamiento predeterminado.  Consulte [Usar un menú contextual personalizado con un control TextBox](../../../../docs/framework/wpf/controls/how-to-use-a-custom-context-menu-with-a-textbox.md) para obtener más información.  
  
<a name="creating_textboxes"></a>   
## Crear controles TextBox  
 Un <xref:System.Windows.Controls.TextBox> puede tener una sola línea o varias.  Un control <xref:System.Windows.Controls.TextBox> de una sola línea es más adecuado para especificar cantidades pequeñas de texto sin formato \(como el "  Nombre", el "Número de teléfono", etc.  en un formulario\).  En el ejemplo siguiente se muestra cómo crear un control <xref:System.Windows.Controls.TextBox> de una sola línea.  
  
 [!code-xml[TextBoxMiscSnippets_snip#BasicTextBoxExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/basictextboxexample.xaml#basictextboxexamplewholepage)]  
  
 También puede crear controles <xref:System.Windows.Controls.TextBox> que permitan al usuario escribir varias líneas de texto.  Por ejemplo, si en el formulario se pide una pequeña biografía del usuario, deberá utilizar un control <xref:System.Windows.Controls.TextBox> que admita varias líneas de texto.  En el ejemplo siguiente se muestra cómo utilizar [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para definir un control <xref:System.Windows.Controls.TextBox> que se expande automáticamente para alojar varias líneas de texto.  
  
 [!code-xml[TextBox_MiscCode#_MultilineTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
 Al establecer el atributo <xref:System.Windows.Controls.TextBox.TextWrapping%2A> en `Wrap`, el texto se ajusta para continuar en una nueva línea cuando se alcanza el borde del control <xref:System.Windows.Controls.TextBox>, lo que expande automáticamente el control <xref:System.Windows.Controls.TextBox> a fin de incluir espacio para una nueva línea, si es necesario.  
  
 Establecer el atributo <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> en `true` hace que se inserte una nueva línea cuando se presiona la tecla ENTRAR, con lo que <xref:System.Windows.Controls.TextBox> se expande automáticamente una vez más a fin de incluir espacio para una nueva línea, si es necesario.  
  
 El atributo <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> agrega una barra de desplazamiento a <xref:System.Windows.Controls.TextBox>, a fin de que sea posible recorrer el contenido de <xref:System.Windows.Controls.TextBox> si <xref:System.Windows.Controls.TextBox> se expande más allá del tamaño del marco o de la ventana que lo enmarca.  
  
 Para obtener más información sobre distintas tareas asociadas al uso de un control <xref:System.Windows.Controls.TextBox>, consulte [Temas "Cómo..."](../../../../docs/framework/wpf/controls/textbox-how-to-topics.md).  
  
<a name="editing_commands"></a>   
## Detectar los cambios de contenido  
 Normalmente, se debe utilizar el evento <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> para detectar los cambios del texto de un control <xref:System.Windows.Controls.TextBox> o <xref:System.Windows.Controls.RichTextBox>, en lugar de <xref:System.Windows.UIElement.KeyDown>, como cabría esperar.  Vea [Detectar cuándo cambia el texto en un control TextBox](../../../../docs/framework/wpf/controls/how-to-detect-when-text-in-a-textbox-has-changed.md) para obtener un ejemplo.  
  
## Vea también  
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/textbox-how-to-topics.md)   
 [Información general sobre el control RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)