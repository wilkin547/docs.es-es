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
ms.openlocfilehash: 689094bda355f095c30d6cc2a462e6d0e630753b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378202"
---
# <a name="richtextbox-overview"></a>Información general sobre el control RichTextBox
El <xref:System.Windows.Controls.RichTextBox> control permite mostrar o editar el contenido dinámico incluido párrafos, imágenes, tablas y mucho más. Este tema se presenta la <xref:System.Windows.Controls.TextBox> clase y se proporcionan ejemplos de cómo se usa tanto en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y C#.  
  
  
<a name="textbox_or_richtextbox"></a>   
## <a name="textbox-or-richtextbox"></a>¿TextBox o RichTextBox?  
 Ambos <xref:System.Windows.Controls.RichTextBox> y <xref:System.Windows.Controls.TextBox> permiten a los usuarios editar texto, sin embargo, los dos controles se usan en escenarios diferentes. Un <xref:System.Windows.Controls.RichTextBox> es una opción mejor cuando es necesario para el usuario editar texto con formato, imágenes, tablas u otro contenido enriquecido. Por ejemplo, la edición de un documento, artículo o blog que requiera formato, imágenes, etcetera se logra mejor mediante un <xref:System.Windows.Controls.RichTextBox>. Un <xref:System.Windows.Controls.TextBox> requiere menos recursos del sistema, a continuación, un <xref:System.Windows.Controls.RichTextBox> y es ideal cuando solo texto sin formato tiene que Editar (es decir, el uso en formularios). Consulte [información general sobre TextBox](textbox-overview.md) para obtener más información sobre <xref:System.Windows.Controls.TextBox>. En la tabla siguiente se resume las características principales de <xref:System.Windows.Controls.TextBox> y <xref:System.Windows.Controls.RichTextBox>.  
  
|Control|Revisión ortográfica en tiempo real|Menú contextual|Aplicar formato a los comandos como <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (CTR+b)|<xref:System.Windows.Documents.FlowDocument> contenido, como imágenes, párrafos, tablas, etcetera.|  
|-------------|------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.TextBox>|Sí|Sí|No|No.|  
|<xref:System.Windows.Controls.RichTextBox>|Sí|Sí|Sí|Sí|  
  
 **Nota:** Aunque <xref:System.Windows.Controls.TextBox> no admite el formato de los comandos relacionados como <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (CTR+b), muchos comandos básicos son compatibles con ambos controles, como <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>.  
  
 Las características de la tabla anterior se detallan más adelante.  
  
