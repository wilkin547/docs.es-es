---
title: Información general sobre TextBox
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], TextBox
- TextBox control [WPF], about TextBox control
ms.assetid: 1ba6dc5b-11a7-4247-9213-36c6729ee35f
ms.openlocfilehash: 86b2cf8cb0c72186fd92bdad0af6bf5bd3fa9f3f
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174437"
---
# <a name="textbox-overview"></a>Información general sobre TextBox
La <xref:System.Windows.Controls.TextBox> clase le permite mostrar o editar texto sin formato. Un uso común de <xref:System.Windows.Controls.TextBox> es la edición de texto sin formato en un formulario. Por ejemplo, un formulario que solicita el nombre del usuario, el número de teléfono, etc <xref:System.Windows.Controls.TextBox> . usaría controles para la entrada de texto. En este tema se presenta la <xref:System.Windows.Controls.TextBox> clase y se proporcionan ejemplos de cómo usarla en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y C#.  

<a name="textbox_or_richtextbox"></a>
## <a name="textbox-or-richtextbox"></a>¿TextBox o RichTextBox?  
 <xref:System.Windows.Controls.TextBox>Y <xref:System.Windows.Controls.RichTextBox> permiten a los usuarios escribir texto, pero los dos controles se usan para distintos escenarios. Un <xref:System.Windows.Controls.TextBox> requiere menos recursos del sistema y, <xref:System.Windows.Controls.RichTextBox> por tanto, es ideal cuando solo es necesario editar texto sin formato (es decir, el uso en un formulario). Una <xref:System.Windows.Controls.RichTextBox> es una opción mejor cuando es necesario que el usuario edite texto con formato, imágenes, tablas u otro contenido compatible. Por ejemplo, la edición de un documento, artículo o blog que requiera formato, imágenes, etc., se consigue mejor mediante <xref:System.Windows.Controls.RichTextBox> . En la tabla siguiente se resumen las características principales de <xref:System.Windows.Controls.TextBox> y <xref:System.Windows.Controls.RichTextBox> .  
  
|Control|Revisión ortográfica en tiempo real|Menú contextual|Comandos de formato como <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (CTR + B)|<xref:System.Windows.Documents.FlowDocument>contenido como imágenes, párrafos, tablas, etc.|  
|-------------|------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.TextBox>|Sí.|Sí|No|No.|  
|<xref:System.Windows.Controls.RichTextBox>|Sí.|Sí|Sí (consulte [RichTextBox Overview](richtextbox-overview.md)[Introducción a RichTextBox])|Sí (consulte [RichTextBox Overview](richtextbox-overview.md)[Introducción a RichTextBox])|  
  
> [!NOTE]
> Aunque no <xref:System.Windows.Controls.TextBox> admite el formato de comandos de edición relacionados como <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (CTR + B), muchos comandos básicos son compatibles con ambos controles, como <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A> . Vea <xref:System.Windows.Documents.EditingCommands> para obtener más información.  
  
 Las características admitidas por <xref:System.Windows.Controls.TextBox> se describen en las secciones siguientes. Para obtener más información sobre <xref:System.Windows.Controls.RichTextBox> , vea [información general sobre RichTextBox](richtextbox-overview.md).  
  
