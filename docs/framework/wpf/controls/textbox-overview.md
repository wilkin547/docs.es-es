---
title: Información general sobre TextBox
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], TextBox
- TextBox control [WPF], about TextBox control
ms.assetid: 1ba6dc5b-11a7-4247-9213-36c6729ee35f
ms.openlocfilehash: 46600fd1a3023a80d49fae6f020279be6131916a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951486"
---
# <a name="textbox-overview"></a>Información general sobre TextBox
La <xref:System.Windows.Controls.TextBox> clase le permite mostrar o editar texto sin formato. Un uso común de es <xref:System.Windows.Controls.TextBox> la edición de texto sin formato en un formulario. Por ejemplo, un formulario que solicita el nombre del usuario, el número de teléfono, etc <xref:System.Windows.Controls.TextBox> . usaría controles para la entrada de texto. En este tema se <xref:System.Windows.Controls.TextBox> presenta la clase y se proporcionan ejemplos de cómo usarla en C# [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y.  

<a name="textbox_or_richtextbox"></a>   
## <a name="textbox-or-richtextbox"></a>¿TextBox o RichTextBox?  
 Y permiten <xref:System.Windows.Controls.RichTextBox> a los usuarios escribir texto, pero los dos controles se usan para distintos escenarios. <xref:System.Windows.Controls.TextBox> Un <xref:System.Windows.Controls.TextBox> requiere menos recursos del sistema <xref:System.Windows.Controls.RichTextBox> y, por tanto, es ideal cuando solo es necesario editar texto sin formato (es decir, el uso en un formulario). Una <xref:System.Windows.Controls.RichTextBox> es una opción mejor cuando es necesario que el usuario edite texto con formato, imágenes, tablas u otro contenido compatible. Por ejemplo, la edición de un documento, artículo o blog que requiera formato, imágenes, etc <xref:System.Windows.Controls.RichTextBox>., se consigue mejor mediante. En la tabla siguiente se resumen las características principales <xref:System.Windows.Controls.TextBox> de <xref:System.Windows.Controls.TextBox>y.  
  
|Control|Revisión ortográfica en tiempo real|Menú contextual|Comandos de formato <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> como (CTR + B)|<xref:System.Windows.Documents.FlowDocument>contenido como imágenes, párrafos, tablas, etc.|  
|-------------|------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.TextBox>|Sí|Sí|Sin|No.|  
|<xref:System.Windows.Controls.RichTextBox>|Sí|Sí|Sí (consulte [RichTextBox Overview](richtextbox-overview.md)[Introducción a RichTextBox])|Sí (consulte [RichTextBox Overview](richtextbox-overview.md)[Introducción a RichTextBox])|  
  
> [!NOTE]
> Aunque <xref:System.Windows.Controls.TextBox> no admite el formato de comandos de edición <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> relacionados como (CTR + B), muchos comandos básicos son compatibles <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>con ambos controles, como. Vea <xref:System.Windows.Documents.EditingCommands> para obtener más información.  
  
 Las características admitidas por <xref:System.Windows.Controls.TextBox> se describen en las secciones siguientes. Para obtener más información <xref:System.Windows.Controls.RichTextBox>sobre, vea [información general sobre RichTextBox](richtextbox-overview.md).  
  
