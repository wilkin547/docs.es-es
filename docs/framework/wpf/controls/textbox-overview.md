---
title: Información general sobre TextBox
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], TextBox
- TextBox control [WPF], about TextBox control
ms.assetid: 1ba6dc5b-11a7-4247-9213-36c6729ee35f
ms.openlocfilehash: bb03d09b1730f4a8d607773f9024eee4f125e2c7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="textbox-overview"></a>Información general sobre TextBox
La <xref:System.Windows.Controls.TextBox> clase le permite mostrar o editar texto sin formato. Un uso común de un <xref:System.Windows.Controls.TextBox> está editando el texto sin formato en un formulario. Por ejemplo, un formulario que pide el nombre del usuario, el número de teléfono, etcetera utilizaría <xref:System.Windows.Controls.TextBox> controles de entrada de texto. Este tema se presentan los <xref:System.Windows.Controls.TextBox> clase y proporciona ejemplos de cómo usar tanto en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y C#.  
  
 
  
<a name="textbox_or_richtextbox"></a>   
## <a name="textbox-or-richtextbox"></a>¿TextBox o RichTextBox?  
 Ambos <xref:System.Windows.Controls.TextBox> y <xref:System.Windows.Controls.RichTextBox> permiten a los usuarios escribir texto, pero los dos controles se utilizan para escenarios diferentes. A <xref:System.Windows.Controls.TextBox> requiere menos recursos del sistema, a continuación, un <xref:System.Windows.Controls.RichTextBox> por lo que resulta ideal cuando es necesario editar solo texto sin formato (es decir, el uso de un formulario). A <xref:System.Windows.Controls.RichTextBox> es una opción mejor cuando es necesario para el usuario editar texto con formato, imágenes, tablas o sí admite contenida. Por ejemplo, editar un documento, artículo o blog que requieran formato, imágenes, etcetera se logra mejor usando un <xref:System.Windows.Controls.RichTextBox>. En la tabla siguiente se resume las principales características de <xref:System.Windows.Controls.TextBox> y <xref:System.Windows.Controls.TextBox>.  
  
|Control|Revisión ortográfica en tiempo real|Menú contextual|Formato de comandos, como <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (Ctr + B)|<xref:System.Windows.Documents.FlowDocument> contenido, como imágenes, párrafos, tablas, etcetera.|  
|-------------|------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.TextBox>|Sí|Sí|No|No.|  
|<xref:System.Windows.Controls.RichTextBox>|Sí|Sí|Sí (consulte [RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md)[Introducción a RichTextBox])|Sí (consulte [RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md)[Introducción a RichTextBox])|  
  
> [!NOTE]
>  Aunque <xref:System.Windows.Controls.TextBox> hace comandos admite el formato de edición relacionadas como <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (Ctr + B), muchos comandos básicos son compatibles con ambos controles como <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>. Vea <xref:System.Windows.Documents.EditingCommands> para obtener más información.  
  
 Características admitidas por <xref:System.Windows.Controls.TextBox> se tratan en las secciones siguientes. Para obtener más información acerca de <xref:System.Windows.Controls.RichTextBox>, consulte [RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md).  
  
