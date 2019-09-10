---
title: Información general sobre el control RichTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], RichTextBox
- RichTextBox control [WPF], about RichTextBox control
ms.assetid: c94548b2-c1e9-4b62-b10c-dd8740eb23d8
ms.openlocfilehash: bfed42bcf3693ef744b3ed2b54ebe070931513a9
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855733"
---
# <a name="richtextbox-overview"></a>Información general sobre el control RichTextBox

El <xref:System.Windows.Controls.RichTextBox> control permite mostrar o editar el contenido del flujo, como párrafos, imágenes, tablas, etc. En este tema se <xref:System.Windows.Controls.TextBox> presenta la clase y se proporcionan ejemplos de cómo usarla en C# [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y.

<a name="textbox_or_richtextbox"></a>

## <a name="textbox-or-richtextbox"></a>¿TextBox o RichTextBox?

<xref:System.Windows.Controls.RichTextBox> Y<xref:System.Windows.Controls.TextBox> permiten a los usuarios editar texto, sin embargo, los dos controles se usan en escenarios diferentes. Una <xref:System.Windows.Controls.RichTextBox> es una opción mejor cuando es necesario que el usuario edite texto con formato, imágenes, tablas u otro contenido enriquecido. Por ejemplo, la edición de un documento, artículo o blog que requiera formato, imágenes, etc <xref:System.Windows.Controls.RichTextBox>., se consigue mejor mediante. Una <xref:System.Windows.Controls.TextBox> requiere menos recursos del sistema y <xref:System.Windows.Controls.RichTextBox> es ideal cuando solo es necesario editar texto sin formato (es decir, el uso en formularios). Vea [información general](textbox-overview.md) sobre el cuadro de <xref:System.Windows.Controls.TextBox>texto para obtener más información sobre. En la tabla siguiente se resumen las características principales <xref:System.Windows.Controls.TextBox> de <xref:System.Windows.Controls.RichTextBox>y.

|Control|Revisión ortográfica en tiempo real|Menú contextual|Comandos de formato <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> como (CTR + B)|<xref:System.Windows.Documents.FlowDocument>contenido como imágenes, párrafos, tablas, etc.|
|-------------|------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|<xref:System.Windows.Controls.TextBox>|Sí|Sí|Sin|No.|
|<xref:System.Windows.Controls.RichTextBox>|Sí|Sí|Sí|Sí|

> [!NOTE]
> Aunque <xref:System.Windows.Controls.TextBox> no admite comandos relacionados con el formato <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> como (CTR + B), muchos comandos básicos son compatibles <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>con ambos controles, como.

Las características de la tabla anterior se detallan más adelante.

<a name="creating_a_richtextbox"></a>

## <a name="creating-a-richtextbox"></a>Creación de RichTextBox

En el código siguiente se muestra cómo crear <xref:System.Windows.Controls.RichTextBox> un que un usuario pueda editar contenido enriquecido en.