### <a name="real-time-spellchecking"></a>Revisión ortográfica en tiempo real  
 Puede habilitar la revisión ortográfica en tiempo real en un <xref:System.Windows.Controls.TextBox> o <xref:System.Windows.Controls.RichTextBox> . Cuando se activa la revisión ortográfica, aparece una línea roja debajo de las palabras con errores de ortografía (consulte la siguiente imagen).  
  
 ![Cuadro de texto con comprobación de&#45;ortográfica](./media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")  
  
 Consulte [Cómo habilitar el corrector ortográfico en un control de edición de texto](how-to-enable-spell-checking-in-a-text-editing-control.md) para más información sobre cómo activar la revisión ortográfica.  
  
### <a name="context-menu"></a>Menú contextual  
 De forma predeterminada, <xref:System.Windows.Controls.TextBox> y <xref:System.Windows.Controls.RichTextBox> tienen un menú contextual que aparece cuando un usuario hace clic con el botón secundario dentro del control. El menú contextual permite al usuario cortar, copiar o pegar (consulte la siguiente imagen).  
  
 ![TextBox con menú contextual](./media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")  
  
 Puede crear su propio menú contextual personalizado para invalidar el comportamiento predeterminado. Consulte [Use a Custom Context Menu with a TextBox](how-to-use-a-custom-context-menu-with-a-textbox.md) (Usar un menú contextual personalizado con TextBox) para más información.  
  
<a name="creating_textboxes"></a>
## <a name="creating-textboxes"></a>Crear controles TextBox  
 <xref:System.Windows.Controls.TextBox>Puede ser una sola línea de alto o contener varias líneas. Una sola línea <xref:System.Windows.Controls.TextBox> es mejor para insertar pequeñas cantidades de texto sin formato (es decir, "nombre", "número de teléfono", etc. en un formulario). En el ejemplo siguiente se muestra cómo crear una sola línea <xref:System.Windows.Controls.TextBox> .  
  
 [!code-xaml[TextBoxMiscSnippets_snip#BasicTextBoxExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/basictextboxexample.xaml#basictextboxexamplewholepage)]  
  
 También puede crear un <xref:System.Windows.Controls.TextBox> que permita al usuario escribir varias líneas de texto. Por ejemplo, si el formulario solicita un boceto biográfico del usuario, querrá usar un <xref:System.Windows.Controls.TextBox> que admita varias líneas de texto. En el ejemplo siguiente se muestra cómo utilizar [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] para definir un <xref:System.Windows.Controls.TextBox> control que se expande automáticamente para alojar varias líneas de texto.  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
 <xref:System.Windows.Controls.TextBox.TextWrapping%2A>Si se establece el atributo en `Wrap` , el texto se ajusta a una nueva línea cuando se alcanza el borde del <xref:System.Windows.Controls.TextBox> control, expandiendo automáticamente el <xref:System.Windows.Controls.TextBox> control para incluir espacio para una nueva línea, si es necesario.  
  
 <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A>Si se establece el atributo en `true` , se insertará una nueva línea cuando se presione la tecla entrar, se expandirá de nuevo automáticamente <xref:System.Windows.Controls.TextBox> para incluir el espacio para una nueva línea, si es necesario.  
  
 El <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> atributo agrega una barra de desplazamiento a <xref:System.Windows.Controls.TextBox> , de modo que el contenido de <xref:System.Windows.Controls.TextBox> se puede desplazar a través de si el objeto se <xref:System.Windows.Controls.TextBox> expande más allá del tamaño del marco o de la ventana que lo incluye.  
  
 Para obtener más información sobre las distintas tareas asociadas al uso de <xref:System.Windows.Controls.TextBox> , consulte los [temas de procedimientos](textbox-how-to-topics.md).  
  
<a name="editing_commands"></a>
## <a name="detect-when-content-changes"></a>Detectar los cambios de contenido  
 Normalmente <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> , el evento se debe usar para detectar siempre que el texto de un <xref:System.Windows.Controls.TextBox> o <xref:System.Windows.Controls.RichTextBox> cambie, en lugar <xref:System.Windows.UIElement.KeyDown> de como cabría esperar. Consulte [Detect When Text in a TextBox Has Changed](how-to-detect-when-text-in-a-textbox-has-changed.md) (Detectar cuándo cambia el texto en un control TextBox) para ver un ejemplo.  
  
## <a name="see-also"></a>Vea también

- [Temas "Cómo..."](textbox-how-to-topics.md)
- [Información general sobre el control RichTextBox](richtextbox-overview.md)