### <a name="real-time-spellchecking"></a>Revisión ortográfica en tiempo real  
 Puede habilitar la revisión ortográfica en tiempo real en un <xref:System.Windows.Controls.TextBox> o <xref:System.Windows.Controls.RichTextBox>. Cuando se activa la revisión ortográfica, aparece una línea roja debajo de las palabras con errores de ortografía (consulte la siguiente imagen).  
  
 ![Textbox con revisión ortográfica](../../../../docs/framework/wpf/controls/media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")  
  
 Consulte [Cómo habilitar el corrector ortográfico en un control de edición de texto](../../../../docs/framework/wpf/controls/how-to-enable-spell-checking-in-a-text-editing-control.md) para más información sobre cómo activar la revisión ortográfica.  
  
### <a name="context-menu"></a>Menú contextual  
 De forma predeterminada, ambos <xref:System.Windows.Controls.TextBox> y <xref:System.Windows.Controls.RichTextBox> tiene un menú contextual que aparece cuando un usuario hace clic con un botón dentro del control. El menú contextual permite al usuario cortar, copiar o pegar (consulte la siguiente imagen).  
  
 ![TextBox con menú contextual](../../../../docs/framework/wpf/controls/media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")  
  
 Puede crear su propio menú contextual personalizado para invalidar el comportamiento predeterminado. Consulte [Use a Custom Context Menu with a TextBox](../../../../docs/framework/wpf/controls/how-to-use-a-custom-context-menu-with-a-textbox.md) (Usar un menú contextual personalizado con TextBox) para más información.  
  
<a name="creating_textboxes"></a>   
## <a name="creating-textboxes"></a>Crear controles TextBox  
 Un <xref:System.Windows.Controls.TextBox> puede ser una sola línea de alto o contienen varias líneas. Una sola línea <xref:System.Windows.Controls.TextBox> es más adecuado para especificar cantidades pequeñas de texto sin formato (es decir, el nombre, el número de teléfono, etc. en un formulario). En el ejemplo siguiente se muestra cómo crear una sola línea <xref:System.Windows.Controls.TextBox>.  
  
 [!code-xaml[TextBoxMiscSnippets_snip#BasicTextBoxExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/basictextboxexample.xaml#basictextboxexamplewholepage)]  
  
 También puede crear un <xref:System.Windows.Controls.TextBox> que permite al usuario escribir varias líneas de texto. Por ejemplo, si el formulario se pide una pequeña biografía del usuario, que desea usar un <xref:System.Windows.Controls.TextBox> que es compatible con varias líneas de texto. En el ejemplo siguiente se muestra cómo usar [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para definir un <xref:System.Windows.Controls.TextBox> control que se expande automáticamente para alojar varias líneas de texto.  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
 Establecer el <xref:System.Windows.Controls.TextBox.TextWrapping%2A> atribuir a `Wrap` hace que el texto se ajuste a una nueva línea cuando el borde de la <xref:System.Windows.Controls.TextBox> control se alcanza, expanda automáticamente la <xref:System.Windows.Controls.TextBox> control debe incluir el espacio para una nueva línea, si es necesario.  
  
 Establecer el <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> atribuir a `true` provoca una nueva línea insertará cuando se presiona la tecla ENTRAR, se expande automáticamente una vez más la <xref:System.Windows.Controls.TextBox> incluir espacio para una nueva línea, si es necesario.  
  
 El <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> atributo agrega una barra de desplazamiento a la <xref:System.Windows.Controls.TextBox>, de modo que el contenido de la <xref:System.Windows.Controls.TextBox> puede desplazarse a través de if el <xref:System.Windows.Controls.TextBox> se expande más allá del tamaño del marco o la ventana que lo incluye.  
  
 Para obtener más información sobre distintas tareas asociadas con el uso de un <xref:System.Windows.Controls.TextBox>, consulte [temas "Cómo..."](../../../../docs/framework/wpf/controls/textbox-how-to-topics.md).  
  
<a name="editing_commands"></a>   
## <a name="detect-when-content-changes"></a>Detectar los cambios de contenido  
 Normalmente el <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> evento debe usarse para detectar cada vez que el texto de un <xref:System.Windows.Controls.TextBox> o <xref:System.Windows.Controls.RichTextBox> cambia, en lugar de en <xref:System.Windows.UIElement.KeyDown> como cabría esperar. Consulte [Detectar cuándo cambiad el texto en un control TextBox](../../../../docs/framework/wpf/controls/how-to-detect-when-text-in-a-textbox-has-changed.md) para ver un ejemplo.  
  
## <a name="see-also"></a>Vea también  
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/textbox-how-to-topics.md)  
 [RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md) (Introducción a RichTextBox)