<a name="creating_a_richtextbox"></a>   
## <a name="creating-a-richtextbox"></a>Creación de RichTextBox  
 El código siguiente muestra cómo crear un <xref:System.Windows.Controls.RichTextBox> que un usuario puede modificar su contenido enriquecido.  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#BasicRichTextBoxExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/BasicRichTextBoxExample.xaml#basicrichtextboxexamplewholepage)]  
  
 En concreto, puede editar el contenido en un <xref:System.Windows.Controls.RichTextBox> es contenido dinámico. El contenido dinámico puede incluir muchos tipos de elementos, como texto con formato, imágenes, listas y tablas. Consulte [Información general sobre documentos dinámicos](../advanced/flow-document-overview.md) para ver información detallada sobre los documentos dinámicos. Para incluir contenido dinámico, un <xref:System.Windows.Controls.RichTextBox> hosts un <xref:System.Windows.Documents.FlowDocument> objeto que contiene a su vez el contenido editable. Para mostrar el contenido dinámico en un <xref:System.Windows.Controls.RichTextBox>, el código siguiente muestra cómo crear un <xref:System.Windows.Controls.RichTextBox> con un párrafo y texto en negrita.  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#RichTextBoxWithContentExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/RichTextBoxWithContentExample.xaml#richtextboxwithcontentexamplewholepage)]  
  
 [!code-csharp[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/CSharp/BasicRichTextBoxWithContentExample.cs#basicrichtextboxwithcontentcodeonlyexample)]
 [!code-vb[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/visualbasic/basicrichtextboxwithcontentexample.vb#basicrichtextboxwithcontentcodeonlyexample)]  
  
 En la siguiente ilustración se muestra cómo se representa este ejemplo.  
  
 ![RichTextBox con contenido](./media/editing-richtextbox-with-content.png "Editing_RichTextBox_with_Content")  
  
 Elementos como <xref:System.Windows.Documents.Paragraph> y <xref:System.Windows.Documents.Bold> determinar cómo el contenido dentro de un <xref:System.Windows.Controls.RichTextBox> aparece. Cuando un usuario edita <xref:System.Windows.Controls.RichTextBox> contenido, cambian el contenido dinámico. Para más información sobre las características del contenido dinámico y cómo trabajar con él, consulte [Información general sobre documentos dinámicos](../advanced/flow-document-overview.md).  
  
 **Nota:** El flujo del contenido dentro de un <xref:System.Windows.Controls.RichTextBox> no se comporta exactamente igual que contenido dinámico incluido en otros controles. Por ejemplo, no hay ninguna columna en un <xref:System.Windows.Controls.RichTextBox> y, por tanto, no automático cambiar el tamaño de comportamiento. También, integrada en las características, como modo de visualización, búsqueda, navegación de páginas y zoom no están disponibles dentro de un <xref:System.Windows.Controls.RichTextBox>.  
  
<a name="realtime_spellechecking"></a>   
## <a name="real-time-spell-checking"></a>Revisión ortográfica en tiempo real  
 Puede habilitar la revisión ortográfica en tiempo real en un <xref:System.Windows.Controls.TextBox> o <xref:System.Windows.Controls.RichTextBox>. Cuando se activa la revisión ortográfica, aparece una línea roja debajo de las palabras con errores de ortografía (consulte la siguiente imagen).  
  
 ![Textbox con revisión ortográfica](./media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")  
  
 Consulte [Cómo habilitar el corrector ortográfico en un control de edición de texto](how-to-enable-spell-checking-in-a-text-editing-control.md) para más información sobre cómo activar la revisión ortográfica.  
  
<a name="context_menu"></a>   
## <a name="context-menu"></a>Menú contextual  
 De forma predeterminada, ambos <xref:System.Windows.Controls.TextBox> y <xref:System.Windows.Controls.RichTextBox> tiene un menú contextual que aparece cuando un usuario del botón secundario dentro del control. El menú contextual permite al usuario cortar, copiar o pegar (consulte la siguiente ilustración).  
  
 ![TextBox con menú contextual](./media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")  
  
 Puede crear su propio menú contextual personalizado para invalidar el predeterminado. Consulte [Colocar un menú contextual personalizado en un control RichTextBox](how-to-position-a-custom-context-menu-in-a-richtextbox.md) para más información.  
  
<a name="detect_when_content_changes"></a>   
## <a name="editing-commands"></a>Comandos de edición  
 Editar comandos que permiten a los usuarios dar formato a contenido modificable de un <xref:System.Windows.Controls.RichTextBox>. Edición de comandos, además de basic <xref:System.Windows.Controls.RichTextBox> incluye comandos de formato que <xref:System.Windows.Controls.TextBox> no admite. Por ejemplo, cuando se edita en un <xref:System.Windows.Controls.RichTextBox>, un usuario podría presionar CTR+b para alternar el formato de texto en negrita. Consulte <xref:System.Windows.Documents.EditingCommands> para obtener una lista completa de comandos disponibles. Además de usar métodos abreviados de teclado, puede enlazar los comandos a otros controles como botones. En el siguiente ejemplo, se muestra cómo crear una herramienta de la barra sencilla que contiene botones que el usuario puede usar para cambiar el formato de texto.  
  
 [!code-xaml[RichTextBox_InputPanel_snip#RichTextBoxWithToolBarExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_InputPanel_snip/CS/Window1.xaml#richtextboxwithtoolbarexamplewholepage)]  
  
 En la siguiente ilustración, se muestra cómo se representa este ejemplo.  
  
 ![RichTextBox con barra de herramientas](./media/editing-richtextbox-with-toobar.gif "Editing_RichTextBox_with_TooBar")  
  
<a name="editing_commands"></a>   
## <a name="detect-when-content-changes"></a>Detección de cambios de contenido  
 Normalmente el <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> evento debe usarse para detectar cada vez que el texto en un <xref:System.Windows.Controls.TextBox> o <xref:System.Windows.Controls.RichTextBox> cambia en su lugar, a continuación, <xref:System.Windows.UIElement.KeyDown> como cabría esperar. Consulte [Detectar cuándo cambiad el texto en un control TextBox](how-to-detect-when-text-in-a-textbox-has-changed.md) para ver un ejemplo.  
  
<a name="save_load_and_print_richtextbox_content"></a>   
## <a name="save-load-and-print-richtextbox-content"></a>Guardar, cargar e imprimir contenido de un control RichTextBox  
 El ejemplo siguiente muestra cómo guardar el contenido de un <xref:System.Windows.Controls.RichTextBox> en un archivo, cargar ese contenido de nuevo en el <xref:System.Windows.Controls.RichTextBox>e imprimir el contenido. A continuación, se muestra el marcado para el ejemplo.  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml#saveloadprintrtbexamplewholepage)]  
  
 A continuación, se muestra el código subyacente para el ejemplo.  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml.cs#saveloadprintrtbcodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/SaveLoadPrintRTB.xaml.vb#saveloadprintrtbcodeexamplewholepage)]  
  
## <a name="see-also"></a>Vea también
- [Temas "Cómo..."](richtextbox-how-to-topics.md)
- [Información general sobre TextBox](textbox-overview.md)
