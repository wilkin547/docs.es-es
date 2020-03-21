---
title: Información general sobre TextBox
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], TextBox
- TextBox control [WPF], about TextBox control
ms.assetid: 1ba6dc5b-11a7-4247-9213-36c6729ee35f
ms.openlocfilehash: 9fbae5ac4de4c78a1086bcbd9bfc9e01eb597fb8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186643"
---
# <a name="textbox-overview"></a>Información general sobre TextBox
La <xref:System.Windows.Controls.TextBox> clase le permite mostrar o editar texto sin formato. Un uso común <xref:System.Windows.Controls.TextBox> de a es editar texto sin formato en un formulario. Por ejemplo, un formulario que pide el nombre del <xref:System.Windows.Controls.TextBox> usuario, el número de teléfono, etc. usaría controles para la entrada de texto. En este tema <xref:System.Windows.Controls.TextBox> se presenta la clase y se [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] proporcionan ejemplos de cómo usarla tanto en C.  

<a name="textbox_or_richtextbox"></a>
## <a name="textbox-or-richtextbox"></a>¿TextBox o RichTextBox?  
 Tanto <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.RichTextBox> permiten a los usuarios introducir texto, pero los dos controles se usan para escenarios diferentes. A <xref:System.Windows.Controls.TextBox> requiere menos recursos <xref:System.Windows.Controls.RichTextBox> del sistema y, por lo que es ideal cuando solo se necesita editar texto sin formato (es decir, el uso en un formulario). A <xref:System.Windows.Controls.RichTextBox> es una mejor opción cuando es necesario que el usuario edite texto con formato, imágenes, tablas u otro contenido compatible. Por ejemplo, editar un documento, artículo o blog que requiera formato, <xref:System.Windows.Controls.RichTextBox>imágenes, etc. se realiza mejor mediante un archivo . La siguiente tabla resume las <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.TextBox>características principales de y .  
  
|Control|Revisión ortográfica en tiempo real|Menú contextual|Formato de <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> comandos como (Ctr+B)|<xref:System.Windows.Documents.FlowDocument>contenido como imágenes, párrafos, tablas, etc.|  
|-------------|------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.TextBox>|Sí|Sí|Sin |No.|  
|<xref:System.Windows.Controls.RichTextBox>|Sí|Sí|Sí (consulte [RichTextBox Overview](richtextbox-overview.md)[Introducción a RichTextBox])|Sí (consulte [RichTextBox Overview](richtextbox-overview.md)[Introducción a RichTextBox])|  
  
> [!NOTE]
> Aunque <xref:System.Windows.Controls.TextBox> no admite el formato <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> de comandos de edición relacionados como (Ctr+B), muchos comandos básicos son compatibles con ambos controles como <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>. Consulte <xref:System.Windows.Documents.EditingCommands> para obtener más información.  
  
 Las características <xref:System.Windows.Controls.TextBox> admitidas se tratan en las secciones siguientes. Para obtener <xref:System.Windows.Controls.RichTextBox>más información acerca de , vea [Información general sobre RichTextBox](richtextbox-overview.md).  
  
### <a name="real-time-spellchecking"></a>Revisión ortográfica en tiempo real  
 Puede habilitar la corrección ortográfica en tiempo real en a <xref:System.Windows.Controls.TextBox> o <xref:System.Windows.Controls.RichTextBox>. Cuando se activa la revisión ortográfica, aparece una línea roja debajo de las palabras con errores de ortografía (consulte la siguiente imagen).  
  
 ![Cuadro de texto con&#45;de ortografía](./media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")  
  
 Consulte [Cómo habilitar el corrector ortográfico en un control de edición de texto](how-to-enable-spell-checking-in-a-text-editing-control.md) para más información sobre cómo activar la revisión ortográfica.  
  
### <a name="context-menu"></a>Menú contextual  
 De forma <xref:System.Windows.Controls.TextBox> predeterminada, ambos y <xref:System.Windows.Controls.RichTextBox> tienen un menú contextual que aparece cuando un usuario hace clic con el botón derecho dentro del control. El menú contextual permite al usuario cortar, copiar o pegar (consulte la siguiente imagen).  
  
 ![TextBox con menú contextual](./media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")  
  
 Puede crear su propio menú contextual personalizado para invalidar el comportamiento predeterminado. Consulte [Use a Custom Context Menu with a TextBox](how-to-use-a-custom-context-menu-with-a-textbox.md) (Usar un menú contextual personalizado con TextBox) para más información.  
  
<a name="creating_textboxes"></a>
## <a name="creating-textboxes"></a>Crear controles TextBox  
 A <xref:System.Windows.Controls.TextBox> puede ser una sola línea de altura o comprender varias líneas. Una sola <xref:System.Windows.Controls.TextBox> línea es mejor para introducir pequeñas cantidades de texto sin formato (es decir, "Nombre", "Número de teléfono", etc. en un formulario). En el ejemplo siguiente se <xref:System.Windows.Controls.TextBox>muestra cómo crear una sola línea.  
  
 [!code-xaml[TextBoxMiscSnippets_snip#BasicTextBoxExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/basictextboxexample.xaml#basictextboxexamplewholepage)]  
  
 También puede crear <xref:System.Windows.Controls.TextBox> un que permita al usuario introducir varias líneas de texto. Por ejemplo, si el formulario solicita un boceto biográfico del <xref:System.Windows.Controls.TextBox> usuario, desearía utilizar un que admita varias líneas de texto. En el ejemplo siguiente [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] se <xref:System.Windows.Controls.TextBox> muestra cómo utilizar para definir un control que se expande automáticamente para dar cabida a varias líneas de texto.  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
 Establecer <xref:System.Windows.Controls.TextBox.TextWrapping%2A> el `Wrap` atributo en hace que el texto se <xref:System.Windows.Controls.TextBox> ajuste a una nueva <xref:System.Windows.Controls.TextBox> línea cuando se alcanza el borde del control, expandiendo automáticamente el control para incluir espacio para una nueva línea, si es necesario.  
  
 Establecer <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> el `true` atributo para que se inserte una nueva línea cuando se presiona <xref:System.Windows.Controls.TextBox> la tecla RETURN, expandiendo automáticamente el espacio de inclusión para una nueva línea, si es necesario.  
  
 El <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> atributo agrega una barra <xref:System.Windows.Controls.TextBox>de desplazamiento al <xref:System.Windows.Controls.TextBox> , para que el <xref:System.Windows.Controls.TextBox> contenido de la se puede desplazar a través si las expandes más allá del tamaño del marco o ventana que lo encierra.  
  
 Para obtener más información sobre <xref:System.Windows.Controls.TextBox>las diferentes tareas asociadas con el uso de un , vea [Temas de cómo hacerlo](textbox-how-to-topics.md).  
  
<a name="editing_commands"></a>
## <a name="detect-when-content-changes"></a>Detectar los cambios de contenido  
 Normalmente, <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> el evento se debe usar <xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.RichTextBox> para detectar <xref:System.Windows.UIElement.KeyDown> siempre que el texto de un o cambia, en lugar de lo que es de esperar. Consulte [Detect When Text in a TextBox Has Changed](how-to-detect-when-text-in-a-textbox-has-changed.md) (Detectar cuándo cambia el texto en un control TextBox) para ver un ejemplo.  
  
## <a name="see-also"></a>Consulte también

- [Temas de información](textbox-how-to-topics.md)
- [Información general sobre el control RichTextBox](richtextbox-overview.md)