### <a name="real-time-spellchecking"></a>Revisión ortográfica en tiempo real  
 Puede habilitar la revisión ortográfica en tiempo real en <xref:System.Windows.Controls.TextBox> un <xref:System.Windows.Controls.RichTextBox>o. Cuando se activa la revisión ortográfica, aparece una línea roja debajo de las palabras con errores de ortografía (consulte la siguiente imagen).  
  
 ![Textbox con revisión ortográfica](./media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")  
  
 Consulte [Cómo habilitar el corrector ortográfico en un control de edición de texto](how-to-enable-spell-checking-in-a-text-editing-control.md) para más información sobre cómo activar la revisión ortográfica.  
  
### <a name="context-menu"></a>Menú contextual  
 De forma predeterminada, <xref:System.Windows.Controls.TextBox> y <xref:System.Windows.Controls.RichTextBox> tienen un menú contextual que aparece cuando un usuario hace clic con el botón secundario dentro del control. El menú contextual permite al usuario cortar, copiar o pegar (consulte la siguiente imagen).  
  
 ![TextBox con menú contextual](./media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")  
  
 Puede crear su propio menú contextual personalizado para invalidar el comportamiento predeterminado. Consulte [Use a Custom Context Menu with a TextBox](how-to-use-a-custom-context-menu-with-a-textbox.md) (Usar un menú contextual personalizado con TextBox) para más información.  
  
<a name="creating_textboxes"></a>   
## <a name="creating-textboxes"></a>Crear controles TextBox  
 <xref:System.Windows.Controls.TextBox> Puede ser una sola línea de alto o contener varias líneas. Una sola línea <xref:System.Windows.Controls.TextBox> es mejor para la entrada de pequeñas cantidades de texto sin formato (es decir, el nombre, el número de teléfono, etc. en un formulario). En el ejemplo siguiente se muestra cómo crear una sola <xref:System.Windows.Controls.TextBox>línea.  
  
 [!code-xaml[TextBoxMiscSnippets_snip#BasicTextBoxExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/basictextboxexample.xaml#basictextboxexamplewholepage)]  
  
 También puede crear un <xref:System.Windows.Controls.TextBox> que permita al usuario escribir varias líneas de texto. Por ejemplo, si el formulario solicita un boceto biográfico del usuario, querrá usar un <xref:System.Windows.Controls.TextBox> que admita varias líneas de texto. En el ejemplo siguiente se muestra cómo [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] utilizar para definir <xref:System.Windows.Controls.TextBox> un control que se expande automáticamente para alojar varias líneas de texto.  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
 Si se <xref:System.Windows.Controls.TextBox.TextWrapping%2A> establece el `Wrap` atributo en, el texto se ajusta a una nueva línea <xref:System.Windows.Controls.TextBox> cuando se alcanza el borde del control, expandiendo <xref:System.Windows.Controls.TextBox> automáticamente el control para incluir espacio para una nueva línea, si es necesario.  
  
 Si se <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> establece el `true` atributo en, se insertará una nueva línea cuando se presione la tecla entrar, se expandirá <xref:System.Windows.Controls.TextBox> de nuevo automáticamente para incluir el espacio para una nueva línea, si es necesario.  
  
 El <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> atributo agrega una barra <xref:System.Windows.Controls.TextBox>de desplazamiento a, de modo <xref:System.Windows.Controls.TextBox> que el contenido de se puede desplazar a través <xref:System.Windows.Controls.TextBox> de si el objeto se expande más allá del tamaño del marco o de la ventana que lo incluye.  
  
 Para obtener más información sobre las distintas tareas asociadas al <xref:System.Windows.Controls.TextBox>uso de, consulte los [temas de procedimientos](textbox-how-to-topics.md).  
  
<a name="editing_commands"></a>   
## <a name="detect-when-content-changes"></a>Detectar los cambios de contenido  
 Normalmente, <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> el evento se debe usar para detectar siempre que el texto <xref:System.Windows.Controls.TextBox> de <xref:System.Windows.Controls.RichTextBox> un <xref:System.Windows.UIElement.KeyDown> o cambie, en lugar de como cabría esperar. Consulte [Detectar cuándo cambiad el texto en un control TextBox](how-to-detect-when-text-in-a-textbox-has-changed.md) para ver un ejemplo.  
  
## <a name="see-also"></a>Vea también

- [Temas "Cómo..."](textbox-how-to-topics.md)
- [RichTextBox Overview](richtextbox-overview.md) (Introducción a RichTextBox)