[!code-xaml[RichTextBoxMiscSnippets_snip#BasicRichTextBoxExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/BasicRichTextBoxExample.xaml#basicrichtextboxexamplewholepage)]

En concreto, el contenido editado en <xref:System.Windows.Controls.RichTextBox> un es contenido dinámico. El contenido dinámico puede incluir muchos tipos de elementos, como texto con formato, imágenes, listas y tablas. Consulte [Información general sobre documentos dinámicos](../advanced/flow-document-overview.md) para ver información detallada sobre los documentos dinámicos. Para incluir contenido dinámico, un hospeda un <xref:System.Windows.Controls.RichTextBox> <xref:System.Windows.Documents.FlowDocument> objeto que, a su vez, contiene el contenido modificable. Para mostrar el contenido dinámico en <xref:System.Windows.Controls.RichTextBox>un, el código siguiente muestra cómo crear un <xref:System.Windows.Controls.RichTextBox> con un párrafo y un texto en negrita.

[!code-xaml[RichTextBoxMiscSnippets_snip#RichTextBoxWithContentExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/RichTextBoxWithContentExample.xaml#richtextboxwithcontentexamplewholepage)]

[!code-csharp[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/CSharp/BasicRichTextBoxWithContentExample.cs#basicrichtextboxwithcontentcodeonlyexample)]
[!code-vb[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/visualbasic/basicrichtextboxwithcontentexample.vb#basicrichtextboxwithcontentcodeonlyexample)]

En la siguiente ilustración se muestra cómo se representa este ejemplo.

![RichTextBox con contenido](./media/editing-richtextbox-with-content.png "Editing_RichTextBox_with_Content")

Los elementos <xref:System.Windows.Documents.Paragraph> como <xref:System.Windows.Documents.Bold> y determinan cómo aparece <xref:System.Windows.Controls.RichTextBox> el contenido dentro de. Cuando un usuario edita <xref:System.Windows.Controls.RichTextBox> el contenido, cambia este contenido dinámico. Para más información sobre las características del contenido dinámico y cómo trabajar con él, consulte [Información general sobre documentos dinámicos](../advanced/flow-document-overview.md).

> [!NOTE]
> El contenido dinámico dentro <xref:System.Windows.Controls.RichTextBox> de no se comporta exactamente igual que el contenido dinámico contenido en otros controles. Por ejemplo, no hay ninguna columna en <xref:System.Windows.Controls.RichTextBox> y, por lo tanto, no hay ningún comportamiento de cambio de tamaño automático. Además, las características integradas, como la búsqueda, el modo de visualización, la navegación de páginas y <xref:System.Windows.Controls.RichTextBox>el zoom, no están disponibles en.

<a name="realtime_spellechecking"></a>

## <a name="real-time-spell-checking"></a>Revisión ortográfica en tiempo real

Puede habilitar la revisión ortográfica en tiempo real en un <xref:System.Windows.Controls.TextBox> o <xref:System.Windows.Controls.RichTextBox>. Cuando se activa la revisión ortográfica, aparece una línea roja debajo de las palabras con errores de ortografía (consulte la siguiente imagen).

![Textbox con revisión ortográfica](./media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")

Consulte [Cómo habilitar el corrector ortográfico en un control de edición de texto](how-to-enable-spell-checking-in-a-text-editing-control.md) para más información sobre cómo activar la revisión ortográfica.

<a name="context_menu"></a>

## <a name="context-menu"></a>Menú contextual

De forma predeterminada, <xref:System.Windows.Controls.TextBox> y <xref:System.Windows.Controls.RichTextBox> tienen un menú contextual que aparece cuando un usuario hace clic con el botón secundario dentro del control. El menú contextual permite al usuario cortar, copiar o pegar (consulte la siguiente ilustración).

![TextBox con menú contextual](./media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")

Puede crear su propio menú contextual personalizado para invalidar el predeterminado. Consulte [Colocar un menú contextual personalizado en un control RichTextBox](how-to-position-a-custom-context-menu-in-a-richtextbox.md) para más información.

<a name="detect_when_content_changes"></a>

## <a name="editing-commands"></a>Comandos de edición

Los comandos de edición permiten a los usuarios dar formato <xref:System.Windows.Controls.RichTextBox>al contenido editable dentro de. Además de los comandos de <xref:System.Windows.Controls.RichTextBox> edición básicos, incluye <xref:System.Windows.Controls.TextBox> comandos de formato que no admite. Por ejemplo, al editar en un <xref:System.Windows.Controls.RichTextBox>, un usuario podría presionar CTR + B para alternar el formato de texto en negrita. Vea <xref:System.Windows.Documents.EditingCommands> para obtener una lista completa de los comandos disponibles. Además de usar métodos abreviados de teclado, puede enlazar los comandos a otros controles como botones. En el siguiente ejemplo, se muestra cómo crear una herramienta de la barra sencilla que contiene botones que el usuario puede usar para cambiar el formato de texto.

[!code-xaml[RichTextBox_InputPanel_snip#RichTextBoxWithToolBarExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_InputPanel_snip/CS/Window1.xaml#richtextboxwithtoolbarexamplewholepage)]

En la siguiente ilustración, se muestra cómo se representa este ejemplo.

![RichTextBox con barra de herramientas](./media/editing-richtextbox-with-toobar.gif "Editing_RichTextBox_with_TooBar")

<a name="editing_commands"></a>

## <a name="detect-when-content-changes"></a>Detección de cambios de contenido

Normalmente, <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> el evento se debe usar para detectar siempre que el texto <xref:System.Windows.Controls.TextBox> de <xref:System.Windows.Controls.RichTextBox> un o cambie <xref:System.Windows.UIElement.KeyDown> en lugar de como cabría esperar. Consulte [Detectar cuándo cambiad el texto en un control TextBox](how-to-detect-when-text-in-a-textbox-has-changed.md) para ver un ejemplo.

<a name="save_load_and_print_richtextbox_content"></a>

## <a name="save-load-and-print-richtextbox-content"></a>Guardar, cargar e imprimir contenido de un control RichTextBox

En el ejemplo siguiente se muestra cómo guardar el contenido <xref:System.Windows.Controls.RichTextBox> de un en un archivo, cargar el contenido de <xref:System.Windows.Controls.RichTextBox>nuevo en e imprimir el contenido. A continuación, se muestra el marcado para el ejemplo.

[!code-xaml[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml#saveloadprintrtbexamplewholepage)]

A continuación, se muestra el código subyacente para el ejemplo.

[!code-csharp[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml.cs#saveloadprintrtbcodeexamplewholepage)]
[!code-vb[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/SaveLoadPrintRTB.xaml.vb#saveloadprintrtbcodeexamplewholepage)]

## <a name="see-also"></a>Vea también

- [Temas "Cómo..."](richtextbox-how-to-topics.md)
- [Información general sobre TextBox](textbox-overview.md)
